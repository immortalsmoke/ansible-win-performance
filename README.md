# ansible-win-performance
Edits Windows Server registry in an attempt to disable graphical features that hinder performance.  Currently only supports Server 2016.

##### Instructions
None

#####  Task Overview
1. Create temp dir
2. Copy the appropriate registry file to the target server
3. Merge the registry file with the server's registry
   
##### Assumptions:
1. `files/versionXX.reg` exists, where XX is the major version number of the target server's Windows installation


##### Additional Notes
The .reg file was generated using the following process.  If you have a better process, please open an issue and let me know.
1. Taking a registry snapshot
2. Navigating to "Performance Options" > "Visual Effects" > selecting "Adjust for best performance" > clicking "Apply"
3. Taking another registry snapshot
4. Running a differential between the two snapshots and exporting the difference as a .reg file
