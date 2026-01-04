## SDR_Confidence_Score_Item

**SDR Type Name:** [[SDR_Confidence_Score_Item]]

**Description:** Represents a confidence score, typically associated with a piece of data or an assertion, along with optional rationale or method of derivation.

**Fields:**

| Field Name             | Data Type                     | Multiplicity | Description                                                                              |
| :--------------------- | :---------------------------- | :----------- | :--------------------------------------------------------------------------------------- |
| `Confidence_Item_UID`  | `Synapse_UID`                 | `1`          | Unique identifier for this specific confidence score instance.                           |
| `Score_Value`          | `Synapse_Float`               | `1`          | The numerical confidence score (e.g., between 0.0 for no confidence and 1.0 for full confidence). |
| `Scale_Minimum`        | `Synapse_Float`               | `0..1`       | Minimum value of the scale used (if not 0.0).                                            |
| `Scale_Maximum`        | `Synapse_Float`               | `0..1`       | Maximum value of the scale used (if not 1.0).                                            |
| `Derivation_Method`    | `[[SDR_Text_Block]]`          | `0..1`       | UID of an SDR_Text_Block. Description of how the confidence score was derived or calculated. |
| `Supporting_Evidence_UIDs`| `List<Synapse_UID>`         | `0..*`       | List of UIDs pointing to SDR instances that provide evidence supporting this score.      |
| `Confidence_Metadata`  | `[[SDR_Metadata_Block]]`      | `0..1`       | UID of an SDR_Metadata_Block. Optional metadata for this confidence score item.          |