---
title: Pipelines
sidebar_label: Pipelines
---

# Pipelines


A [Flowpipe pipeline](https://flowpipe.io/docs/flowpipe-hcl/pipeline) is a sequence of steps to do work. Pipelines are distributed in [mods](/pipes/docs/using/flowpipe/mods) - you must [install one or more Flowpipe mods](/pipes/docs/using/flowpipe/mods#installing-recommended-mods) to run pipelines.  You can find mods on the [Flowpipe Hub](https://hub.flowpipe.io/), but you can also [write your own mods](https://flowpipe.io/docs/build) and run them in Pipes.


## Viewing Pipelines

You can view and run pipelines from the **Pipelines** tab for the Flowpipe service in your workspace.  Navigate to your workspace, then the the **Pipes** tab, and choose **Flowpipe**.  The **Pipelines** tab will list the runnable pipelines for the mods that you have installed, as well as information about any triggers that have been set up, the last time the pipeline has run, and the next time it will run if it has been scheduled. You can type a search string or filter in the **Query** box to filter the list.


![](/images/docs/pipes/flowpipe/flowpipe_pipelines_list.png)



Clicking on a pipeline will take you to the pipeline detail page.  


![](/images/docs/pipes/flowpipe/flowpipe_pipeline_detail.png)


The pipeline detail page provides extended information about the pipeline, including the last run status, name, description, tags, and information about who created it and when.  You can also see a list of triggers that are configured to run this pipeline, as well a link to the process logs for all runs of the pipeline.  From this page you also have the option to run the pipeline or create a trigger for it.


## Running a Pipeline

You can run a Flowpipe pipeline by clicking the **Run Pipeline** button from the **Pipelines** tab for your workspace or from the pipeline detail page.  If the pipeline has parameters defined, you will be prompted for them.  Enter the parameter values and click **Run Pipeline**.

![](/images/docs/pipes/flowpipe/flowpipe_pipeline_run.png)
.

The pipeline will be submitted for execution, and you will be redirected to the process page where you can view the logs as the process runs.

![](/images/docs/pipes/flowpipe/flowpipe_pipeline_run_complete.png)


## Scheduling a Pipeline

You can set up triggers to run your pipelines automatically.  You can create a trigger from the **Pipelines** list by clicking the clock icon next to the pipeline you wish to trigger.   Alternately, you can click the **Run Pipeline** dropdown and select **Create Trigger** from either the **Pipelines** page or the pipeline detail page.

You will be prompted for any parameters.  

![](/images/docs/pipes/flowpipe/flowpipe_pipeline_scheduled_params.png)



Enter them and click **Next**.  You are then prompted for a schedule.

![](/images/docs/pipes/flowpipe/flowpipe_pipeline_scheduled_frequency.png)


Select the desired interval or enter a custom cron schedule and then click **Create**.


A schedule trigger will be created, and you are redirected to the trigger detail page.

![](/images/docs/pipes/flowpipe/flowpipe_schedule_trigger_detail.png)





