---
title: Triggers
sidebar_label: Triggers
---

# Triggers



A [Flowpipe trigger](https://flowpipe.io/docs/flowpipe-hcl/trigger) is a mechanism to execute a pipeline automatically when an event occurs.  Triggers may be included in  [mods](/pipes/docs/using/flowpipe/mods), but you can also create and delete your own triggers in Pipes.



## Managing Triggers

You can view and manage triggers from the **Triggers** tab for the Flowpipe service in your workspace.  Navigate to your workspace, then the the **Pipes** tab, and choose **Flowpipe**.  The **Triggers** tab will list the triggers for the mods that you have installed, as well as any triggers that you have created in Pipes.  In addition to the trigger name, you can see the trigger state, the last time the pipeline has run, and the next time it will run if it has been scheduled. 

You can type a search string or filter in the **Query** box to filter the list.


SCREEN SHOT.....



## Editing a Trigger

Clicking on a trigger title or the corresponding gear icon will take you to the trigger detail page.  

SCREEN SHOT.....

The trigger detail page provides extended information about the trigger, including the last run status, name, description, tags, and information about who created it and when.  You can also see a list of pipelines that the trigger is configured to run, as well a link to the process logs for all executions of the trigger.  

You can edit the trigger title, description, or frequency (schedule). You can  **Enable** or **Disable** the trigger, or click the **Run Now** button to execute it on demand.



## Managing Triggers

You can set up triggers to run your pipelines automatically.  You can create a trigger from the **Pipelines** list by clicking the clock icon next to the pipeline you wish to trigger.   Alternately, you can click the **Run Pipeline** dropdown and select **Create Trigger** from either the **Pipelines** page or the pipeline detail page.

You will be prompted for any parameters.  

SCREEN SHOT...

Enter them and click **Next**.  You are then prompted for a schedule.  Select the desired interval or enter a custom cron schedule and then click **Create**


## Editing triggers  
You can enable or disable a trigger or change its frequency from the trigger detail page.  To view the trigger detail, you can click on the trigger from the list of pipelines on the **Pipelines** tab or from the trigger list in the pipeline detail page.  

SCREEN SHOT...

Like the pipeline detail page, the trigger detail page shows the last run status, name, description, tags, and information about who created it and when, as well as links to **All Runs** to view historical process logs.  

If the pipeline tags arguments, they will appear as well. Click the pencil icon next to the **Args** to edit them.

The **Details** section will also show the **Frequency**.  Click the pencil icon next to the **Frequency** to edit the schedule.

You can also enable, disable or run the trigger from this page.  The **Run Now** button will execute the trigger manually.  Depending on the state of the trigger there will also be an **Enable** or **Disable** button to change the state.


## Deleting triggers

If you created the trigger in pipes, you can delete it from the trigger detail page.   To view the trigger detail, you can click on the trigger from the list of pipelines on the **Pipelines** tab or from the trigger list in the pipeline detail page.  

At the bottom right, click **Delete Trigger** to delete.  You will be prompted to confirm deletion.  

SCREEN SHOT...

Click **Delete** to permanently delete the trigger.

Note that triggers that are defined in [mods](/pipes/docs/using/flowpipe/mods) cannot be deleted (but you can disable them).
