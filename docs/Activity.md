
# Type: activity


a provence-generating activity

URI: [ocl:Activity](http://w3id.org/oclActivity)


![img](http://yuml.me/diagram/nofunky;dir:TB/class/[Agent],[Agent]<was%20associated%20with%200..1-++[Activity&#124;activity_id:string;started_at_time:string%20%3F;ended_at_time:string%20%3F;used:string%20%3F],[Activity]<was%20informed%20by%200..1-%20[Activity],[Change]-%20was%20generated%20by%200..1>[Activity],[Change])

## Referenced by class

 *  **None** *[was generated by](was_generated_by.md)*  <sub>OPT</sub>  **[Activity](Activity.md)**
 *  **None** *[was informed by](was_informed_by.md)*  <sub>OPT</sub>  **[Activity](Activity.md)**

## Attributes


### Own

 * [activity id](activity_id.md)  <sub>REQ</sub>
    * range: [String](types/String.md)
 * [ended at time](ended_at_time.md)  <sub>OPT</sub>
    * range: [String](types/String.md)
 * [started at time](started_at_time.md)  <sub>OPT</sub>
    * range: [String](types/String.md)
 * [used](used.md)  <sub>OPT</sub>
    * range: [String](types/String.md)
 * [was associated with](was_associated_with.md)  <sub>OPT</sub>
    * range: [Agent](Agent.md)
 * [was informed by](was_informed_by.md)  <sub>OPT</sub>
    * range: [Activity](Activity.md)

## Other properties

|  |  |  |
| --- | --- | --- |
| **Mappings:** | | prov:Activity |

