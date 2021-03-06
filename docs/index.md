
# Ocl schema


A data model for describing change operations at a high level on an ontology or ontology-like artefact. See [https://github.com/cmungall/ontology-change-language](https://github.com/cmungall/ontology-change-language)


### Classes

 * [Activity](Activity.md) - a provence-generating activity
 * [Agent](Agent.md) - a provence-generating agent
 * [Change](Change.md) - Any change perform on an ontology or knowledge graph
    * [ComplexChange](ComplexChange.md) - A change that is is a composition of other changes
    * [SimpleChange](SimpleChange.md) - A change that is about a single ontology element
       * [DatatypeChange](DatatypeChange.md)
       * [EdgeChange](EdgeChange.md) - A change in which the entity changes is an edge
          * [EdgeCreation](EdgeCreation.md) - An edge change in which a de-novo edge is created. The edge is potentially annotated in the same action.
          * [EdgeDeletion](EdgeDeletion.md) - An edge change in which an edge is removed. All edge annotations/properies are removed in the same action.
          * [EdgeLabelChange](EdgeLabelChange.md) - An edge change where the edge label (relationship type) is modified.
          * [EdgeLogicalInterpretationChange](EdgeLogicalInterpretationChange.md) - An edge change where the subjet, object, and edge label are unchanged, but the logical interpretation changes
          * [EdgeObsoletion](EdgeObsoletion.md) - An edge change in which an edge is obsoleted.
          * [NodeMove](NodeMove.md) - A node move is a combination of deleting a parent edge and adding a parent edge, where the edge label is preserved and the object/parent node changes
             * [NodeDeepening](NodeDeepening.md) - A node move in which a node where the destination is a proper descendant of the original location. Note that here descendant applied not just to subclass, but edges of any edge label in the relational graph
             * [NodeShallowing](NodeShallowing.md) - The opposite of node deepening
       * [NodeChange](NodeChange.md) - A simple change where the change is about a node
          * [AddNodeToSubset](AddNodeToSubset.md) - Places a node inside a subset, by annotating that node
          * [NodeAnnotationChange](NodeAnnotationChange.md) - A node change where the change alters node properties/annotations. TODO
             * [NodeAnnotationReplacement](NodeAnnotationReplacement.md) - A node annotation change where the change replaces a particular property value. TODO
          * [NodeCreation](NodeCreation.md)
          * [NodeDeletion](NodeDeletion.md) - Deletion of a node from the graph. Note it is recommended nodes are obsoleted and never merged, but this operation exists to represent deletions in ontologies, accidental or otherwise
          * [NodeObsoletion](NodeObsoletion.md) - Obsoletion of a node deprecates usage of that node, but does not delete it.
             * [NodeObsoletionWithMerge](NodeObsoletionWithMerge.md) - An obsoletion change in which information from the obsoleted node is moved to a single target.
             * [NodeObsoletionWithSplit](NodeObsoletionWithSplit.md) - An obsoletion change in which information from the obsoleted node is moved selectively to multiple targets
          * [NodeRename](NodeRename.md) - A node change where the name (aka rdfs:label) of the node changes
          * [NodeSynonymChange](NodeSynonymChange.md)
             * [NewSynonym](NewSynonym.md) - A node change where a de-novo synonym is created
             * [RemoveSynonym](RemoveSynonym.md) - A node change where a synonym is deleted
             * [SynonymReplacement](SynonymReplacement.md) - A node change where the text of a synonym is changed
          * [NodeTextDefinitionChange](NodeTextDefinitionChange.md)
             * [NewTextDefinition](NewTextDefinition.md) - A node change where a de-novo text definition is created
             * [RemoveTextDefinition](RemoveTextDefinition.md) - A node change where a text definition is deleted
             * [TextDefinitionReplacement](TextDefinitionReplacement.md) - A node change where a text definition is modified
          * [NodeUnobsoletion](NodeUnobsoletion.md) - unobsoletion of a node deprecates usage of that node. Rarely applied.
          * [RemovedNodeFromSubset](RemovedNodeFromSubset.md) - Removes a node from a subset, by removing an annotation
 * [ChangeSetSummaryStatistic](ChangeSetSummaryStatistic.md) - A summary statistic for a set of changes of the same type, grouped by zero or more node properties
 * [OntologyElement](OntologyElement.md) - Any component of an ontology or knowledge graph
    * [Edge](Edge.md) - A relationship between two nodes. We assume owlstar or similar for existential restrictions
    * [LogicalDefinition](LogicalDefinition.md)
    * [Node](Node.md) - Any named entity in an ontology. May be a class, individual, property
       * [ClassNode](ClassNode.md) - A node that is a class
       * [InstanceNode](InstanceNode.md) - A node that is an individual
    * [PropertyValue](PropertyValue.md) - a property-value pair
       * [Annotation](Annotation.md) - owl annotations. Not to be confused with annotations sensu GO
    * [Subset](Subset.md)
 * [TextualDiff](TextualDiff.md) - A summarizing of a change on a piece of text. This could be rendered in a number of different ways
 * [Transaction](Transaction.md) - A unified set of changes. Could be a single change, or the results of an ontology diff

### Mixins

 * [AddToSubset](AddToSubset.md) - placing an element inside a subset
 * [ChangeMixin](ChangeMixin.md) - root class for all change mixins
    * [AddToSubset](AddToSubset.md) - placing an element inside a subset
    * [Creation](Creation.md) - Creation of an element.
    * [Deletion](Deletion.md) - Removal of an element.
    * [Obsoletion](Obsoletion.md) - Obsoletion of an element deprecates usage of that element, but does not delete that element.
    * [RemoveFromSubset](RemoveFromSubset.md) - removing an element from a subset
    * [Unobsoletion](Unobsoletion.md) - Opposite operation of obsoletion. Rarely performed.
 * [Creation](Creation.md) - Creation of an element.
 * [Deletion](Deletion.md) - Removal of an element.
 * [Obsoletion](Obsoletion.md) - Obsoletion of an element deprecates usage of that element, but does not delete that element.
 * [RemoveFromSubset](RemoveFromSubset.md) - removing an element from a subset
 * [Unobsoletion](Unobsoletion.md) - Opposite operation of obsoletion. Rarely performed.

### Slots

 * [about](about.md) - The 'focus' entity on which the change operates
    * [edge change➞about](edge_change_about.md)
    * [node change➞about](node_change_about.md)
       * [node obsoletion with merge➞about](node_obsoletion_with_merge_about.md)
 * [acted on behalf of](acted_on_behalf_of.md)
 * [activity id](activity_id.md)
 * [annotation set](annotation_set.md)
 * [change description](change_description.md) - A string serialization of the change
    * [edge creation➞change description](edge_creation_change_description.md)
    * [edge deletion➞change description](edge_deletion_change_description.md)
    * [edge label change➞change description](edge_label_change_change_description.md)
    * [edge obsoletion➞change description](edge_obsoletion_change_description.md)
    * [node creation➞change description](node_creation_change_description.md)
    * [node deletion➞change description](node_deletion_change_description.md)
    * [node move➞change description](node_move_change_description.md)
       * [node deepening➞change description](node_deepening_change_description.md)
       * [node shallowing➞change description](node_shallowing_change_description.md)
    * [node obsoletion➞change description](node_obsoletion_change_description.md)
       * [node obsoletion with merge➞change description](node_obsoletion_with_merge_change_description.md)
       * [node obsoletion with split➞change description](node_obsoletion_with_split_change_description.md)
    * [node rename➞change description](node_rename_change_description.md)
    * [node unobsoletion➞change description](node_unobsoletion_change_description.md)
 * [change set](change_set.md)
 * [change type](change_type.md)
 * [consider](consider.md)
    * [node unobsoletion➞consider](node_unobsoletion_consider.md)
 * [count](count.md)
 * [edge label](edge_label.md)
 * [ended at time](ended_at_time.md)
 * [filler](filler.md)
 * [has textual diff](has_textual_diff.md)
 * [id](id.md) - CURIE or URI
 * [in subset](in_subset.md) - subset that the element is being placed inside.
    * [remove from subset➞in subset](remove_from_subset_in_subset.md) - subset that the element is being removed from
 * [name](name.md)
 * [new value](new_value.md) - The value of a property held in the old instance of the ontology
    * [node rename➞new value](node_rename_new_value.md)
 * [object](object.md)
 * [old value](old_value.md) - The value of a property held in the old instance of the ontology
    * [node rename➞old value](node_rename_old_value.md)
 * [property](property.md)
 * [property value set](property_value_set.md)
    * [change set summary statistic➞property value set](change_set_summary_statistic_property_value_set.md) - Summary statistic is grouped by these constraints
 * [replaced by](replaced_by.md)
    * [node unobsoletion➞replaced by](node_unobsoletion_replaced_by.md)
 * [started at time](started_at_time.md)
 * [subject](subject.md)
 * [target](target.md) - The secondary entity on which the change operates
    * [node obsoletion with merge➞target](node_obsoletion_with_merge_target.md)
    * [node obsoletion with split➞target](node_obsoletion_with_split_target.md)
 * [used](used.md)
 * [was associated with](was_associated_with.md)
 * [was generated by](was_generated_by.md)
 * [was informed by](was_informed_by.md)

### Types


#### Built in

 * **Bool**
 * **ElementIdentifier**
 * **NCName**
 * **NodeIdentifier**
 * **URI**
 * **URIorCURIE**
 * **XSDDate**
 * **XSDDateTime**
 * **XSDTime**
 * **float**
 * **int**
 * **str**

#### Defined

 * [Boolean](types/Boolean.md)  (**Bool**)  - A binary (true or false) value
 * [ChangeClassType](types/ChangeClassType.md)  ([Uriorcurie](types/Uriorcurie.md))  - CURIE for a class within this datamodel. E.g. ocl:NodeObsoletion
 * [Date](types/Date.md)  (**XSDDate**)  - a date (year, month and day) in an idealized calendar
 * [Datetime](types/Datetime.md)  (**XSDDateTime**)  - The combination of a date and time
 * [Double](types/Double.md)  (**float**)  - A real number that conforms to the xsd:double specification
 * [Float](types/Float.md)  (**float**)  - A real number that conforms to the xsd:float specification
 * [Integer](types/Integer.md)  (**int**)  - An integer
 * [Ncname](types/Ncname.md)  (**NCName**)  - Prefix part of CURIE
 * [Nodeidentifier](types/Nodeidentifier.md)  (**NodeIdentifier**)  - A URI, CURIE or BNODE that represents a node in a model.
 * [Objectidentifier](types/Objectidentifier.md)  (**ElementIdentifier**)  - A URI or CURIE that represents an object in the model.
 * [String](types/String.md)  (**str**)  - A character string
 * [Time](types/Time.md)  (**XSDTime**)  - A time object represents a (local) time of day, independent of any particular day
 * [Uri](types/Uri.md)  (**URI**)  - a complete URI
 * [Uriorcurie](types/Uriorcurie.md)  (**URIorCURIE**)  - a URI or a CURIE
