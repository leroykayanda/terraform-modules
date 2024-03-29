    module "rds" {
      source                                = "modules/aws-rds?ref=v1.0.18"
      env                                   = var.env
      team                                  = var.team
      microservice_name                     = var.microservice_name
      db_subnets                            = var.private_subnets
      instance_class                        = var.instance_class
      sns_topic                             = var.sns_topic
      security_group_id                     = aws_security_group.db_security_group.id
      engine                                = var.engine
      publicly_accessible                   = var.publicly_accessible
      engine_version                        = var.db_engine_version
      username                              = var.db_username
      password                              = var.db_password
      port                                  = var.port
      db_name                               = var.db_name
      multi_az                              = var.multi_az
      region                                = var.region
      storage_throughput                    = local.db_storage_throughput
      parameter_group_family                = var.parameter_group_family #below are optional
      enabled_cloudwatch_logs_exports       = var.enabled_cloudwatch_logs_exports
      performance_insights_retention_period = var.performance_insights_retention_period
      iops_alarm_threshold                  = var.iops_alarm_threshold
      throughput_alarm_threshold            = var.throughput_alarm_threshold
      queue_depth_alarm_threshold           = var.queue_depth_alarm_threshold
      storage_alarm_threshold               = var.storage_alarm_threshold
      memory_alarm_threshold                = var.memory_alarm_threshold
      backup_retention_period               = var.backup_retention_period
      create_cpu_credit_alarm               = var.create_cpu_credit_alarm
      maintenance_window                    = var.maintenance_window
      backup_window                         = var.backup_window
      allocated_storage                     = var.allocated_storage
      max_allocated_storage                 = var.max_allocated_storage
      deletion_protection                   = var.deletion_protection
      iops                                  = local.iops
    }
