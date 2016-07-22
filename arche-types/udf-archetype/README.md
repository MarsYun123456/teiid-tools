TEIID UDF Arche Type
================

This maven project is use to create the TEIID UDF archetype, which then can be used to generate a new java project for developing a UDF.


-----------
Generate Project
-----------

After the arche type is installed, then to generate a translator project, do the following:

-  use the following template to generate the project:

***********
* TEMPLATE
***********

mvn archetype:generate       -DarchethypeRepository=https://repository.jboss.org/nexus/content/repositories/releases/                                \
  -DarchetypeGroupId=org.jboss.teiid.arche-types               \
  -DarchetypeArtifactId=translator-archetype          \
  -DarchetypeVersion=8.12.1               \
  -DgroupId=${groupId}   				\
  -DartifactId=translator-${translator-type}	\
  -Dpackage=org.teiid.translator.${translator-type}    \
  -Dversion=${version}    \
  -Dtranslator-type=${translator-type}   \
  -Dtranslator-name=${translator-name}
  -Dteiid-version=${teiid-version}
  
mvn archetype:generate       -DarchethypeRepository=https://repository.jboss.org/nexus/content/repositories/releases/                                \
  -DarchetypeGroupId=org.jboss.teiid.arche-types               \
  -DarchetypeArtifactId=udf-archetype          \
  -DarchetypeVersion=9.0.0     \
  -DgroupId=${groupId}   				\
  -DartifactId=${udf-artifact-id}	\
  -Dpackage=${packageName}    \
  -Dversion=0.0.1-SNAPSHOT      \
  -Dudf-name=${functionName}  \
  -Dmethod-name=${methodName}      \
  -Dmethod-args=${methodArguments}   \
  -Dreturn-type=${returnType}


********
* where:
********

  -DarchetypeGroupId    -  is the group ID for the arche type to use to generate
  -DarchetypeArtifactId -  is the artifact ID for the arche type to use to generate
  -DarchetypeVersion	-  is the version for the arche type to use to generate
  -DgroupId		-  (user defined) group ID for the new udf project pom.xml
  -DartifactId		-  (user defined) artifact ID for the new udf project pom.xml
  -Dpackage		-  (user defined) the package structure where the java, module and resource files will be created
  -Dversion		-  (user defined) the version that the new connector project pom.xml will be
  -Dudf-name    	-  (user defined) the name to give the new user defined function, will become the Class Name 
  -Dmethod-name	        -  (user defined) the name of the method that will be configured in the model procedure
  -Dmethod-args         -  (user defined) the arguments the method will accept.  'Type name[, Type name[,...]]  Example:  'String arg0' or 'String arg0, integer arg1'
  -Dreturn-type         -  (user defined) the data type of the value returned by the method

*********
* EXAMPLE
*********

-  this is an example of the template that can be run:

mvn archetype:generate       -DarchethypeRepository=https://repository.jboss.org/nexus/content/repositories/releases/                                \
  -DarchetypeGroupId=org.jboss.teiid.arche-types               \
  -DarchetypeArtifactId=udf-archetype          \
  -DarchetypeVersion=9.0.0     \
  -DgroupId=org.teiid.udf   \
  -DartifactId=udf-myFunction    \
  -Dpackage=org.teiid.udf    \
  -Dversion=0.0.1-SNAPSHOT      \
  -Dudf-name=myFunction \
  -Dmethod-name=myFunction      \
  -Dmethod-args='String arg1'   \
  -Dreturn-type=String


When executed, you will be asked to confirm the package property

[INFO] Archetype repository not defined. Using the one from [org.jboss.teiid.arche-types:udf-archetype:9.0.0] found in catalog local
[INFO] Using property: groupId = org.teiid.udf
[INFO] Using property: artifactId = udf-myFunction
[INFO] Using property: version = 0.0.1-SNAPSHOT
[INFO] Using property: package = org.teiid.udf
[INFO] Using property: method-args = String arg1
[INFO] Using property: method-name = myFunction
[INFO] Using property: return-type = String
[INFO] Using property: udf-name = myFunction
Confirm properties configuration:
groupId: org.teiid.udf
artifactId: udf-myFunction
version: 0.0.1-SNAPSHOT
package: org.teiid.udf
method-args: String arg1
method-name: myFunction
return-type: String
udf-name: myFunction
 Y: : y



type Y (yes) and press enter, and the creation of the udf project will be done
