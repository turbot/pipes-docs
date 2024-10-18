---
title: Pipelines
sidebar_label: Pipelines
---

# Pipelines


A [Flowpipe pipeline](https://flowpipe.io/docs/flowpipe-hcl/pipeline) is a sequence of steps to do work. Pipelines are distributed in [mods](/pipes/docs/using/flowpipe/mods).  You can find mods on the [Flowpipe Hub](https://hub.flowpipe.io/), but you can also [write your own mods](https://flowpipe.io/docs/build) and run them in Pipes.


## Viewing Pipelines

You can view and run pipelines from the **Pipelines** tab for the Flowpipe service in your workspace.  Navigate to your workspace, then the the **Pipes** tab, and choose **Flowpipe**.  The **Pipelines** tab will list the runnable pipelines for the mods that you have installed, as well as information about any triggers that have been set up, the last time the pipeline has run, and the next time it will run if it has been scheduled. You can type a search string or filter in the **Query** box to filter the list.


SCREEN SHOT.....


Clicking on a pipeline will take you to the pipeline detail page.  


SCREEN SHOT.....

The pipeline detail page provides extended information about the pipeline, including the last run status, name, description, tags, and information about who created it and when.  You can also see a list of triggers that are configured to run this pipeline, as well a link to the process logs for all runs of the pipeline.  From this page you also have the option to run the pipeline or create a trigger for it.


## Running a Pipeline

You can run a Flowpipe pipeline by clicking the **Run Pipeline** button from the **Pipelines** tab for your workspace or from the pipeline detail page.  If the pipeline has parameters defined, you will be prompted for them.  Enter the parameter values and click **Run Pipeline**.

SCREEN SHOT.....

The pipeline will be submitted for execution, and you will be redirected to the process page where you can view the logs as the process runs.



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