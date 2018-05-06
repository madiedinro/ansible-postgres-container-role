


# Asible role base server OS configuration (Ubuntu)

## Usage

Add to ansible playbook following:

    - import_role:
        name: dr.postgres-container
      vars:
        pg_docker_service: '{{def_postgres_service}}'
        pg_docker_net_name: '{{def_docker_net_name}}'
        pg_docker_bind_ip: '{{def_docker_ip}}'
        pg_docker_pass: '{{hst_postgres_pass}}'
        #  - {name: dbname}
        pg_docker_dbs: '{{hst_postgres_dbs}}'
        #  - {name: username, pass: userpass, db: db, flags: CREATEDB,SUPERUSER}
        pg_docker_users: '{{hst_postgres_users}}'
      when: hst_setup_pg is defined and hst_setup_pg == true
      tags: ['postgres']


## Default parameters

Discover in `defaults/main.yml`
