# BPMN Patterns for Process Variability

Various approaches exist to achieve variability in business processes.
However, most of them require proprietary modeling languages and/or tools.
This repository demonstrates how simple BPMN patterns allow for modeling variability in process models by relying solely on BPMN, which makes it possible to use any BPMN-compliant process engine.
For each usecase, there is always one core process containing variation points (i.e. variable parts of the process) and various supporting processes enablich variability.
Depending on which supporting process is deployed together with the core process to the process engine, the behaviour differs.

## Variation Points

Variable elements (i.e., variation points) include activities, events, and gateways.

## Example Processes

**Travel Request Process:** In German municipalities, the process for requesting business travels differs.
In most cases, a manager needs to approve the request. Depending on the municipality, if the travel destination is outside the state or the travel entails an overnight stay, another manager or even the mayor may need to be involved.

**Parking Permit Renewal:** In many German municipalities, craftspeople may apply for a special parking permit.
This permit allows them to park their vehicle in the urban area without buying a parking ticket at each stop and sometimes in areas where parking is not permitted for regular citizens.
The parking permit is valid for a specific period.
After that, the parking permit has to be renewed.
Depending on the city, this can be an opt-in or opt-out renewal process.
Furthermore, in some cases, the craftsperson is notified before the permit expires.

## Workflow Management Systems

Although the visual aspects of the process models are almost identical when targeting different workflow management systems, the process models need to be enriched with technical properties so that they can be executed on the respective workflow management system.

The process models have been implemented for the following workflow management systems and are provided in the respective folders of this repository:

* Camunda 7
* Camunda 8

For Camunda 7 and 8 the [Camunda Desktop Modeller](https://camunda.com/download/modeler/) can be used.

Note that while the names might suggest otherwise, Camunda 8 is not the new version of Camunda 7 but a new product.
This means that the technical implementation of the process models is completely different.
Furthermore, for the process models targeting Camunda 8, the following "Connectors" are used.

* [Email connector](https://docs.camunda.io/docs/components/connectors/out-of-the-box-connectors/email/) 
* [Send BPMN Message](https://marketplace.camunda.com/en-US/apps/448966/send-bpmn-message)

The required element templates are contained in the Camunda8 folder. In order to use them in the Camunda desktop modeler, they need to be copied to `\resources\element-templates` in the folder containing the desktop modeler.
In order to get the e-mail activity to work, the SMTP server needs to be configured.

## License 
[cc-by-nc-nd]: http://creativecommons.org/licenses/by-nc-nd/4.0/


This work is licensed under a
[Creative Commons Attribution-NonCommercial-NoDerivs 4.0 International License][cc-by-nc-nd].