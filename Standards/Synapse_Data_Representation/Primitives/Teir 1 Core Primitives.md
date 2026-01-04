##Universal

- [[SDR_UID_Reference]]: Structure to hold a Unique Identifier.
- [[SDR_Text_Block]]: For general text, descriptions, names (with attributes like language).
- [[SDR_Numeric_Value]]: For all kinds of numbers (integer, float, with units if applicable).
- [[SDR_Boolean_Value]]: For true/false states.
- [[SDR_Timestamp]]: For representing points in time or durations.
- [[SDR_Confidence_Score]]: A standardized way to express certainty (e.g., a float 0.0-1.0).
- [[SDR_Status_Code_Item]]: An item from a controlled vocabulary of status codes (e.g., [[Task_Pending]], [[Data_Validated]], [[Error_NetworkFailure]]).
- [[SDR_Metadata_Block]]: A common container for metadata elements like [[Source_UID]], [[Creation_Timestamp]], [[Version_Info]], [[Owning_Model_UID]]. This would be embedded in many other SDRs.