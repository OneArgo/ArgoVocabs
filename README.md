# ArgoVocabs
A repository for the management of issues related to vocabularies managed by the Argo Data Management Team
The dashboard for ArgoVocabs ticket is : https://github.com/orgs/nvs-vocabs/projects/2

# Guidance for management of issues
1) Raise, describe, label and assigne your issue
2) Discuss the issue along the thread of the ticket
3) Update label relevantly
4) Once an agreement has been reached summarize the agreement so that readers do not have to read the full thread back to know what to do
5) Publish action list in the form a ticking boxes with the responsible for each action
6) close the ticket when all the sub-actions are fulfilled.

# The importance of label
* Label are used for proper management of tickets.
* Each ticket should be flagged with the appropriate label for good management and labeling evolve as discussion progress.
* Each label has a short description of its meaning.
* While everyone should label ticket, it is part of the responsibilities of the co-chair of the AVTT to regularly review and update ticket labeling.

# Standard process for releasing vocab, documentation and checker
* The update and release of the new collection is made "on the fly", following ticket requierments.
* Once the collection is created, the documentation is updated accordingly.
* The release of new version of the documentation is made regularly, there is no scheddule for new format version. New version documentation must be advertised through the argo-dm@groups.wmo.int mailing list.
* Once the documentation is released, the checker will be updated. New version file checker must be advertised through the argo-dm@groups.wmo.int mailing list.
* The release of new version of the documentation is made regularly, there is no formal scheddule for new format version.
* The release of new version of the file checker is made regularly, following documentation update. Similarly, there is no formal scheddule for new checker version.

# Resources: M2M access to the NVS via API

<p>For machine to machine (M2M) access to the Argo Vocabularies on the NVS, the <strong>NVS SPARQL endpoint</strong> can be used.</p>
<p>General information on the NVS SPARQL endpoint can be found on the NVS website: https://vocab.nerc.ac.uk/sparql/</p>
<p>SPARQL queries can be integrated into code written in other programming languages (Python, Matlab etc.).</p>

> For a basic example, please see the "m2m_NVS_sparql.ipynb" file linked to this repo.
>> To test, open the file into a Jupyter Notebook; edit lines marked by '# Switch' to select either prefLabel/altLabel, and point to specific Argo vocabularies by inserting its name (e.g. 'R03') where the line is marked by '# Edit'.




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
