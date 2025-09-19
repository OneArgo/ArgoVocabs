# ArgoVocabs
A repository for the management of issues related to vocabularies managed by the Argo Data Management Team
The dashboard for ArgoVocabs ticket is : https://github.com/orgs/OneArgo/projects/4

# Guidance for management of issues
1) Raise, describe, label and indicate an assignee of your issue
2) Discuss the issue along the thread of the ticket
3) Update label relevantly (targetted table(s), mappings, documentation relevance, File checker, discussion is needed at the level of AVTT, ADMT approval is requested, etc.)
4) On the right panel, add the project "AVTT issues Management" and select the status "to do", "in progress","avtt approval","done": this ensures it appears correctly on the dashboard https://github.com/orgs/OneArgo/projects/4
5) Once an agreement has been reached summarize the agreement so that readers do not have to read the full thread back to know what to do
6) Publish an action list in the form a ticking boxes with the responsible for each action (and add them as assignee so relevant people can filter on this to quickly get the list of the actions they have to do)
7) Once assignee has started to effectively work on the ticket, label the ticket as **"on-going"**, and move the project status to "in progress"
8) Label the ticket as **"done"** when all the sub-actions are completely fulfilled (i.e. before "ticking an action", wait for the change to be visible in the operational flow. For instance, if you modify a table entry, wait for it to be accepted by NOC team, and effectively published in the table. This ensures potential final steps issues are not unnoticed).  
9) The list of **"done"** tickets will be reviewed at the following AVTT meeting for closure. Move the project status to "done" => This will automatically close the ticket.

N.B.: there is some duplications between status (for the project) and labels. For the moment, we keep this duplication live because it is easy to filter on label in the main issue page, whereas status helps in ordering the dashboard nicely. This may be adapted later on.

## Special case when issues comes from an ADMT action
Sometimes, vocabulary discussions stem from a point raised at the ADMT. When this is the case, the chairs from the ADMT repository will attached the "AVTT issues management" project to OneArgo/ADMT action. Thus the action appears on the left hand side of the dashboard. It is the responsibility of the AVTT chair(s) to:
- create as many sub-actions as necessary in the OneArgo/ArgoVocabs repository,
- add the parent ADMT action to them (using relationship in the right panel; tip you need to use <- symbol and type OneArgo/ADMT to get access to the ADMT actions),
- change in the parent ADMT action, the status in the "AVTT issues management" project from "no status" to "ADMT repository action": this means the above steps have been performed.

The ADMT action has in general a wider scope than the sub-AVTT actions and can enclose more than vocabulary related sub-actions. Once the AVTT sub-actions are completed, the AVTT chair(s) report(s) within the ADMT action the completion of them.

# The importance of label
* Label are used for proper management of tickets and filtering for review, action follow-up, etc.
* Each ticket should be flagged with the appropriate label for good management and labeling evolves as discussion progress.
* Each label has a short description of its meaning.
* While everyone should label ticket, it is part of the responsibilities of the co-chair of the AVTT to regularly review and update ticket labeling.

# Standard process for releasing vocab, documentation and checker
* The update and release of the new collection is made "on the fly", following ticket requirements.
* When a new vocabulary collection is created, the documentation is updated accordingly (at the very least to indicate the new collection url).
* When a new metadata field is created, it is good practice to first make this new metadata field optionnal. It should remain optionnal during a transition phase, which can usually last from 1 to 3 years, allowing the time necessary for DACs to perform the associated updates in their processing chain. Then, the field can be switched to mandatory and the _Format_version_ number is increased.
* The release of new version of the documentation is made regularly (no formal schedule). New version documentation must be advertised through the *argo-dm@groups.wmo.int* mailing list.  
* Once the documentation is released, the checker is updated. New version of the file checker must be advertised through the *argo-dm@groups.wmo.int* mailing list.

