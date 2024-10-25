---
title: Triggers
sidebar_label: Triggers
---

# Triggers

You can set up triggers to run your pipelines automatically. A [Flowpipe trigger](https://flowpipe.io/docs/flowpipe-hcl/trigger) is a mechanism that executes a pipeline automatically when an event occurs.  Triggers may be included in  [mods](/pipes/docs/using/flowpipe/mods), but you can also create and delete your own triggers in Pipes.


## Viewing Triggers

You can view and manage triggers from the **Triggers** tab for the Flowpipe service in your workspace.  Navigate to your workspace, then to the **Pipes** tab, and choose **Flowpipe**.  Go to the **Triggers** tab.


![](/images/docs/pipes/flowpipe/flowpipe_triggers_list.png)

 The **Triggers** tab will list the triggers for the mods that you have installed, as well as any triggers that you have created in Pipes.  In addition to the trigger name, you can see the trigger state, the last time the pipeline has run, and the next time it will run if it has been scheduled. 

You can type a search string or filter in the **Query** box to filter the list.

Clicking on a trigger title or the corresponding gear icon will take you to the trigger detail page where you can [enable, disable, edit](#editing-a-trigger) or [delete](#deleting-a-trigger) the trigger.
  


## Creating a Trigger

You can create a trigger by clicking the **New Trigger** button on the Flowpipe **Triggers** tab for your workspace. 

First, select the pipeline to run.  Click **Next**.

![](/images/docs/pipes/flowpipe/flowpipe_create_trigger_select_pipeline.png)


Next, enter the parameters to use when the pipeline runs. Click **Next**.

![](/images/docs/pipes/flowpipe/flowpipe_create_trigger_set_params.png)


Finally, you are prompted for a schedule.  Select the desired interval or enter a custom cron schedule and then click **Create**

![](/images/docs/pipes/flowpipe/flowpipe_create_trigger_set_schedule.png)


You can also [create triggers from the **Pipelines** tab](/pipes/docs/using/flowpipe/pipelines#scheduling-a-pipeline) by clicking the clock icon next to the pipeline you wish to trigger, or from the [pipeline detail page](/pipes/docs/using/flowpipe/pipelines#viewing-pipelines) by clicking the **Run Pipeline** button and selecting **Create Trigger** from the dropdown.


## Editing a Trigger
You can enable or disable a trigger or change its frequency from the trigger detail page. To view the trigger detail, you can click on the trigger title or gear icon from the list on the **Triggers** tab. You can also navigate to the trigger detail from the **Pipelines** tab by clicking the trigger from the **Triggers** column next to a pipeline.

![](/images/docs/pipes/flowpipe/flowpipe_schedule_trigger_detail.png)


The trigger detail page provides extended information about the trigger, including the last run status, name, description, tags, and information about who created it and when.  You can also see a list of pipelines that the trigger is configured to run, as well as a link to the process logs for all executions of the trigger.  

You can edit the trigger **Title**, **Description**, or **Frequency** (schedule) as well as the pipeline **Args**. Click the pencil icon next to the field to edit it.

You can also enable, disable, or run the trigger from this page.  The **Run Now** button will execute the trigger manually.  Depending on the state of the trigger, there will also be an **Enable** or **Disable** button to change the state.


## Deleting a trigger

If you created the trigger in pipes, you can delete it from the trigger detail page.  To view the trigger detail, you can click on the trigger title or gear icon from the list on the **Triggers** tab.  You can also navigate to the trigger detail from the **Pipelines** tab by clicking the trigger from the **Triggers** column next to a pipeline.

At the bottom right, click **Delete Trigger** to delete.  You will be prompted to confirm deletion.  Click **Delete** to permanently delete the trigger.

Note that triggers that are defined in [mods](/pipes/docs/using/flowpipe/mods) cannot be deleted (but you can disable them).
