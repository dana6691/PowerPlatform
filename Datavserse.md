## Microsoft Dataverse
a cloud data platform for MS Power Platform. It can be used for creating Power Apps, controlling the tables, rows, and columns. Backing up or configuring database is not nevessary, all data is encrypted at rest and in transit. It also allowed integration with MS 365 and MS Azure. 

### Tables
- Data stored within a set of records
- Logical structure of rows and columns, represent a set of data
- *Standard* table is the basic, you can also create *custom* tables
- Create and edit tables using Power Apps maker portal
- Properties
  - Name/Row/Columns/Relationships/Alternate keys/Forms/Views(define the rows and columns)/Charts/Business rules/Metadata
    - Row keys = Primary key = a GUID, a 32-character string, generated automatically when a row is created.
    - Primary column: text string used to represent the row in apps and flows, default to *Name*
- How to create
  - In the portal, Tables > +New table >   

- Types
  1. Standard: can store data and add to the navigation in model-driven apps.
  2. Activity: store interactions, primary column are fixed and can't be changed. EX) phone calls, tasks, and appointments
  3. Virtual: from external source; Azure SQL DB or Sharepointlist  

### Create a custom table
- Power Apps maker portal > Tables > + New Table > Enter properties
- Advanced options: schema name unless automatically assigned and table ownership (user or team/organization)
### Add a custom column
- + button > enter New column pane > Create the choice values(+New choice) > drop-down list under Sync this choice with > select Prospect Stage 
### Customize a view
- Data experiences > Views > select Active Pets > + View Column
- To arrange the columns, drag and select Move Left /Move Right > Save > Publish
### Customize a form
- Tables > Pet > Views > Forms > Information > select Table columns > drag columns > Save and publish

### Import data into Dataverse database
Import from Excel,Access,Sharepoint, SQL and others
1. Create sample import data
   - office.com > app launcher > All apps > Sharepoint > New > List > Blank list > write name and Create > Add column 
3. Import data into your dataverse table
   - separate page, Power Apps maker portal > select Tables > select Pet table > select import > select Import data
   - Choose data source > query edit window > Map tables
  
### Table Relationships
1. One-to-many
2. Many-to-many
   - Many-to-many relationships are not supported by relational databases and Dataverse creates a hidden Intersect table to link the table rows. This intersect table does not have a form and you cannot edit its properties or add columns to the table.
4. Lookup columns (many-to-one relationship)

#### How to create
- Lookup: Click table > + New > Column > under Data type = Lookup > select Related table
- One-to-many: Tables > Account > Schema pane, select Relationships > + New relationship > One-to-many

### Logic and Security
#### Logic 
- **Business rule**: validate data across multiple columns in a table, and provide warning and error messages. created and managed in the Power Apps maker portal.
  - How
    - Table designer > Customizations panse > Business rules > + New business rule > Condition New Condition < Properties pane > select Components tab > drag Set Business Required >  under Field select Probability, under Status, choose Business Required.
  - set the value for a table column
  - perform calculations on columns
  - validate data
  - enforce data requirements
  - prompt users to enter data into a column
  - Scope
    - Individual form: The rule applies only to the specified model-driven app form.
    - All forms: The rule applies to all model-driven app forms.
    - Entity: The rule applies to all model-driven app forms and when the row is created or updated on the Dataverse table. This is the default setting.
  - Model-driven apps VS Canvas app
    - Canvas cannot do
       1. Show or hide columns.
       2. Enable or disable columns.
       3. Create business recommendations based on business intelligence.
- **Business process flows**: ensure they enter data and follow the same steps every day
- **Real-time workflows**: automate business processes
- **Business logic with code**

#### Dataverse security
Access to data in Dataverse is controlled using role-based access control (RBAC). Security roles are managed from the **Power Platform admin center**. Select environment> Settings > expand Users + permissions > select Security roles
![image](https://github.com/dana6691/PowerPlatform/assets/29461344/d8fe31cf-3088-47cc-8c31-096ed25f8dac)

- Roles
  - System Administrator: full permission to customize
  - Environment Maker: can create new resources associated with an environment, such as, apps, flows, and connections
  - Basic Users: can run an app within the environment and perform common tasks for rows on the out-of-the-box tables such as Account and Contact.
    
### Dataveres audition
- By default, auditing is enabled on all auditable table columns but is disabled at the table and environment level.
- Restricted to users who have certain security privileges: View Audit History, and View Audit Summary. also privileges specific to partitions: View Audit Partitions, and Delete Audit Partitions
- Audited data changes are stored in the records of the audit table.
- Auditing can be configured at three levels: environment, table, and column
  - Environment: MS Power Platform Admin Center > Settings 
  - Table: Power Apps maker portal > Advanced options > checked Audit changes to its data
  - Columns: Power Apps maker portal > Advanced options > checked to Enable auditing
- A user must be assigned the System Administrator or System Customizer security role

### Dual-write VS virtual tables
allow Dataverse to access the data in external and write back to the source

## Dual-write
*near-real-time* interaction between Dataverse and *Dynamics 365 finance and operations apps or Business Central apps*. provides tightly coupled, bi-directional integration. Dual-write will duplicate the data in both directions (to and from Dat

## Virtual Tables
integration of data residing in external systems by seamlessly representing that data as tables in Microsoft Dataverse, without replication of data and often without custom coding. When connecting to outside of Dynamic 365, either built-in connectors or custom connectors.


