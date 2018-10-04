# Retest Test Selection for Product-Line Regression Testing of Variants and Versions of Variants
This repository provides the download of the prototypical implementation as well as the experimental data for the journal article "Retest Test Selection for Product-Line Regression Testing of Variants and Versions of Variants" by Sascha Lity, Manuel Nieke, Thomas Thüm, and Ina Schaefer accepted for publication in the [VaMoS 2018 Special Issue of the Journal of Systems and Software](https://vamos2018.wordpress.com/special-issue/).

## Download
* [Eclipse Modeling Tools Oxygen](http://www.eclipse.org/downloads/packages/release/oxygen/3a/eclipse-modeling-tools) for accessing the data obtained by the application of the prototype to the input data.
* [CPA/Tiger](https://github.com/sosy-lab/cpachecker/tree/tigerIntegration) for applying the test-case generation.
* [Prototypical implementation](prototype.jar) of our framework facilitating SPL regression testing.
* [Input](Input) files of the vending machine and wiper SPL comprising 1. the XMI file with the feature model versions and respective feature configurations (VendingMachineNEARIN.xmi & WiperNEARIN.xmi) and 2. the XMI file with the higher-order delta model (HODModel_vm.xmi & HODModel_wiper.xmi)
* Result files of the vending machine as well as wiper SPL comprising the XMI file (*.regression) with the respective test artifacts.
* Meta-model Eclipse plugins representing the data structure of our prototype. The plugins are required to access the input and result XMI files of the subject SPL systems (Vending Machine & Wiper) in an installed Eclipse instance.
* CPA config files used during the evaluation of our framework.
