This script takes advantage of Check Point's 'fwm logexport'. logexport is used to export logs into a raw csv format.

This script can be used to extract the users needed data into a single csv file that has been reduced and uniqued across connections.

Currently the script is setup to extract Action, Source, Destination, Service, port (all the possible fields are at the end of this document)

If you need different data just adjust this line in the script
  "included_fields = action,src,dst,proto,service,<REST_OF_FIELDS>" >> $FWDIR/conf/logexport.ini

  NOTE: The 'num' column is 1st by default and cannot be changed.

The date of the logs you want to export is controlled in the script and can be adjusted by changing 'DATE="2018-06-01*"' by default it will process everything in $FWDIR/log

The final file 'final-connection-report.csv' will be placed in the working directory of where the script was executed.





num; action;src;dst;proto;service;date;time;orig;type;action;alert;i/f_name;i/f_dir;product;LogId;ContextNum;origin_id;ContentVersion;HighLevelLogKey;SequenceNum;log_sys_message;ProductFamily;inzone;outzone;service_id;user;src_user_name;src_machine_name;src_user_dn;snid;dst_user_name;dst_machine_name;dst_user_dn;UP_match_table_match_id;UP_match_table_layer_uuid;UP_match_table_layer_name;UP_match_table_rule_uid;UP_match_table_rule_name;UP_match_table_action;UP_match_table_parent_rule;context_num;s_port;xlatesrc;xlatedst;NAT_rulenum;NAT_addtnl_rulenum;xlatedport;xlatesport;log_id;status;short_desc;long_desc;scan_hosts_hour;scan_hosts_day;scan_hosts_week;unique_detected_hour;unique_detected_day;unique_detected_week;scan_mail;update_status;update_description;is_first_download;blade_status;blade_description;email_scanned;downloaded_files_scanned;files_in_queue;number_of_emulation_environments;scanned_files;scanned_files_last_day;scanned_files_last_week;scanned_files_last_month;malware_detected;malware_detected_last_day;malware_detected_last_week;malware_detected_last_month;scanned_files_on_threat_cloud;scanned_files_on_threat_cloud_last_day;scanned_files_on_threat_cloud_last_week;scanned_files_on_threat_cloud_last_month;malware_detected_on_threat_cloud;malware_detected_on_threat_cloud_last_day;malware_detected_on_threat_cloud_last_week;malware_detected_on_threat_cloud_last_month;average_process_time;average_process_time_last_day;average_process_time_last_week;average_process_time_last_month;average_emulated_file_size;average_emulated_file_size_last_day;average_emulated_file_size_last_week;average_emulated_file_size_last_month;average_queue_size;average_queue_size_last_day;average_queue_size_last_week;average_queue_size_last_month;peak_queue_size;peak_queue_size_last_day;peak_queue_size_last_week;peak_queue_size_last_month;engine_major_version;engine_minor_version;file_type;scanned;scanned_last_day;scanned_last_week;scanned_last_month;threatcloud_scanned;threatcloud_scanned_last_day;threatcloud_scanned_last_week;threatcloud_scanned_last_month;threatcloud_malware;threatcloud_malware_detected_last_day;threatcloud_malware_detected_last_week;threatcloud_malware_detected_last_month;filter_by_static_analysis;filter_by_static_analysis_last_day;filter_by_static_analysis_last_week;filter_by_static_analysis_last_month;cache_hit_rate;cache_hit_rate_last_day;cache_hit_rate_last_week;cache_hit_rate_last_month;error_count;error_count_last_day;error_count_last_week;error_count_last_month;no_resource_count;no_resource_count_last_day;no_resource_count_last_week;no_resource_count_last_month;contract_name;subs_exp;cloud_hourly_quota;cloud_monthly_quota;cloud_hourly_remaining_quota;cloud_remaining_quota;max_vms_num;subscription_status;subscription_description;cloud_quota_status;cloud_quota_description;cloud_quota_identifier;cloud_monthly_quota_period_start;cloud_monthly_quota_period_end;cloud_monthly_quota_usage_for_this_gw;cloud_hourly_quota_usage_for_this_gw;cloud_monthly_quota_usage_for_quota_id;cloud_hourly_quota_usage_for_quota_id;cloud_monthly_quota_exceeded;cloud_hourly_quota_exceeded;cloud_last_quota_update_gmt_time;packet_capture_unique_id;packet_capture_time;packet_capture_name;Suppressed logs;sent_bytes;received_bytes;action_reason;TCP packet out of state;tcp_flags;db_ver;description;Update Status;Severity;subscription_stat;subscription_stat_desc;next_update_desc;ICMP;ICMP Type;ICMP Code;rule_guid;hit;policy;first_hit_time;last_hit_time;sensor_test_name;sensor_alert_title;sensor_alert_category;sensor_alert_message;sensor_alert_module;sensor_alert_type;sensor_alert_source;sensor_alert_id;sensor_alert_solution;sensor_alert_solution_sk;sensor_alert_blade;sensor_alert_duration;SmartDefense profile;policy_time;session_id;Source_OS;dst_country;rule_uid;rule_name;malware_rule_id;malware_rule_name;resource;reject_id_kid;ser_agent_kid;server_kid;TP_match_table_layer_uuid;TP_match_table_layer_name;TP_match_table_malware_rule_id;TP_match_table_malware_rule_name;TP_match_table_SmartDefense profile;attack;Attack Info;Protection Name;Protection ID;Confidence Level;Industry Reference;Performance Impact;Protection Type;Description URL;scope;file_name;file_size;file_md5;file_sha1;file_sha256;verdict;analyzed_on;emulated_on;detected_on;Errors;TE_verdict_determined_by;malware_action;url;web_client_type;web_server_type;Source OS;proxy_src_ip;version;comment;update_service;cvpn_category;event_type;user_dn;device_identification;login_timestamp;duration;reason;note;session_uid;malware_family;information;Destination DNS Hostname;protection_id;vendor_list;action_details;rpc_prog;failure_impact;control_log_type;client_name;client_version;client_build;auth_method;auth_method2;auth_method3;login_option;failed_login_factor;failed_login_factor_num;fingerprint;certificate_serial_number;certificate_issuer;user_group;host_type;os_name;os_version;os_edition;os_service_pack;os_build;os_bits;browser;hardware_model;session_timeout;host_ip;office_mode_ip;tunnel_protocol;methods:;latitude;longitude;license;Suppressed_Logs;More;mac_address;Hostname;domain_name;auth_encryption_methods;scheme:;peer gateway;encryption failure:;partner;community;vpn_user;fw_subproduct;vpn_feature_name;srckeyid;dstkeyid;IKE:;CookieI;CookieR;msgid;IKE notification:;Certificate DN:;IKE IDs:;start_time;connection_uid;hll_key;update_count;connection_count;aggregated_log_count;creation_time;segment_time;elapsed;packets;bytes;client_inbound_packets;client_outbound_packets;server_inbound_packets;server_outbound_packets;client_inbound_bytes;client_outbound_bytes;server_inbound_bytes;server_outbound_bytes;client_inbound_interface;client_outbound_interface;server_inbound_interface;server_outbound_interface;message;old IP;old port;new IP;new port