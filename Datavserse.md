## Microsoft Dataverse
a cloud data platform for MS Power Platform. It can be used for creating Power Apps, controlling the tables, rows, and columns. Backing up or configuring database is not nevessary, all data is encrypted at rest and in transit. It also allowed integration with MS 365 and MS Azure. 

### Tables
- Data stored within a set of records
- Logical structure of rows and columns, represent a set of data
- *Standard* table is the basic, you can also create *custom* tables
- Create and edit tables using Power Apps maker portal
- Properties
  - Name/Row/Columns/Relationships/Alternate keys/Forms/Views(define the rows and columns)/Charts/Business rules/Metadata
    - Row keys: primary key is uniquely identifies a single row in the table. it is a GUID, a 32 character string, generated automatically when a row is created.
    - primary column: text string used to represent the row in apps and flows
- How to create
  - In the portal, Tables > +New table >   

- Types
  1. Standard: 
  2. Activity: store interactions, primary column are fixed and can't be changed. EX) phone calls, tasks, and appointments
  3. Virtual: from external source; Azure SQL DB or Sharepointlist  

