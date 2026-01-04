## SDR_Setting_Description

**SDR Type Name:** [[SDR_Setting_Description]]

**Description:** Details the specific environment, location, and time period for a narrative or a particular scene within it. Used by `[[SDR_Narrative_Blueprint]]` and `[[SDR_Scene_Description]]`.

**Fields:**

| Field Name                     | Data Type                         | Multiplicity | Description                                                                                                                                 |
| :----------------------------- | :-------------------------------- | :----------- | :------------------------------------------------------------------------------------------------------------------------------------------ |
| `Setting_Description_UID`      | `Synapse_UID`                     | `1`          | Unique identifier for this setting description.                                                                                             |
| `Setting_Name_UID`             | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Text_Block]]` providing a name for the setting (e.g., "TheCrimsonForest", "Neo-ParisDistrict7").                          |
| `Location_Description_Text_UID`| `Synapse_UID`                     | `1`          | UID of an `[[SDR_Text_Block]]` detailing the physical characteristics of the location.                                                      |
| `Time_Period_Description_UID`  | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Text_Block]]` or `[[SDR_Time_Duration]]` describing the historical era, time of day, or specific temporal context.         |
| `Sensory_Details_UIDs`         | `List<Synapse_UID>`               | `0..*`       | List of UIDs, each pointing to an `[[SDR_Text_Block]]` describing sensory inputs (visuals, sounds, smells, atmosphere).                     |
| `Mood_And_Atmosphere_UID`      | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Qualitative_Assessment]]` or `[[SDR_Text_Block]]` describing the prevailing mood or atmosphere of the setting.           |
| `Key_Features_Or_Landmarks_UIDs`| `List<Synapse_UID>`              | `0..*`       | List of UIDs, each pointing to an `[[SDR_Text_Block]]` or `[[SDR_Entity_Reference]]` describing important features or landmarks.         |
| `Setting_Image_Concept_Ref_UIDs`| `List<Synapse_UID>`              | `0..*`       | Optional list of UIDs pointing to `[[SDR_Data_Reference]]`s (e.g., for inspirational images or Visionary's concept art).                  |
| `Setting_Metadata`             | `[[SDR_Metadata_Block]]`          | `0..1`       | UID of an `[[SDR_Metadata_Block]]` for this setting description.                                                                          |