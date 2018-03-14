# Use the CM API

## Query cluster deployment

```
    curl -u jovv:cloudera 'http://ec2-34-242-187-43.eu-west-1.compute.amazonaws.com:7180/api/v2/cm/deployment'
```

Output:

```
{
    "timestamp": "2018-03-14T09:41:39.881Z",
    "clusters": [
        {
            "name": "jovv",
            "version": "CDH5",
            "services": [
                {
                    "name": "zookeeper",
                    "type": "ZOOKEEPER",
                    "config": {
                        "roleTypeConfigs": [],
                        "items": []
                    },
                    "roles": [
                        {
                            "name": "zookeeper-SERVER-f0df28d0d5d07244a749a7c2503f529e",
                            "type": "SERVER",
                            "hostRef": {
                                "hostId": "i-06ff68cfabb384211"
                            },
                            "config": {
                                "items": [
                                    {
                                        "name": "role_jceks_password",
                                        "value": "d7qswfgxjpu9msq3bex89hv2v"
                                    },
                                    {
                                        "name": "serverId",
                                        "value": "3"
                                    }
                                ]
                            }
                        },
                        {
                            "name": "zookeeper-SERVER-fe1b5bc1941577e812004af799ef22ed",
                            "type": "SERVER",
                            "hostRef": {
                                "hostId": "i-053e3427d734e38ee"
                            },
                            "config": {
                                "items": [
                                    {
                                        "name": "role_jceks_password",
                                        "value": "1telxx86wa7wd02f8c993vh7a"
                                    },
                                    {
                                        "name": "serverId",
                                        "value": "1"
                                    }
                                ]
                            }
                        },
                        {
                            "name": "zookeeper-SERVER-fe936e0f763a8708d3e26e24d1692d02",
                            "type": "SERVER",
                            "hostRef": {
                                "hostId": "i-057f340038c217d67"
                            },
                            "config": {
                                "items": [
                                    {
                                        "name": "role_jceks_password",
                                        "value": "15c3tdqlhdubj9wfl6x8qonjw"
                                    },
                                    {
                                        "name": "serverId",
                                        "value": "2"
                                    }
                                ]
                            }
                        }
                    ],
                    "displayName": "ZooKeeper"
                },
                {
                    "name": "oozie",
                    "type": "OOZIE",
                    "config": {
                        "roleTypeConfigs": [
                            {
                                "roleType": "OOZIE_SERVER",
                                "items": [
                                    {
                                        "name": "oozie_database_host",
                                        "value": "ip-172-31-15-191.eu-west-1.compute.internal"
                                    },
                                    {
                                        "name": "oozie_database_password",
                                        "value": "oozie_password"
                                    },
                                    {
                                        "name": "oozie_database_type",
                                        "value": "mysql"
                                    },
                                    {
                                        "name": "oozie_database_user",
                                        "value": "oozie"
                                    }
                                ]
                            }
                        ],
                        "items": [
                            {
                                "name": "hive_service",
                                "value": "hive"
                            },
                            {
                                "name": "mapreduce_yarn_service",
                                "value": "yarn"
                            },
                            {
                                "name": "zookeeper_service",
                                "value": "zookeeper"
                            }
                        ]
                    },
                    "roles": [
                        {
                            "name": "oozie-OOZIE_SERVER-e50982cc167ab38c8ba06232e47269a3",
                            "type": "OOZIE_SERVER",
                            "hostRef": {
                                "hostId": "i-01b4409d49de9ad91"
                            },
                            "config": {
                                "items": [
                                    {
                                        "name": "role_jceks_password",
                                        "value": "24ersthmf3gx9dmhpig5w2g9z"
                                    }
                                ]
                            }
                        }
                    ],
                    "displayName": "Oozie"
                },
                {
                    "name": "hue",
                    "type": "HUE",
                    "config": {
                        "roleTypeConfigs": [],
                        "items": [
                            {
                                "name": "database_host",
                                "value": "ip-172-31-15-191.eu-west-1.compute.internal"
                            },
                            {
                                "name": "database_password",
                                "value": "hue_password"
                            },
                            {
                                "name": "database_type",
                                "value": "mysql"
                            },
                            {
                                "name": "hive_service",
                                "value": "hive"
                            },
                            {
                                "name": "hue_webhdfs",
                                "value": "hdfs-HTTPFS-e50982cc167ab38c8ba06232e47269a3"
                            },
                            {
                                "name": "oozie_service",
                                "value": "oozie"
                            },
                            {
                                "name": "zookeeper_service",
                                "value": "zookeeper"
                            }
                        ]
                    },
                    "roles": [
                        {
                            "name": "hue-HUE_SERVER-e50982cc167ab38c8ba06232e47269a3",
                            "type": "HUE_SERVER",
                            "hostRef": {
                                "hostId": "i-01b4409d49de9ad91"
                            },
                            "config": {
                                "items": [
                                    {
                                        "name": "role_jceks_password",
                                        "value": "27ny992y2pk7ndz85qzx5tyfe"
                                    },
                                    {
                                        "name": "secret_key",
                                        "value": "88UzeNciDeLN0nHMRVPtml1gI7J0VJ"
                                    }
                                ]
                            }
                        }
                    ],
                    "displayName": "Hue"
                },
                {
                    "name": "hdfs",
                    "type": "HDFS",
                    "config": {
                        "roleTypeConfigs": [
                            {
                                "roleType": "DATANODE",
                                "items": [
                                    {
                                        "name": "datanode_java_heapsize",
                                        "value": "1073741824"
                                    },
                                    {
                                        "name": "dfs_data_dir_list",
                                        "value": "/dfs/dn"
                                    },
                                    {
                                        "name": "dfs_datanode_du_reserved",
                                        "value": "5367448780"
                                    },
                                    {
                                        "name": "dfs_datanode_max_locked_memory",
                                        "value": "4294967296"
                                    },
                                    {
                                        "name": "rm_cpu_shares",
                                        "value": "400"
                                    },
                                    {
                                        "name": "rm_io_weight",
                                        "value": "200"
                                    }
                                ]
                            },
                            {
                                "roleType": "GATEWAY",
                                "items": [
                                    {
                                        "name": "dfs_client_use_trash",
                                        "value": "true"
                                    }
                                ]
                            },
                            {
                                "roleType": "JOURNALNODE",
                                "items": [
                                    {
                                        "name": "dfs_journalnode_edits_dir",
                                        "value": "/dfs/jn"
                                    }
                                ]
                            },
                            {
                                "roleType": "NAMENODE",
                                "items": [
                                    {
                                        "name": "dfs_name_dir_list",
                                        "value": "/dfs/nn"
                                    },
                                    {
                                        "name": "dfs_namenode_servicerpc_address",
                                        "value": "8022"
                                    },
                                    {
                                        "name": "namenode_java_heapsize",
                                        "value": "1073741824"
                                    }
                                ]
                            },
                            {
                                "roleType": "SECONDARYNAMENODE",
                                "items": [
                                    {
                                        "name": "fs_checkpoint_dir_list",
                                        "value": "/dfs/snn"
                                    },
                                    {
                                        "name": "secondary_namenode_java_heapsize",
                                        "value": "1073741824"
                                    }
                                ]
                            }
                        ],
                        "items": [
                            {
                                "name": "dfs_ha_fencing_cloudera_manager_secret_key",
                                "value": "387iZULCWNow7Np8L26l7ERuQdQqGw"
                            },
                            {
                                "name": "dfs_ha_fencing_methods",
                                "value": "shell(true)"
                            },
                            {
                                "name": "fc_authorization_secret_key",
                                "value": "Y7NiVN5X2o9ebNH7OXVuaMWE3FaQYF"
                            },
                            {
                                "name": "http_auth_signature_secret",
                                "value": "fY2HiAwhbQ4dFCYpn2lUVEbrFB0zG4"
                            },
                            {
                                "name": "rm_dirty",
                                "value": "false"
                            },
                            {
                                "name": "rm_last_allocation_percentage",
                                "value": "20"
                            },
                            {
                                "name": "zookeeper_service",
                                "value": "zookeeper"
                            }
                        ]
                    },
                    "roles": [
                        {
                            "name": "hdfs-BALANCER-e50982cc167ab38c8ba06232e47269a3",
                            "type": "BALANCER",
                            "hostRef": {
                                "hostId": "i-01b4409d49de9ad91"
                            },
                            "config": {
                                "items": []
                            }
                        },
                        {
                            "name": "hdfs-DATANODE-f0df28d0d5d07244a749a7c2503f529e",
                            "type": "DATANODE",
                            "hostRef": {
                                "hostId": "i-06ff68cfabb384211"
                            },
                            "config": {
                                "items": [
                                    {
                                        "name": "role_jceks_password",
                                        "value": "6a382vbrkwtfpg4l9awdgatvz"
                                    }
                                ]
                            }
                        },
                        {
                            "name": "hdfs-DATANODE-fe1b5bc1941577e812004af799ef22ed",
                            "type": "DATANODE",
                            "hostRef": {
                                "hostId": "i-053e3427d734e38ee"
                            },
                            "config": {
                                "items": [
                                    {
                                        "name": "role_jceks_password",
                                        "value": "6f14cw5diocyvc3542ihzh6u6"
                                    }
                                ]
                            }
                        },
                        {
                            "name": "hdfs-DATANODE-fe936e0f763a8708d3e26e24d1692d02",
                            "type": "DATANODE",
                            "hostRef": {
                                "hostId": "i-057f340038c217d67"
                            },
                            "config": {
                                "items": [
                                    {
                                        "name": "role_jceks_password",
                                        "value": "ee7h8yo9cpvgt5kvdd44qoxus"
                                    }
                                ]
                            }
                        },
                        {
                            "name": "hdfs-FAILOVERCONTROLLER-254aaba64f12b01bac320242644a9384",
                            "type": "FAILOVERCONTROLLER",
                            "hostRef": {
                                "hostId": "i-0062d7ef171235091"
                            },
                            "config": {
                                "items": [
                                    {
                                        "name": "role_jceks_password",
                                        "value": "9h2ym40mj51o0lh3as9id6pff"
                                    }
                                ]
                            }
                        },
                        {
                            "name": "hdfs-FAILOVERCONTROLLER-e50982cc167ab38c8ba06232e47269a3",
                            "type": "FAILOVERCONTROLLER",
                            "hostRef": {
                                "hostId": "i-01b4409d49de9ad91"
                            },
                            "config": {
                                "items": [
                                    {
                                        "name": "role_jceks_password",
                                        "value": "dfzxt4ijj1c4hyu2e7smarxb6"
                                    }
                                ]
                            }
                        },
                        {
                            "name": "hdfs-HTTPFS-e50982cc167ab38c8ba06232e47269a3",
                            "type": "HTTPFS",
                            "hostRef": {
                                "hostId": "i-01b4409d49de9ad91"
                            },
                            "config": {
                                "items": [
                                    {
                                        "name": "role_jceks_password",
                                        "value": "4h1t0dvc8muzje7yexnpg7a71"
                                    }
                                ]
                            }
                        },
                        {
                            "name": "hdfs-JOURNALNODE-f0df28d0d5d07244a749a7c2503f529e",
                            "type": "JOURNALNODE",
                            "hostRef": {
                                "hostId": "i-06ff68cfabb384211"
                            },
                            "config": {
                                "items": [
                                    {
                                        "name": "role_jceks_password",
                                        "value": "81vtewweo1cpuholwcn6ulgql"
                                    }
                                ]
                            }
                        },
                        {
                            "name": "hdfs-JOURNALNODE-fe1b5bc1941577e812004af799ef22ed",
                            "type": "JOURNALNODE",
                            "hostRef": {
                                "hostId": "i-053e3427d734e38ee"
                            },
                            "config": {
                                "items": [
                                    {
                                        "name": "role_jceks_password",
                                        "value": "33tpejwvauoi4ajwl2zah1f6s"
                                    }
                                ]
                            }
                        },
                        {
                            "name": "hdfs-JOURNALNODE-fe936e0f763a8708d3e26e24d1692d02",
                            "type": "JOURNALNODE",
                            "hostRef": {
                                "hostId": "i-057f340038c217d67"
                            },
                            "config": {
                                "items": [
                                    {
                                        "name": "role_jceks_password",
                                        "value": "5139sk90aqk3izscxites75m6"
                                    }
                                ]
                            }
                        },
                        {
                            "name": "hdfs-NAMENODE-254aaba64f12b01bac320242644a9384",
                            "type": "NAMENODE",
                            "hostRef": {
                                "hostId": "i-0062d7ef171235091"
                            },
                            "config": {
                                "items": [
                                    {
                                        "name": "autofailover_enabled",
                                        "value": "true"
                                    },
                                    {
                                        "name": "dfs_federation_namenode_nameservice",
                                        "value": "nameservice1"
                                    },
                                    {
                                        "name": "dfs_namenode_quorum_journal_name",
                                        "value": "nameservice1"
                                    },
                                    {
                                        "name": "namenode_id",
                                        "value": "59"
                                    },
                                    {
                                        "name": "role_jceks_password",
                                        "value": "5xezakomu40yjvikpr2l90caz"
                                    }
                                ]
                            }
                        },
                        {
                            "name": "hdfs-NAMENODE-e50982cc167ab38c8ba06232e47269a3",
                            "type": "NAMENODE",
                            "hostRef": {
                                "hostId": "i-01b4409d49de9ad91"
                            },
                            "config": {
                                "items": [
                                    {
                                        "name": "autofailover_enabled",
                                        "value": "true"
                                    },
                                    {
                                        "name": "dfs_federation_namenode_nameservice",
                                        "value": "nameservice1"
                                    },
                                    {
                                        "name": "dfs_namenode_quorum_journal_name",
                                        "value": "nameservice1"
                                    },
                                    {
                                        "name": "namenode_id",
                                        "value": "45"
                                    },
                                    {
                                        "name": "role_jceks_password",
                                        "value": "chuk9gnva1gwhjao4i93h4vsq"
                                    }
                                ]
                            }
                        }
                    ],
                    "displayName": "HDFS"
                },
                {
                    "name": "yarn",
                    "type": "YARN",
                    "config": {
                        "roleTypeConfigs": [
                            {
                                "roleType": "GATEWAY",
                                "items": [
                                    {
                                        "name": "mapred_reduce_tasks",
                                        "value": "6"
                                    },
                                    {
                                        "name": "mapred_submit_replication",
                                        "value": "1"
                                    }
                                ]
                            },
                            {
                                "roleType": "JOBHISTORY",
                                "items": [
                                    {
                                        "name": "mr2_jobhistory_java_heapsize",
                                        "value": "932184064"
                                    }
                                ]
                            },
                            {
                                "roleType": "NODEMANAGER",
                                "items": [
                                    {
                                        "name": "rm_cpu_shares",
                                        "value": "1600"
                                    },
                                    {
                                        "name": "rm_io_weight",
                                        "value": "800"
                                    },
                                    {
                                        "name": "yarn_nodemanager_heartbeat_interval_ms",
                                        "value": "100"
                                    },
                                    {
                                        "name": "yarn_nodemanager_local_dirs",
                                        "value": "/yarn/nm"
                                    },
                                    {
                                        "name": "yarn_nodemanager_log_dirs",
                                        "value": "/yarn/container-logs"
                                    },
                                    {
                                        "name": "yarn_nodemanager_resource_cpu_vcores",
                                        "value": "3"
                                    },
                                    {
                                        "name": "yarn_nodemanager_resource_memory_mb",
                                        "value": "3146"
                                    }
                                ]
                            },
                            {
                                "roleType": "RESOURCEMANAGER",
                                "items": [
                                    {
                                        "name": "yarn_scheduler_maximum_allocation_mb",
                                        "value": "3146"
                                    },
                                    {
                                        "name": "yarn_scheduler_maximum_allocation_vcores",
                                        "value": "3"
                                    }
                                ]
                            }
                        ],
                        "items": [
                            {
                                "name": "hdfs_service",
                                "value": "hdfs"
                            },
                            {
                                "name": "rm_dirty",
                                "value": "false"
                            },
                            {
                                "name": "rm_last_allocation_percentage",
                                "value": "80"
                            },
                            {
                                "name": "yarn_service_cgroups",
                                "value": "false"
                            },
                            {
                                "name": "yarn_service_lce_always",
                                "value": "false"
                            },
                            {
                                "name": "zk_authorization_secret_key",
                                "value": "xWAg5KjIQvu2gMUsKRGE9SQJQvXPKR"
                            },
                            {
                                "name": "zookeeper_service",
                                "value": "zookeeper"
                            }
                        ]
                    },
                    "roles": [
                        {
                            "name": "yarn-JOBHISTORY-254aaba64f12b01bac320242644a9384",
                            "type": "JOBHISTORY",
                            "hostRef": {
                                "hostId": "i-0062d7ef171235091"
                            },
                            "config": {
                                "items": [
                                    {
                                        "name": "role_jceks_password",
                                        "value": "9237cxieqzwvqwn0w4va3np1o"
                                    }
                                ]
                            }
                        },
                        {
                            "name": "yarn-NODEMANAGER-f0df28d0d5d07244a749a7c2503f529e",
                            "type": "NODEMANAGER",
                            "hostRef": {
                                "hostId": "i-06ff68cfabb384211"
                            },
                            "config": {
                                "items": [
                                    {
                                        "name": "role_jceks_password",
                                        "value": "b6pj71ksd3x7b7vx2gu742dx5"
                                    }
                                ]
                            }
                        },
                        {
                            "name": "yarn-NODEMANAGER-fe1b5bc1941577e812004af799ef22ed",
                            "type": "NODEMANAGER",
                            "hostRef": {
                                "hostId": "i-053e3427d734e38ee"
                            },
                            "config": {
                                "items": [
                                    {
                                        "name": "role_jceks_password",
                                        "value": "cygf7wkgly02bwsqpoyc7ic7g"
                                    }
                                ]
                            }
                        },
                        {
                            "name": "yarn-NODEMANAGER-fe936e0f763a8708d3e26e24d1692d02",
                            "type": "NODEMANAGER",
                            "hostRef": {
                                "hostId": "i-057f340038c217d67"
                            },
                            "config": {
                                "items": [
                                    {
                                        "name": "role_jceks_password",
                                        "value": "7p024ijjwt2fa9xvm4y6yiou4"
                                    }
                                ]
                            }
                        },
                        {
                            "name": "yarn-RESOURCEMANAGER-e50982cc167ab38c8ba06232e47269a3",
                            "type": "RESOURCEMANAGER",
                            "hostRef": {
                                "hostId": "i-01b4409d49de9ad91"
                            },
                            "config": {
                                "items": [
                                    {
                                        "name": "rm_id",
                                        "value": "51"
                                    },
                                    {
                                        "name": "role_jceks_password",
                                        "value": "5vhs7ckj91mx3g2jd3xpug5jk"
                                    }
                                ]
                            }
                        }
                    ],
                    "displayName": "YARN (MR2 Included)"
                },
                {
                    "name": "hive",
                    "type": "HIVE",
                    "config": {
                        "roleTypeConfigs": [
                            {
                                "roleType": "HIVEMETASTORE",
                                "items": [
                                    {
                                        "name": "hive_metastore_java_heapsize",
                                        "value": "932184064"
                                    }
                                ]
                            },
                            {
                                "roleType": "HIVESERVER2",
                                "items": [
                                    {
                                        "name": "hiveserver2_java_heapsize",
                                        "value": "3085959168"
                                    },
                                    {
                                        "name": "hiveserver2_spark_driver_memory",
                                        "value": "966367641"
                                    },
                                    {
                                        "name": "hiveserver2_spark_executor_cores",
                                        "value": "4"
                                    },
                                    {
                                        "name": "hiveserver2_spark_executor_memory",
                                        "value": "3524159078"
                                    },
                                    {
                                        "name": "hiveserver2_spark_yarn_driver_memory_overhead",
                                        "value": "102"
                                    },
                                    {
                                        "name": "hiveserver2_spark_yarn_executor_memory_overhead",
                                        "value": "593"
                                    }
                                ]
                            }
                        ],
                        "items": [
                            {
                                "name": "hive_metastore_database_host",
                                "value": "ip-172-31-2-135.eu-west-1.compute.internal"
                            },
                            {
                                "name": "hive_metastore_database_password",
                                "value": "hive_password"
                            },
                            {
                                "name": "mapreduce_yarn_service",
                                "value": "yarn"
                            },
                            {
                                "name": "zookeeper_service",
                                "value": "zookeeper"
                            }
                        ]
                    },
                    "roles": [
                        {
                            "name": "hive-GATEWAY-254aaba64f12b01bac320242644a9384",
                            "type": "GATEWAY",
                            "hostRef": {
                                "hostId": "i-0062d7ef171235091"
                            },
                            "config": {
                                "items": []
                            }
                        },
                        {
                            "name": "hive-GATEWAY-e50982cc167ab38c8ba06232e47269a3",
                            "type": "GATEWAY",
                            "hostRef": {
                                "hostId": "i-01b4409d49de9ad91"
                            },
                            "config": {
                                "items": []
                            }
                        },
                        {
                            "name": "hive-GATEWAY-f0df28d0d5d07244a749a7c2503f529e",
                            "type": "GATEWAY",
                            "hostRef": {
                                "hostId": "i-06ff68cfabb384211"
                            },
                            "config": {
                                "items": []
                            }
                        },
                        {
                            "name": "hive-GATEWAY-fe1b5bc1941577e812004af799ef22ed",
                            "type": "GATEWAY",
                            "hostRef": {
                                "hostId": "i-053e3427d734e38ee"
                            },
                            "config": {
                                "items": []
                            }
                        },
                        {
                            "name": "hive-GATEWAY-fe936e0f763a8708d3e26e24d1692d02",
                            "type": "GATEWAY",
                            "hostRef": {
                                "hostId": "i-057f340038c217d67"
                            },
                            "config": {
                                "items": []
                            }
                        },
                        {
                            "name": "hive-HIVEMETASTORE-254aaba64f12b01bac320242644a9384",
                            "type": "HIVEMETASTORE",
                            "hostRef": {
                                "hostId": "i-0062d7ef171235091"
                            },
                            "config": {
                                "items": [
                                    {
                                        "name": "role_jceks_password",
                                        "value": "5r3ec781qixsz49e0fye6o3ki"
                                    }
                                ]
                            }
                        },
                        {
                            "name": "hive-HIVESERVER2-e50982cc167ab38c8ba06232e47269a3",
                            "type": "HIVESERVER2",
                            "hostRef": {
                                "hostId": "i-01b4409d49de9ad91"
                            },
                            "config": {
                                "items": [
                                    {
                                        "name": "role_jceks_password",
                                        "value": "2kbn1migl56ntcjl0x8sy6x3w"
                                    }
                                ]
                            }
                        }
                    ],
                    "displayName": "Hive"
                }
            ]
        }
    ],
    "hosts": [
        {
            "hostId": "i-053e3427d734e38ee",
            "ipAddress": "172.31.13.106",
            "hostname": "ip-172-31-13-106.eu-west-1.compute.internal",
            "rackId": "/default",
            "config": {
                "items": []
            }
        },
        {
            "hostId": "i-057f340038c217d67",
            "ipAddress": "172.31.13.203",
            "hostname": "ip-172-31-13-203.eu-west-1.compute.internal",
            "rackId": "/default",
            "config": {
                "items": []
            }
        },
        {
            "hostId": "i-01b4409d49de9ad91",
            "ipAddress": "172.31.15.191",
            "hostname": "ip-172-31-15-191.eu-west-1.compute.internal",
            "rackId": "/default",
            "config": {
                "items": []
            }
        },
        {
            "hostId": "i-0062d7ef171235091",
            "ipAddress": "172.31.2.135",
            "hostname": "ip-172-31-2-135.eu-west-1.compute.internal",
            "rackId": "/default",
            "config": {
                "items": []
            }
        },
        {
            "hostId": "i-06ff68cfabb384211",
            "ipAddress": "172.31.3.132",
            "hostname": "ip-172-31-3-132.eu-west-1.compute.internal",
            "rackId": "/default",
            "config": {
                "items": []
            }
        }
    ],
    "users": [
        {
            "name": "__cloudera_internal_user__mgmt-ACTIVITYMONITOR-254aaba64f12b01bac320242644a9384",
            "roles": [
                "ROLE_USER"
            ],
            "pwHash": "ec3e48c40dfa153b0baed3e1f2186ba50c37ba599fd554ad41a85550b91187f0",
            "pwSalt": -5729554793044635720,
            "pwLogin": true
        },
        {
            "name": "__cloudera_internal_user__mgmt-EVENTSERVER-254aaba64f12b01bac320242644a9384",
            "roles": [
                "ROLE_USER"
            ],
            "pwHash": "d277bad502ea7ddf00c973b7c0e0f62c64edd7da8b0b0837f23192914bd7be7a",
            "pwSalt": -3847175683891664840,
            "pwLogin": true
        },
        {
            "name": "__cloudera_internal_user__mgmt-HOSTMONITOR-254aaba64f12b01bac320242644a9384",
            "roles": [
                "ROLE_USER"
            ],
            "pwHash": "ad4969f727cd8a3b732ad17b68b5c9c76848049c4ca3c59be6af6b8ceb20d230",
            "pwSalt": -6562964748947723830,
            "pwLogin": true
        },
        {
            "name": "__cloudera_internal_user__mgmt-REPORTSMANAGER-254aaba64f12b01bac320242644a9384",
            "roles": [
                "ROLE_USER"
            ],
            "pwHash": "39bbdc9a3ee38d1d61610bd1a045f81651810aaf423083b17c95f796f48b0f50",
            "pwSalt": -7261111299381598923,
            "pwLogin": true
        },
        {
            "name": "__cloudera_internal_user__mgmt-SERVICEMONITOR-254aaba64f12b01bac320242644a9384",
            "roles": [
                "ROLE_USER"
            ],
            "pwHash": "ec68b5fb36fb0e3f70bdf06e914c92481b738ed07972fc0ab421ee9a3123deba",
            "pwSalt": -1002264457165977715,
            "pwLogin": true
        },
        {
            "name": "admin",
            "roles": [
                "ROLE_LIMITED"
            ],
            "pwHash": "1f383046cee5ae2752844a05fbfcea8d7babb9758d25b6d60be4fca734547107",
            "pwSalt": -3474808610864199201,
            "pwLogin": true
        },
        {
            "name": "jovv",
            "roles": [
                "ROLE_ADMIN"
            ],
            "pwHash": "e4e8f69bae3e6abfe2f6b74e2b1b8c9adec00dd7c8e067ba2a16ff4dbf6d809e",
            "pwSalt": -6664390314381458889,
            "pwLogin": true
        },
        {
            "name": "minotaur",
            "roles": [
                "ROLE_CONFIGURATOR"
            ],
            "pwHash": "8556cf25fb3827ebcbf08b5ea8011900abab7d64c43c0ec1dad7a67acca49b83",
            "pwSalt": 572895750210382091,
            "pwLogin": true
        }
    ],
    "versionInfo": {
        "version": "5.9.3",
        "buildUser": "jenkins",
        "buildTimestamp": "20170627-1506",
        "gitHash": "23506bb4e114dd460bdac64c57a672e6be631907",
        "snapshot": false
    },
    "managementService": {
        "name": "mgmt",
        "type": "MGMT",
        "config": {
            "roleTypeConfigs": [
                {
                    "roleType": "ACTIVITYMONITOR",
                    "items": [
                        {
                            "name": "firehose_database_host",
                            "value": "ip-172-31-2-135.eu-west-1.compute.internal"
                        },
                        {
                            "name": "firehose_database_name",
                            "value": "amon"
                        },
                        {
                            "name": "firehose_database_password",
                            "value": "amon_password"
                        },
                        {
                            "name": "firehose_database_user",
                            "value": "amon"
                        },
                        {
                            "name": "firehose_heapsize",
                            "value": "932184064"
                        }
                    ]
                },
                {
                    "roleType": "EVENTSERVER",
                    "items": [
                        {
                            "name": "event_server_heapsize",
                            "value": "932184064"
                        }
                    ]
                },
                {
                    "roleType": "HOSTMONITOR",
                    "items": [
                        {
                            "name": "firehose_non_java_memory_bytes",
                            "value": "1212153856"
                        }
                    ]
                },
                {
                    "roleType": "REPORTSMANAGER",
                    "items": [
                        {
                            "name": "headlamp_database_host",
                            "value": "ip-172-31-2-135.eu-west-1.compute.internal"
                        },
                        {
                            "name": "headlamp_database_name",
                            "value": "rman"
                        },
                        {
                            "name": "headlamp_database_password",
                            "value": "rman_password"
                        },
                        {
                            "name": "headlamp_database_user",
                            "value": "rman"
                        },
                        {
                            "name": "headlamp_heapsize",
                            "value": "932184064"
                        }
                    ]
                },
                {
                    "roleType": "SERVICEMONITOR",
                    "items": [
                        {
                            "name": "firehose_non_java_memory_bytes",
                            "value": "1212153856"
                        }
                    ]
                }
            ],
            "items": []
        },
        "roles": [
            {
                "name": "mgmt-ACTIVITYMONITOR-254aaba64f12b01bac320242644a9384",
                "type": "ACTIVITYMONITOR",
                "hostRef": {
                    "hostId": "i-0062d7ef171235091"
                },
                "config": {
                    "items": [
                        {
                            "name": "role_jceks_password",
                            "value": "31pafcv3x1klq9yt4mhcgwudx"
                        }
                    ]
                }
            },
            {
                "name": "mgmt-ALERTPUBLISHER-254aaba64f12b01bac320242644a9384",
                "type": "ALERTPUBLISHER",
                "hostRef": {
                    "hostId": "i-0062d7ef171235091"
                },
                "config": {
                    "items": [
                        {
                            "name": "role_jceks_password",
                            "value": "bqi4k7qycpsayyz3gn4oj184j"
                        }
                    ]
                }
            },
            {
                "name": "mgmt-EVENTSERVER-254aaba64f12b01bac320242644a9384",
                "type": "EVENTSERVER",
                "hostRef": {
                    "hostId": "i-0062d7ef171235091"
                },
                "config": {
                    "items": [
                        {
                            "name": "role_jceks_password",
                            "value": "6p0tz5jrotettehoa63y2m99u"
                        }
                    ]
                }
            },
            {
                "name": "mgmt-HOSTMONITOR-254aaba64f12b01bac320242644a9384",
                "type": "HOSTMONITOR",
                "hostRef": {
                    "hostId": "i-0062d7ef171235091"
                },
                "config": {
                    "items": [
                        {
                            "name": "role_jceks_password",
                            "value": "dxz4u5inaxkaaace2tu7mu6i9"
                        }
                    ]
                }
            },
            {
                "name": "mgmt-REPORTSMANAGER-254aaba64f12b01bac320242644a9384",
                "type": "REPORTSMANAGER",
                "hostRef": {
                    "hostId": "i-0062d7ef171235091"
                },
                "config": {
                    "items": [
                        {
                            "name": "role_jceks_password",
                            "value": "ug5sol2vwwubwq0m9rmxv5fe"
                        }
                    ]
                }
            },
            {
                "name": "mgmt-SERVICEMONITOR-254aaba64f12b01bac320242644a9384",
                "type": "SERVICEMONITOR",
                "hostRef": {
                    "hostId": "i-0062d7ef171235091"
                },
                "config": {
                    "items": [
                        {
                            "name": "role_jceks_password",
                            "value": "9e4y1r4qgtwc60wru2b2zxj8g"
                        }
                    ]
                }
            }
        ],
        "displayName": "Cloudera Management Service"
    },
    "managerSettings": {
        "items": [
            {
                "name": "CLUSTER_STATS_START",
                "value": "10/23/2012 1:10"
            },
            {
                "name": "PUBLIC_CLOUD_STATUS",
                "value": "ON_PUBLIC_CLOUD"
            },
            {
                "name": "REMOTE_PARCEL_REPO_URLS",
                "value": "https://archive.cloudera.com/cdh5/parcels/{latest_supported}/,https://archive.cloudera.com/cdh4/parcels/latest/,https://archive.cloudera.com/impala/parcels/latest/,https://archive.cloudera.com/search/parcels/latest/,https://archive.cloudera.com/accumulo/parcels/1.4/,https://archive.cloudera.com/accumulo-c5/parcels/latest/,https://archive.cloudera.com/kafka/parcels/latest/,https://archive.cloudera.com/navigator-keytrustee5/parcels/latest/,https://archive.cloudera.com/spark/parcels/latest/,https://archive.cloudera.com/sqoop-connectors/parcels/latest/"
            }
        ]
    }
}
```