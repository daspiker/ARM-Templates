<!DOCTYPE html>
<html>
<body>
<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fdaspiker%2FARM-Templates%2Fmaster%2FCEF%2520Collector%2FcefCollectorArmTemplate.json" target="_blank">
  <img src="https://aka.ms/deploytoazurebutton"/>
</a>

<p>
This ARM Template is designed for a low cost, single collector design to make it easy to get Syslog and CEF formatted Syslog feeds into Azure Sentinel for a lab or testing environment or a production environment where cost considerations are paramount.  The template is built around a Standard_D2s_v4 VM which should work well in a lab or low EPS / GB per Day environment but it does not provide auto-scaling or high performance.  There are VMSS based templates for enterprise scale deployments and requirements available here:
</p>

<p>
https://techcommunity.microsoft.com/t5/azure-sentinel/scaling-up-syslog-cef-collection/ba-p/1185854
</p>

<p>
Please consider the security requirements of your organization before deploying this ARM Template and feel free to modify for your needs.  This link provides some security guidance: 
</p>

<p>
https://docs.microsoft.com/en-us/azure/sentinel/connect-common-event-format#security-considerations
</p>

<p>
Once this collector is deployed, you can just point CEF log sources at the IP address of the collector and those log should start showing up in the CommonSecurityLog table in Azure Sentinel.  For Syslog log source, you can just point the logs sources at the IP address of the collector but you will need to configure the facilities to collect in the Log Analytics Workspace with the Azure portal under Log Analystics Workspace > <Select your Workspace> > Advanced Settings > Data > Syslog > <Enter the facilities that your Syslog sources are using and check the log levels you want>  Make sure to select the checkbox to "Apply below configuration...." and click Save.  This will push these settings to the collector.  Once this is done you should see the logs appear under the Syslog table.
</p>

<p>
To deploy this template you will need:
</p>

<p>
Workspace Id <br>
Workspace Key 
</p>

<p>
You can find these settings under: <br>
Log Analytics Workspace > <Pick the Workspace you want to use> > Advanced Settings > Agents Management
</p>

<p>
The Workspace Key can be the Primary or Secondary key 
</p>
</body>
</html>




