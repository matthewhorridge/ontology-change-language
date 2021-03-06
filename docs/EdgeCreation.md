
# Type: edge creation


An edge change in which a de-novo edge is created. The edge is potentially annotated in the same action.

URI: [ocl:EdgeCreation](http://w3id.org/oclEdgeCreation)


![img](http://yuml.me/diagram/nofunky;dir:TB/class/[Node],[Annotation]<annotation%20set%200..1-++[EdgeCreation&#124;change_description:string%20%3F;about(i):string%20%3F;old_value(i):string%20%3F;new_value(i):string%20%3F],[Node]<object%200..1-%20[EdgeCreation],[Node]<edge%20label%200..1-%20[EdgeCreation],[Node]<subject%200..1-%20[EdgeCreation],[EdgeCreation]uses%20-.->[Creation],[EdgeChange]^-[EdgeCreation],[EdgeChange],[Creation],[Annotation],[Activity])

## Parents

 *  is_a: [EdgeChange](EdgeChange.md) - A change in which the entity changes is an edge

## Uses Mixins

 *  mixin: [Creation](Creation.md) - Creation of an element.

## Referenced by class


## Attributes


### Own

 * [annotation set](annotation_set.md)  <sub>OPT</sub>
    * range: [Annotation](Annotation.md)
 * [edge creation➞change description](edge_creation_change_description.md)  <sub>OPT</sub>
    * range: [String](types/String.md)
 * [edge label](edge_label.md)  <sub>OPT</sub>
    * range: [Node](Node.md)
 * [object](object.md)  <sub>OPT</sub>
    * range: [Node](Node.md)
 * [subject](subject.md)  <sub>OPT</sub>
    * range: [Node](Node.md)

### Inherited from edge change:

 * [edge change➞about](edge_change_about.md)  <sub>OPT</sub>
    * range: [String](types/String.md)
 * [new value](new_value.md)  <sub>OPT</sub>
    * Description: The value of a property held in the old instance of the ontology
    * range: [String](types/String.md)
 * [old value](old_value.md)  <sub>OPT</sub>
    * Description: The value of a property held in the old instance of the ontology
    * range: [String](types/String.md)
 * [was generated by](was_generated_by.md)  <sub>OPT</sub>
    * range: [Activity](Activity.md)

## Other properties

|  |  |  |
| --- | --- | --- |
| **Aliases:** | | relationship creation |
| **See also:** | | http://wiki.geneontology.org/index.php/Guidelines_for_creating_relationships_between_terms |

