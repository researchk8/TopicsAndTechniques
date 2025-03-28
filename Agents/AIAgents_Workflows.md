# Workflows

Workflows are a simple yet powerful construct that takes a callable and returns elements. Workflows operate well with pipelines but can work with any callable object. Workflows are streaming and work on data in batches, allowing large volumes of data to be processed efficiently.

Given that pipelines are callable objects, workflows enable efficient processing of pipeline data. Large language models typically work with smaller batches of data, workflows are well suited to feed a series of transformers pipelines. 


## Components

### Schedule
Workflows can run on a repeating basis with schedules. This is suitable in cases where a workflow is run against a dynamically expanding input, like an API service or directory of files.

The schedule method takes a cron expression, list of static elements (which dynamically expand i.e. API service, directory listing) and an optional maximum number of iterations.

### Tasks

Workflows execute tasks. Tasks are callable objects with a number of parameters to control the processing of data at a given step. While similar to pipelines, tasks encapsulate processing and don't perform signficant transformations on their own. Tasks perform logic to prepare content for the underlying action(s).


# Resources
- https://neuml.github.io/txtai/workflow/
- https://neuml.github.io/txtai/workflow/schedule/