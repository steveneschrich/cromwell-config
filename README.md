# cromwell-config
Configuration definitions for running cromwell server


## Backend Specification
The backend is the what runs the tasks.

Per (https://github.com/broadinstitute/cromwell/issues/3533), a backend is selected by:

- Default backend declared in workflow options (?)
- Task definition runtime includes `backend`
- Default backend is declared


Thus, if you are creating a options.json file for running, include:
```
{
    "default_runtime_attributes": {
        "backend": "apptainer"
    }
}
```



# runtime-attributes
Within a task (or set as defaults), there are several runtime attributes that can be passed to the backend for help in running the job. In the simplest case, this includes things like the amount of memory (`memory`) or number of cpus (`cpu`).

There are a set of common attributes and some custom attributes for specific platforms:
https://cromwell.readthedocs.io/en/stable/RuntimeAttributes/. At least for the SFS (which at least HPC uses), you can create your own attributes as needed.




