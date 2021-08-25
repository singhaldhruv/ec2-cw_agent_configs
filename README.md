# ec2-cw_agent_configs
Config file to enable EC2 server memory utilization metrics in AWS CloudWatch

{
      "agent": {
        "metrics_collection_interval": 60,
        "logfile": "/opt/aws/amazon-cloudwatch-agent/logs/amazon-cloudwatch-agent.log"
      },
"metrics": {
    "metrics_collected": {
      "mem": {
        "measurement": [
          {"name": "used", "rename": "MemoryUsed"},
          {"name": "mem_available", "rename": "MemoryAvailable"}
        ]
        }
      },
    "append_dimensions": {
      "InstanceId": "${aws:InstanceId}"
    }
  }
}
