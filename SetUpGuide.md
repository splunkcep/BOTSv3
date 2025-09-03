# Boss of the SOC (BOTS) Dataset Version 3
Este es un conjunto de datos de ejemplo de nuestra plataforma CTF (Capture the Flag) para profesionales de la seguridad de la información, investigadores, estudiantes y entusiastas. 

Esta página contiene información sobre la versión 3 del conjunto de datos del **Boss of the Soc (BOTS)**. 

## Download del Dataset

| Dataset          | Descripción | Tamaño | Formato | MD5 |
| ---------------- | ----------- | ---- | ------ | --- |
| [BOTS V3 Dataset](https://botsdataset.s3.amazonaws.com/botsv3/botsv3_data_set.tgz) |  BOTSv3 dataset. | 320.1MB | Pre-indexed Splunk | d7ccca99a01cff070dff3c139cdc10eb |


## Instalación
1. Descarga el archivo del conjunto de datos indicado arriba y verifica el hash MD5 para asegurar su integridad.

``` bash
cd /tmp
wget https://botsdataset.s3.amazonaws.com/botsv3/botsv3_data_set.tgz
md5sum botsv3_data_set.tgz
```
   
3. Instala las aplicaciones y Add-Ons listados en la sección [Software Requerido](#software-requerido) a continuación. Es importante que coincida la versión específica de cada aplicación y complemento.
4. Descomprime/desempaqueta el archivo descargado en $SPLUNK_HOME/etc/apps

``` bash
sudo tar -xzvf botsv3_data_set.tgz -C /opt/splunk/etc/apps
```

5. Da acceso al dataset a splunkuser

``` bash
sudo chown -R splunkuser:splunkuser /opt/splunk/etc/apps/botsv3_data_set
```
   
6. Reinicia Splunk

``` bash
/opt/splunk/bin/splun restart
```

7. Ve a **Search App** y valida los datos realizando la siguiente búsqueda
``` bash
index=botsv3 earliest=0
```
8. Ten en cuenta que, dado que los datos se distribuyen en un formato pre-indexado, no hay límites de licencia basados en volumen de los que preocuparse.

## Data Sourcetypes incluidos
* access_combined
* alternatives
* amazon-ssm-agent
* amazon-ssm-agent-too_small
* apache_error
* aws:cloudtrail
* aws:cloudwatch
* aws:cloudwatch:guardduty
* aws:cloudwatchlogs
* aws:cloudwatchlogs:vpcflow
* aws:config:rule
* aws:description
* aws:elb:accesslogs
* aws:rds:audit
* aws:rds:error
* aws:s3:accesslogs
* bandwidth
* bash_history
* bootstrap
* cisco:asa
* cloud-init
* cloud-init-output
* code42:api
* code42:computer
* code42:org
* code42:security
* code42:user
* config_file
* cpu
* cron-too_small
* df
* dmesg
* dpkg
* error-too_small
* errors
* errors-too_small
* ess_content_importer
* hardware
* history-2
* interfaces
* iostat
* lastlog
* linux_audit
* linux_secure
* localhost-5
* lsof
* maillog-too_small
* ms:aad:audit
* ms:aad:signin
* ms:o365:management
* ms:o365:reporting:messagetrace
* netstat
* o365:management:activity
* openports
* osquery:info
* osquery:results
* osquery:warning
* out-3
* package
* perfmonmk:process
* protocol
* ps
* script:getendpointinfo
* script:installedapps
* script:listeningports
* stream:arp
* stream:dhcp
* stream:dns
* stream:http
* stream:icmp
* stream:igmp
* stream:ip
* stream:mysql
* stream:smb
* stream:smtp
* stream:tcp
* stream:udp
* symantec:ep:agent:file
* symantec:ep:agt_system:file
* symantec:ep:behavior:file
* symantec:ep:packet:file
* symantec:ep:risk:file
* symantec:ep:scm_system:file
* symantec:ep:security:file
* symantec:ep:traffic:file
* syslog
* time
* top
* unix:listeningports
* unix:service
* unix:sshdconfig
* unix:update
* unix:uptime
* unix:useraccounts
* unix:version
* userswithloginprivs
* vmstat
* who
* wineventlog
* winhostmon
* xmlwineventlog:microsoft-windows-sysmon/operational
* yum-too_small


## Software Requerido
Este dataset requiere el siguiente software que se distribuye y licencia por separado, y debe instalarse antes de usar el conjunto de datos. Las versiones listadas son las que se utilizaron para crear el conjunto de datos. Diferentes versiones del software pueden o no funcionar correctamente. Si eres nuevo en Splunk, sigue [estas instrucciones](https://docs.splunk.com/Documentation/AddOns/released/Overview/Singleserverinstall) para instalar los Apps y Add-Ons.


|	App / Add-on	|	Version	|	Download
| ----------- | ------- | -------- |
| Splunk Enterprise                               | 7.1.7 | http://www.splunk.com
|	Aws_guardduty	                                  |	1.0.4	|	https://splunkbase.splunk.com/app/3790/
|	CiscoNVM	                                      |	1.0.346	|	https://splunkbase.splunk.com/app/2992/
|	Code42 App For Splunk	                          |	3.0.6	|	https://splunkbase.splunk.com/app/3736/
|	Code42ForSplunk Technology Add-On	              |	3.0.4	|	https://splunkbase.splunk.com/app/3746/
|	Splunk Add-on for Cisco ASA	                    |	3.3.0	|	https://splunkbase.splunk.com/app/1620/
|	Splunk Add-on for Microsoft Cloud Services	    |	2.1.0	|	https://splunkbase.splunk.com/app/3110/
|	Splunk Add-on for Microsoft Office 365	        |	1.0.0	|	https://splunkbase.splunk.com/app/4055/
|	Splunk Add-on for Microsoft Windows	            |	4.8.4	|	https://splunkbase.splunk.com/app/742/
|	Splunk Add-on for Symantec Endpoint Protection	|	2.3.0	|	https://splunkbase.splunk.com/app/2772/
|	Splunk Add-on for Tenable	                      |	5.1.3	|	https://splunkbase.splunk.com/app/1710/
|	Splunk Add-on for Unix and Linux	              |	5.2.4	|	https://splunkbase.splunk.com/app/833/
|	Splunk Common Information Model	                |	4.11.0	|	https://splunkbase.splunk.com/app/1621/
|	Splunk Security Essentials	                    |	2.2.0	|	https://splunkbase.splunk.com/app/3435/
|	Splunk Stream Add-on	                          |	7.1.2	|	https://splunkbase.splunk.com/app/1809/
|	TA-VirusTotalActions	                          |	0.2.0	|	https://splunkbase.splunk.com/app/3446/
|	URL Toolbox	                                    |	1.6	  |	https://splunkbase.splunk.com/app/2734/
|	DecryptCommands	                                |	2	|	https://splunkbase.splunk.com/app/2655/
|	Microsoft Azure Active Directory Reporting Add-on for Splunk	|	1.0.1	|	https://splunkbase.splunk.com/app/3757/
|	Microsoft Cloud App for Splunk	                |	1.0.1	|	https://splunkbase.splunk.com/app/3786/
|	Microsoft Office 365 Reporting Add-on for Splunk  |	1.0.1	|	https://splunkbase.splunk.com/app/3720/
|	Microsoft Sysmon Add-on	                        |	8.0.0	|	https://splunkbase.splunk.com/app/1914/
|	OSquery App for Splunk	                        |	0.6.0	|	https://splunkbase.splunk.com/app/3902/
|	Splunk Add-on for AWS	                          |	4.5.0	|	https://splunkbase.splunk.com/app/1876/
|	ES Content Updates	                            |	1.0.25	|	https://splunkbase.splunk.com/app/3449/
|	SA-cim_vladiator	                              |	1.2	|	https://splunkbase.splunk.com/app/2968/


## Advertencia

**Tenga en cuenta que este conjunto de datos puede contener blasfemias, jerga, expresiones vulgares y/o terminología generalmente ofensiva. Úselo con discreción.**


Este conjunto de datos contiene evidencia capturada durante incidentes reales de seguridad informática, o de recreaciones realistas en laboratorio de incidentes de seguridad. Como tal, el conjunto de datos puede contener blasfemias, jerga, expresiones vulgares y/o terminología generalmente ofensiva. Los autores creen que los beneficios educativos de preservar el realismo del conjunto de datos superan el riesgo de ofender a algunos usuarios. Si la posibilidad de encontrar este tipo de material ofensivo es una preocupación para usted o para cualquier audiencia con la que planea compartir el conjunto de datos, deténgase ahora y no continúe.


## Autores

Escrito en 2018 por Ryan Kovar, David Herrald, James Brodsky, John Stoner, Jim Apger, David Veuve, Lily Lee y Matt Valites.


## Derechos de Autor y Licencia

En la medida de lo posible bajo la ley, los autores han dedicado todos los derechos de autor y derechos conexos y afines de este software al dominio público en todo el mundo. Este software se distribuye sin ninguna garantía. Deberías haber recibido una copia de la Dedicación de Dominio Público CC0 junto con este software. Si no, consulta http://creativecommons.org/publicdomain/zero/1.0/.
