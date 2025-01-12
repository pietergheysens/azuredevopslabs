<a name="Overview"></a>

## Overview ##

Many teams prefer to define their build and release pipelines using YAML (YAML Ain’t Markup Language). This allows them to access the same pipeline features as those using the visual designer, but with a markup file that can be managed like any other source file. YAML build definitions can be added to a project by simply adding their source file to the root of the repository. Azure DevOps also provides default templates for popular project types, as well as a YAML designer to simplify the process of defining build and release tasks.
 
<a name="Exercise1"></a>
## Exercise 1: Configuring CI Pipeline as Code with YAML in Azure DevOps ##

<a name="Ex1Task3"></a>
### Task 1: Configuring the Parts Unlimited project ###

1. Navigate to your team project on Azure DevOps in a new browser tab. Before digging into the YAML pipelines, you will want to disable the existing build pipeline.

1. Navigate to **Pipelines**.

    ![](images/008.png)

1. Select the existing **PartsUnlimitedE2E** pipeline.

    ![](images/009.png)

1. From the dropdown, select **Pause pipeline**.

    ![](images/010.png)

<a name="Ex1Task4"></a>
### Task 2: Adding a YAML build definition ###

1. Navigate to the **Pipelines** hub.

    ![](images/011.png)

1. Click **New pipeline**. We will use the wizard to automatically create the YAML definition based on our project.

    ![](images/012.png)

1. Select the **Azure Repos Git** as the source hosting platform. Note the others supported.

    ![](images/013.png)

1. Select the **PartsUnlimited** repo.

    ![](images/014.png)

1. Select the **ASP.NET** template as the starting point for your pipeline.

    ![](images/015.png)

1. Review the contents of the YAML definition. It will be saved as a new file called **"azure-pipelines.yml"** in the root of the repository and contain everything needed to build and test a typical ASP.NET solution. You can also customize the build as needed. In this case, update the **pool** to specify the build should use a Visual Studio 2017 build VM.

    ![](images/poolimage.png)

1. Review trigger and point to **master** if you repo does not have **main** (new repos will have "main" instead of "master").

1. Click **Save and run**.

    ![](images/017.png)

1. Click **Save and run** to confirm the commit.

    ![](images/018.png)

1. Track the build until it completes. Click **Job** to see the logs.

    ![](images/019.png)

1. Each task from the YAML file is available for review, including any warnings and errors.

    ![](images/020.png)

1. Close the tasks view.

    ![](images/021.png)

1. Select the **Tests** tab.

    ![](images/022.png)

1. The tests should now succeed as expected.

    ![](images/023.png)
