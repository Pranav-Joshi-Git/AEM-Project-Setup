**AEM Project Setup**

1.  Make sure the system is ready with all the required dependencies
    i.e., Maven and JDK.

2.  Copy below command and paste it in command prompt in desired folder
    (make sure entire command is on single line):

3.  Post running this command, project build may fail because of below
    error:

![A screenshot of a computer program Description automatically
generated](./image1.png){width="6.5in"
height="1.7326388888888888in"}

4.  Compare folder structure in generated project and the main
    pom.xml(modules) of the project. **dispatcher.ams** folder will not
    be there as part of folder structure.

![A screenshot of a computer Description automatically
generated](./image2.png){width="3.5335444006999124in"
height="4.616247812773404in"}![A screen shot of a computer Description
automatically
generated](./image3.png){width="3.1225831146106735in"
height="4.658672353455818in"}

5.  To see exact error, we need to build the project (In project's
    directory). Do it with the help of the command below:

6.  After running the command, below exact error will be shown:

![A computer screen shot of a black screen Description automatically
generated](./image4.png){width="6.575in"
height="2.1006944444444446in"}

Which clearly mentions that the mentioned folder is not present.

7.  Open pom.xml of dispatcher folder which will look something like
    this:

![A screen shot of a computer Description automatically
generated](./image5.png){width="6.268055555555556in"
height="1.7770833333333333in"}

Here artifactId clearly mentions that this folder is of dispatcher.ams

So, rename dispatcher folder to dispatcher.ams.

8.  After this we do not need dispatcher module anymore in our main
    pom.xml. So, delete or comment as follows:

![A screen shot of a computer Description automatically
generated](./image6.png){width="3.168850612423447in"
height="2.9591272965879267in"}

9.  Run build command i.e., mvn package again. Build may fail again with
    the following error:

![A screen shot of a computer screen Description automatically
generated](./image7.png){width="7.268055555555556in"
height="2.227777777777778in"}

The error essentially tells that there is not any Header Model (Java
Class) for that component (logo component in this case). Try navigating
to the core folder till models.

At the same time error is being thrown for the target folder which comes
into picture at the time of build (For compiling and packaging). Whereas
the main code resides under the src folder.

So, delete the logo component (folder from below paths) from both src
and target folders.

**aem-guides-practice/ui.apps/target/generated-sources/htl/org/apache/sling/scripting/sightly/apps/practice/components/commerce**

**aem-guides-practice\\ui.apps\\src\\main\\content\\jcr_root\\apps\\practice\\components\\commerce**
