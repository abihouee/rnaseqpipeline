#My RNASeq Pipeline

##Motivation

RNA Seq pipeline generated using jsvelocity (https://github.com/lindenb/jsvelocity) and GNU make.

## Example

* project.json is generated using  https://github.com/lindenb/jvarkit/wiki/Illuminadir
* config.json described the parameters specific to this analysis:

```json
{
"outdir":"/commun/data/projects/213911_SNL149_61_AD2C11ACXX/align2131114",
"reference":"mm10",
"replicates":{
        "6VGT": {
                "name":"6VGT",
                "samples":["6VGT1","6VGT2","6VGT3"]
                },
        "6VGXA": {
                "name":"6VGXA",
                "samples":["6VGXA1","6VGXA2","6VGXA3"]
                },
        "6VYBS":{
                "name":"6VYBS",
                "samples":["6VYBS1","6VYBS2"]
                },
        "3VGT": {
                "name":"3VGT",
                "samples":["3VGT1","3VGT3"]
                },
        "3VGXA": {
                "name":"3VGXA",
                "samples":["3VGXA1","3VGXA2","3VGXA3"]
                },
        "3VYBS":{
                "name":"3VYBS",
                "samples":["3VYBS1","3VYBS2","3VYBS3"]
                },
        "45VGT": {
                "name":"45VGT",
                "samples":["45VGT1","45VGT2","45VGT3"]
                },
        "45VGXA": {
                "name":"45VGXA",
                "samples":["45VGXA1","45VGXA2"]
                },
        "45VYBS":{
                "name":"45VYBS",
                "samples":["45VYBS1","45VYBS2","45VYBS3"]
                }
        }
}
```

Generating the Makefile:

```bash
java -jar ~/src/jsvelocity/dist/jsvelocity.jar \
        -f config config.json \
        -f references ./src/main/json/references.json \
        -f project /commun/data/projects/20130911_SNL149_0061_AD2C11ACXX/scripts/project.json \
        src/main/velocity/project2make.vm  > Makefile
```

##History

* First functional test: 17 Nov 2013
* Created Nov 2013



