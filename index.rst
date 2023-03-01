:tocdepth: 1

.. sectnum::

.. Metadata such as the title, authors, and description are set in metadata.yaml

.. TODO: Delete the note below before merging new content to the main branch.

.. note::

   **This technote is a work-in-progress.**

- Introduction

  - Raw Data

    - Raw telescope images
    - Precursor Data
    - Engineering Facilities Database
    - Large File Annex

  - Analysis Data

    - Data Releases
    - Data Previews

  - Service Data
  - Staff Data

- Summary


Introduction
============

This document details the data retention policies for the Vera C. Rubin Observatory Data Management team. This document seeks to describe these different policies by classifying the data into one of four types, to be elaborated upon further in this writing. These policies will be enforced by the services being developed by the Data Management team in support of observatory operations. Details concerning the implementation of the policies described herein lie outside the scope of this document, and will be described in a separate document to follow this one.

Raw Data
========

The raw tier consists of the data considered to be most critical to observatory operation. Due to its nature, this data can be considered irreplaceable due to either monetary or temporal constraints. Data considered to belong to the raw tier includes:

- Images taken by instruments during the preoperational, and operational periods of the survey
- Precursor data to the Rubin survey operations
- Engineering Facilities Database contents
- Large File Annex contents

Data in the raw tier should be retained for a period of no less than 100 years. There may be some additional constraints on this level of data, such as ensuring that some categories are copied to tape storage within a given timeframe of the creation of that data. All data belonging to the raw tier should be present on tape storage at SLAC National Lab with (at minimum) dual-replication for the duration of the retention period. Tape storage resources will be further provided by CCIN2P3 in France. A full copy of the raw tier data should be maintained at each SLAC and CCIN2P3. Metadata about all files in the raw tier should be maintained, especially an Alder CRC32 checksum.


Analysis Data
=============

The analysis tier contains expanded datasets derived from raw data products. Data in the analysis tier is includes datasets such as:

- Data Releases
- Data Previews

The analysis data tier is not considered to be of the same critical importance as the raw tier. Analysis data should be retained for a period of no less than 10 years. In case of a catastrophic data loss event, this data may be recreated from the raw data, possibly combined with other sources and processed by additional software. A set of metadata must be maintained which will allow for regeneration of the data in the event of a catastrophic loss. By policy, a full copy of the analysis data tier must reside at the US Data Facility. There is also no requirement that tape storage be enforced as dual-copy. Other storage technology besides tape such as disk or SSD may be used, but still there should exist two replicas which do not reside on the same physical device.

Service Data
============

The service data tier is composed of data that must be maintained to provide a long term backup of data used to maintain operational services in case of catastrophic data loss. Examples of service data include:

- Data Butler databases
- PanDA databases
- Rucio database
- FTS3 database
- Definitions of Grafana dashboards
- User quota information

Service data does not require that it be maintained at any particular facility, nor for any required period of time. However, policies should be used on a per-service basis when the service data backups are created to determine the lifetime of the service data, so that storage may be reclaimed when the data is no longer useful. The lifetime of the data should be based on how the operation needs of the observatory, and enforced using software such as Rucio to ensure that storage is freed at the appropriate time.



Staff Data
==========

The staff data tier is data defined by users or data management staff to be of a criticality sufficient that it be mandated this information be stored for a longer period of time. Data in the staff tier includes:

- Results of testing
- Important configuration
- Any data agreed upon by users and Data Management to require long-term archival

This retention period should, similar to the service data tier, be defined according to the needs of the observatory, so that storage may be reclaimed when the data is no longer useful. In this case the data lifetimes should also be software enforced.


Summary
=======

There are four distinct classifications of data that each require a different retention policy. These policies might be strict in the case of raw and analysis data, or based more closely on the specifics of the future usage of that data such as with service and staff data. In any case, software enforcement should be used to ensure that the requisite number of copies are maintained, and the retention lifetimes are used for storage recovery.

