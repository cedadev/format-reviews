# Review of PP format

Primary reviewer: Kevin Marsh. 2009-10-06

Other reviewers: Alan Iwi (comments added 2009-10-07), Ag Stephens and Sam Pepler (comments added 2009-10-08).

This format is being reviewed as it is the usual format for binary numerical model output from the UK Met Office and Hadley Centre.

## R1: Producers can make the files on most platforms with available tools. 
 - Who are the foreseen creators that would produce data in this format? – UK Met Office/Hadley centre. Other institutes which run the numerical models derived from these organizations.
 - What are the foreseen feature types for the data? – Gridded 2/3/4 D maps although some support for cross sections (and maybe other types) can be retro-fitted to this format
 - What are their preferred computing platforms and tools for this community? – Primarily unix/linux based. Number of community tools (e.g. xconv, perl scripts) which can handle these files.
 - Are there existing tools to create files in this environment? – Files can be created by various scripts, but requires level of expertise.  Typically the only motivation for creating PP data that is not already in that format is for driving the numerical models.  This particularly applies to model dump/fields/ancillary file format, which is based on PP but with additional header info and a reordering of the internal structure.  Even when there are tools that can write the file format, the main difficulty in creating these files is populating the headers, so typically as many of the header values as possible will be copied from an existing file.
 - If not, can they create the files with other tools available to them? –Some tools written in FORTRAN and IDL.
## R2: format should be platform neutral. 
 - Do the files have a big-endian, little-endian options?  - Yes.  The files can be swapped between big-endian and little-endian byte ordering, but this is not without its problems, as sometimes files containing 64-bit data nonetheless also contain 32-bit data and when swapping on a 64-bit basis, the ordering of pairs of 32-bit numbers will be swapped; on encountering 32-bit data, tools like xconv have to make (or ask the user to make) some assumption about the endianness of the machine on which the data was written.  I believe that for later versions of the UM (vn5.x onwards) the files are always written big-endian even on a little-endian machine, which mitigates this problem but does not apply e.g. to HadCM3 which is based on vn4.5. The files are not strictly self describing, in that the endianess can not be determined until the file contents are examined.
 - If text files, are files in a specified character set? – N/A.
 - Is common software for reading the data available on common platforms? –Xconv is the closest to this. CDAT has some capability for read-only operations and is also available on source forge.
## R3: Required file level metadata can be encoded. 
 - What metadata standards are used by the user community? – Variable names from lookup tables, non-CF compliant.
 - What are the requirements for file level metadata for ingest and use? – Variable, date, levels, etc.
 - Are all of these metadata elements encodable into the format? – Largely.  However one of the problems is the dependence on external lookup tables for mapping from STASH codes (numerical variable IDs) to intelligible descriptions of variable contents and where applicable to CF standard names; there can be situations where a copy of the numerical model has been modified such that a field with a given numerical STASH code contains a different variable than it would do in the standard unmodified model – this information is not encoded into the format, although an accompanying file (“user STASHmaster” in UM-speak) may sometimes be provided which gives some metadata, though stopping short of a CF standard name. 
 - Are there established conventions for encoding the metadata into the format? – Yes, but have to use external lookup tables to decode some header information. No provenance information is carried with the files.
## R4: Format compliance can be checked. 
 - Are there tools to check file format compliance? No known format checking tools. Xconv can be used to see if the file can be parsed.
 - Are there tools to check metadata conventions compliance? No known format checking tools.
 - Is it feasible to develop checking tools? – Yes, minimum compliance is easy to check for, as regards the file structure (e.g. for basic PP, does it contain a succession of valid Fortran-style records with appropriate lengths) but checking even basic believability of metadata is harder.
## R5: Format should be stable (changes are managed). 
 - Are changes to the format managed? – Yes via internal UK Met Office documents.
 - Historically what is the frequency of changes to the format? – Format changes are only done very rarely. There are believed to be many variants of PP used within the UK Met Office.
 - Have changes been backwards compatible? Unknown.  The format itself virtually never changes; however the interpretation of certain metadata elements can change (and has changed) between versions; these are documented to some extent in Met Office documents. Variable definitions may change between versions of the STASHMASTER files.
 - Have tools to read old version been preserved? – Unknown
## R6: Format should be open (if not one has any software to read the data, user can write their own). 
 - Are there public domain document describing the format? Yes, via NCAS website.
 - Are the documents sufficient to engineer software to read data in the file format? – Yes, and this has been done in the past.  However the interpretation of some elements is not clear from the documents, and typically this ends up being done empirically from certain existing files, and then further modified as more files are encountered which may not fit with initial empirical assumptions.
 - How much effort would it be to engineer read software from scratch? Moderate effort to develop basic code (2-3 weeks), depending on level of expertise and experience of programmer. Some aspects (packing, byte swapping) need careful attention.
## R7: Format should be migratable (as improved formats appear the significant properties of the files can be transferred to new formats). 
 - Are there any format specific encodings that would be hard to move to other formats. (e.g. coloured cells in excel)  - No.
## R8: Format is in use by the data centre user community 
 - What is the designated user community for this feature type and use metadata? – Widely used by the UK Met. and climate change research communities
 
# Conclusions
 - The format is suitable the following feature types: Gridded simulation data.
 - The format is suitable the following producers: Any numerical simulation group if already using Met Office models; not recommended if model output is not already in this format. 
 - The format is suitable the following users: There are general visualization tools available for the format. It is also possible to write code to read and process the data. If the data usage is within the specialist modeling community where expert knowledge is present, this is a good format.
 - Recommended conventions: Metadata conventions are built into the format, in terms of how the header block is structured. However some metadata needs to be decoded via lookup tables.  Supply user STASHmaster files to accompany any data where it is applicable.
 - The format should be a recommended format: No, but will be accepted. 
 - When should this be reviewed again? 2011 
 - Accept this format for use, but note that CF-compliant NetCDF preferred for long term preservation and ease of use of this feature type.
 - Advise ingle data block and simple packing. More tools are likely to cope. 
 - A standard pp to CF-compliant NetCDF converter (CMOR) is under development at the Met Office though this will require careful configuration for each set of model output.

#Actions
1.	Add UM docs to CEDA repository from NCAS web site.
 

 

