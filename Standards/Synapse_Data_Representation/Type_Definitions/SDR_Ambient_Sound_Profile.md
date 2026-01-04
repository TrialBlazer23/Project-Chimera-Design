## SDR_Ambient_Sound_Profile

**SDR Type Name:** [[SDR_Ambient_Sound_Profile]]

**Description:** Details the background environmental sounds that create the general atmosphere for a location or scene. Referenced by `[[SDR_Soundscape_Brief]]`.

**Fields:**

| Field Name                            | Data Type                         | Multiplicity | Description                                                                                                                                  |
| :------------------------------------ | :-------------------------------- | :----------- | :------------------------------------------------------------------------------------------------------------------------------------------- |
| `Ambient_Profile_UID`               | `Synapse_UID`                     | `1`          | Unique identifier for this ambient sound profile.                                                                                            |
| `Profile_Name_Or_Context_UID`       | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Text_Block]]` providing a name or context (e.g., "DenseForestNight", "BusyMarketDay", "QuietSpaceshipCorridor").            |
| `Overall_Atmosphere_Description_UID`| `Synapse_UID`                     | `1`          | UID of an `[[SDR_Text_Block]]` describing the overall feeling and character of the ambient soundscape.                                     |
| `Dominant_Ambient_Elements_UIDs`    | `List<Synapse_UID>`               | `0..*`       | List of UIDs, each pointing to an `[[SDR_Sound_Element_Descriptor]]` for recurring or prominent ambient sounds (e.g., wind, rain, distant traffic, machinery hum). *(Introduces `SDR_Sound_Element_Descriptor`)* |
| `Subtle_Background_Elements_UIDs`   | `List<Synapse_UID>`               | `0..*`       | List of UIDs, each pointing