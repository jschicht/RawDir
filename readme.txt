Introduction

The tool resolves content in directories by resolving INDX ($I30) records. It is very powerful and easy to use. It has 2 mode, one verbose output and one compact output. 


Details

The output of mode 2 (verbose) will include the following for each entry within the INDX: 
 -Entry number
 -FileName
 -MFT Ref 
 -MFT Ref SeqNo
 -Parent MFT Ref
 -Parent MFT Ref SeqNo
 -Flags
 -File Create Time
 -File Modified Time
 -MFT Entry modified Time
 -File Last Access Time
 -Allocated Size
 -Real Size
 -NameSpace
 -IndexFlags
 -SubNodeVCN

Timestamps are presented in UTC 0.00 at the nanosec precision. Format is YYYY-MM-DD HH:MM:SS:MSMSMS:NSNSNSNS 


Syntax:
Example printing verbose output from the hidden system folder C:\$Extend 
RawDir.exe 1 C:\$Extend 


Example printing compact output on the root of the C: volume 
RawDir.exe 2 C:\ 


Limitation:
Will not show files marked as deleted. 


Changelog

v1.0.0.4: Fixed bug that caused only one or the other of $INDEX_ROOT/$INDEX_ALLOCATION to be evaluated for content.
v1.0.0.3: Fixed bug when $MFT itself contained an $ATTRIBUTE_LIST. Fixed bug with handling records that was split across dataruns. Increased initialization size of array for runs and vcns which caused it to crash with extreme fragmentation.
v1.0.0.2: Added support for MFT record sizes of 4096 bytes.