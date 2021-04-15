# Serial Savior




### Archive releases
```bash
$ git archive --format=zip --output=../myproject_v1.0.zip v1.0
```



### VSC setup
Add to `.gitattributes`:
```
*.pro filter=kicad_project
*.sch filter=kicad_sch
```

Configure git
```bash
$ git config --global filter.kicad_project.clean "sed -E 's/^update=.*$/update=Date/'"
$ git config --global filter.kicad_project.smudge cat
$ git config --global filter.kicad_sch.clean "sed -E 's/#(PWR|FLG)[0-9]+/#\1?/'"
$ git config --global filter.kicad_sch.smudge cat
```
Source: https://jnavila.github.io/plotkicadsch/
