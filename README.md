# ansible-role-etherpad


[![Build Status](https://travis-ci.org/systemli/ansible-role-etherpad.svg)](https://travis-ci.org/systemli/ansible-role-etherpad) [![Ansible Galaxy](http://img.shields.io/badge/ansible--galaxy-etherpad-blue.svg)](https://galaxy.ansible.com/systemli/etherpad/)

Role to install & maintain Etherpad Lite.

## Role Variables

The playbook requires special configuration. You must set the `etherpad_api_key`!

Defaults:

    etherpad_required_packages:
      - curl
      - git
    etherpad_repository: "https://github.com/ether/etherpad-lite.git"
    etherpad_repository_key_file: ""
    etherpad_repository_version: "master"
    etherpad_user: "etherpad"
    etherpad_group: "{{ etherpad_user }}"
    etherpad_home: "/home/etherpad"
    etherpad_path: "{{ etherpad_home }}/etherpad-lite"
    etherpad_console_path: "{{ etherpad_home }}/etherpad-lite-console"
    etherpad_console_purge_delay: 30
    etherpad_console_purge_enabled: False
    etherpad_title: "Etherpad"
    etherpad_favicon: "favicon.ico"
    etherpad_ip: 0.0.0.0
    etherpad_port: 9001
    etherpad_ssl_enabled: False
    etherpad_ssl_key: "/path-to-your/epl-server.key"
    etherpad_ssl_cert: "/path-to-your/epl-server.crt"
    etherpad_ssl_ca_intermediate_cert1: "/path-to-your/epl-intermediate-cert1.crt"
    etherpad_ssl_ca_intermediate_cert2: "/path-to-your/epl-intermediate-cert2.crt"
    etherpad_db_type: dirty
    etherpad_users: []
    #  -
    #    name: admin
    #    password: ""
    #    is_admin: "true"
    etherpad_api_key: ""
    etherpad_session_key: "Y7sc5qSXw5aEBIDGsjfkyLJDV"
    etherpad_disable_ip_logging: "true"
    etherpad_default_text: '"Welcome to Etherpad!\\n\\nThis pad text is synchronized as you type, so that everyone viewing this page sees the same text. This allows you to collaborate seamlessly on documents!\\n\\nGet involved with Etherpad at http:\\/\\/etherpad.org\\n"'
    etherpad_pad_options_no_colors: "false"
    etherpad_pad_options_show_controls: "true"
    etherpad_pad_options_show_chat: "true"
    etherpad_pad_options_show_line_numbers: "true"
    etherpad_pad_options_use_monospace_font: "false"
    etherpad_pad_options_user_name: "false"
    etherpad_pad_options_user_color: "false"
    etherpad_pad_options_rtl: "false"
    etherpad_pad_options_always_show_chat: "false"
    etherpad_pad_options_chat_and_users: "false"
    etherpad_pad_options_lang: "en-gb"
    etherpad_suppress_errors_in_pad_text: "false"
    etherpad_require_session: "false"
    etherpad_edit_only: "false"
    etherpad_session_no_password: "false"
    etherpad_minify: "true"
    etherpad_max_age: 21600
    etherpad_abiword: "null"
    etherpad_soffice: "null"
    etherpad_tidyhtml: "null"
    etherpad_allow_unknown_file_ends: "true"
    etherpad_require_authentication: "false"
    etherpad_require_authorization: "false"
    etherpad_trust_proxy: "false"
    etherpad_socket_transport_protocols: ["xhr-polling", "jsonp-polling", "htmlfile"]
    etherpad_load_test: "false"
    etherpad_indentation_on_new_line: "false"
    etherpad_toolbar:
      left:
        - ["bold", "italic", "underline", "strikethrough"]
        - ["orderedlist", "unorderedlist", "indent", "outdent"]
        - ["undo", "redo"]
        - ["clearauthorship"]
      right:
        - ["importexport", "timeslider", "savedrevision"]
        - ["settings", "embed"]
        - ["showusers"]
      timeslider:
        - ["timeslider_export", "timeslider_returnToPad"]
    etherpad_log_level: "INFO"
    etherpad_log_appenders:
      -
        type: console
    #  -
    #    type: file
    #    filename: your-log-file-here.log
    #    maxLogSize: 1024
    #    backups: 3
    etherpad_console_enabled: False
    etherpad_monit_enabled: False
    # list of etherpad plugins to be installed
    etherpad_plugins: []
    
    # Redis settings
    etherpad_redis_host: localhost
    etherpad_redis_port: 6379
    etherpad_redis_database: 0
    
    # MySQL settings
    etherpad_mysql_database_host: localhost
    etherpad_mysql_database_name: etherpad
    etherpad_mysql_database_user: etherpad
    etherpad_mysql_database_password:
    etherpad_mysql_database_port: 3306
    # Recommendation for large setups is MyISAM
    etherpad_mysql_database_engine: InnoDB
    etherpad_mysql_database_collation: utf8mb4_bin
    etherpad_mysql_database_charset: utf8mb4
    
    # Dirty settings
    etherpad_dirty_filename: "var/dirty.db"

## Dependencies

 * geerlingguy.nodejs

## Example Playbook

    - hosts: servers
      roles:
         - { role: systemli.etherpad }

Tests
-----

For developing and testing the role we use Travis CI, Molecule and Vagrant. On the local environment you can easily test the role with

Run local tests with:

```
molecule test 
```

Requires Molecule, Vagrant and `python-vagrant` to be installed.For developing and testing the role we use Travis CI, Molecule and Vagrant. On the local environment you can easily test the role with


## License

GPLv3

## Author Information

https://www.systemli.org
