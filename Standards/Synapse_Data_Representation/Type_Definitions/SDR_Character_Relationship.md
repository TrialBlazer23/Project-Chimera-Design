## SDR_Character_Relationship

**SDR Type Name:** [[SDR_Character_Relationship]]

**Description:** Defines the nature of a relationship between two characters within the narrative. Used by `[[SDR_Character_Profile]]`.

**Fields:**

| Field Name                     | Data Type                  | Multiplicity | Description                                                                                                                                |
| :----------------------------- | :------------------------- | :----------- | :----------------------------------------------------------------------------------------------------------------------------------------- |
| `Character_Relationship_UID`   | `Synapse_UID`              | `1`          | Unique identifier for this specific character relationship instance.                                                                       |
| `Character_One_Profile_UID`    | `Synapse_UID`              | `1`          | UID of the `[[SDR_Character_Profile]]` for the first character in the relationship.                                                         |
| `Character_Two_Profile_UID`    | `Synapse_UID`              | `1`          | UID of the `[[SDR_Character_Profile]]` for the second character in the relationship.                                                        |
| `Relationship_Type_UID`        | `Synapse_UID`              | `1`          | UID of an `[[SDR_Vocabulary_Term]]` describing the primary nature of their relationship (e.g., "Family_Sibling", "Friend_Close", "Professional_Colleague", "Romantic_Partner", "Antagonist_Nemesis"). |
| `Relationship_Description_UID` | `Synapse_UID`              | `0..1`       | UID of an `[[SDR_Text_Block]]` providing a more nuanced description of their dynamic or history.                                           |
| `Relationship_Strength_UID`    | `Synapse_UID`              | `0..1`       | UID of an `[[SDR_Qualitative_Assessment]]` or `[[SDR_Confidence_Score_Item]]` indicating the strength or intensity of the relationship.     |
| `Relationship_Status_UID`      | `Synapse_UID`              | `0..1`       | UID of an `[[SDR_Vocabulary_Term]]` indicating current status (e.g., "Active", "Strained", "Broken", "Developing").                          |
| `Start_Event_In_Narrative_UID` | `Synapse_UID`              | `0..1`       | UID of an `[[SDR_Plot_Point]]` or `[[SDR_Text_Block]]` describing when/how their relationship began in the context of the story.          |
| `Key_Moments_UIDs`             | `List<Synapse_UID>`        | `0..*`       | List of UIDs pointing to `[[SDR_Plot_Point]]`s significant to their relationship.                                                          |
| `Character_Relationship_Metadata`| `[[SDR_Metadata_Block]]` | `0..1`       | UID of an `[[SDR_Metadata_Block]]` for this character relationship.                                                                        |