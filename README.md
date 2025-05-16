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


