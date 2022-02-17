# Supported Formats 
CEDA Data centres cannot support a multitude of file formats, because we need to be able to have systems that can parse both the internal metadata and data so as to make them available to services (e.g. catalogues and visualisation/subsetting services). We are long past the point where we can operate as a big file store and just rely on a filename convention and a file hierarchy. So there is a very real and major cost with every new format. For this reason it is important clearly identify our supported formats, list the reasons why they have been selected, and give guidance on metadata standards. Our default policy should be that new formats are not acceptable unless:

 - it is not possible for the data creators to encode their data satisfactorily in one of the formats we already support, or
 - it is not possible for the data users to easily manipulate the data in one of the formats we already support, or
 - the data is being provided in a specific format because it conforms to the requirements of a major international programme.

CEDA should take a leadership responsibility to make it easy to create and use existing supported formats (e.g. by development of software like nappy), and to encourage, cajole, and demand that existing supported formats are used wherever possible. In the case of NERC programmes we will insist supported standards are adopted, but even in programmes outside our direct control we should advise and seek to influence the choice of format. CEDA should actively review the formats its supports for ingest, storage and access. The current policy is to ingest, store and access data in the same format. A supported format should satisfy all the requirements below: 

 - R1: Producers can make the files on most platforms with available tools. *Ingest* 
 - R2: format should be platform neutral. *Ingest and use* 
 - R3: Required file level metadata can be encoded. *Ingest, preservation and use* 
 - R4: Format compliance can be checked. *Ingest*
 - R5: Format should be stable (changes are managed). *Preservation* 
 - R6: Format should be open (if not one has any software to read the data, 
user can write there own). *Preservation* 
 - R7: Format should be migratable (as improved formats appear the significant properties of the files can be transferred to new formats). *Preservation and use* 
 - R8: Format is in use by the data centre user community *Use*

## Methodology for examining a format
All formats should be critically reviewed before they are accepted as a format that is used in the archive. The methodology used in the review is to form a panel of data scientists to examine the format. This panel must have at least 3 people. One of the panel members is tasked with presenting the case for and against the formats introduction to the list of recommended formats. This person will have prepared the answers to the questions below in advance of the meeting and have tried to create and read data in the format. The requirements are examined in turn. The result of the review is an indication of its suitability for particular feature types and for which communities of users and producers. Also recommendation on conventions and metadata encoding that should be adopted.

## Question for the review to consider:

 - R1: Producers can make the files on most platforms with available tools.
    - Who are the foreseen creators that would produce data in this format?
    - What are the foreseen feature types for the data?
    - What are their preferred computing platforms and tools for this community?
    - Are there existing tools to create files in this environment?
    - If not can they create the files with other tools available to them?
 - R2: format should be platform neutral.
    - Do the files have a big-endian, little-endian options?
    - If text files, are files in a specified character set?
    - Is common software for reading the data available on common platforms?
 - R3: Required file level metadata can be encoded.
    - What metadata standards are used by the user community?
    - What are the requirements for file level metadata for ingest and use?
    - Are all of these metadata elements encodable into the format?
    - Are there established conventions for encoding the metadata into the format?
 - R4: Format compliance can be checked.
    - Are there tools to check file format compliance?
    - Are there tools to check metadata conventions compliance?
    - Is it feasible to develop checking tools?
 - R5: Format should be stable (changes are managed).
    - Are changes to the format managed?
    - Historically what is the frequency of changes to the format?
    - Have changes been backwards compatible?
    - Have tools to read old version been preserved?
 - R6: Format should be open (if not one has any software to read the data, user can write there own).
    - Are there public domain document describing the format?
    - Are the documents sufficient to engineer software to read data in the file format?
    - How much effort would it be to engineer read software from scratch?
 - R7: Format should be migratable (as improved formats appear the significant properties of the files can be transferred to new formats).
    - Are there any format specific encodings that would be hard to move to other formats. (e.g. coloured cells in excel)
 - R8: Format is in use by the data centre user community
    - What is the designated user community for this feature type and use metadata?

## Review results
The review results should be a document with the answers to the above questions and a conclusion section which lays out if and in what context the format is suitable (example below).

 - The format is suitable the following feature types: Gridded data such as model data.
 - The format is suitable the following producers: EO and Atmospheric. The tools available make this data only producible by technically literate.
 - The format is suitable the following users: Reads into common tools like Grads, xconv and IDL. Not suitable for spreadsheet users.
 - Recommended conventions: Use of already established CF conventions
 - The format should be a recommended format: YES
 - Comments:
 - When should this be review again? 2011

Once a format has been accepted it should be documented on the appropriate data centre website with reasons for suitability, production and use tools, a description of the format and links to external resources.

Current formats
The formats below are the formats BADC and NEODC should accept for ingest.
