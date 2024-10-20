# Storage Engine (WAL importance)


- How N0-SQL intearnally handels READ and Write ?
- How do we store data in No-sql where every entry mmay have a variable size ?
1. **Approach 1** 
   (File storage -> key-value in same line )
      **Problems with approach 1** : 
      - **Problem First** : Read data from any location in DB will be O(N), because line by line traversal is required
      - **Problem Second** : Writing an item will be difficult , because  agar "Ram" ko edit kr k "Lakhan" krna hai agar to ram 3 letter ka hi tha but lakhan 6 letter ka hai , ab sare letters ko aage khaskana padega
      
      

2. **Approach 2** (solution of problem second):
   Second : Just keep adding content at the end of WAL ,this will make Writes easy O(1) .
      BUT
   ***Above solution will increase other problems***
   - **Problem Third** :Size of DB will increase as we just keep adding, in case of update also. 
   - **Problem Four** : Redundant data
   - Read is still very Difficult because now there is chance of duplicasy of data.

3. **Approach 3**: WAL + (Indexing)

   - to optimise reads start reading from backwasrd , because probability is higher as we are storing new data in end.
   - **Indexing** : if we create index table of data and address it will further optimise the reads
   Time Complexity : O(1)

   ***Now we have succesfully optimised the problem 1 and problem 2 We are still left with problem 3 and Problem 4***

4. **Approach 4**  WAL + Indexing + Comppaction [Page 67 in detail]
   - **Compaction (de-duplication)** is the process of removing redundent data and keeping only updated , latest date in a new file. 
   Compaction will create multiple files with diffrent data.
      - Chunking => Deduplication => update new table => Update index Table 
      ```
      if(address != index.address){ 
         drop row
         } 
      else{
         add to new table
      }
      ```
   ***Now we have solved problem 4 of data redundency , only left is Problem 3 of high memory usage***
---
5. **Approach 5** LSM Trees
   we will solve all remaining problems
   1. **Mem Table** : Stores latest chunk of WAL logs
   2. **SS Table** : Sorted WAL File (multiple tables)
   3. **SS Index** :  File that stores start Index of all SS Table.

   Write Workflow
   : Write back caching ki help se write karenge

   Read Workflow
   : Check Meme table => look for address(SS Index) => Read from SS Table.

|         | Read     | Write  |
|---- | ----  | ----    |
| SQL  | O(Log N) | O(LogN) |
| Approach 1 (CSV files)| O(N) | O(N)  |
| Approach 2 WAL   | O(N)     | O(1)    |
| Approach 3 (WAL + Index) | O(1)| O(1)    |
| Approach 4 (WAL+ Index + Compaction) | O(N) | 0(Log N)|
| Approach 5 (LSM ) | O(Log N)        | O(Log N)   |
   