# A few information on NVS updates
## Necessary inputs to request the creation of a new collection to NOC/BODC
The Vocab editors do not have the right to create new collections. This is only granted to NOC/BODC. This is to avoid duplication of similar collections when something already in place may be suitable for the purpose. 
Thus, to create a new collection, a request must be sent to NOC/BODC (Dani). This request must contain the following information:
 - Governance: who is the editor in charge of the table update
 - Collection Name
 - Description: description of the content of the collection
 - An excel or csv file containing the elements of the table: ID; preffered Label; Alternative Label (if relevant); Definition

## Mappings
Mappings are used to inform relationship between concepts. For instance, inform all the sensor_models manufactured by one sensor_maker, or all the platform_types manufactures by one platform_maker, etc.
They are used by the FileChecker to ensure the consistency between these metadata fields in the Argo dataset.
The Vocab editors have the right to insert mappings. It is advised to ask NOC/BODC the appropriate mapping type before proceeding.

### __How to read a mapping ?__ 

Mappings are relationships between \[NVS\] concepts. There is a "subject", a "predicate" and an "object". "predicate" indicates the relationship type between the "subject" and the "object". There are two kinds of predicates: "__narrower/broader__" when there is a __hierarchy__ between the subject and the object, and "__related__" when the subject is related to the object __without strict hierarchy__. <br>
An example mapping can be found here https://vocab.nerc.ac.uk/mapping/I/1700614/. In this example, the "subject" https://vocab.nerc.ac.uk/collection/R27/current/AANDERAA_OPTODE_3830/ has a relationship to a "broader" concept (the "object"): http://vocab.nerc.ac.uk/collection/R26/current/AANDERAA/. The manufacturer is a broader concept than the more granular sensor designed and developed by the manufacturer.<br>
Mappings can also be seen by clicking on the individual URIs for each concept. For instance, in https://vocab.nerc.ac.uk/collection/R27/current/AANDERAA_OPTODE_3830/, the optode (subject of the relationship) has a relationship to the broader concept ‘Aanderaa’, the manufacturer.<br>

It is important to note that the inverse mapping/relationship must also exist for each of these, so if there is a ‘broader’ mapping in one direction between subject and object, a ‘narrower’ mapping must also exist in the other direction between object and subject. Otherwise the mappings won’t resolve on the NVS. For ‘related’, the inverse mapping is also ‘related’. By clicking on the ‘object’ in the above example: http://vocab.nerc.ac.uk/collection/R26/current/AANDERAA/, ‘Aanderaa’ is now the subject, and the relationship is now ‘narrower’ as the manufacturer is related to all the narrower, individual sensors.

### __How to create a mapping ?__

When mappings are loaded via the vocab editor, you only need to load one set of mappings in one direction however (i.e. only the broader ones, or only the narrower ones etc). This is because the inverse mappings are automatically generated on a trigger when we process what you have loaded.<br>

For "__broader/narrower__" relationship, the "__BRD__" predicate code is used, for "__related__" relationship, the "__MIN__" predicate code is used (minor match).<br>

Care must be taken as subject and object are reversed in the file, which can create confusion. Columns are as follows:<br>
- object_NVS_table, object_concept_id, predicate_code, subject_NVS_table, subject_concept_id, modification_type (I for Insertion)

Below is a concrete example of a mapping file's content submitted to the NVS editor (bulk update option) between table R23 (platform_type) and R08 (intrument_type = platform_type + mounted CTD sensor type), and between table R27 (sensor_model) and table R25 (sensor):<br>
- R23, ALTO, BRD, R08, 873, I
- R27, AANDERAA_OPTODE , MIN, R25, OPTODE_DOXY , I

The Vocab editors cannot delete mappings. If ever a correction was needed, the editor must ask NOC/BODC (Dani) to perform the deletion


# Resources: M2M access to the NVS via API

<p>For machine to machine (M2M) access to the Argo Vocabularies on the NVS, the <strong>NVS SPARQL endpoint</strong> can be used.</p>
<p>General information on the NVS SPARQL endpoint can be found on the NVS website: https://vocab.nerc.ac.uk/sparql/</p>
<p>SPARQL queries can be integrated into code written in other programming languages (Python, Matlab etc.).</p>

