Name:
-----
IBM Tivoli Netcool Impact Performance Health Check Evaluation Portal.


Description:
------------
This Web Portal identifies the Key Performance Indicators(KPIs) of existing IBM Tivoli Netcool Impact deployment, validates the KPI values with the reference baseline values recommended by IBM and generates a Performance Health Check Report.


Usage:
------
To Generate the Performance Health Check Report for IBM Tivoli Netcool Impact, Obtain the KPI's from the existing installation of Impact by using the script: get_impact_metrics.pl and upload the output file (generated in the json format) by using the upload option available on the web portal and click on the Submit button.

There is an alternate option to manually enter the values of KPI's obtained from the existing Impact Installation and then click on the submit button to generate the Performance Health Check Report.

Refer to the Section "Procedure to run the get_impact_metrics.pl script" for more details.


Dependencies:
-------------
For obtaining the Netcool Impact Performance KPI's, the get_impact_metrics.pl script needs to be executed. It needs 1 input argument.

1. The output of nci_collect_logs script, Like other command line scripts, nci_collect_logs is located in the $IMPACT_HOME/bin directory. The output file generated (impact_logs_<DATEANDTIME>.zip) will by default be placed in the $IMPACT_HOME/tmp directory.  

Refer to the URL below for more details on running the nci_collect_logs script.
https://www.ibm.com/docs/en/tivoli-netcoolimpact/7.1?topic=tools-nci-collect-logs


Procedure to Run the get_impact_metrics.pl Script:
--------------------------------------------------
Run the script "get_impact_metrics.pl" for obtaining the Key Performance Indicators(KPIs) from the existing installation of IBM Tivoli Netcool Impact.
1. Download the "get_impact_metrics.pl" script from the location: <>
2. Create a new directory (Ex: mkdir /tmp/nci_kpis)
3. Copy the "get_impact_metrics.pl" script to the newly created directory /tmp/nci_kpis.
4. Copy the output of nci_collect_logs script (impact_logs_<DATEANDTIME>.zip) to the newly created directory /tmp/nci_kpis
   cp <path of impact_logs_<DATEANDTIME>.zip> /tmp/nci_kpis
5. Run the commands given below:
   cd /tmp/nci_kpis
   perl get_impact_metrics.pl impact_logs_<DATEANDTIME>.zip  
6. The output file impact_kpi.out is generated in the same directory /tmp/nci_kpis.
7. Get the impact_kpi.out file from the server where it was generated and upload it on the Netcool Impact Health Check Portal to validate & generate the IBM Tivoli Netcool Impact Performance Health Check Report.
8. Once the Report is generated, It can be downloaded in the pdf format to the local pc.


Limitations:
------------
1. The Script get_impact_metrics.pl retrieves the Performance KPI's only from the Linux based installation of IBM Tivoli Netcool Impact.
2. Perl is required to run the script get_impact_metrics.pl. Perl should be pre-installed on the server where the script get_impact_metrics.pl is executed.


Scripts Download Location:
--------------------------
<git-hub Location>


REVISION HISTORY:
-----------------
REVISION 1 :
Date: 15-April-2024, Initial release.


CONTACT:
--------
Author: Karthikeyan P, karpandr@in.ibm.com

