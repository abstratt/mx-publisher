### Comparing the metamodels of Mendix and UML/TextUML/Cloudfier

#### Activities vs. Microflows

Activities (UML) and microflows (Mendix) are quite similar, and provide the basic block of behavior that you can attach to models. 

#### Actions

Both UML and Mendix have actions, and they seem quite similar conceptually, even if the actual actions are different.

##### Object actions

Sources:
- Mendix [documentation for object actions](https://world.mendix.com/display/refguide6/Object+Activities).

| Feature         | UML                                                            | Mendix                            | Notes                                                                      |
|-----------------|----------------------------------------------------------------|-----------------------------------|----------------------------------------------------------------------------|
| object creation | CreateObject                                                   | CreateObject                      | Mendix: can initialize values on creation                                  |
| object deletion | DestroyObject                                                  | DeleteObject(s)                   | Mendix: can delete multiple objects at once                                |
| object updating | Add/Remove/CleanStructuralFeatureValueAction Create / DestroyLinkAction | ChangeObject                      | Mendix: meant for existing objects UML: new and existing                   |
| casting         |                                                                | CastObject                        | TextUML: StructuredActivityNode marked w/ «Cast»                           |
| traversal       | ReadLinkAction                                                 | Retrieve (association)            |                                                                            |
| retrieval       | ReadExtentAction (all instances)                               | Retrieve (from DB)                | Mendix: one, all, block TextUML: see collection actions                    |
| transactions    | out of scope                                                   | CommitObject(s) RollbackObject(s) | Cloudfier: commit happens at end of block (or rollback, in case of error)  |

##### Collection actions

* TextUML/Cloudfier: see [mdd_collections.tuml](https://github.com/abstratt/textuml/blob/master/plugins/com.abstratt.mdd.core/models/libraries/mdd_collections.tuml)
* Mendix: see [documentation for list actions](https://world.mendix.com/display/refguide6/List+Activities).

