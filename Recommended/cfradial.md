
# Reveiw details

| Reviewers compiling report |  Graham |  
| When was it complied | 28/10/2014 13:35:27 | 


# Format details

|   |   |
|---|---|
| Format Title | CfRadial Data File Format |  
| short name | cfradial |
| file suffix(s) | .nc |

Links to documentation/community pages: 
 - http://www.ral.ucar.edu/projects/titan/docs/radial_formats/CfRadialDoc.pdf
 - https://opensky.ucar.edu/islandora/object/manuscripts%3A838
 - https://community.wmo.int/activity-areas/weather-radar-observations/radar-data-exchange

General format type 
Conventions on top of NetCDF

		data from radar and lidars with a radial component	all platforms able to support netCDF production	standard netCDF tools?		no	NA	yes - all tools that can read netCDF files should be able to cope with these data too	CF	strict compliance with CF-radial requirements	yes	Being established - see http://www.ral.ucar.edu/projects/titan/docs/radial_formats/CfRadialDoc.pdf	yes - CF-netCDF checkers	yes - CF-netCDF checkers	no need	yes - see http://www.ral.ucar.edu/projects/titan/docs/radial_formats/CfRadialDoc.pdf	"3 sub-versions to date: 
v1.1 - 2011-02-01; 
v1.2 - 2011-06-07
v1.3 - 2013-06-01"	Changes are backwards compatable to v1.1	remain the same tools 	http://www.ral.ucar.edu/projects/titan/docs/radial_formats/CfRadialDoc.pdf	yes	lots, but no need to as netCDF based	radial component and use of axis as coordinate breaks with normal netCDF	weather radar and lidar research community, national weather forecasting agencies	



# Producers can make the files on most platforms with available tools.

### Who are the foreseen creators that would produce data in this format?  
Operators of radars and lidar instruments carrying out scans and producing data with radial components

### What are the foreseen feature types for the data?  
data from radar and lidars with a radial component

### What are their preferred computing platforms and tools for this community?  
all platforms able to support netCDF production

### Are there existing tools to create files in this environment?  
standard netCDF tools?

# format should be platform neutral.
The format is platform nutral as based on NetCDF.

# Required file level metadata can be encoded.
R3A :What metadata standards are used by the user community?
R3B : What are the requirements for file level metadata for ingest and use?
R3C : Are all of these metadata elements encodable into the format?
R3D : Are there established conventions for encoding the metadata into the format?

CF	strict compliance with CF-radial requirements	yes	Being established - see http://www.ral.ucar.edu/projects/titan/docs/radial_formats/CfRadialDoc.pdf

# Format compliance can be checked.
R4 A: Are there tools to check file format compliance?
R4 B: Are there tools to check metadata conventions compliance?
R4 C: Is it feasible to develop checking tools?

# Format should be stable (changes are managed).
R5A: Are changes to the format managed?
R5A: Historically what is the frequency of changes to the format?
R5A: Have changes been backwards compatible?
R5A: Have tools to read old version been preserved?

# Format should be open (if not one has any software to read the data, user can write there own).
R6A: Are there public domain document describing the format?
R6B: Are the documents sufficient to engineer software to read data in the file format?
R6C: How much effort would it be to engineer read software from scratch?

# Format should be migratable (as improved formats appear the significant properties of the files can be transferred to new formats).
R7A: Are there any format specific encodings that would be hard to move to other formats. (e.g. coloured cells in excel)

# Format is in use by the data centre user community
R8A: What is the designated user community for this feature type and use metadata?

# Conclusions