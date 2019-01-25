---
UID: NS:poclass._BATTERY_STATUS
title: "_BATTERY_STATUS" (poclass.h)
description: The BATTERY_STATUS structure is used by battery miniclass drivers to return status information in response to a call to BatteryMiniQueryStatus.
old-location: battery\battery_status.htm
tech.root: battery
ms.assetid: 48df787b-f9f6-45d1-872c-ceeda3087af6
ms.date: 02/15/2018
ms.keywords: "*PBATTERY_STATUS, BATTERY_STATUS, BATTERY_STATUS structure [Battery Devices], PBATTERY_STATUS, PBATTERY_STATUS structure pointer [Battery Devices], _BATTERY_STATUS, bat-struct_11dfaf25-0f90-4c5b-8017-15fb2124423b.xml, battery.battery_status, poclass/BATTERY_STATUS, poclass/PBATTERY_STATUS"
ms.topic: struct
req.header: poclass.h
req.include-header: Batclass.h
req.target-type: Windows
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library:
req.lib:
req.dll:
req.irql: Called at PASSIVE_LEVEL.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	poclass.h
api_name:
-	BATTERY_STATUS
product:
- Windows
targetos: Windows
req.typenames: BATTERY_STATUS, *PBATTERY_STATUS
---

# _BATTERY_STATUS structure


## -description


The BATTERY_STATUS structure is used by battery miniclass drivers to return status information in response to a call to <a href="https://msdn.microsoft.com/04811f63-8a57-4b39-84c5-c9b7f803c057">BatteryMiniQueryStatus</a>.


## -syntax


```cpp
typedef struct _BATTERY_STATUS {
  ULONG PowerState;
  ULONG Capacity;
  ULONG Voltage;
  LONG  Rate;
} BATTERY_STATUS, *PBATTERY_STATUS;
```


## -struct-fields




### -field PowerState

Specifies a battery power state as one or more of the following flags, ORed together: BATTERY_POWER_ON_LINE, BATTERY_DISCHARGING, BATTERY_CHARGING, and BATTERY_CRITICAL.


### -field Capacity

Specifies the capacity of the given battery, in milliwatt-hours, or BATTERY_UNKNOWN_CAPACITY if the capacity cannot be determined.


### -field Voltage

Specifies the voltage, in millivolts, across the terminals of the given battery, or BATTERY_UNKNOWN_VOLTAGE if the voltage cannot be determined.


### -field Rate

Specifies the current rate of battery usage in milliwatts or, if the driver reports relative capacity, in units per hour. A positive value means that the battery is charging; a negative value means the battery is discharging. If the driver cannot determine the rate, it should return BATTERY_UNKNOWN_RATE.


## -see-also

<a href="https://msdn.microsoft.com/04811f63-8a57-4b39-84c5-c9b7f803c057">BatteryMiniQueryStatus</a>



 

 


