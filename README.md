<div align="center">

# STIX-2.1-Generator
**Master's thesis project for the automatic generation of STIX 2.1 bundles using LLM.**

**STIX 2.1 Generator** is a tool designed to automatically create, validate, and export STIX 2.1 bundles that comply with the OASIS standard. This tool simplifies the programmatic generation of indicators of compromise (IOCs), threat actors, malware, and indicators.

</div>

---

## ℹ️ About the Project

The **STIX 2.1 Generator** is a comprehensive tool designed to simplify the creation, validation, and manipulation of Cyber Threat Intelligence (CTI) data compliant with the **OASIS STIX™ Version 2.1** standard.

Manually writing complex JSON payloads for STIX objects can be error-prone and time-consuming. This project allowing developers and security analysts to focus on modeling threat intelligence rather than worrying about syntax and schema compliance.

### Key Functions & Capabilities

* **Standard-Compliant Object Generation**: Easily instantiate core STIX Domain Objects (SDOs) such as *Indicators, Malware, Threat Actors, Campaigns,* and *Identities* using native Python classes.
* **Automated Relationship Mapping**: Streamline the creation of STIX Relationship Objects (SROs) to define semantic links between entities (e.g., `indicates`, `uses`, `attributed-to`).
* **Schema Validation**: Enforces strict adherence to the STIX 2.1 specification, ensuring that required fields are present and data types are correct before serialization.
* **JSON Serialization**: fast and efficient export of Python objects to valid, minified, or pretty-printed JSON strings ready for external integration.
