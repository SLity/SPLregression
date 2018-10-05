# Retest Test Selection for Product-Line Regression Testing of Variants and Versions of Variants
This repository provides the download of the prototypical implementation as well as the experimental data for the journal article [Retest Test Selection for Product-Line Regression Testing of Variants and Versions of Variants](https://doi.org/10.1016/j.jss.2018.09.090) by Sascha Lity, Manuel Nieke, Thomas Thüm, and Ina Schaefer accepted for publication in the [VaMoS 2018 Special Issue of the Journal of Systems and Software](https://vamos2018.wordpress.com/special-issue/).

## Download
* [Eclipse Modeling Tools Oxygen](http://www.eclipse.org/downloads/packages/release/oxygen/3a/eclipse-modeling-tools) for accessing the data obtained by the application of the prototype to the input data.
* [CPA/Tiger](https://github.com/sosy-lab/cpachecker/tree/tigerIntegration) for applying the test-case generation.
* [Prototypical implementation](prototype.jar) of our framework facilitating SPL regression testing.
* [Input](Input) files of the vending machine and wiper SPL comprising 1. the XMI file with the feature model versions and respective feature configurations ([VendingMachineNEARIN.xmi](Input/VendingMachineNEARIN.xmi) & [WiperNEARIN.xmi](Input/WiperNEARIN.xmi)) and 2. the XMI file with the higher-order delta model ([HODModel_vm.xmi](Input/HODModel_vm.xmi) & [HODModel_wiper.xmi](Input/HODModel_wiper.xmi))
* [Result](Result) files of the vending machine as well as wiper SPL comprising the XMI file (*.regression) with the respective test artifacts.
* [Meta-model](Meta_Model_Plugins) Eclipse plugins representing the data structure of our prototype. The plugins are required to access the input and result XMI files of the subject SPL systems (Vending Machine & Wiper) in an installed Eclipse instance.
* [CPA config](CPA_Config/config) files used during the evaluation of our framework.

## Data Access
To access the data used as input and obtained by applying our prototype, the download and installation of Eclipse modeling tools (latest oxygen version) is required. In addition, the meta model plugins (*.jar files) have to be added to the plugins folder of the installed Eclipse instance. Afterwards, start the Eclipse instance, create an empty project, and add the input as well as the already obtained result files to the project. The files can be opened via the sample ecore model editor.
```
"Right click on File" --> "Open with" --> "Other.." --> "Sample Ecore Model Editor"
```

## Prerequisites & CPA/Tiger
For the application of the CPA/Tiger as test-case generator, the Java version of the [Z3 Theorem Prover](https://github.com/Z3Prover/z3) is required to be installed on your system. Afterwards, download and install CPA/Tiger on your system. Furthermore, unzip the CPAconfig archive on your system as we adapted some CPA/Tiger configuration files for our evaluation.

## Prototype Execution
For executing the prototype of our framework, we require as parameters 1. the project name (*projectName*), 2. the path to the XMI file comprising the feature model and feature configuration versions (*pathToFMandConfig*), 3. the path to the XMI file containing the higher-order delta model (*pathToHOD*), 4. the path to the CPA/Tiger installation (*pathToCPATiger*), 5. the path to the config file "tiger-variants.properties" from our provided CPA configuration files (*pathToConfigFile*), and 6. the path to the output folder (*pathToOutput*). As the prototype prints information on the command line, we suggest to pipe the command line output to a separate log file facilitating an easier review of the execution. In addition, the execution of CPA/Tiger requires a specific amount of heap memory, where we suggest 10GB if possible. To this end, the prototype is executed via the command
```
java -Xmx10000M -jar prototype.jar projectName pathToFMandConfig pathToHOD pathToCPATiger pathToConfigFile pathToOutput > eval.log 2>&1
```
