# AWS CLI

### EC2 Instances

List instance ids

```
INSTANCES=$(aws ec2 describe-instances | jq .Reservations[].Instances[].InstanceId -r); echo $INSTANCES
```

Start instances

```
aws ec2 start-instances --instance-ids $INSTANCES
```

List public IPs

```
aws ec2 describe-instances | jq '.Reservations[].Instances[].InstanceId, .Reservations[].Instances[].PublicIpAddress' -r
```

Stop instances

```
aws ec2 stop-instances --instance-ids $INSTANCES
```

