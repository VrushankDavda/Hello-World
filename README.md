# This are the integration filed mapping between EDW and Salesforce as per below.

# Broker Group

EDW_Staging.dbo.map_broker_groups	Broker_Group__c
null	Id
null	Error
null	Broker_designation__c
BGCode	Broker_Group_ID__c
null	City__c
null	Headquarter_Address__c
null	In_force_Policy_Count__c
null	In_force_Premium_USD__c
null	Incurred_to_date_loss_ratio__c
MasterBrokerGroup	Name
'00570000000oNazAAE' -- tq	OwnerId
null	Postal_Code__c
null	Relationship_Manager__c
null	State__c
null	Status__c
null	Website__c


# Broker Region

EDW_Staging.dbo.map_broker_zone	Broker_Region__c
null	Id
null	Error
null	BD__c
BrokerZone	Broker_Region_ID__c
null	In_force_Policy_Count__c
null	In_force_Premium_USD__c
BrokerZone	Name
'00570000000oNazAAE' -- tq	OwnerId

# Broker Account

Account	EDW_PREPROD.dbo.LOOKUP_CRM_broker_CLEANSED
Id	null
Error	null
Account_Status__c	null
AnnualRevenue	case when [annual revenue]='' then 0 when [annual revenue] is null then 0 else [annual revenue] end
AW_Claims_Amount_USD__c	[gross loss & alae paid (usd)]
AW_Claims_Count__c	[claims count]
BillingCity	case when len(broker_city) > 40 then left(broker_city,40) else broker_city end
BillingCountry	case when len(broker_country) > 40 then left(broker_country,40) else broker_country end
BillingPostalCode	case when len(broker_postal_code) > 20 then left(broker_postal_code,20) else broker_postal_code end
BillingState	case when len(broker_state) > 20 then left(broker_state,20) else broker_state end
BillingStreet 	broker_street_address_1 + char(13) +  broker_street_address_2
broker_Designation__c	drbrokertype
Broker_Group__c	brokergroup
Broker_Regional_Group__c	regionalbrokergroup
Broker_Specialty__c	null
Broker_Type__c	brokertype
Company_Type__c	null
Description	null
Duns__c	case when len([d&b number] > 10 then left([d&b number],10) else [d&b number] end
Fax	broker_fax_number
Genius_ID__c	broker_code + 'B'
geocodedstatus__c	null
Hidden_Geocoded__c	null
HS_Import_Run__c	null
In_force_Policy_Count__c	[policy count]
In_force_Premium_USD__c	[Premium (USD)]
In_force_Premium_USD_Energy__c	[Premium (USD) EN]
In_force_Premium_USD_Fronted_Prop__c	[Premium (USD) FP]
In_force_Premium_USD_GC__c	[Premium (USD) GC]
In_force_Premium_USD_HC__c	[Premium (USD) HC]
In_force_Premium_USD_iBind_D_O__c	[Premium (USD) iBind DO]
In_force_Premium_USD_iBind_E_O__c	[Premium (USD) iBind EO]
In_force_Premium_USD_PL__c	[Premium (USD) PL]
In_force_Premium_USD_PROP__c	[Premium (USD) PROP]
Industry	null
lat__c	0.00
lon__c	0.00
Market_Cap_USD__c	0.00
NAIC__c	null
[Name]	ISNULL(EDW_PREPROD.dbo.LOOKUP_CRM_POL_COUNTS_AMOUNTS.broker_name, broker_name)
NumberOfEmployees	convert(int,0)
OwnerId	'00570000000oNazAAE' -- tq
Ownership__c	null
Phone	broker_phone_number
RecordTypeId	'012700000005EGSAA2'
ShippingCity	case when len(broker_city) > 40 then left(broker_city,40) else broker_city end
ShippingCountry	case when len(broker_country) > 40 then left(broker_country,40) else broker_country end
ShippingPostalCode 	case when len(broker_postal_code) > 20 then left(broker_postal_code,20) else broker_postal_code end
ShippingState	case when len(broker_state) > 20 then left(broker_state,20) else broker_state end
ShippingStreet	broker_street_address_1 + char(13) +  broker_street_address_2
Site	null
Target_Casualty__c	'false'
Target_Fronted_Property__c	'false'
Target_Healthcare__c	'false'
Target_Professional_Liability__c	'false'
Target_Property__c	'false'
Target_Property_Energy__c	'false'
Type	null
Website	null
Total_Premium_Since_Inception__c	PremiumITD
First_Year_of_Insured__c	minInception,
Recent_Year_Insured__c	maxInception,
Number_of_Inception_Years__c	countInception,
Broker_Region_Lookup__c	ISNULL(ISNULL(EDW_Staging.dbo.map_broker_zone_city.ProductionRegion, EDW_Staging.dbo.map_broker_zone), zone)
Broker_Group_Lookup__c	MDS.mdm.Broker.[Broker Group_Code]
CreatedDate	GETDATE()

# Insured Account 

Account	edw_preprod.dbo.LOOKUP_CRM_Assured_CLEANSED
Id	null
Error	null
Account_Status__c	null
AnnualRevenue	case when [annual revenue]='' then 0 when [annual revenue] is null then 0 else [annual revenue] end
AW_Claims_Amount_USD__c	[gross loss & alae paid (usd)]
AW_Claims_Count__c	[claims count]
BillingCity	case when len(assured_city) > 40 then left(assured_city,40) else assured_city end
BillingCountry	case when len(assured_country) > 40 then left(assured_country,40) else assured_country end
BillingPostalCode 	case when len(assured_postal_code) > 20 then left(assured_postal_code,20) else assured_postal_code end
BillingState	case when len(assured_state) > 20 then left(assured_state,20) else assured_state end
BillingStreet	case when assured_code='POSC0025' then '' else assured_street_address_1 + char(13) + assured_street_address_2 end
assured_Designation__c	null
assured_Group__c	null
assured_Regional_Group__c	null
assured_Specialty__c	null
assured_Type__c	null
Company_Type__c	null
Description	null
Duns__c	case when len([d&b number]) > 10 then left([d&b number],10) else [d&amp;b number] end
Fax	assured_fax_number
Genius_ID__c	assured_code + 'A'
geocodedstatus__c	null
Hidden_Geocoded__c	null
HS_Import_Run__c	null
In_force_Policy_Count__c	[policy count]
In_force_Premium_USD__c	[Premium (USD)]
In_force_Premium_USD_Energy__c	[Premium (USD) EN]
In_force_Premium_USD_Fronted_Prop__c	[Premium (USD) FP]
In_force_Premium_USD_GC__c	[Premium (USD) GC]
In_force_Premium_USD_HC__c	[Premium (USD) HC]
In_force_Premium_USD_iBind_D_O__c	[Premium (USD) iBind DO]
In_force_Premium_USD_iBind_E_O__c	[Premium (USD) iBind EO]
In_force_Premium_USD_PL__c	[Premium (USD) PL]
In_force_Premium_USD_PROP__c	[Premium (USD) PROP]
Industry	null
lat__c	0.00
lon__c	0.00
Market_Cap_USD__c	0.00
Name	assured_name
NumberOfEmployees	0
OwnerId	'00570000000oNazAAE' -- tq
Ownership__c	null
Phone	assured_phone_number
RecordTypeId	'012700000005EGXAA2'
ShippingCity	case when len(assured_city) > 40 then left(assured_city,40) else assured_city end
ShippingCountry	case when len(assured_country) > 40 then left(assured_country,40) else assured_country end
ShippingPostalCode 	case when len(assured_postal_code) > 20 then left(assured_postal_code,20) else assured_postal_code end
ShippingState	case when len(assured_state) > 20 then left(assured_state,20) else assured_state end
ShippingStreet	case when assured_code='POSC0025' then '' else assured_street_address_1 + char(13) +  assured_street_address_2 end
Site	null
Target_Casualty__c	'false'
Target_Fronted_Property__c	'false'
Target_Healthcare__c	'false'
Target_Professional_Liability__c	'false'
Target_Property__c	'false'
Target_Property_Energy__c	'false'
[Type]	null
Website	null
Total_Premium_Since_Inception__c	PremiumITD
First_Year_of_Insured__c	minInception
Recent_Year_Insured__c	maxInception
Number_of_Inception_Years__c	countInception
NAIC__c	ASSRD_NAIC
NAIC_Sector__c	Sector
NAIC_US_Industry__c	US_Industry
CreatedDate	GETDATE()

# Opportunity 

Opportunity	EDW_PREPROD.dbo.LOOKUP_CRM_POL_COUNTS_AMOUNTS
Id	null
Error	null
AccountId	broker_code + 'B' -- lookup
Amount	[premium (usd)]
Attachment_Point_Org_del__c	null
Attachment_Point_USD__c	[occurrence attachment (usd)]
AW_Branch_2__c	null
AW_Branch__c	branch
AW_Claims_Count__c	[claims count]
AW_Claims_USD__c	[gross loss &amp; alae paid (usd)]
AW_Region2__c	branch_group
AW_Region__c	branch_group
Campaign__c	null
Cloned_Opportunity__c	null
CloseDate	inception_date
Degree__c	null
Description	null
EMail_UA_Submission_Details__c	'false'
Expiry_Date__c	expiry_date
ForecastCategoryName	null
Genius_ID__c	policy_number
Inception_Date__c	inception_date
Insured__c	assured_code + 'A' -- lookup
Issuing_Company__c	insurer_name
LeadSource	null
Main_Competitors__c	null
Name	assured_name
NextStep	null
Occurance_Limit_Org_del__c	null
Occurrence_Limit__c	[occurrence limit (usd)]
Original_Currency__c	null
Originating_Broker_Firm__c	case when original_broker_code is null then null when ltrim(rtrim(original_broker_code)),'' then null else original_broker_code + 'B' end -- lookup
OwnerId	ownerid
Part_Of_Org_del__c	null
Part_of_USD__c	[occurrence part of (usd)]
Policy_Number__c	policy_number
Policy_Status__c	policy_status
Policy_Type__c	policy_record_type
Potential_Premium_USD__c	[estimated premium (usd)]
Pricebook2Id	null
Product_Line__c	product_department_name
Reason_Lost__c	null
Selected_UA_Email_2__c	null
Selected_UE_Email__c	null
StageName	stage
Sub_Product__c	case when Product_Department_Name in ( 'airlines''aerospace''general aviation' ) then Product_Department_Name else lob end -- lob
Target_Expiry_Date__c	expiry_date
Target_Inception_Date__c	inception_date
Target_Premium_USD__c	[estimated premium (usd)]
Type	null
UA__c	null
US_Business_Type__c	us_business_type
UW_Name__c	uw_name
Wholesale_Broker_Firm__c	null

![image](https://user-images.githubusercontent.com/82831785/115915549-76545580-a441-11eb-8424-80f549a1bbd4.png)
