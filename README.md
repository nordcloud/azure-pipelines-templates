# azure-pipelines-templates

Hi, 👋. This repository holds azure pipeline templates that can be reused in our projects. 

## How to use ?

Documentation can be found in Microsoft pages: https://docs.microsoft.com/en-us/azure/devops/pipelines/process/templates?view=azure-devops#passing-parameters. 

PAT recommendations:
* keep the main pipeline file in `azure-pipelines.yml` in the root of the repository if you have one pipeline only
* if you go multi pipeline, keep your pipeline ymls in `.azure-pipelines` 
* for templates create: `.azure-pipelines/templates` directory and keep the templates there

## Adding new template

Adding new template should be done by a PR to this repository. File naming convention is `{type}-yourname.yml`, where `{type}` should be either: `step, job or stagr` depending on the type of template. 

Inside the template file add a comment manifest, example:

```markdown
# Version: 0.1
# Maintainer: Dariusz Dwornikowski
# Parameters:
# version: version of the tool (string)
```
You can also add any comment that explains how template parameters are to used. 


## Usage example

```yaml
      - template: templates/step-cache-go-mod.yml
        parameters:
          path:  $(GOPATH)/pkg/mod
```

## Owners

Onwers of the repo is PAT