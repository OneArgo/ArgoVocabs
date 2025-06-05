# ArgoVocabs
A repository for the management of issues related to vocabularies managed by the Argo Data Management Team
The dashboard for ArgoVocabs ticket is : https://github.com/orgs/nvs-vocabs/projects/2

# Guidance for management of issues
1) Raise, describe, label and indicate an assignee of your issue
2) Discuss the issue along the thread of the ticket
3) Update label relevantly
4) Once an agreement has been reached summarize the agreement so that readers do not have to read the full thread back to know what to do
5) Publish action list in the form a ticking boxes with the responsible for each action (and add them as assignee so relevant people can filter on this to quickly get the list of the actions they have to do)
6) close the ticket when all the sub-actions are completely fulfilled (i.e. before "ticking an action", wait for the change to be visible in the operational flow. For instance, if you modify a table entry, wait for it to be accepted by NOC team, and effectively published in the table. This ensures potential final steps issues are not unnoticed).

# The importance of label
* Label are used for proper management of tickets and filtering for review, action follow-up, etc.
* Each ticket should be flagged with the appropriate label for good management and labeling evolves as discussion progress.
* Each label has a short description of its meaning.
* While everyone should label ticket, it is part of the responsibilities of the co-chair of the AVTT to regularly review and update ticket labeling.

# Standard process for releasing vocab, documentation and checker
* The update and release of the new collection is made "on the fly", following ticket requirements.
* When a new vocabulary collection is created, the documentation is updated accordingly (at the very least to indicate the new collection url).
* The release of new version of the documentation is made regularly (no formal schedule). New version documentation must be advertised through the *argo-dm@groups.wmo.int* mailing list.
    * Format_version evolves from version x.x to x.(x+1) or (x.1).0 when previous file in version x.x will not pass anymore the FileChecker with the envisioned change. It is good practice to make new metadata field optionnal, during a transition phase, which can last 1 to 3 years, before making them mandatory and hence increase the Format_version numbering). 
* Once the documentation is released, the checker is updated. New version of the file checker must be advertised through the *argo-dm@groups.wmo.int* mailing list.

# A few information on NVS updates
## Necessary inputs to request the creation of a new collection to NOC/BODC
The Vocab editors do not have the right to create new collections. This is only granted to NOC/BOSC. This is to avoid duplicate of similar collections when something already in place may be suitable for the purpose. 
Thus, to create a new collection, a request must be sent to NOC/BODC (Dani). This request must contain the following information:
 - Governance: who is the editor in charge of the table update
 - Collection Name
 - Description: description of the content of the collection
 - an excel or csv file containing the elements of the table: ID; preffered Label; Alternative Label (if relevant); Definition

## Mappings
Mappings are used to inform relationship between tables. For instance, inform all the sensor_models manufactured by one sensor_maker, or all the platform_types manufactures by one platform_maker, etc.
They are used by the FileChecker to ensure the consistency between these metadata fields in the Argo dataset.
The Vocab editors have the right to perform mappings. It is advised to ask NOC/BODC the appropriate mapping type before proceeding. Herebelow is an example of mapping file content submitted to NVS editor (bulk update option) between table R23 (platform_type) and R08 (intrument_type = platform_type + mounted CTD sensor type) and between R23 and R24 (platform_maker). BRD stands for broader, and MIN for MINIMUM
- R23, ALTO, BRD, R08, 873, I
- R23, HM2000, BRD, R08, 870, I
- R23, HM4000, BRD, R08, 881, I
- R23, XUANWU, BRD, R08, 882, I
- R23, HM4000, MIN, R24, QNLM, I

