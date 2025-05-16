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
