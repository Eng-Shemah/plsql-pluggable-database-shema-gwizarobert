# Assignment II: Pluggable Database Creation, Deletion & OEM

## Student Information
- **Name:** Robert Shema Gwiza
- **Student ID:** 27949
- **Course:** PL/SQL Language
- **Database:** Oracle 21c
- **Operating System:** Windows 10

---

## Overview

This assignment involved three main tasks related to Oracle Database administration using Oracle 21c on Windows 10.

### Task 1: Pluggable Database Creation
I created a pluggable database (PDB) named `ro_pdb_27949` with an administrative user `robert_plsqlauca_27949`. This PDB serves as the primary container for storing all class work throughout the semester. The database was successfully created using the `CREATE PLUGGABLE DATABASE` command and configured to open automatically on system startup.

### Task 2: PDB Creation and Deletion
To demonstrate understanding of database lifecycle management, I created a temporary PDB named `ro_to_delete_pdb_27949` with the same administrative credentials. After verifying its successful creation, I performed a complete deletion of this PDB including all associated datafiles using the `DROP PLUGGABLE DATABASE` command. This task demonstrated proper procedures for both provisioning and deprovisioning database resources.

### Task 3: Oracle Enterprise Manager Configuration
I configured and accessed Oracle Enterprise Manager (OEM) Database Express to provide a web-based graphical interface for database administration. This involved setting the HTTPS port to 5500 and accessing the dashboard through a web browser at `https://localhost:5500/em`. The OEM dashboard provides comprehensive monitoring and management capabilities for the pluggable database.

---

## Technical Details

### PDB Naming Convention
- **Main PDB:** `ro_pdb_27949`
- **Temporary PDB:** `ro_to_delete_pdb_27949`
- **Username:** `robert_plsqlauca_27949`
- **Password:** `Auca@1234`

### Commands Used

#### Task 1: Create Main PDB
```sql
CREATE PLUGGABLE DATABASE ro_pdb_27949
ADMIN USER robert_plsqlauca_27949 IDENTIFIED BY "Auca@1234"
FILE_NAME_CONVERT=('pdbseed','ro_pdb_27949');

ALTER PLUGGABLE DATABASE ro_pdb_27949 OPEN;
ALTER PLUGGABLE DATABASE ro_pdb_27949 SAVE STATE;
SELECT name, open_mode FROM v$pdbs;
