# VulsTotal

VulsTotal: A Unified Platform for Evaluating SAST Tools for Android.

The platform combines the detection capability of 11 select SAST tools for Android and finally generates a comprehensive detection report (CSV file) for the target APK.

The 11 selected SAST tools for Android are:

- [MobSF](https://github.com/MobSF/Mobile-Security-Framework-MobSF)
- [QARK](https://github.com/linkedin/qark)
- [AndroBugs](https://github.com/AndroBugs/AndroBugs_Framework)
- [APKHunt](https://github.com/Cyber-Buddy/APKHunt)
- [SUPER](https://github.com/SUPERAndroidAnalyzer/super)
- [JAADAS](https://github.com/flankerhqd/JAADAS)
- [DroidStatx](https://github.com/clviper/droidstatx)
- [Marvin](https://github.com/programa-stic/Marvin-static-Analyzer)
- [Trueseeing](https://github.com/alterakey/trueseeing)
- [AUSERA](https://github.com/tjusenchen/AUSERA)
- [SPECK](https://github.com/SPRITZ-Research-Group/SPECK)


## Our Goal

- Evaluate SAST tools for Android.

- Get a comprehensive inspection report of the target APK.

  

## Introduction of Project Components

- [_SAST tools selection.md_](https://github.com/android-app-sast/VulsTotal/blob/master/SAST%20tools%20selection.md): Details for selecting the 11 selected tools.
- [_GHERA benchmark.md_](https://github.com/android-app-sast/VulsTotal/blob/master/GHERA%20benchmark.md): Includes the GHERA benchmark.
- [_MSTG&PIVAA benchmark.md_](https://github.com/android-app-sast/VulsTotal/blob/master/MSTG%26PIVAA%20benchmark.md): Includes the MSTG&PIVAA benchmark.
- [_MSTG&PIVAA benchmark_](https://github.com/android-app-sast/VulsTotal/tree/master/MSTG%26PIVAA%20benchmark): Contains two sample APKs from MSTG & PIVAA.
- [_CVE-based benchmark.md_](https://github.com/android-app-sast/VulsTotal/blob/master/CVE-based%20benchmark.md): Introduces the CVE entries involved in the CVE-based benchmark.
- [_Effectiveness in three benchmarks.md_](https://github.com/android-app-sast/VulsTotal/blob/master/Effectiveness%20%20in%20three%20benchmarks.md): (RQ3) Detection performance of each SAST tool on the three benchmarks (i.e. CVE-based benchmark, GHERA benchmark, and MSTG&PIVAA benchmark).


- [_CSV_sample.csv_](https://github.com/android-app-sast/VulsTotal/blob/master/CSV_sample.csv): A sample CSV file of the final report of the target APK generated by VulsTotal.
- [_Android_specific_CVEs_detail.md_](https://github.com/android-app-sast/VulsTotal/blob/master/Android_specific_CVEs_detail.md): Describes the details of the types of vulnerabilities contained in Android-specific CVEs.
- [_The unique vuln types within 11 tools.md_](https://github.com/android-app-sast/VulsTotal/blob/master/The%20unique%20vuln%20types%20within%2011%20tools.md): Details of vulnerability types uniquely supported by 11 tools.
- [_VulsTotal_](https://github.com/android-app-sast/VulsTotal/tree/master/VulsTotal/platform): The source code of the VulsTotal platform.





## The Benchmark Resources 

The CVE-based benchmark is available at https://zenodo.org/records/10428695



## Configuration Platform VulsTotal 

Since the platform integrates the detection capabilities of 11 tools, we need to install each of the 11 tools separately. We will optimize this feature to allow users to access the platform via a web service.

Note that please use the installation packages of the 11 tools provided with this project, as the tools have been modified by us to varying degrees to accommodate the platform.

### The Usage of VulsTotal 

```
usage: python VulsTotal.py [-h] -d APK_FOLDER -c CSV_FOLDER -s STRATEGY -f CONFIDENCE

VulsTotal - A Unified Platform for Evaluating and Benchmarking SAST Tools for Android

optional arguments:
  -h, 	--help            	show this help message and exit
  -d, 	--apk_folder  		The APK folder stored the target APKs
  -c, 	--CSV_folder 	 	The CSV folder stored the final CSV reports
  -s, 	--strategy  		The strategy option (0:customized majority voting; 1:granularity-aware majority voting)
  -f, 	--confidence  		The confidence option (please in the number in [50,100)
```

