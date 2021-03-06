# Amazon Inspector findings<a name="inspector_findings"></a>

*Findings* are potential security issues that Amazon Inspector discovers during an assessment of your assessment target\. Findings are displayed on the Amazon Inspector console or through the API\. Findings contain detailed descriptions of the security issues and recommendations for resolving them\.

After Amazon Inspector generates the findings, you can track them by assigning Amazon Inspector attributes to them\. These attributes consist of key\-value pairs\.

Tracking your findings with attributes can be useful for managing the workflow of your security strategy\. For example, after you create and run an assessment, it generates a list of findings of various levels of severity, urgency, and interest to you, based on your security goals and approach\. You might want to follow one finding's recommendation steps right away to resolve a potentially urgent security issue\. Or you might want to postpone resolving another finding until your next upcoming service update\. For example, to track a finding to resolve right away, you can create and assign to a finding an attribute with a key\-value pair of **Status** / **Urgent**\. You could also use attributes to distribute the workload of resolving potential security issues\. For example, to give Bob \(who is a security engineer on your team\) the task of resolving a finding, you can assign to a finding an attribute with a key\-value pair of **Assigned Engineer** / **Bob**\.

## Working with findings<a name="finding_via_console"></a>

Complete the following procedure on any of the generated Amazon Inspector findings\.

**To locate, analyze, and assign attributes to findings**

1. Sign in to the AWS Management Console and open the Amazon Inspector console at [https://console\.aws\.amazon\.com/inspector/](https://console.aws.amazon.com/inspector/)\.

1. After you run an assessment, navigate to the **Findings** page in the Amazon Inspector console to view your findings\.

   You can also see your findings in the **Notable Findings** section on the **Dashboard** page of the Amazon Inspector console\.
**Note**  
You can't view the findings that are generated by an assessment run while it is still in progress\. However, you can view a subset of findings if you stop the assessment before it completes its duration\. In a production environment, we recommend that you let every assessment run through its entire duration so that it can produce a full set of findings\.

1. To view the details of a specific finding, choose the **Expand** widget next to that finding\. The details of the finding include the following:
   + Name of the assessment target that includes the EC2 instance where this finding was registered\.
   + Name of the assessment template that was used to produce this finding\.
   + Assessment run start time\.
   + Assessment run end time\.
   + Assessment run status\.
   + Name of the rules package that includes the rule that triggered this finding\.
   + Name of the finding\.
   + Severity of the finding\.
   + Native severity details from the Common Vulnerability Scoring System \(CVSS\)\. These include CVSS vector and CVSS score metrics \(including CVSS version 2\.0 and 3\.0\) for the findings triggered by the rules in the Common Vulnerabilities and Exposures rules package\. For details about the CVSS, see [https://www\.first\.org/cvss/](https://www.first.org/cvss/)\.
   + Native severity details from the Center of Internet Security \(CIS\)\. These include the CIS weight metric for the findings triggered by the rules in the CIS Benchmarks package\. For more information about CIS weight metric, see [https://www\.cisecurity\.org/](https://www.cisecurity.org/)\.
   + Description of the finding\.
   + Recommended steps that you can complete to fix the potential security issue described by the finding\.

1. To assign attributes to a finding, choose a finding, and then choose **Add/Edit Attributes**\.

   You can also assign attributes to findings as you create an assessment template\. To do that, you configure the new template to automatically assign attributes to all findings that are generated by the assessment run\. You can use the **Key** and **Value** fields from the **Tags for findings from this assessment** field\. For more information, see [Amazon Inspector assessment templates and assessment runs](inspector_assessments.md)\.

1. To export findings to a spreadsheet, choose the down arrow in the upper\-right corner of the **Findings** page\. In the dialog box, choose **Export all columns** or **Export visible columns**\.

   Note that in the exported content, all datetime values are epoch timestamps\.

1. To show or hide columns for the generated findings and to filter through the generated findings, choose the settings icon in the upper\-right corner of the **Findings** page\.

1. To delete findings, navigate to the **Assessment runs** page and choose the run that resulted in the findings that you want to delete\. Then choose **Delete**\. When prompted for confirmation, choose **Yes**\.
**Important**  
You can't delete individual findings in Amazon Inspector\. When you delete an assessment run, all findings and all versions of the report from that run are also deleted\.

   You can also delete an assessment run by using the [DeleteAssessmentRun](https://docs.aws.amazon.com/inspector/latest/APIReference/API_DeleteAssessmentRun.html) API\. 