The Vocab editors can not delete mappings. If ever a correction was needed, the editor must ask NOC/BODC (Dani) to perform the deletion


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
|[R01](https://vocab.nerc.ac.uk/search_nvs/R01/) - DATA_TYPE|[vturpin](https://github.com/vturpin), [tcarval](https://github.com/tcarval), [MKrieger29](https://github.com/MKrieger29), [RomainCancouet](https://github.com/RomainCancouet)|
|[RR2](https://vocab.nerc.ac.uk/search_nvs/RR2/) - RT_QC_FLAG|[vturpin](https://github.com/vturpin), [tcarval](https://github.com/tcarval), [MKrieger29](https://github.com/MKrieger29), [RomainCancouet](https://github.com/RomainCancouet), [delphinedobler](https://github.com/delphinedobler)|
|[RD2](https://vocab.nerc.ac.uk/search_nvs/RD2/) - DM_QC_FLAG|[vturpin](https://github.com/vturpin), [tcarval](https://github.com/tcarval), [MKrieger29](https://github.com/MKrieger29), [RomainCancouet](https://github.com/RomainCancouet), [delphinedobler](https://github.com/delphinedobler)|
|[RP2](https://vocab.nerc.ac.uk/search_nvs/RP2/) - PROF_QC_FLAG|[vturpin](https://github.com/vturpin), [tcarval](https://github.com/tcarval), [MKrieger29](https://github.com/MKrieger29), [RomainCancouet](https://github.com/RomainCancouet)|
|[R03](https://vocab.nerc.ac.uk/search_nvs/R03/) - PARAMETER|[vturpin](https://github.com/vturpin), [tcarval](https://github.com/tcarval), [catsch](https://github.com/catsch), [apswong](https://github.com/apswong)|
|[R04](https://vocab.nerc.ac.uk/search_nvs/R04/) - DATA_CENTRE_CODES|[vturpin](https://github.com/vturpin), [tcarval](https://github.com/tcarval), [MKrieger29](https://github.com/MKrieger29), [RomainCancouet](https://github.com/RomainCancouet)|
|[R05](https://vocab.nerc.ac.uk/search_nvs/R05/) - POSITION_ACCURACY|[vturpin](https://github.com/vturpin), [tcarval](https://github.com/tcarval), [MKrieger29](https://github.com/MKrieger29), [RomainCancouet](https://github.com/RomainCancouet)|
|[R06](https://vocab.nerc.ac.uk/search_nvs/R06/) - DATA_STATE_INDICATOR|[vturpin](https://github.com/vturpin), [tcarval](https://github.com/tcarval), [MKrieger29](https://github.com/MKrieger29), [RomainCancouet](https://github.com/RomainCancouet)|
|[R07](https://vocab.nerc.ac.uk/search_nvs/R07/) - HISTORY_ACTION|[vturpin](https://github.com/vturpin), [tcarval](https://github.com/tcarval), [MKrieger29](https://github.com/MKrieger29), [RomainCancouet](https://github.com/RomainCancouet)|
|[R08](https://vocab.nerc.ac.uk/search_nvs/R08/) - ARGO_WMO_INST_TYPE|[vturpin](https://github.com/vturpin), [tcarval](https://github.com/tcarval), [MKrieger29](https://github.com/MKrieger29), [RomainCancouet](https://github.com/RomainCancouet)|
|[R09](https://vocab.nerc.ac.uk/search_nvs/R09/) - POSITIONING_SYSTEM|[vturpin](https://github.com/vturpin), [tcarval](https://github.com/tcarval), [MKrieger29](https://github.com/MKrieger29), [RomainCancouet](https://github.com/RomainCancouet)|
|[R10](https://vocab.nerc.ac.uk/search_nvs/R10/) - TRANS_SYSTEM|[vturpin](https://github.com/vturpin), [tcarval](https://github.com/tcarval), [MKrieger29](https://github.com/MKrieger29), [RomainCancouet](https://github.com/RomainCancouet)|
|[R11](https://vocab.nerc.ac.uk/search_nvs/R11/) - RTQC_TESTID|[vturpin](https://github.com/vturpin), [tcarval](https://github.com/tcarval), [MKrieger29](https://github.com/MKrieger29), [RomainCancouet](https://github.com/RomainCancouet), [delphinedobler](https://github.com/delphinedobler)|
|[R12](https://vocab.nerc.ac.uk/search_nvs/R12/) - HISTORY_STEP|[vturpin](https://github.com/vturpin), [tcarval](https://github.com/tcarval), [MKrieger29](https://github.com/MKrieger29), [RomainCancouet](https://github.com/RomainCancouet)|
|[R13](https://vocab.nerc.ac.uk/search_nvs/R13/) - OCEAN_CODE|[vturpin](https://github.com/vturpin), [tcarval](https://github.com/tcarval), [MKrieger29](https://github.com/MKrieger29), [RomainCancouet](https://github.com/RomainCancouet), [delphinedobler](https://github.com/delphinedobler)|
|[R14](https://vocab.nerc.ac.uk/search_nvs/R14/) - TECHNICAL_PARAMETER_NAME|[vturpin](https://github.com/vturpin), [tcarval](https://github.com/tcarval), [RomainCancouet](https://github.com/RomainCancouet)|
|[R18](https://vocab.nerc.ac.uk/search_nvs/R18/) - CONFIG_PARAMETER_NAME|[vturpin](https://github.com/vturpin), [tcarval](https://github.com/tcarval), [catsch](https://github.com/catsch), [RomainCancouet](https://github.com/RomainCancouet)|
|[R15](https://vocab.nerc.ac.uk/search_nvs/R15/) - MEASUREMENT_CODE_ID|[vturpin](https://github.com/vturpin), [tcarval](https://github.com/tcarval), [mscanderbeg](https://github.com/mscanderbeg)|
|[RMC](https://vocab.nerc.ac.uk/search_nvs/RMC/) - MEASUREMENT_CODE_CATEGORY|[vturpin](https://github.com/vturpin), [tcarval](https://github.com/tcarval), [mscanderbeg](https://github.com/mscanderbeg)|
|[RTV](https://vocab.nerc.ac.uk/search_nvs/RTV/) - CYCLE_TIMING_VARIABLE|[vturpin](https://github.com/vturpin), [tcarval](https://github.com/tcarval), [mscanderbeg](https://github.com/mscanderbeg)|
|[R16](https://vocab.nerc.ac.uk/search_nvs/R16/) - VERTICAL_SAMPLING_SCHEME|[vturpin](https://github.com/vturpin), [tcarval](https://github.com/tcarval), [MKrieger29](https://github.com/MKrieger29), [RomainCancouet](https://github.com/RomainCancouet)|
|[R19](https://vocab.nerc.ac.uk/search_nvs/R19/) - STATUS|[vturpin](https://github.com/vturpin), [tcarval](https://github.com/tcarval), [MKrieger29](https://github.com/MKrieger29), [RomainCancouet](https://github.com/RomainCancouet)|
|[R20](https://vocab.nerc.ac.uk/search_nvs/R20/) - GROUNDED|[vturpin](https://github.com/vturpin), [tcarval](https://github.com/tcarval), [MKrieger29](https://github.com/MKrieger29), [RomainCancouet](https://github.com/RomainCancouet)|
|[R21](https://vocab.nerc.ac.uk/search_nvs/R21/) - REPRESENTATIVE_PARK_PRESSURE_STATUS|[vturpin](https://github.com/vturpin), [tcarval](https://github.com/tcarval), [MKrieger29](https://github.com/MKrieger29), [RomainCancouet](https://github.com/RomainCancouet)|
|[R22](https://vocab.nerc.ac.uk/search_nvs/R22/) - PLATFORM_FAMILY|[vturpin](https://github.com/vturpin), [tcarval](https://github.com/tcarval), [MKrieger29](https://github.com/MKrieger29), [RomainCancouet](https://github.com/RomainCancouet), [delphinedobler](https://github.com/delphinedobler)|
|[R23](https://vocab.nerc.ac.uk/search_nvs/R23/) - PLATFORM_TYPE|[vturpin](https://github.com/vturpin), [tcarval](https://github.com/tcarval), [MKrieger29](https://github.com/MKrieger29), [RomainCancouet](https://github.com/RomainCancouet), [delphinedobler](https://github.com/delphinedobler)|
|[R24](https://vocab.nerc.ac.uk/search_nvs/R24/) - PLATFORM_MAKER|[vturpin](https://github.com/vturpin), [tcarval](https://github.com/tcarval), [MKrieger29](https://github.com/MKrieger29), [RomainCancouet](https://github.com/RomainCancouet), [delphinedobler](https://github.com/delphinedobler)|
|[R25](https://vocab.nerc.ac.uk/search_nvs/R25/) - SENSOR|[vturpin](https://github.com/vturpin), [tcarval](https://github.com/tcarval), [MKrieger29](https://github.com/MKrieger29), [RomainCancouet](https://github.com/RomainCancouet), [delphinedobler](https://github.com/delphinedobler)|
|[R26](https://vocab.nerc.ac.uk/search_nvs/R26/) - SENSOR_MAKER|[vturpin](https://github.com/vturpin), [tcarval](https://github.com/tcarval), [MKrieger29](https://github.com/MKrieger29), [RomainCancouet](https://github.com/RomainCancouet), [delphinedobler](https://github.com/delphinedobler)|
|[R27](https://vocab.nerc.ac.uk/search_nvs/R27/) - SENSOR_MODEL|[vturpin](https://github.com/vturpin), [tcarval](https://github.com/tcarval), [MKrieger29](https://github.com/MKrieger29), [RomainCancouet](https://github.com/RomainCancouet), [delphinedobler](https://github.com/delphinedobler)|
|[R28](https://vocab.nerc.ac.uk/search_nvs/R28/) - CONTROLLER_BOARD_TYPE|[vturpin](https://github.com/vturpin), [tcarval](https://github.com/tcarval), [MKrieger29](https://github.com/MKrieger29), [RomainCancouet](https://github.com/RomainCancouet), [ClareBellingham](https://github.com/ClareBellingham)|
|[R40](https://vocab.nerc.ac.uk/search_nvs/R40/) - PI_NAME|[vturpin](https://github.com/vturpin), [tcarval](https://github.com/tcarval), [MKrieger29](https://github.com/MKrieger29), [RomainCancouet](https://github.com/RomainCancouet), [roswri](https://github.com/roswri), [delphinedobler](https://github.com/delphinedobler)|
