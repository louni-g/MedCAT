### Overview of the CSV Fields
If a concept has mutliple names it can appear in multiple rows, each time with the same `CID` but with a different name. In this case it is recommended that only the first appearance contains any Optional fields while everything else only the required fields. But this is only recommended to reduce the size of the CSV - it has ~zero impact on everything else.


#### Required 
`CUI` - str/int - The ID of the concept (in UMLS this would be a CUI, is snomed a S-code, but it can be any unique string or int).
`name` - the name of this concept (can be an alias).

#### Optional
`ontology` - from where is this concept coming (e.g. SNOMED/UMLS or whatever you want).
`name_status` - can be `['P', 'N', 'A']`. `P` - this name is the preffered name of this concept and when we find it in text in >95% pf cases it links to this concept. `N` - this name links to this concept in <50% of cases. `A` - I've no idea how often this name links, let MedCAT decide this automatically. Whenever possible please try to assing this value, it is very important. 
`semantic_type_id` - ID of the semantic type for this concept (sematic type is to some extent equivalent to `group`, in other words you can use it as such).
`semantic_type_name` - Fully qualified naem for the sematic type of this concept
`description` - Description of this concept, if multiple rows are associated to the same concept then only one should contain the description (mainly because of the size).