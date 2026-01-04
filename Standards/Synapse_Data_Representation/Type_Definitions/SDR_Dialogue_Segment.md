## SDR_Dialogue_Segment

**SDR Type Name:** [[SDR_Dialogue_Segment]]

**Description:** Represents a segment of dialogue spoken by a character, including delivery notes.

**Fields:**

| Field Name                        | Data Type                  | Multiplicity | Description                                                                                                    |
| :-------------------------------- | :------------------------- | :----------- | :------------------------------------------------------------------------------------------------------------- |
| `Dialogue_Segment_UID`            | `Synapse_UID`              | `1`          | Unique identifier for this dialogue segment.                                                                   |
| `Scene_Context_SDR_UID`           | `Synapse_UID`              | `1`          | UID of the `[[SDR_Scene_Description]]` this dialogue occurs in.                                                 |
| `Sequence_In_Scene`               | `Synapse_Integer`          | `1`          | Order of this dialogue segment within the scene.                                                               |
| `Speaker_Character_Profile_UID`   | `Synapse_UID`              | `1`          | UID of the `[[SDR_Character_Profile]]` for the character speaking.                                              |
| `Addressee_Character_Profile_UIDs`| `List<Synapse_UID>`        | `0..*`       | List of UIDs of `[[SDR_Character_Profile]]`s for character(s) being directly addressed. If empty, could be internal thought or addressed to a general audience. |
| `Dialogue_Text_UID`               | `Synapse_UID`              | `1`          | UID of an `[[SDR_Text_Block]]` containing the spoken words.                                                      |
| `Parenthetical_Delivery_Notes_UID`| `Synapse_UID`              | `0..1`       | UID of an `[[SDR_Text_Block]]` for parenthetical notes (e.g., "whispering", "sarcastically", "to herself").        |
| `Emotional_Tone_UID`              | `Synapse_UID`              | `0..1`       | UID of an `[[SDR_Vocabulary_Term]]` or `[[SDR_Qualitative_Assessment]]` indicating the emotional tone.           |
| `Subtext_Description_UID`         | `Synapse_UID`              | `0..1`       | UID of an `[[SDR_Text_Block]]` describing any underlying meaning or subtext.                                   |
| `Dialogue_Metadata`               | `[[SDR_Metadata_Block]]`   | `0..1`       | UID of an `[[SDR_Metadata_Block]]` for this dialogue segment.                                                  |