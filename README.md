# HL7 v2 examples

This repository contains examples of Health Level Seven (HL7) version 2 messages. 

These examples are thanks to <https://github.com/eerohele/pipehat>.

We welcome constructive advice and help.

For more information contact Joel Parker Henderson (<joel.henderson@wales.nhs.uk>).

## HL7 version 2

<https://en.wikipedia.org/wiki/Health_Level_7>

Health Level Seven, abbreviated to HL7, is a range of global standards for the
transfer of clinical and administrative health data between applications with
the aim to improve patient outcomes and health system performance.

## HL7 version 2 syntax

<https://en.wikipedia.org/wiki/Health_Level_7>

HL7 v2.x messages use a non-XML encoding syntax based on segments (lines) and
one-character delimiters. 

Segments have composites (fields) separated by the composite delimiter. 

A composite can have sub-composites (components) separated by the sub-composite
delimiter, and sub-composites can have sub-sub-composites (subcomponents)
separated by the sub-sub-composite delimiter. 

The default delimiters are carriage return for the segment separator, vertical
bar or pipe (|) for the field separator, caret (^) for the component separator,
ampersand (&) for the subcomponent separator, and number sign (#) for the
default truncation separator. 

The tilde (~) is the default repetition separator. 

Each segment starts with a 3-character string that identifies the segment type.
Each segment of the message contains one specific category of information. 

Every message has MSH as its first segment, which includes a field that
identifies the message type. The message type determines the expected segment
types in the message. The segment types used in a particular message type are
specified by the segment grammar notation used in the HL7 standards.

## HL7 version 2 example

The following is an example of an HL7 v2 admission message. 

* MSH is the header segment
  
* PID is the Patient Identity
  
* PV1 is the Patient Visit information
  
* etc.

The 5th field in the PID segment is the patient's name, in the order, family
name, given name, second name (or their initials), suffix, etc. 

Depending on the HL7 V2.x standard version, more fields are available in the
segment for additional patient information.

Example:

```HL7
MSH|^~\&|MegaReg|XYZHospC|SuperOE|XYZImgCtr|20060529090131-0500||ADT^A01^ADT_A01|01052901|P|2.5
EVN||200605290901||||
PID|||56782445^^^UAReg^PI||KLEINSAMPLE^BARRY^Q^JR||19620910|M||2028-9^^HL70005^RA99113^^XYZ|260 GOODWIN CREST DRIVE^^BIRMINGHAM^AL^35209^^M~NICKELL’S PICKLES^10000 W 100TH AVE^BIRMINGHAM^AL^35200^^O|||||||0105I30001^^^99DEF^AN
PV1||I|W^389^1^UABH^^^^3||||12345^MORGAN^REX^J^^^MD^0010^UAMC^L||67890^GRAINGER^LUCY^X^^^MD^0010^UAMC^L|MED|||||A0||13579^POTTER^SHERMAN^T^^^MD^0010^UAMC^L|||||||||||||||||||||||||||200605290900
OBX|1|NM|^Body Height||1.80|m^Meter^ISO+|||||F
OBX|2|NM|^Body Weight||79|kg^Kilogram^ISO+|||||F
AL1|1||^ASPIRIN
DG1|1||786.50^CHEST PAIN, UNSPECIFIED^I9|||A
```
