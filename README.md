# VulsTotal

VulsTotal: A Unified Platform for Evaluating and Benchmarking SAST Tools for Android.

The platform combines the detection capability of 8 select SAST tools for Android and finally generates a comprehensive detection report (CSV file) for the target APK.

The 8 selected SAST tools for Android are:

- QARK: [linkedin/qark: Tool to look for several security related Android application vulnerabilities (github.com)](https://github.com/linkedin/qark)
- AndroBugs: [AndroBugs/AndroBugs_Framework: AndroBugs Framework is an efficient Android vulnerability scanner that helps developers or hackers find potential security vulnerabilities in Android applications. No need to install on Windows. (github.com)](https://github.com/AndroBugs/AndroBugs_Framework)
- JAADAS: [flankerhqd/JAADAS: Joint Advanced Defect assEsment for android applications (github.com)](https://github.com/flankerhqd/JAADAS)
- Marvin: [programa-stic/Marvin-static-Analyzer: Marvin static analyzer is an Android application vulnerability scanner. The framework uses androguard and Static Android Analysis Framework (SAAF). (github.com)](https://github.com/programa-stic/Marvin-static-Analyzer)
- SUPER: [SUPERAndroidAnalyzer/super: Secure, Unified, Powerful and Extensible Rust Android Analyzer (github.com)](https://github.com/SUPERAndroidAnalyzer/super)
- MobSF: [MobSF/Mobile-Security-Framework-MobSF: Mobile Security Framework (MobSF) is an automated, all-in-one mobile application (Android/iOS/Windows) pen-testing, malware analysis and security assessment framework capable of performing static and dynamic analysis. (github.com)](https://github.com/MobSF/Mobile-Security-Framework-MobSF)
- SPECK: [SPRITZ-Research-Group/SPECK: SPECK: From Google Textual Guidelines to Automatic Detection of Android Apps Vulnerabilities (github.com)](https://github.com/SPRITZ-Research-Group/SPECK)
- AUSERA: [tjusenchen/AUSERA: AUSERA: Automated Security Vulnerability Detection for Android Apps (github.com)](https://github.com/tjusenchen/AUSERA)

## Our Goal

- Evaluate SAST tools for Android

- Construct real-world benchmarks for Android

- Get a comprehensive inspection report of the target APK.

  

## Introduction of Project Components

- _MSTG&DIVA benchmark_:Contains two sample APKs from MSTG & DIVA: MSTG-Android-Java.apk; diva-beta.apk
- _CSV_sample.csv_: A sample CSV file of the final report on the comprehensive results generated by the target APK.
- _CVE-based benchmark.md_: Contains the CVE entries involved in the CVE-based benchmark we built and the corresponding vulnerable APKs and their ground truth labels for the 8 selected tool support vulnerabilities.
- _Effectiveness in three benchmarks.md_: Detection performance of each SAST tool in the 3 benchmarks(i.e. CVE-based benchmark, GHERA benchmark, MSTG&DIVA benchmark)
- _Fine-grained granularity.md_: For the types of vulnerabilities that involve fine-grained granularity in our build of the unified taxonomy, the detection strength of each tool is shown.
- _GHERA benchmark.md_: Includes the GHERA benchmark involving the corresponding vulnerable APKs and the ground truth label for the 8 selected tool support vulnerabilities.
- _MSTG&DIVA benchmark.md_: Includes the MSTG&DIVAbenchmark involving the corresponding vulnerable APKs and the ground truth label for the 8 selected tool support vulnerabilities.
- _Platform base(SAST tools) selection.md_: Detailed information on the screening process for selecting the 8 selected tools.
- _Real-world benchmark.md_: The apk name of the 3 real-world benchmarks we constructed by VulsTotal and its ground truth label containing the vulnerability
- _VulsTotal_: VulsTotal platform source code.



## The Benchmark Resources 

The Real-World Benchmark constructed by VulsTotal and the CVE-based benchmark is available at [https://doi.org/10.5281/zenodo.8223173](https://zenodo.org/record/8223397)

This Zenodo dataset contains four benchmarks as follows:

1. customized_50: which applies customized majority voting with 50% confidence.
2. customized_100: which applies customized/granularity-aware majority voting with 100% confidence.  
3. granularity_50: which applies granularity-aware majority voting with 50% confidence.
4. CVE-based benchmark.



## Configuration Platform VulsTotal 

Since the platform integrates the detection capabilities of 8 tools, we need to install each of the 8 tools separately. Of course, we will optimize this feature to allow users to access the platform via domain name.

Note that please use the installation packages of the 8 tools provided with this project, as the tools have been modified to varying degrees to accommodate the platform

### The Usage of VulsTotal 

```
usage: python VulsTotal.py [-h] -d APK_FOLDER -r REPORT_FOLDER -c CSV_FOLDER -s STRATEGY -f CONFIDENCE

VulsTotal - A Unified Platform for Evaluating and Benchmarking SAST Tools for Android

optional arguments:
  -h, 	--help            	show this help message and exit
  -d, 	--apk_folder  		The APK folder stored the target APKs
  -r,	--report_folder 	The report folder stored the intermediate reports
  -c, 	--CSV_folder 	 	The CSV folder stored the final CSV reports
  -s, 	--strategy  		The strategy option(0:customized majority voting; 1:granularity-aware majority voting)
  -f, 	--confidence  		The confidence option(please in the number in [50,100)
```



### Development Environment

Using Python 2.7 in VulsTotal

