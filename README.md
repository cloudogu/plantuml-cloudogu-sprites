# Sprites for PlantUML

This repository includes a set of logos from [Cloudogu EcoSystem](https://cloudogu.com/?mtm_campaign=sprites&mtm_kwd=website&mtm_source=github&mtm_medium=link) Dogus and other tools for using as [Sprites](http://plantuml.com/sprite) in [PlantUML](http://plantuml.com). BTW: Check out our Git based wiki [Smeagol](https://github.com/cloudogu/smeagol) which has rich PlantUML support!

This work was inspired by [tupadr3/plantuml-icon-font-sprites](https://github.com/tupadr3/plantuml-icon-font-sprites). (Note: if you use their sprites in the same PlantUML diagram with sprites from this repo, you don't have to include the file common.puml from their repo. The code is already in common.puml of this repo.)

## Usage

First include the file common.puml either via path or url. It also contains style definitions according to the Cloudogu CI

```
[...]
!include ../common.puml
!includeurl https://raw.githubusercontent.com/cloudogu/plantuml-cloudogu-sprites/master/common.puml
[...]
```
You can define a macro for the URL

```
[...]
!define CLOUDOGUURL https://raw.githubusercontent.com/cloudogu/plantuml-cloudogu-sprites/master
!includeurl CLOUDOGUURL/common.puml
[...]
```

Then include the sprites that you want to use 

```
[...]
!includeurl CLOUDOGUURL/dogus/scm.puml
!includeurl CLOUDOGUURL/dogus/smeagol.puml
[...]
```

To use the Sprites you can include their name directly with <<$name>>

```
[...]
node "Cloudogu Ecosystem" <<$cloudogu>> {
[...]
```

or add one of the defined macros. Prefix can be either 'DOGU' or 'TOOL':

```
[...]
<prefix>_<name>(alias)
<prefix>_<name>(alias,label)
<prefix>_<name>(alias,label,shape)
<prefix>_<name>(alias,label,shape,color)
[...]
```

## Complete Example
```
@startuml
!define CLOUDOGUURL https://raw.githubusercontent.com/cloudogu/plantuml-cloudogu-sprites/master
!includeurl CLOUDOGUURL/common.puml
!includeurl CLOUDOGUURL/dogus/jenkins.puml
!includeurl CLOUDOGUURL/dogus/cloudogu.puml
!includeurl CLOUDOGUURL/dogus/scm.puml
!includeurl CLOUDOGUURL/dogus/smeagol.puml
!includeurl CLOUDOGUURL/dogus/nexus.puml
!includeurl CLOUDOGUURL/tools/k8s.puml

node "Cloudogu Ecosystem" <<$cloudogu>> {
	DOGU_JENKINS(jenkins, Jenkins) #ffffff
	DOGU_SCM(scm, SCM-Manager) #ffffff
	DOGU_SMEAGOL(smeagol, Smeagol) #ffffff
	DOGU_NEXUS(nexus,Nexus) #ffffff
}

TOOL_K8S(k8s, Kubernetes) #ffffff

actor developer

developer -> smeagol : "Edit Slides"
smeagol -> scm : Push
scm -> jenkins : Trigger
jenkins -> nexus : Deploy
jenkins -> k8s : Deploy

@enduml
```

![Example](example.png "Example")

## List of all Dogu Sprites

| Sprite | Dogu name | Macro | Name |
|--------|-----------|-------|------|
| ![CAS](https://github.com/cloudogu/plantuml-cloudogu-sprites/raw/master/dogus/cas.jpg "CAS") | CAS | DOGU_CAS | $cas |
| ![Cloudogu](https://github.com/cloudogu/plantuml-cloudogu-sprites/raw/master/dogus/cloudogu.jpg "Cloudogu") | Cloudogu | DOGU_CLOUDOGU | $cloudogu |
| ![Cockpit](https://github.com/cloudogu/plantuml-cloudogu-sprites/raw/master/dogus/cockpit.png "Cockpit") | Cockpit | DOGU_COCKPIT | $cockpit |
| ![Jenkins](https://github.com/cloudogu/plantuml-cloudogu-sprites/raw/master/dogus/jenkins.jpg "Jenkins") | Jenkins | DOGU_JENKINS | $jenkins |
| ![Nexus](https://github.com/cloudogu/plantuml-cloudogu-sprites/raw/master/dogus/nexus.jpg "Nexus") | Nexus | DOGU_NEXUS | $nexus |
| ![Nginx](https://github.com/cloudogu/plantuml-cloudogu-sprites/raw/master/dogus/nginx.jpg "Nginx") | Nginx | DOGU_NGINX | $nginx |
| ![OpenLDAP](https://github.com/cloudogu/plantuml-cloudogu-sprites/raw/master/dogus/openldap.jpg "OpenLDAP") | OpenLDAP | DOGU_OPENLDAP | $openldap |
| ![PlantUML](https://github.com/cloudogu/plantuml-cloudogu-sprites/raw/master/dogus/plantuml.jpg "PlantUML") | PlantUML | DOGU_PLANTUML | $plantuml |
| ![Postfix](https://github.com/cloudogu/plantuml-cloudogu-sprites/raw/master/dogus/postfix.jpg "Postfix") | Postfix | DOGU_POSTFIX | $postfix |
| ![Redmine](https://github.com/cloudogu/plantuml-cloudogu-sprites/raw/master/dogus/redmine.jpg "Redmine") | Redmine | DOGU_REDMINE | $redmine |
| ![Registrator](https://github.com/cloudogu/plantuml-cloudogu-sprites/raw/master/dogus/registrator.jpg "Registrator") | Registrator | DOGU_REGISTRATOR | $registrator |
| ![SCM Manager](https://github.com/cloudogu/plantuml-cloudogu-sprites/raw/master/dogus/scm.jpg "SCM Manager") | SCM Manager | DOGU_SCM | $scm |
| ![Smeagol](https://github.com/cloudogu/plantuml-cloudogu-sprites/raw/master/dogus/smeagol.png "Smeagol") | Smeagol | DOGU_SMEAGOL | $smeagol |
| ![Sonarqube](https://github.com/cloudogu/plantuml-cloudogu-sprites/raw/master/dogus/sonarqube.jpg "Sonarqube") | Sonarqube | DOGU_SONARQUBE | $sonarqube |
| ![User management](https://github.com/cloudogu/plantuml-cloudogu-sprites/raw/master/dogus/usermgmt.png "User management") | User management | DOGU_USERMGMT | $usermgmt |
| ![LDAP mapper](https://github.com/cloudogu/plantuml-cloudogu-sprites/raw/master/dogus/ldapmapper.png "LDAP mapper") | LDAP mapper | DOGU_LDAPMAPPER | $ldapmapper |
| ![Jira](https://github.com/cloudogu/plantuml-cloudogu-sprites/raw/master/dogus/jira.png "Jira") | jira | DOGU_JIRA | $jira |

## List of all other tools sprites

| Sprite | Tool name | Macro | Name |
|--------|-----------|-------|------|
| ![Ansible](https://github.com/cloudogu/plantuml-cloudogu-sprites/raw/master/tools/ansible.jpg "Ansible") | Ansible | TOOL_ANSIBLE | $ansible |
| ![Docker](https://github.com/cloudogu/plantuml-cloudogu-sprites/raw/master/tools/docker.jpg "Docker") | Docker | TOOL_DOCKER | $docker |
| ![Elastic Search](https://github.com/cloudogu/plantuml-cloudogu-sprites/raw/master/tools/elastic.jpg "Elastic Search") | Elastic Search | TOOL_ELASTIC | $elastic |
| ![Etcd](https://github.com/cloudogu/plantuml-cloudogu-sprites/raw/master/tools/etcd.jpg "Etcd") | Etcd | TOOL_ETCD | $etcd |
| ![Grafana](https://github.com/cloudogu/plantuml-cloudogu-sprites/raw/master/tools/grafana.jpg "Grafana") | Grafana | TOOL_GRAFANA | $grafana |
| ![JUnit](https://github.com/cloudogu/plantuml-cloudogu-sprites/raw/master/tools/junit.jpg "JUnit") | JUnit | TOOL_JUNIT | $junit |
| ![Kubernetes](https://github.com/cloudogu/plantuml-cloudogu-sprites/raw/master/tools/k8s.jpg "Kubernetes") | Kubernetes | TOOL_K8S | $k8s |
| ![Prometheus](https://github.com/cloudogu/plantuml-cloudogu-sprites/raw/master/tools/prometheus.jpg "Prometheus") | Prometheus | TOOL_PROMETHEUS | $prometheus |
| ![QEmu](https://github.com/cloudogu/plantuml-cloudogu-sprites/raw/master/tools/qemu.jpg "QEmu") | QEmu | TOOL_QEMU | $qemu |
| ![Terraform](https://github.com/cloudogu/plantuml-cloudogu-sprites/raw/master/tools/terraform.jpg "Terraform") | Terraform | TOOL_TERRAFORM | $terraform |
| ![Ubuntu](https://github.com/cloudogu/plantuml-cloudogu-sprites/raw/master/tools/ubuntu.jpg "Ubuntu") | Ubuntu | TOOL_UBUNTU | $ubuntu |
| ![Virtualbox](https://github.com/cloudogu/plantuml-cloudogu-sprites/raw/master/tools/virtualbox.jpg "Virtualbox") | Virtualbox | TOOL_VIRTUALBOX | $virtualbox |
| ![VMWare](https://github.com/cloudogu/plantuml-cloudogu-sprites/raw/master/tools/vmware.jpg "VMWare") | VMWare | TOOL_VMWARE | $vmware |

All trademarks, product names and logos appearing above are the property of their respective owners, including in some instances Cloudogu GmbH. Any rights not expressly granted herein are reserved.

---
### What is the Cloudogu EcoSystem?
The Cloudogu EcoSystem is an open platform, which lets you choose how and where your team creates great software. Each service or tool is delivered as a Dogu, a Docker container. Each Dogu can easily be integrated in your environment just by pulling it from our registry. We have a growing number of ready-to-use Dogus, e.g. SCM-Manager, Jenkins, Nexus, SonarQube, Redmine and many more. Every Dogu can be tailored to your specific needs. Take advantage of a central authentication service, a dynamic navigation, that lets you easily switch between the web UIs and a smart configuration magic, which automatically detects and responds to dependencies between Dogus. The Cloudogu EcoSystem is open source and it runs either on-premises or in the cloud. The Cloudogu EcoSystem is developed by Cloudogu GmbH under [MIT License](https://cloudogu.com/en/license/?mtm_campaign=sprites&mtm_kwd=license&mtm_source=github&mtm_medium=link).

### How to get in touch?
Want to talk to the Cloudogu team? Need help or support? There are several ways to get in touch with us:

* [Website](https://cloudogu.com/?mtm_campaign=sprites&mtm_kwd=website&mtm_source=github&mtm_medium=link)
* [myCloudogu-Forum](https://forum.cloudogu.com/topic/34?ctx=1)
* [Email hello@cloudogu.com](mailto:hello@cloudogu.com)

---
&copy; 2020 Cloudogu GmbH - MADE WITH :heart: FOR DEV ADDICTS. [Legal notice / Impressum](https://cloudogu.com/en/imprint/?mtm_campaign=sprites&mtm_kwd=imprint&mtm_source=github&mtm_medium=link)
