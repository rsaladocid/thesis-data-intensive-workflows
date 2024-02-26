# SWEL - A Domain-Specific Language for Modelling Data-Intensive Workflows

| _Table of contents_   |
|-----------------------|
| [Abstract](#abstract)   |
| [SWEL Technical Report](#swel-technical-report) |
| [JSON Concrete Syntax Validator](#json-concrete-syntax-validator) |
| [Evaluation of Model Transformations](#evaluation-of-model-transformations) |
| [Demo Tool for Model Interoperability between SWfMS](#demo-tool-for-model-interoperability-between-swfms) |
| [Experimentation - Survey](#experimentation---survey) |

## Abstract

SWEL is a domain-specific modelling workflow language for defining data-intensive applications, which use advanced computing techniques with the aim of discovering valuable knowledge from huge amounts of data coming from real-world sources. The objective of SWEL is to provide a high-level, domain-independent definition language for the formulation of scientific workflows, hiding low-level computational aspects. SWEL is founded on a multi-layered structure that enables both the definition of workflows for different domains, the reuse of knowledge and the portability and interoperability among different workflow platforms.

## SWEL Technical Report

This [technical report](./swel_technical_report.pdf) defines the formal specification of SWEL (Scientific Workflow Execution Language) in terms of its meta-models and constraints, making this definition syntax-independent, according to the precepts of model-driven engineering. 

## Tool Support

### JSON Concrete Syntax Validator

JSON is an IETF ([Internet Engineering Task Force](https://datatracker.ietf.org/doc/html/rfc8259)) standard language widely used as a data exchange format on the web via, e.g., REST APIs and services. JSON is also possible to use SWEL as a concrete textual notation for the serialisation of DIW models. To improve practicability, a syntactic validator is a useful tool to verify that the JSON document is well constructed and conforms to both the standard and the SWEL metamodel. To this end, a JSON schema has been generated in accordance with the declaration of the JSON-based concrete notation corresponding to the metamodel. The validation tool has been implemented in Java and it provides a command-line interface whose only argument is the path of the JSON file to be analysed. It reads and parses the input file in order to check if its content is according to the JSON scheme. If not compliant, the execution console reports the detected errors.

- Download JSON Validator ([Runnable JAR](./Tool_Support/JSON_Validator/validator-jar.zip))
- How to execute it:
```
java -jar validator.jar <path_to_workflow.json>
```
- Workflows: [Example1](./Tool_Support/JSON_Validator/example1-json.zip), [Example2](./Tool_Support/JSON_Validator/example2-json.zip), [Example3](./Tool_Support/JSON_Validator/example3-json.zip) (with errors)

#### Screenshoots:

_Validation of a valid SWEL workflow: Example2_

![Validation of a valid SWEL workflow: Example2](https://github.com/rsaladocid/thesis-data-intensive-workflows/assets/1663767/d9c789a6-0a22-49a1-ade7-7fa6a25de255)

_Output of an invalid SWEL workflow: Example3 (with errors)_

![Output of an invalid SWEL workflow: Example3 (with errors)](https://github.com/rsaladocid/thesis-data-intensive-workflows/assets/1663767/923f07ad-9d74-4e3c-a34a-b1233818a003)


## Validation of SWEL

### Evaluation of Model Transformations

To evaluate the suitability of SWEL metamodel, it is used as a mechanism for interoperability between WfMS. We work with SCUFL and MoML, showing the possible reuse of workflows generated in Taverna towards Kepler. A second use case examines how SWEL can be used to facilitate the collective development of new pipelines in different tools like CWL. In this section, we provide the diferrent assets used in the model transformations process, such as metamodels, model-to-model transformations, text-to-model transformations and model-to-text transformations.

#### Metamodels:
- SWEL metamodel ([ecore](./Validation/1_Model_Transformations/EcoreMM_swel.zip))
- CWL metamodel ([ecore](./Validation/1_Model_Transformations/EcoreMM_cwl.zip))  
- MoML metamodel ([ecore](./Validation/1_Model_Transformations/EcoreMM_moml.zip))

_Diagram: MoML metamodel_

![image](https://github.com/jrromero/swel/assets/16683876/f208f950-bcee-4719-8730-0801213ffd7a)

- SCUFL metamodel ([ecore](./Validation/1_Model_Transformations/EcoreMM_scufl.zip))

_Diagram: Main elements of SCUFL_

![image](https://github.com/jrromero/swel/assets/16683876/6a2dfc60-be85-4789-9645-6276129ab1e9)

_Diagram: ConfigBeans-related elements_

![image](https://github.com/jrromero/swel/assets/16683876/c7827d2f-0e27-4265-88f3-dda147a45111)

#### Text-to-model Transformations:

- SCUFL T2M transformations ([XSL](./Validation/1_Model_Transformations/XSL_scufl.zip))
- CWL T2M transformations ([XSL](./Validation/1_Model_Transformations/XSL_cwl.zip))

#### Model-to-model Unidirectional Transformations:

- SCUFL to SWEL M2M transformations ([QVT](./Validation/1_Model_Transformations/QVT_M2M_scufl2swel.zip))
- SWEL to MoML M2M transformations ([QVT](./Validation/1_Model_Transformations/QVT_M2M_swel2moml.zip))

#### Model-to-model Bidirectional Transformations:

- CWL to SWEL (and vice versa) M2M transformations ([QVT](./Validation/1_Model_Transformations/QVT_M2M_cwl2swel.zip))

#### Model-to-Text Transformations:

- MoML M2T transformations ([MTL](./Validation/1_Model_Transformations/MTL_M2T_moml.zip))

### Demo Tool for Model Interoperability between SWfMS

A demo tool has been developed to illustrate the complete transformation horseshoe process to enable interoperability between different WfMS. Currently, this tool supports both SCUFL and CWL workflows as input, in order to generate MoML workflows. During the transformation process, the output of each model transformation (text-to-model, model-to-model and model-to-text) is shown in the UI and stored in the local directory chosen by the user.

- Download demo tool ([Runnable JAR](./swel_demo_tool_jar.zip))
- How To Use it:
```
java -jar demo-tool.jar
```
- Source workflows ([SCUFL](./Validation/2_Model_Interoperability/example-SCUFL.zip), [CWL](./Validation/2_Model_Interoperability/example-CWL.zip))

#### Videos

1. Transforming a SCUFL workflow into a MoML workflow.


https://github.com/rsaladocid/thesis-data-intensive-workflows/assets/1663767/bc808b20-67c7-4da0-9df8-f3dfab68c051


2. Showing the intermediate models generated during transformation process and stored in a local directory.


https://github.com/rsaladocid/thesis-data-intensive-workflows/assets/1663767/88475a3a-f190-4e5d-a903-dbf28abb71af


3. Transforming a CWL workflow into a MoML workflow.


https://github.com/rsaladocid/thesis-data-intensive-workflows/assets/1663767/75c04f62-7421-47a3-830a-7350e9447602


4. Opening the resulting MoML workflow in Kepler WfMS.


https://github.com/rsaladocid/thesis-data-intensive-workflows/assets/1663767/bfb99651-7f97-424c-a284-e8f338c67a3d


## Experimentation - Survey

We conducted a human-based survey evaluation to assess the adequacy of SWEL as an intermediate model in the interoperability process between the Taverna and Kepler tools. We also analyse the suitability and comprehensibility of SWEL as a representation language for DIWs. For this purpose, a team of 11 experts, not involved in the prior design, development, and evaluation of SWEL, was selected. 5 of the experts work in academia in diverse areas of data science, while 6 are data scientists in industry. Both senior and junior profiles have been considered in both cases. These external experts have extensive knowledge of DI applications and were, therefore, well-suited to provide additional insights.

The experiment consisted of three exercises: (1) a first training transformation on a given workflow; (2) a transformation of a workflow chosen by the expert and downloaded from a public repository; and (3) an analysis of the adequacy and the comprehensibility of SWEL as a representation model for DIWs, as well as its accuracy in incorporating the concepts of the source (Taverna) and target (Kepler) models. Each expert responded to a total of 18 questions, rated on a scale of 1 (lowest) to 10 (highest).

We provide the __validation package__ ([ZIP](./Validation/3_Survey_Experiment/Q&A_experiment.zip)) containing the Q&A of the experiment with the following file structure:
- Expert evaluation form (```Expert_Evaluation_Form.pdf```)
- Experiment results (```Experiment_results.pdf```)
- Training exercise (```exercise1```)
  - Source workflow (```source```)
    - Taverna file (```Example.t2flow```)
    - Workflow representation (```source.jpg```)
  - Target workflow (```target```)
    - Kepler file (```Example.xml```)
    - Workflow representation (```target.jpg```)
  - Taverna model (```model_source.xmi```)
  - SWEL model (```model_swel.xmi```)
  - Kepler model (```model_target.xmi```)
