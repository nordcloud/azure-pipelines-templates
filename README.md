# azure-pipelines-templates

Hi, 👋. This repository holds azure pipeline templates that can be reused in your projects. 

## How to use the templates ?

Documentation can be found in Microsoft pages: https://docs.microsoft.com/en-us/azure/devops/pipelines/process/templates?view=azure-devops#passing-parameters. 

PAT recommendations:
* keep the main pipeline file in `azure-pipelines.yml` in the root of the repository if you have one pipeline only
* if you go multi pipeline, keep your pipeline ymls in `.azure-pipelines` 
* for templates create: `.azure-pipelines/templates` directory and keep the templates there

## Templates

* `step-assume-role-arn.yml` - sets credentials of the assumed role
* `step-cache-go-mod.yml` - sets caching of the `$GOPATH/mod/pkg` directory

## Usage example

If you copy a template to your repo:

```yaml
      - template: templates/step-cache-go-mod.yml
        parameters:
          path:  $(GOPATH)/pkg/mod
```

Or if you want to reference it from a foreign repository check it here (https://docs.microsoft.com/en-us/azure/devops/pipelines/process/templates?view=azure-devops#using-other-repositories). 


## Contributing 

Adding new template should be done by a PR to this repository. File naming convention is `{type}-yourname.yml`, where `{type}` should be either: `step, job or stage` depending on the type of template. 

Inside the template file add a comment manifest, example:

```markdown
# Version: 0.1
# Maintainer: Dariusz Dwornikowski
# Parameters:
# version: version of the tool (string)
```

You can also add any comment that explains how template parameters are to used.

## License 

MIT

## Authors 

Platform and Tools, Nordcloud, Poland

