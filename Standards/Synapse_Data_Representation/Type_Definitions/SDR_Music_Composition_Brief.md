## SDR_Music_Composition_Brief

**SDR Type Name:** [[SDR_Music_Composition_Brief]]

**Description:** A brief for the Visionary to compose thematic music for a character, scene, location, or overall narrative mood.

**Fields:**

| Field Name                       | Data Type                         | Multiplicity | Description                                                                                                                                   |
| :------------------------------- | :-------------------------------- | :----------- | :-------------------------------------------------------------------------------------------------------------------------------------------- |
| `Music_Composition_Brief_UID`    | `Synapse_UID`                     | `1`          | Unique identifier for this music composition brief.                                                                                           |
| `Composition_Title_Or_Purpose_UID`| `Synapse_UID`                    | `1`          | UID of an `[[SDR_Text_Block]]` describing the title or purpose (e.g., "HeroCharacterTheme", "FinalBattleScore", "AmbientExplorationMusic").  |
| `Associated_Narrative_Element_UID`| `Synapse_UID`                    | `0..1`       | UID of an `[[SDR_Scene_Description]]`, `[[SDR_Character_Profile]]`, or `[[SDR_Story_Arc]]` this music is primarily associated with.         |
| `Genre_Style_Suggestions_UIDs`   | `List<Synapse_UID>`               | `0..*`       | List of UIDs, each pointing to an `[[SDR_Vocabulary_Term]]` or `[[SDR_Text_Block]]` suggesting musical genres/styles (e.g., "OrchestralEpic", "ElectronicAmbient", "FolkMelody"). |
| `Tempo_Description_UID`          | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Text_Block]]` or `[[SDR_Vocabulary_Term]]` describing desired tempo (e.g., "SlowAndSolemn", "FastPacedAction", "Approx120BPM"). |
| `Key_Modality_Suggestions_UID`   | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Text_Block]]` or `[[SDR_Vocabulary_Term]]` suggesting musical key or modality (e.g., "CMinor", "DorianMode", "Atonal").     |
| `Instrumentation_Palette_UIDs`   | `List<Synapse_UID>`               | `0..*`       | List of UIDs, each pointing to an `[[SDR_Vocabulary_Term]]` or `[[SDR_Text_Block]]` suggesting instrumentation (e.g., "StringSection", "Synthesizers", "SoloPiano", "PercussionEnsemble"). |
| `Emotional_Arc_Target_UID`       | `Synapse_UID`                     | `1`          | UID of an `[[SDR_Text_Block]]` or `[[SDR_Qualitative_Assessment]]` describing the desired emotional journey or feeling the music should evoke. |
| `Estimated_Duration_UID`         | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Time_Duration]]` providing an estimated length for the composition.                                                         |
| `Reference_Tracks_Or_Motifs_UIDs`| `List<Synapse_UID>`               | `0..*`       | List of UIDs pointing to `[[SDR_Data_Reference]]` instances (e.g., links to existing musical pieces for inspiration or specific motifs to incorporate). |
| `Dynamic_Changes_Notes_UID`      | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Text_Block]]` describing any points where the music should change dynamically based on events.                              |
| `Music_Composition_Metadata`     | `[[SDR_Metadata_Block]]`          | `0..1`       | UID of an `[[SDR_Metadata_Block]]` for this brief.                                                                                           |