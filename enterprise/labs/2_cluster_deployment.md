# Cloudera Manager API Result
```
curl -u admin:****  http://node01.sebc:7180/api/v2/cm/deployment
```

```
{
  "timestamp" : "2017-06-07T10:28:25.397Z",
  "clusters" : [ {
    "name" : "Xefke",
    "version" : "CDH5",
    "services" : [ {
      "name" : "hive",
      "type" : "HIVE",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "HIVEMETASTORE",
          "items" : [ {
            "name" : "hive_metastore_java_heapsize",
            "value" : "612368384"
          } ]
        }, {
          "roleType" : "HIVESERVER2",
          "items" : [ {
            "name" : "hiveserver2_java_heapsize",
            "value" : "612368384"
          }, {
            "name" : "hiveserver2_spark_driver_memory",
            "value" : "966367641"
          }, {
            "name" : "hiveserver2_spark_executor_cores",
            "value" : "4"
          }, {
            "name" : "hiveserver2_spark_executor_memory",
            "value" : "2380634521"
          }, {
            "name" : "hiveserver2_spark_yarn_driver_memory_overhead",
            "value" : "102"
          }, {
            "name" : "hiveserver2_spark_yarn_executor_memory_overhead",
            "value" : "400"
          } ]
        } ],
        "items" : [ {
          "name" : "hive_metastore_database_host",
          "value" : "node01.sebc"
        }, {
          "name" : "hive_metastore_database_password",
          "value" : "hivepw"
        }, {
          "name" : "mapreduce_yarn_service",
          "value" : "yarn"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hive-GATEWAY-34b61e7bd52c4d186139352c278cdb95",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "i-0f55d85cfd0ec791a"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-4de095a05b50c14a2a5c5d6bc96aa0d5",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "i-0ffd09518881c85eb"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-77333a17d553cc66cc48fce1542f303b",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "i-04feb7da391ec2d22"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-dca9179fe1e9628a9f467181cc5ff239",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "i-02ae373c52e0c99bc"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-ef8298bc7f39a0f72b7fe1dddc6f9184",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "i-06e2b096a7c6013e3"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-HIVEMETASTORE-77333a17d553cc66cc48fce1542f303b",
        "type" : "HIVEMETASTORE",
        "hostRef" : {
          "hostId" : "i-04feb7da391ec2d22"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "azl4sq20wpi6jqlfvaft8jhru"
          } ]
        }
      }, {
        "name" : "hive-HIVESERVER2-77333a17d553cc66cc48fce1542f303b",
        "type" : "HIVESERVER2",
        "hostRef" : {
          "hostId" : "i-04feb7da391ec2d22"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "876y9dilzz8b25sc5bx9knsdt"
          } ]
        }
      } ],
      "displayName" : "Hive"
    }, {
      "name" : "zookeeper",
      "type" : "ZOOKEEPER",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "SERVER",
          "items" : [ {
            "name" : "zookeeper_server_java_heapsize",
            "value" : "612368384"
          } ]
        } ],
        "items" : [ ]
      },
      "roles" : [ {
        "name" : "zookeeper-SERVER-34b61e7bd52c4d186139352c278cdb95",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "i-0f55d85cfd0ec791a"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "9ezr3r3uv7ejdzqgwl9hp53ak"
          }, {
            "name" : "serverId",
            "value" : "2"
          } ]
        }
      }, {
        "name" : "zookeeper-SERVER-77333a17d553cc66cc48fce1542f303b",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "i-04feb7da391ec2d22"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "b33b4bgdbhqk394qxzugbbsz6"
          }, {
            "name" : "serverId",
            "value" : "3"
          } ]
        }
      }, {
        "name" : "zookeeper-SERVER-dca9179fe1e9628a9f467181cc5ff239",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "i-02ae373c52e0c99bc"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "16xmryhh4u9tygl9tqvbl484a"
          }, {
            "name" : "serverId",
            "value" : "1"
          } ]
        }
      } ],
      "displayName" : "ZooKeeper"
    }, {
      "name" : "hue",
      "type" : "HUE",
      "config" : {
        "roleTypeConfigs" : [ ],
        "items" : [ {
          "name" : "database_host",
          "value" : "node01.sebc"
        }, {
          "name" : "database_password",
          "value" : "huepw"
        }, {
          "name" : "database_type",
          "value" : "mysql"
        }, {
          "name" : "hive_service",
          "value" : "hive"
        }, {
          "name" : "hue_webhdfs",
          "value" : "hdfs-NAMENODE-77333a17d553cc66cc48fce1542f303b"
        }, {
          "name" : "oozie_service",
          "value" : "oozie"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hue-HUE_SERVER-77333a17d553cc66cc48fce1542f303b",
        "type" : "HUE_SERVER",
        "hostRef" : {
          "hostId" : "i-04feb7da391ec2d22"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "582y1h7v2euabkltg0jctb7av"
          }, {
            "name" : "secret_key",
            "value" : "7VbUejZkcXwhJQErEXjGkRvqzRGLaD"
          } ]
        }
      } ],
      "displayName" : "Hue"
    }, {
      "name" : "oozie",
      "type" : "OOZIE",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "OOZIE_SERVER",
          "items" : [ {
            "name" : "oozie_database_host",
            "value" : "node01.sebc"
          }, {
            "name" : "oozie_database_password",
            "value" : "ooziepw"
          }, {
            "name" : "oozie_database_type",
            "value" : "mysql"
          }, {
            "name" : "oozie_database_user",
            "value" : "oozie"
          }, {
            "name" : "oozie_java_heapsize",
            "value" : "612368384"
          } ]
        } ],
        "items" : [ {
          "name" : "hive_service",
          "value" : "hive"
        }, {
          "name" : "mapreduce_yarn_service",
          "value" : "yarn"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "oozie-OOZIE_SERVER-77333a17d553cc66cc48fce1542f303b",
        "type" : "OOZIE_SERVER",
        "hostRef" : {
          "hostId" : "i-04feb7da391ec2d22"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "4ozy9in8fuoqlceih361bmopa"
          } ]
        }
      } ],
      "displayName" : "Oozie"
    }, {
      "name" : "yarn",
      "type" : "YARN",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "GATEWAY",
          "items" : [ {
            "name" : "mapred_reduce_tasks",
            "value" : "8"
          }, {
            "name" : "mapred_submit_replication",
            "value" : "2"
          } ]
        }, {
          "roleType" : "JOBHISTORY",
          "items" : [ {
            "name" : "mr2_jobhistory_java_heapsize",
            "value" : "612368384"
          } ]
        }, {
          "roleType" : "NODEMANAGER",
          "items" : [ {
            "name" : "rm_cpu_shares",
            "value" : "1800"
          }, {
            "name" : "rm_io_weight",
            "value" : "900"
          }, {
            "name" : "yarn_nodemanager_heartbeat_interval_ms",
            "value" : "100"
          }, {
            "name" : "yarn_nodemanager_local_dirs",
            "value" : "/yarn/nm"
          }, {
            "name" : "yarn_nodemanager_log_dirs",
            "value" : "/yarn/container-logs"
          }, {
            "name" : "yarn_nodemanager_resource_cpu_vcores",
            "value" : "3"
          }, {
            "name" : "yarn_nodemanager_resource_memory_mb",
            "value" : "5250"
          } ]
        }, {
          "roleType" : "RESOURCEMANAGER",
          "items" : [ {
            "name" : "resource_manager_java_heapsize",
            "value" : "612368384"
          }, {
            "name" : "yarn_scheduler_maximum_allocation_mb",
            "value" : "5250"
          }, {
            "name" : "yarn_scheduler_maximum_allocation_vcores",
            "value" : "3"
          } ]
        } ],
        "items" : [ {
          "name" : "hdfs_service",
          "value" : "hdfs"
        }, {
          "name" : "rm_dirty",
          "value" : "false"
        }, {
          "name" : "rm_last_allocation_percentage",
          "value" : "90"
        }, {
          "name" : "yarn_service_cgroups",
          "value" : "false"
        }, {
          "name" : "yarn_service_lce_always",
          "value" : "false"
        }, {
          "name" : "zk_authorization_secret_key",
          "value" : "OuHsup0Eii4DzX8mOWpy9fosrxARhj"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "yarn-JOBHISTORY-77333a17d553cc66cc48fce1542f303b",
        "type" : "JOBHISTORY",
        "hostRef" : {
          "hostId" : "i-04feb7da391ec2d22"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "4i76k71nitc0z5plse9b6to50"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-34b61e7bd52c4d186139352c278cdb95",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "i-0f55d85cfd0ec791a"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "6v7mr8ombg4jzo5ssh10anwdj"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-4de095a05b50c14a2a5c5d6bc96aa0d5",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "i-0ffd09518881c85eb"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "bm4988j4ja57v8yxq28owjrvo"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-dca9179fe1e9628a9f467181cc5ff239",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "i-02ae373c52e0c99bc"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "5du58bjnixcabgtuaywjz1tmw"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-ef8298bc7f39a0f72b7fe1dddc6f9184",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "i-06e2b096a7c6013e3"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "3qf24iuzt99ot865zn7bxpa4i"
          } ]
        }
      }, {
        "name" : "yarn-RESOURCEMANAGER-77333a17d553cc66cc48fce1542f303b",
        "type" : "RESOURCEMANAGER",
        "hostRef" : {
          "hostId" : "i-04feb7da391ec2d22"
        },
        "config" : {
          "items" : [ {
            "name" : "rm_id",
            "value" : "55"
          }, {
            "name" : "role_jceks_password",
            "value" : "9bc5zd3sgtm0a24t93ci6h1ui"
          } ]
        }
      } ],
      "displayName" : "YARN (MR2 Included)"
    }, {
      "name" : "hdfs",
      "type" : "HDFS",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "BALANCER",
          "items" : [ {
            "name" : "balancer_java_heapsize",
            "value" : "612368384"
          } ]
        }, {
          "roleType" : "DATANODE",
          "items" : [ {
            "name" : "datanode_java_heapsize",
            "value" : "1073741824"
          }, {
            "name" : "dfs_data_dir_list",
            "value" : "/dfs/dn"
          }, {
            "name" : "dfs_datanode_max_locked_memory",
            "value" : "4294967296"
          }, {
            "name" : "rm_cpu_shares",
            "value" : "200"
          }, {
            "name" : "rm_io_weight",
            "value" : "100"
          } ]
        }, {
          "roleType" : "GATEWAY",
          "items" : [ {
            "name" : "dfs_client_use_trash",
            "value" : "true"
          } ]
        }, {
          "roleType" : "NAMENODE",
          "items" : [ {
            "name" : "dfs_name_dir_list",
            "value" : "/dfs/nn"
          }, {
            "name" : "dfs_namenode_servicerpc_address",
            "value" : "8022"
          }, {
            "name" : "namenode_java_heapsize",
            "value" : "612368384"
          } ]
        }, {
          "roleType" : "SECONDARYNAMENODE",
          "items" : [ {
            "name" : "fs_checkpoint_dir_list",
            "value" : "/dfs/snn"
          }, {
            "name" : "secondary_namenode_java_heapsize",
            "value" : "612368384"
          } ]
        } ],
        "items" : [ {
          "name" : "dfs_ha_fencing_cloudera_manager_secret_key",
          "value" : "7L6cbLIXB3dpdlvofAdwpHFnPkVwGk"
        }, {
          "name" : "fc_authorization_secret_key",
          "value" : "jBhoBWH2qhRDH12u7hpK4dup6lo5rZ"
        }, {
          "name" : "http_auth_signature_secret",
          "value" : "ia2SZrDa1vdrTPYwlFGvMIfeFmS7wO"
        }, {
          "name" : "rm_dirty",
          "value" : "false"
        }, {
          "name" : "rm_last_allocation_percentage",
          "value" : "10"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hdfs-BALANCER-77333a17d553cc66cc48fce1542f303b",
        "type" : "BALANCER",
        "hostRef" : {
          "hostId" : "i-04feb7da391ec2d22"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hdfs-DATANODE-34b61e7bd52c4d186139352c278cdb95",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "i-0f55d85cfd0ec791a"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "6xc657m07otmju8br1qfcvpjb"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-4de095a05b50c14a2a5c5d6bc96aa0d5",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "i-0ffd09518881c85eb"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "etb7lnpy831uw5qtjyi2p5ol5"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-dca9179fe1e9628a9f467181cc5ff239",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "i-02ae373c52e0c99bc"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "c0cebvavjvo990bi1r9vja3hv"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-ef8298bc7f39a0f72b7fe1dddc6f9184",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "i-06e2b096a7c6013e3"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "5ccen7fmsl8ziainhw0n2mmhb"
          } ]
        }
      }, {
        "name" : "hdfs-NAMENODE-77333a17d553cc66cc48fce1542f303b",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "i-04feb7da391ec2d22"
        },
        "config" : {
          "items" : [ {
            "name" : "namenode_id",
            "value" : "57"
          }, {
            "name" : "role_jceks_password",
            "value" : "akzc0439p0adwxrfleb10xshy"
          } ]
        }
      }, {
        "name" : "hdfs-SECONDARYNAMENODE-34b61e7bd52c4d186139352c278cdb95",
        "type" : "SECONDARYNAMENODE",
        "hostRef" : {
          "hostId" : "i-0f55d85cfd0ec791a"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "19h9gdd45ohebzr77gjzzq24k"
          } ]
        }
      } ],
      "displayName" : "HDFS"
    } ]
  } ],
  "hosts" : [ {
    "hostId" : "i-04feb7da391ec2d22",
    "ipAddress" : "10.1.1.101",
    "hostname" : "node01.sebc",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "i-0f55d85cfd0ec791a",
    "ipAddress" : "10.1.1.102",
    "hostname" : "node02.sebc",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "i-02ae373c52e0c99bc",
    "ipAddress" : "10.1.1.103",
    "hostname" : "node03.sebc",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "i-06e2b096a7c6013e3",
    "ipAddress" : "10.1.1.104",
    "hostname" : "node04.sebc",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "i-0ffd09518881c85eb",
    "ipAddress" : "10.1.1.105",
    "hostname" : "node05.sebc",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  } ],
  "users" : [ {
    "name" : "__cloudera_internal_user__mgmt-ACTIVITYMONITOR-77333a17d553cc66cc48fce1542f303b",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "6e91ce01d44d62ca64b8663d1d4a9fd0d843146d0c1216ece3b0b538161069c8",
    "pwSalt" : 5144037847251159468,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-EVENTSERVER-77333a17d553cc66cc48fce1542f303b",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "ba3d5ea2aca73eb64a5dada9188b5aa5b5548eb3b8878bd7dc5b7520865e5153",
    "pwSalt" : 3665867280219398943,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-HOSTMONITOR-77333a17d553cc66cc48fce1542f303b",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "ddfd161edf7a78816fe1af706764f66b524825f94179cd95f70d028cd3daa0d0",
    "pwSalt" : 7320630045135936775,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-REPORTSMANAGER-77333a17d553cc66cc48fce1542f303b",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "ad311ead9931e5adaab1319f9869f3cbe12083ea9fbf198a9f96d8366d6e5ee6",
    "pwSalt" : -2675318054413726034,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-SERVICEMONITOR-77333a17d553cc66cc48fce1542f303b",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "de23bd61c800d8fd9a3c7d5421765c8f7ae570792db9da08302b242b36977a7e",
    "pwSalt" : -7958648379272064341,
    "pwLogin" : true
  }, {
    "name" : "admin",
    "roles" : [ "ROLE_ADMIN" ],
    "pwHash" : "c8a5b2e18e304f8d1a98e16a4821cd48976f6467e844f79bf9eb2c749100d58f",
    "pwSalt" : -6471596207124471212,
    "pwLogin" : true
  }, {
    "name" : "minotaur",
    "roles" : [ "ROLE_CONFIGURATOR" ],
    "pwHash" : "8d76f2b568ff32522ec087d5f6ceac329cfaaabe31ba04a0d9378f9300a1fe43",
    "pwSalt" : 3741307409339433835,
    "pwLogin" : true
  } ],
  "versionInfo" : {
    "version" : "5.8.3",
    "buildUser" : "jenkins",
    "buildTimestamp" : "20161019-1014",
    "gitHash" : "518f0d6d44abc87bc392646e4369a20c8192b7cf",
    "snapshot" : false
  },
  "managementService" : {
    "name" : "mgmt",
    "type" : "MGMT",
    "config" : {
      "roleTypeConfigs" : [ {
        "roleType" : "ACTIVITYMONITOR",
        "items" : [ {
          "name" : "firehose_database_host",
          "value" : "node01.sebc"
        }, {
          "name" : "firehose_database_name",
          "value" : "amon"
        }, {
          "name" : "firehose_database_password",
          "value" : "amonpw"
        }, {
          "name" : "firehose_database_user",
          "value" : "amon"
        }, {
          "name" : "firehose_heapsize",
          "value" : "612368384"
        } ]
      }, {
        "roleType" : "EVENTSERVER",
        "items" : [ {
          "name" : "event_server_heapsize",
          "value" : "612368384"
        } ]
      }, {
        "roleType" : "HOSTMONITOR",
        "items" : [ {
          "name" : "firehose_heapsize",
          "value" : "612368384"
        }, {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "805306368"
        } ]
      }, {
        "roleType" : "REPORTSMANAGER",
        "items" : [ {
          "name" : "headlamp_database_host",
          "value" : "node01.sebc"
        }, {
          "name" : "headlamp_database_name",
          "value" : "rman"
        }, {
          "name" : "headlamp_database_password",
          "value" : "rmanpw"
        }, {
          "name" : "headlamp_database_user",
          "value" : "rman"
        }, {
          "name" : "headlamp_heapsize",
          "value" : "612368384"
        } ]
      }, {
        "roleType" : "SERVICEMONITOR",
        "items" : [ {
          "name" : "firehose_heapsize",
          "value" : "612368384"
        }, {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "805306368"
        } ]
      } ],
      "items" : [ ]
    },
    "roles" : [ {
      "name" : "mgmt-ACTIVITYMONITOR-77333a17d553cc66cc48fce1542f303b",
      "type" : "ACTIVITYMONITOR",
      "hostRef" : {
        "hostId" : "i-04feb7da391ec2d22"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "9tj67pnul11cpv29z48w0r6z4"
        } ]
      }
    }, {
      "name" : "mgmt-ALERTPUBLISHER-77333a17d553cc66cc48fce1542f303b",
      "type" : "ALERTPUBLISHER",
      "hostRef" : {
        "hostId" : "i-04feb7da391ec2d22"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "d5n53prciqx18pd9yfew6q1uu"
        } ]
      }
    }, {
      "name" : "mgmt-EVENTSERVER-77333a17d553cc66cc48fce1542f303b",
      "type" : "EVENTSERVER",
      "hostRef" : {
        "hostId" : "i-04feb7da391ec2d22"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "3nqvo9kkr2ck6yqbxi0jgp4qu"
        } ]
      }
    }, {
      "name" : "mgmt-HOSTMONITOR-77333a17d553cc66cc48fce1542f303b",
      "type" : "HOSTMONITOR",
      "hostRef" : {
        "hostId" : "i-04feb7da391ec2d22"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "79vbtazdnwt8onguhtrt5ffm8"
        } ]
      }
    }, {
      "name" : "mgmt-REPORTSMANAGER-77333a17d553cc66cc48fce1542f303b",
      "type" : "REPORTSMANAGER",
      "hostRef" : {
        "hostId" : "i-04feb7da391ec2d22"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "4vqvrl63iugbqzulngc2k7a2i"
        } ]
      }
    }, {
      "name" : "mgmt-SERVICEMONITOR-77333a17d553cc66cc48fce1542f303b",
      "type" : "SERVICEMONITOR",
      "hostRef" : {
        "hostId" : "i-04feb7da391ec2d22"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "2bxezqqkjclzezninyqbrfqxv"
        } ]
      }
    } ],
    "displayName" : "Cloudera Management Service"
  },
  "managerSettings" : {
    "items" : [ {
      "name" : "CLUSTER_STATS_START",
      "value" : "10/27/2012 18:10"
    }, {
      "name" : "PUBLIC_CLOUD_STATUS",
      "value" : "ON_PUBLIC_CLOUD"
    }, {
      "name" : "REMOTE_PARCEL_REPO_URLS",
      "value" : "https://archive.cloudera.com/cdh5/parcels/{latest_supported}/,https://archive.cloudera.com/cdh4/parcels/latest/,https://archive.cloudera.com/impala/parcels/latest/,https://archive.cloudera.com/search/parcels/latest/,https://archive.cloudera.com/accumulo/parcels/1.4/,https://archive.cloudera.com/accumulo-c5/parcels/latest/,https://archive.cloudera.com/kafka/parcels/latest/,https://archive.cloudera.com/navigator-keytrustee5/parcels/latest/,https://archive.cloudera.com/spark/parcels/latest/,https://archive.cloudera.com/sqoop-connectors/parcels/latest/"
    } ]
  }
}
```