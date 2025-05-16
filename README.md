# Pg-catalog

PostgreSQL maintains several system catalogs that store metadata about databases, tables, indexes, functions, and more. Below is a list of key system catalogs and their descriptions.

## Catalog List

| Catalog Name | Description |
|-------------|-------------|
| **pg_aggregate** | Stores aggregate functions. |
| **pg_am** | Contains access method information. |
| **pg_amop** | Stores operator families for index access methods. |
| **pg_amproc** | Contains support functions for index access methods. |
| **pg_attrdef** | Stores default values for table columns. |
| **pg_attribute** | Contains metadata about table columns. |
| **pg_authid** | Stores user authentication details. |
| **pg_auth_members** | Manages role memberships. |
| **pg_cast** | Stores type conversion rules. |
| **pg_class** | Contains metadata about tables, indexes, sequences, and views. |
| **pg_collation** | Stores collation settings for text sorting. |
| **pg_constraint** | Contains table constraints (e.g., primary keys, foreign keys). |
| **pg_conversion** | Stores encoding conversion rules. |
| **pg_database** | Contains information about databases. |
| **pg_db_role_setting** | Stores role-specific database settings. |
| **pg_default_acl** | Manages default access control lists. |
| **pg_depend** | Tracks dependencies between database objects. |
| **pg_description** | Stores descriptions of database objects. |
| **pg_enum** | Contains enumerated type values. |
| **pg_event_trigger** | Stores event triggers. |
| **pg_extension** | Manages installed extensions. |
| **pg_foreign_data_wrapper** | Stores foreign data wrapper metadata. |
| **pg_foreign_server** | Contains foreign server details. |
| **pg_foreign_table** | Stores metadata about foreign tables. |
| **pg_index** | Contains index metadata. |
| **pg_inherits** | Tracks table inheritance relationships. |
| **pg_init_privs** | Stores initial privileges for database objects. |
| **pg_language** | Contains metadata about procedural languages. |
| **pg_largeobject** | Stores large object data. |
| **pg_largeobject_metadata** | Contains metadata for large objects. |
| **pg_namespace** | Stores schema information. |
| **pg_opclass** | Contains operator class metadata for indexes. |
| **pg_operator** | Stores operator definitions. |
| **pg_opfamily** | Manages operator families for indexes. |
| **pg_parameter_acl** | Stores parameter-specific access control lists. |
| **pg_partitioned_table** | Contains partitioned table metadata. |
| **pg_policy** | Stores row-level security policies. |
| **pg_proc** | Contains stored procedures and functions. |
| **pg_publication** | Manages logical replication publications. |
| **pg_publication_namespace** | Stores schema-level publications. |
| **pg_publication_rel** | Contains table-level publication details. |
| **pg_range** | Stores range type metadata. |
| **pg_replication_origin** | Manages replication origins. |
| **pg_rewrite** | Stores query rewrite rules. |
| **pg_seclabel** | Contains security labels for database objects. |
| **pg_sequence** | Stores sequence metadata. |
| **pg_shdepend** | Tracks shared object dependencies. |
| **pg_shdescription** | Stores descriptions for shared objects. |
| **pg_shseclabel** | Contains security labels for shared objects. |
| **pg_statistic** | Stores table statistics for query optimization. |
| **pg_statistic_ext** | Contains extended statistics for query optimization. |
| **pg_statistic_ext_data** | Stores extended statistics data. |
| **pg_subscription** | Manages logical replication subscriptions. |
| **pg_subscription_rel** | Contains table-level subscription details. |
| **pg_tablespace** | Stores tablespace metadata. |
| **pg_transform** | Contains type transformation rules. |
| **pg_trigger** | Stores trigger metadata. |
| **pg_ts_config** | Contains text search configuration metadata. |
| **pg_ts_config_map** | Stores mappings for text search configurations. |
| **pg_ts_dict** | Contains text search dictionary metadata. |
| **pg_ts_parser** | Stores text search parser metadata. |
| **pg_ts_template** | Contains text search template metadata. |
| **pg_type** | Stores data type metadata. |
| **pg_user_mapping** | Manages user mappings for foreign data wrappers. |

