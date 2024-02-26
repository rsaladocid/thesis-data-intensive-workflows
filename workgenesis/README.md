# Workgenesis: Low-Code Platform for Generating Domain-Specific Scientific Workflow Management Systems

| _Table of contents_   |
|-----------------------|
| [Abstract](#abstract)   |
| [Architecture Description](#architecture-description)   |
| [Domain-Agnostic and Customizable SWfMS](#domain-agnostic-and-customizable-swfms) |
| [Tool for Defining and Generating Domain-Specific SWfMS](#tool-for-defining-and-generating-domain-specific-swfms) |

## Abstract

The development of data-intensive tools poses a significant challenge when it comes to creating solutions that meet the specific needs and requirements of a particular field or sector, as it involves facing various technical, design, and implementation challenges. Its development requires a significant investment of time and resources, as it demands a deep understanding of both the data-intensive domain at hand and the software development process itself, as well as various data processing technologies and techniques. For this reason, specific solutions are not common, and when they do exist, they are often _ad-hoc_ solutions that have been implemented from scratch, tailored to very specific data types and use cases, which hinders their reuse in other domains and similar use cases.

## Architecture Description

Workgenesis is a solution based on the principle of separation of concerns, providing functionalities tailored to the needs of each user profile. On one hand, the data science expert possesses knowledge about algorithms and implementation of data analysis and knowledge extraction methods. They also have the necessary experience to adapt these methods to different domains and use cases. On the other hand, the domain expert holds knowledge about the application domain and is the one who truly needs data-intensive tools to gain a competitive advantage over competitors.

Internally, Workgenesis is composed of various tools developed to meet the diverse needs of these user profiles. Firstly, a tool for the definition and generation of domain-specific SWfMS for data-intensive domains. Secondly, a highly configurable SWfMS to be adapted to different application domains and execution environments. The resulting SWfMS enables domain experts to visually create and execute data-intensive applications. These tools provide typical elements of visual programming for this purpose.

![Architecture of Workgenesis](https://github.com/rsaladocid/thesis-data-intensive-workflows/assets/1663767/3b5bff93-0182-475f-a799-ecc1e83636f6)

## Domain-Agnostic and Customizable SWfMS

There is a large amount of business logic that is often common and can be used in various data-intensive applications. For example, a data pipeline that takes a set of input data, performs a series of cleaning processes to remove duplicate or null data, and normalizes it within a specific range. Another example is a data pipeline that takes several datasets, merges them into one, and removes duplicate data.

The data science expert has two options for modeling this logic: they can either do it through a programming language and create the code that meets the specific requirements, or they can use a generic and adaptable SWfMS that allows them to do it through visual programming. The latter option involves using a graphical editor that includes the previously defined algorithms and services, thus facilitating the definition of business logic in the form of DIW.

This SWfMS contains all the algorithms previously registered by the data science expert and is primarily composed of two typical components of any \ac{WfMS}: the design environment and the execution engine.

- Download ([Windows](https://drive.google.com/file/d/1swdFSQbOz_dRTyDtN_RXrJZagD6TZ5Oc/view?usp=sharing), [Linux](https://drive.google.com/file/d/1CuyrsNrQpE2PvymFEokfnEDKJ01zU4fQ/view?usp=sharing), [MacOS](https://drive.google.com/file/d/1DYq0ESKeXPG_vJ7t7kdZz6S-5VaDTRHq/view?usp=sharing))

### Demos

1. Executing a simple control-driven workflow composing by a Java process, a data input and a display, in order to perform an image transformation and visualize the result.


https://github.com/rsaladocid/thesis-data-intensive-workflows/assets/1663767/b3a2129a-bb9d-4539-a652-ecb15b65d77e


2. Creating a complex workflow, using existing workflows.


https://github.com/rsaladocid/thesis-data-intensive-workflows/assets/1663767/22f4a3df-d94c-4fdf-888d-1a70f4ba3690


3. Customizing the editor palette with ready-to-use processes to facilitate the definition of new workflows in a particular domain.


https://github.com/rsaladocid/thesis-data-intensive-workflows/assets/1663767/a2cd2068-147b-4bb3-bc52-02d5e51f0da2


4. Executing a workflow, showing the result in the WfMS and storing the workflow engine output in a local file.


https://github.com/rsaladocid/thesis-data-intensive-workflows/assets/1663767/f8f56e3f-dd6e-4188-8a22-94d3d456c9da



## Tool for Defining and Generating Domain-Specific SWfMS

Workgenesis provides a specialized SWfMS generator tool, aimed at data science experts, that allows them to register, configure, and reuse the elements necessary for the definition and execution of DIW in their respective application domains. These elements include data sources (such as CSV files, ARFF, or MySQL databases, among others) and computational tasks (ranging from classification algorithms like J48 or SVM to preprocessing algorithms like attribute selection or data normalization, among others).

To generate these domain-specific SWfMS, the data scientist does not need to possess software development knowledge, as they have high-level functionalities that allow them to define aspects related to the visual appearance of the tool, the available elements for creating DIW in the application domain, or the target execution environment. This not only reduces costs and time-to-market for new data-intensive tools but also enables the data science expert to focus on domain logic without worrying about the technical details of software development.

![image](https://github.com/rsaladocid/thesis-data-intensive-workflows/assets/1663767/cf6caedf-d91d-40ec-b3f1-64ba45afed8a)

- Download ([Windows](https://drive.google.com/file/d/1anvKR35HJJQYXeuw3cA3wZDDFnw67Dvk/view?usp=sharing))