> For a basic example, please see the "m2m_NVS_sparql.ipynb" file linked to this repo.
> To test, open the file into a Jupyter Notebook; edit lines marked by '# Switch' to select either prefLabel/altLabel, and point to specific Argo vocabularies by inserting its name (e.g. 'R03') where the line is marked by '# Edit'.


# Editors list
Editors should be registered as editors in the NVS. Here : https://vocab.nerc.ac.uk/editor/. 
NVS will then allow editors to edit new terms of the corresponding collections.

|Argo NVS Collections|Editors|
|---|---|
|[R01](https://vocab.nerc.ac.uk/search_nvs/R01/) - DATA_TYPE|[vturpin](https://github.com/vturpin), [tcarval](https://github.com/tcarval), [MKrieger29](https://github.com/MKrieger29), [RomainCancouet](https://github.com/RomainCancouet), [delphinedobler](https://github.com/delphinedobler)|
|[RR2](https://vocab.nerc.ac.uk/search_nvs/RR2/) - RT_QC_FLAG|[vturpin](https://github.com/vturpin), [tcarval](https://github.com/tcarval), [MKrieger29](https://github.com/MKrieger29), [RomainCancouet](https://github.com/RomainCancouet), [delphinedobler](https://github.com/delphinedobler)|
|[RD2](https://vocab.nerc.ac.uk/search_nvs/RD2/) - DM_QC_FLAG|[vturpin](https://github.com/vturpin), [tcarval](https://github.com/tcarval), [MKrieger29](https://github.com/MKrieger29), [RomainCancouet](https://github.com/RomainCancouet), [delphinedobler](https://github.com/delphinedobler)|
|[RP2](https://vocab.nerc.ac.uk/search_nvs/RP2/) - PROF_QC_FLAG|[vturpin](https://github.com/vturpin), [tcarval](https://github.com/tcarval), [MKrieger29](https://github.com/MKrieger29), [RomainCancouet](https://github.com/RomainCancouet), [delphinedobler](https://github.com/delphinedobler)|
|[R03](https://vocab.nerc.ac.uk/search_nvs/R03/) - PARAMETER|[vturpin](https://github.com/vturpin), [tcarval](https://github.com/tcarval), [catsch](https://github.com/catsch), [apswong](https://github.com/apswong), [delphinedobler](https://github.com/delphinedobler)|
|[R04](https://vocab.nerc.ac.uk/search_nvs/R04/) - DATA_CENTRE_CODES|[vturpin](https://github.com/vturpin), [tcarval](https://github.com/tcarval), [MKrieger29](https://github.com/MKrieger29), [RomainCancouet](https://github.com/RomainCancouet), [delphinedobler](https://github.com/delphinedobler)|
|[R05](https://vocab.nerc.ac.uk/search_nvs/R05/) - POSITION_ACCURACY|[vturpin](https://github.com/vturpin), [tcarval](https://github.com/tcarval), [MKrieger29](https://github.com/MKrieger29), [RomainCancouet](https://github.com/RomainCancouet), [delphinedobler](https://github.com/delphinedobler)|
|[R06](https://vocab.nerc.ac.uk/search_nvs/R06/) - DATA_STATE_INDICATOR|[vturpin](https://github.com/vturpin), [tcarval](https://github.com/tcarval), [MKrieger29](https://github.com/MKrieger29), [RomainCancouet](https://github.com/RomainCancouet), [delphinedobler](https://github.com/delphinedobler)|
|[R07](https://vocab.nerc.ac.uk/search_nvs/R07/) - HISTORY_ACTION|[vturpin](https://github.com/vturpin), [tcarval](https://github.com/tcarval), [MKrieger29](https://github.com/MKrieger29), [RomainCancouet](https://github.com/RomainCancouet), [delphinedobler](https://github.com/delphinedobler)|
|[R08](https://vocab.nerc.ac.uk/search_nvs/R08/) - ARGO_WMO_INST_TYPE|[vturpin](https://github.com/vturpin), [tcarval](https://github.com/tcarval), [MKrieger29](https://github.com/MKrieger29), [RomainCancouet](https://github.com/RomainCancouet), [delphinedobler](https://github.com/delphinedobler)|
|[R09](https://vocab.nerc.ac.uk/search_nvs/R09/) - POSITIONING_SYSTEM|[vturpin](https://github.com/vturpin), [tcarval](https://github.com/tcarval), [MKrieger29](https://github.com/MKrieger29), [RomainCancouet](https://github.com/RomainCancouet), [delphinedobler](https://github.com/delphinedobler)|
|[R10](https://vocab.nerc.ac.uk/search_nvs/R10/) - TRANS_SYSTEM|[vturpin](https://github.com/vturpin), [tcarval](https://github.com/tcarval), [MKrieger29](https://github.com/MKrieger29), [RomainCancouet](https://github.com/RomainCancouet), [delphinedobler](https://github.com/delphinedobler)|
|[R11](https://vocab.nerc.ac.uk/search_nvs/R11/) - RTQC_TESTID|[vturpin](https://github.com/vturpin), [tcarval](https://github.com/tcarval), [MKrieger29](https://github.com/MKrieger29), [RomainCancouet](https://github.com/RomainCancouet), [delphinedobler](https://github.com/delphinedobler)|
|[R12](https://vocab.nerc.ac.uk/search_nvs/R12/) - HISTORY_STEP|[vturpin](https://github.com/vturpin), [tcarval](https://github.com/tcarval), [MKrieger29](https://github.com/MKrieger29), [RomainCancouet](https://github.com/RomainCancouet), [delphinedobler](https://github.com/delphinedobler)|
|[R13](https://vocab.nerc.ac.uk/search_nvs/R13/) - OCEAN_CODE|[vturpin](https://github.com/vturpin), [tcarval](https://github.com/tcarval), [MKrieger29](https://github.com/MKrieger29), [RomainCancouet](https://github.com/RomainCancouet), [delphinedobler](https://github.com/delphinedobler)|
|[R14](https://vocab.nerc.ac.uk/search_nvs/R14/) - TECHNICAL_PARAMETER_NAME|[vturpin](https://github.com/vturpin), [tcarval](https://github.com/tcarval), [RomainCancouet](https://github.com/RomainCancouet), [delphinedobler](https://github.com/delphinedobler)|
|[R18](https://vocab.nerc.ac.uk/search_nvs/R18/) - CONFIG_PARAMETER_NAME|[vturpin](https://github.com/vturpin), [tcarval](https://github.com/tcarval), [catsch](https://github.com/catsch), [RomainCancouet](https://github.com/RomainCancouet), [delphinedobler](https://github.com/delphinedobler)|
|[R15](https://vocab.nerc.ac.uk/search_nvs/R15/) - MEASUREMENT_CODE_ID|[vturpin](https://github.com/vturpin), [tcarval](https://github.com/tcarval), [mscanderbeg](https://github.com/mscanderbeg), [delphinedobler](https://github.com/delphinedobler)|
|[RMC](https://vocab.nerc.ac.uk/search_nvs/RMC/) - MEASUREMENT_CODE_CATEGORY|[vturpin](https://github.com/vturpin), [tcarval](https://github.com/tcarval), [mscanderbeg](https://github.com/mscanderbeg), [delphinedobler](https://github.com/delphinedobler)|
|[RTV](https://vocab.nerc.ac.uk/search_nvs/RTV/) - CYCLE_TIMING_VARIABLE|[vturpin](https://github.com/vturpin), [tcarval](https://github.com/tcarval), [mscanderbeg](https://github.com/mscanderbeg), [delphinedobler](https://github.com/delphinedobler)|
|[R16](https://vocab.nerc.ac.uk/search_nvs/R16/) - VERTICAL_SAMPLING_SCHEME|[vturpin](https://github.com/vturpin), [tcarval](https://github.com/tcarval), [MKrieger29](https://github.com/MKrieger29), [RomainCancouet](https://github.com/RomainCancouet), [delphinedobler](https://github.com/delphinedobler)|
|[R19](https://vocab.nerc.ac.uk/search_nvs/R19/) - STATUS|[vturpin](https://github.com/vturpin), [tcarval](https://github.com/tcarval), [MKrieger29](https://github.com/MKrieger29), [RomainCancouet](https://github.com/RomainCancouet), [delphinedobler](https://github.com/delphinedobler)|
|[R20](https://vocab.nerc.ac.uk/search_nvs/R20/) - GROUNDED|[vturpin](https://github.com/vturpin), [tcarval](https://github.com/tcarval), [MKrieger29](https://github.com/MKrieger29), [RomainCancouet](https://github.com/RomainCancouet), [delphinedobler](https://github.com/delphinedobler)|
|[R21](https://vocab.nerc.ac.uk/search_nvs/R21/) - REPRESENTATIVE_PARK_PRESSURE_STATUS|[vturpin](https://github.com/vturpin), [tcarval](https://github.com/tcarval), [MKrieger29](https://github.com/MKrieger29), [RomainCancouet](https://github.com/RomainCancouet), [delphinedobler](https://github.com/delphinedobler)|
|[R22](https://vocab.nerc.ac.uk/search_nvs/R22/) - PLATFORM_FAMILY|[vturpin](https://github.com/vturpin), [tcarval](https://github.com/tcarval), [MKrieger29](https://github.com/MKrieger29), [RomainCancouet](https://github.com/RomainCancouet), [delphinedobler](https://github.com/delphinedobler)|
|[R23](https://vocab.nerc.ac.uk/search_nvs/R23/) - PLATFORM_TYPE|[vturpin](https://github.com/vturpin), [tcarval](https://github.com/tcarval), [MKrieger29](https://github.com/MKrieger29), [RomainCancouet](https://github.com/RomainCancouet), [delphinedobler](https://github.com/delphinedobler)|
|[R24](https://vocab.nerc.ac.uk/search_nvs/R24/) - PLATFORM_MAKER|[vturpin](https://github.com/vturpin), [tcarval](https://github.com/tcarval), [MKrieger29](https://github.com/MKrieger29), [RomainCancouet](https://github.com/RomainCancouet), [delphinedobler](https://github.com/delphinedobler)|
|[R25](https://vocab.nerc.ac.uk/search_nvs/R25/) - SENSOR|[vturpin](https://github.com/vturpin), [tcarval](https://github.com/tcarval), [MKrieger29](https://github.com/MKrieger29), [RomainCancouet](https://github.com/RomainCancouet), [delphinedobler](https://github.com/delphinedobler)|
|[R26](https://vocab.nerc.ac.uk/search_nvs/R26/) - SENSOR_MAKER|[vturpin](https://github.com/vturpin), [tcarval](https://github.com/tcarval), [MKrieger29](https://github.com/MKrieger29), [RomainCancouet](https://github.com/RomainCancouet), [delphinedobler](https://github.com/delphinedobler)|
|[R27](https://vocab.nerc.ac.uk/search_nvs/R27/) - SENSOR_MODEL|[vturpin](https://github.com/vturpin), [tcarval](https://github.com/tcarval), [MKrieger29](https://github.com/MKrieger29), [RomainCancouet](https://github.com/RomainCancouet), [delphinedobler](https://github.com/delphinedobler)|
|[R28](https://vocab.nerc.ac.uk/search_nvs/R28/) - CONTROLLER_BOARD_TYPE|[vturpin](https://github.com/vturpin), [tcarval](https://github.com/tcarval), [MKrieger29](https://github.com/MKrieger29), [RomainCancouet](https://github.com/RomainCancouet), [ClareBellingham](https://github.com/ClareBellingham), [delphinedobler](https://github.com/delphinedobler)|
|[R40](https://vocab.nerc.ac.uk/search_nvs/R40/) - PI_NAME|[vturpin](https://github.com/vturpin), [tcarval](https://github.com/tcarval), [MKrieger29](https://github.com/MKrieger29), [RomainCancouet](https://github.com/RomainCancouet), [roswri](https://github.com/roswri), [delphinedobler](https://github.com/delphinedobler)|