## References
For more details, visit the [PostgreSQL System Catalogs Documentation](https://www.postgresql.org/docs/current/catalogs.html).



#### pg_aggregate (Stores information about aggregate functions)

| Column Name        | Description |
|--------------------|-------------|
| aggfnoid          | OID of the aggregate function (references pg_proc.oid) |
| aggkind           | Type of aggregate: n (normal), o (ordered-set), h (hypothetical-set) |
| aggnumdirectargs  | Number of direct (non-aggregated) arguments |
| aggtransfn        | Transition function (references pg_proc.oid) |
| aggfinalfn        | Final function (references pg_proc.oid) |
| aggcombinefn      | Combine function (references pg_proc.oid) |
| aggserialfn       | Serialization function (references pg_proc.oid) |
| aggdeserialfn     | Deserialization function (references pg_proc.oid) |
| aggtranstype      | Data type of the aggregate function's internal transition state |
| aggtransspace     | Approximate average size (in bytes) of the transition state data |

#### pg_am (Stores information about relation access methods)

| Column Name | Description |
|------------|-------------|
| oid        | Row identifier |
| amname     | Name of the access method |
| amhandler  | OID of a handler function responsible for supplying information about the access method |
| amtype     | Type of access method: t (table), i (index) |

#### pg_amop (Stores operators associated with access method operator families)

| Column Name    | Description |
|---------------|-------------|
| amopfamily    | The operator family this entry is for (references pg_opfamily.oid) |
| amoplefttype  | Left-hand input data type of operator (references pg_type.oid) |
| amoprighttype | Right-hand input data type of operator (references pg_type.oid) |
| amopstrategy  | Operator strategy number |
| amoppurpose   | Operator purpose: s (search), o (ordering) |
| amopopr       | OID of the operator (references pg_operator.oid) |
| amopmethod    | Index access method operator family is for (references pg_am.oid) |

#### pg_attrdef (Stores default values for table columns)

| Column Name | Description |
|------------|-------------|
| oid        | Unique identifier for the default value entry. |
| adrelid    | OID of the table the column belongs to (references pg_class.oid). |
| adnum      | Column number (matches the position in the table). |
| adbin      | Internal representation of the default expression for the column. |

#### pg_attribute (Stores metadata about table columns)

| Column Name  | Description |
|-------------|-------------|
| attrelid    | OID of the table this column belongs to (references pg_class.oid). |
| attname     | Name of the column. |
| atttypid    | OID of the data type for this column (references pg_type.oid). |
| attlen      | Length of the data type (for fixed-length types). |
| attnum      | Column number (order within the table). |
| attisdropped | Whether the column is dropped (TRUE or FALSE). |
| attnotnull  | Whether the column has a NOT NULL constraint. |

#### pg_authid (Stores user authentication details)

| Column Name   | Description |
|--------------|-------------|
| oid          | Unique identifier for the role. |
| rolname      | Name of the role (user or group). |
| rolsuper     | Indicates if the role has superuser privileges (TRUE or FALSE). |
| rolinherit   | Whether the role inherits privileges (TRUE or FALSE). |
| rolcreaterole | Whether the role can create new roles. |
| rolcreatedb  | Whether the role can create new databases. |
| rolcanlogin  | Whether the role can log in. |

#### pg_auth_members (Stores role membership relations)

| Column Name      | Type  | Description |
|-----------------|------|-------------|
| roleid         | oid  | ID of a role that has a member |
| member         | oid  | ID of a role that is a member of roleid |
| grantor        | oid  | ID of the role that granted this membership |
| admin_option   | bool | True if the member can grant membership in roleid to others |
| inherit_option | bool | True if the member automatically inherits the privileges of the granted role |
| set_option     | bool | True if the member can SET ROLE to the granted role |

#### pg_cast (Stores data type conversion paths)

| Column Name  | Type  | Description |
|-------------|------|-------------|
| castsource  | oid  | OID of the source data type |
| casttarget  | oid  | OID of the target data type |
| castfunc    | oid  | OID of the function used for the cast (zero if not required) |
| castcontext | char | Contexts where the cast can be invoked (e = explicit, a = assignment, i = implicit) |
| castmethod  | char | How the cast is performed (f = function, i = input/output, b = binary coercible) |

#### pg_class (Describes tables, indexes, sequences, views, and other relations)

| Column Name    | Type   | Description |
|--------------|-------|-------------|
| relname      | name  | Name of the relation |
| relnamespace | oid   | Namespace containing this relation |
| reltype      | oid   | Data type corresponding to this table's row type |
| relowner     | oid   | Owner of the relation |
| relam        | oid   | Access method used for this table or index |
| relfilenode  | oid   | On-disk file name of this relation |
| reltablespace| oid   | Tablespace where this relation is stored |
| relpages     | int4  | Estimated size of the table in pages |
| reltuples    | float4| Estimated number of live rows in the table |
| reltoastrelid| oid   | OID of the TOAST table associated with this table (zero if none) |

#### pg_collation (Describes available collations)

| Column Name   | Description |
|--------------|-------------|
| collname     | Collation name (unique per namespace and encoding) |
| collprovider | Provider of the collation (d = database default, b = builtin, c = libc, i = ICU) |
| collencoding | Encoding in which the collation is applicable |
| collcollate  | LC_COLLATE for this collation object |

#### pg_constraint (Stores constraints on tables and domains)

| Column Name    | Description |
|--------------|-------------|
| conname      | Constraint name |
| contype      | Constraint type (c = check, f = foreign key, p = primary key, u = unique, x = exclusion) |
| condeferrable | Whether the constraint is deferrable |
| convalidated  | Whether the constraint has been validated |

#### pg_conversion (Describes encoding conversion functions)

| Column Name    | Description |
|--------------|-------------|
| conname      | Conversion name |
| conforencoding | Source encoding ID |
| contoencoding  | Destination encoding ID |
| conproc       | Conversion function |

#### pg_database (Stores information about available databases)

| Column Name  | Description |
|-------------|-------------|
| datname     | Database name |
| datdba      | Owner of the database |
| encoding    | Character encoding for the database |
| datcollate  | LC_COLLATE for the database |

#### pg_db_role_setting (Records default values for runtime configuration variables)

| Column Name  | Description |
|-------------|-------------|
| setdatabase | OID of the database the setting applies to |
| setrole     | OID of the role the setting applies to |
| setconfig   | Defaults for runtime configuration variables |

#### pg_default_acl (Stores initial privileges for newly created objects)

| Column Name      | Type     | Description |
|-----------------|---------|-------------|
| oid            | oid     | Row identifier |
| defaclrole     | oid     | Role associated with this entry (references pg_authid.oid) |
| defaclnamespace | oid     | Namespace associated with this entry (references pg_namespace.oid) |
| defaclobjtype  | char    | Type of object (r = relation, S = sequence, f = function, T = type, n = schema) |
| defaclacl      | aclitem[] | Access privileges assigned on creation |

#### pg_depend (Tracks dependencies between database objects)

| Column Name   | Type  | Description |
|--------------|------|-------------|
| classid      | oid  | OID of the system catalog containing the dependent object (references pg_class.oid) |
| objid        | oid  | OID of the specific dependent object |
| objsubid     | int4 | Column number if the object is a table column, otherwise zero |
| refclassid   | oid  | OID of the system catalog containing the referenced object (references pg_class.oid) |
| refobjid     | oid  | OID of the specific referenced object |
| refobjsubid  | int4 | Column number if the referenced object is a table column, otherwise zero |
| deptype      | char | Dependency type (n = normal, a = auto, i = internal) |

#### pg_description (Stores optional descriptions for database objects)

| Column Name  | Type  | Description |
|-------------|------|-------------|
| objoid      | oid  | OID of the object being described |
| classoid    | oid  | OID of the system catalog containing the object (references pg_class.oid) |
| objsubid    | int4 | Column number if the object is a table column, otherwise zero |
| description | text | Text description of the object |

#### pg_enum (Stores values and labels for enum types)

| Column Name   | Type   | Description |
|--------------|-------|-------------|
| oid          | oid   | Row identifier |
| enumtypid    | oid   | OID of the enum type (references pg_type.oid) |
| enumsortorder | float4 | Sort position of this enum value within its type |
| enumlabel    | name  | Textual label for this enum value |

#### pg_event_trigger (Stores event triggers)

| Column Name  | Type  | Description |
|-------------|------|-------------|
| oid         | oid  | Row identifier |
| evtname     | name | Unique name of the event trigger |
| evtevent    | name | Event type for which the trigger fires |
| evtowner    | oid  | Owner of the event trigger (references pg_authid.oid) |
| evtfoid     | oid  | Function to be called (references pg_proc.oid) |
| evtenabled  | char | Trigger firing mode (O = origin, D = disabled, R = replica, A = always) |
| evttags     | text[] | Command tags for which this trigger fires |

#### pg_extension (Stores metadata about installed extensions)

| Column Name   | Type  | Description |
|--------------|------|-------------|
| oid          | oid  | Row identifier |
| extname      | name | Name of the extension |
| extowner     | oid  | Owner of the extension (references pg_authid.oid) |
| extnamespace | oid  | Schema containing the extension's objects (references pg_namespace.oid) |
| extrelocatable | bool | Whether the extension can be relocated to another schema |
| extversion   | text | Version name of the extension |
| extconfig    | oid[] | Array of OIDs for the extension's configuration tables |
| extcondition | text[] | Array of WHERE-clause filter conditions for the extension's configuration tables |

#### pg_foreign_data_wrapper (Stores foreign-data wrapper definitions)

| Column Name  | Type  | Description |
|-------------|------|-------------|
| oid         | oid  | Row identifier |
| fdwname     | name | Name of the foreign-data wrapper |
| fdwowner    | oid  | Owner of the foreign-data wrapper (references pg_authid.oid) |
| fdwhandler  | oid  | Handler function responsible for execution routines (references pg_proc.oid) |
| fdwvalidator | oid | Validator function for checking options (references pg_proc.oid) |
| fdwacl      | aclitem[] | Access privileges |
| fdwoptions  | text[] | Foreign-data wrapper specific options |

#### pg_foreign_server (Stores foreign server definitions)

| Column Name | Type  | Description |
|------------|------|-------------|
| oid        | oid  | Row identifier |
| srvname    | name | Name of the foreign server |
| srvowner   | oid  | Owner of the foreign server (references pg_authid.oid) |
| srvfdw     | oid  | OID of the foreign-data wrapper (references pg_foreign_data_wrapper.oid) |
| srvtype    | text | Type of the server (optional) |
| srvversion | text | Version of the server (optional) |
| srvacl     | aclitem[] | Access privileges |
| srvoptions | text[] | Foreign server specific options |

#### pg_foreign_table (Stores metadata about foreign tables)

| Column Name | Type  | Description |
|------------|------|-------------|
| ftrelid    | oid  | OID of the foreign table (references pg_class.oid) |
| ftserver   | oid  | OID of the foreign server (references pg_foreign_server.oid) |
| ftoptions  | text[] | Foreign table options |

#### pg_index (Stores metadata about indexes)

| Column Name             | Type   | Description |
|------------------------|-------|-------------|
| indexrelid            | oid   | OID of the index (references pg_class.oid) |
| indrelid              | oid   | OID of the table the index is for (references pg_class.oid) |
| indnatts              | int2  | Total number of columns in the index |
| indnkeyatts           | int2  | Number of key columns in the index |
| indisunique           | bool  | Whether the index is unique |
| indnullsnotdistinct   | bool  | Whether null values are considered distinct |
| indisprimary          | bool  | Whether the index represents the primary key |
| indisexclusion        | bool  | Whether the index supports an exclusion constraint |
| indimmediate          | bool  | Whether uniqueness is enforced immediately |
| indisclustered        | bool  | Whether the table was last clustered on this index |
| indisvalid            | bool  | Whether the index is currently valid for queries |

#### pg_inherits (Stores table inheritance relationships)

| Column Name        | Type  | Description |
|-------------------|------|-------------|
| inhrelid        | oid  | OID of the child table or index (references pg_class.oid) |
| inhparent       | oid  | OID of the parent table or index (references pg_class.oid) |
| inhseqno        | int4 | Order of inherited columns (starts at 1) |
| inhdetachpending | bool | TRUE if partition is in the process of being detached |

#### pg_language (Stores procedural languages)

| Column Name  | Type  | Description |
|-------------|------|-------------|
| oid         | oid  | Row identifier |
| lanname     | name | Name of the language |
| lanowner    | oid  | Owner of the language (references pg_authid.oid) |
| lanispl     | bool | TRUE for user-defined languages, FALSE for internal languages |
| lanpltrusted | bool | TRUE if the language is trusted |
| lanplcallfoid | oid  | Function responsible for executing functions in this language |
| laninline   | oid  | Function for executing inline anonymous code blocks |
| lanvalidator | oid  | Function for validating syntax of new functions |
| lanacl      | aclitem[] | Access privileges |

#### pg_largeobject (Stores large object data)

| Column Name | Type  | Description |
|------------|------|-------------|
| loid       | oid  | Identifier of the large object |
| pageno     | int4 | Page number within the large object |
| data       | bytea | Actual data stored in the large object |

#### pg_namespace (Stores schema information)

| Column Name | Type  | Description |
|------------|------|-------------|
| oid        | oid  | Row identifier |
| nspname    | name | Name of the schema |
| nspowner   | oid  | Owner of the schema (references pg_authid.oid) |
| nspacl     | aclitem[] | Access privileges |

#### pg_proc (Stores function and procedure metadata)

| Column Name    | Type   | Description |
|--------------|-------|-------------|
| oid          | oid   | Row identifier |
| proname      | name  | Name of the function |
| pronamespace | oid   | Namespace containing the function |
| proowner     | oid   | Owner of the function |
| prolang      | oid   | Language used for the function |
| procost      | float4 | Estimated execution cost |
| prorows      | float4 | Estimated number of result rows |
| provariadic  | oid   | Data type of variadic parameter elements |
| prokind      | char  | Function type (f = normal, p = procedure, a = aggregate, w = window) |
