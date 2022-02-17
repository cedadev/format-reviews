# Review of JCAMP-DX

Primary reviewer: Sam Pepler. 2009-07-23

Other reviewers: Graham Parton, Robert McPheat. Met on 2009-07-27 comments added.

This format is being review as the suggested format for spectra from the Molecular Spectroscopy Facility. A new supported format is needed because this is a international standard and other formats are inappropriate for spectral data.

## R1: Producers can make the files on most platforms with available tools. 
 - Who are the foreseen creators that would produce data in this format? - In this case the data producers are the MSF and of labs like them. Other labs exchange data in JCAMP format or ad hoc formats.
 - What are the foreseen feature types for the data? – Spectra, this includes raw intensity, interferogramme, absorbance and transmittance.
 - What are their preferred computing platforms and tools for this community? – The MSF uses Windows and proprietary software to acquire the data.
 - Are there existing tools to create files in this environment? - The MSF uses proprietary software to acquire the data from the spectrometer. It does have the facility to save spectra as JCAMP-DX files.
 - If not, can they create the files with other tools available to them? – They also have in house software to read the proprietary format and write it into JCAMP-DX. This is written in FORTRAN and IDL.  
## R2: format should be platform neutral. 
 - Do the files have a big-endian, little-endian options?  - ACSII format. 
 - If text files, are files in a specified character set? – ACSII format.
 - Is common software for reading the data available on common platforms? – JspecView is an open Java read and visualisation tool, JCAMP-DX reference implementation also available on source forge.
## R3: Required file level metadata can be encoded. 
 - What metadata standards are used by the user community? – Little used. Would like to use chemical names from dictionaries. 
 - What are the requirements for file level metadata for ingest and use? – Spectrum range, sample description, instrument, type of spectrum (transmittance, absorption, etc)
 - Are all of these metadata elements encodable into the format? – Yes 
 - Are there established conventions for encoding the metadata into the format? – The format has metadata in its structure. Many elements are optional. 
## R4: Format compliance can be checked. 
 - Are there tools to check file format compliance? No known format checking tools.
 - Are there tools to check metadata conventions compliance? No known format checking tools.
 - Is it feasible to develop checking tools? – Yes, minimum compliance is easy to check for simple spectra. 
## R5: Format should be stable (changes are managed). 
 - Are changes to the format managed? – Yes very much so. Draft changes are discussed by IUPAC committee.
 - Historically what is the frequency of changes to the format? – Format changes are only done on annual timescales. First standard is date 1988.
 - Have changes been backwards compatible? Basis structure of the format is similar to the 1988 version.
 - Have tools to read old version been preserved? – Papers documenting the format have been published in journals. Not sure about tools.
## R6: Format should be open (if not one has any software to read the data, user can write there own). 
 - Are there public domain document describing the format? documenting the format have been published in journals. Copies of these are available.
 - Are the documents sufficient to engineer software to read data in the file format? – Yes, Robert had written programmes to do this and it took 1 day.
 - How much effort would it be to engineer read software from scratch? Small effort for simple unpacked spectra. Complex and bespoke packing require more effort to unpick. There are ways to put more than one block of data in one file, this would also require extra effort to encode. 
## R7: Format should be migratable (as improved formats appear the significant properties of the files can be transferred to new formats). 
 - Are there any format specific encodings that would be hard to move to other formats. (e.g. coloured cells in excel)  - No.
# R8: Format is in use by the data centre user community 
 - What is the designated user community for this feature type and use metadata? – The IUPAC stamp suggests the format is in use. 


# Conclusions
 - The format is suitable the following feature types: Spectra from spectroscopy.
 - The format is suitable the following producers: Any spectroscopy group. Spectrometer manufactures create proprietary formats, but this is usually an option to save the data in an open format from there software. 
 - The format is suitable the following users: There are general visualization tools available for the format. It is also relatively easy to write code to read and process the data. If the data usage is within the spectroscopic community this is a good format.
 - Recommended conventions: Metadata conventions are built into the format. However most information is optional. Recommend reading the standard metadata elements and inserting all possible. It is also possible to encode other producer defined metadata. 
 - The format should be a recommended format: YES 
 - When should this be review again? 2015 
 - Recommend single data block and simple packing. More tools are likely to cope. 
 - BADC-CSV could be used as an alternative, but there are two reasons to stick to JCAMP: 1) This is clearly a spectroscopy community format and 2) Spectroscopy files are frequently of a length that means spreadsheet analysis (the main reason for BADC-CSV) is impractical. A JCAMP-DX to BADC-CSV converter should be investigated.

# Actions
1. Add a JCAMP-DX web page to the BADC.
2. Get more comprehensive list of software.
3. Add links to format standard. These are published papers and a format web site. 
4. As JCAMP-DX files start to arrive investigate the practicality of a BADC-CSV converter. 

