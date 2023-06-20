- https://aws.amazon.com/blogs/networking-and-content-delivery/scaling-nlb-target-groups-by-connections/
- https://aws.amazon.com/about-aws/whats-new/2023/06/amazon-ec2-instance-connect-ssh-rdp-public-ip-address/
  ssh -i K8s.pem ubuntu@i-0dbb7b6d45e690880 -o ProxyCommand='aws ec2-instance-connect open-tunnel --instance-id i-0dbb7b6d45e690880'
  ssh -i K8s.pem ubuntu@i-0dbb7b6d45e690880 -o ProxyCommand='aws eice-002b97c6675087f77 open-tunnel --instance-id i-0dbb7b6d45e690880'
  ssh -i K8s.pem ubuntu@i-0dbb7b6d45e690880 -o ProxyCommand='aws ec2-instance-connect ssh --instance-id i-0dbb7b6d45e690880 --connection-type eice'

          aws ec2-instance-connect open-tunnel --instance-id i-0dbb7b6d45e690880 --local-port 8888
          aws ec2-instance-connect ssh --instance-id i-0dbb7b6d45e690880 --connection-type eice



          aws send-ssh-public-key --instance-id i-0dbb7b6d45e690880 --instance-os-user ubuntu --ssh-public-key K8s.pem

  i-092f395ed31b9ae62
  ssh -i my-key-pair.pem ec2-user@i-092f395ed31b9ae62 -o ProxyCommand='aws ec2-instance-connect open-tunnel --instance-id i-092f395ed31b9ae62'

  aws ec2-instance-connect open-tunnel \
   --instance-id i-092f395ed31b9ae62 \
   --local-port 8888

          {
      "Version": "2012-10-17",
      "Statement": [{
              "Sid": "EC2InstanceConnect",
              "Action": "ec2-instance-connect:OpenTunnel",
              "Effect": "Allow",
              "Resource": "arn:aws:ec2:us-east-2:676968646773:instance-connect-endpoint/eice-002b97c6675087f77",
              "Condition": {
                  "NumericEquals": {
                      "ec2-instance-connect:remotePort": "22"
                  },
                  "IpAddress": {
                      "ec2-instance-connect:privateIpAddress": "10.0.128.0/20"
                  },
                  "NumericLessThanEquals": {
                      "ec2-instance-connect:maxTunnelDuration": "60"
                  }
              }
          },
          {
              "Sid": "Describe",
              "Action": [
                  "ec2:DescribeInstances",
                  "ec2:DescribeInstanceConnectEndpoints"
              ],
              "Effect": "Allow",
              "Resource": "*"
          }
      ]

  }

- https://towardsaws.com/how-to-group-aws-resources-based-on-tags-dba89cb94597

- https://medium.com/@2017tejasgupta/connect-to-your-instances-with-a-private-ipv4-address-using-ec2-instance-connect-endpoint-c92ad3efc545

- https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/permissions-for-ec2-instance-connect-endpoint.html

- https://docs.aws.amazon.com/AWSEC2//latest/UserGuide/AccessingInstancesLinux.html#SSH-using-EC2-Instance-Connect

- https://github.com/awsdocs/amazon-ec2-user-guide/blob/master/doc_source/ec2-instance-connect-set-up.md


- https://towardsaws.com/install-cloudwatch-agent-using-aws-systems-manager-cf460db8ef78


- https://blog.awsfundamentals.com/

## Lambda

- https://thiagonache.github.io/codewiththiago/posts/aws-lambda-go/?utm_id=FAUN_CyraBee376_Link_title



## AWS Environment

- https://www.noq.dev/blog/scps-protecting-your-aws-environment-and-your-job?utm_id=FAUN_CyraBee376_Link_title


## Athena

- https://www.lariatdata.com/blog/continuous-data-quality-athena?utm_id=FAUN_CyraBee376_Link_title

## AWS Codepipeline

- https://medium.com/@dania.ref96/tag-based-deployment-trigger-for-aws-codepipeline-38ace7498fcd

## EKS

- https://securitylabs.datadoghq.com/articles/amazon-eks-attacking-securing-cloud-identities/?utm_id=FAUN_CyraBee376_Link_title

- https://www.freecodecamp.org/news/how-to-deploy-your-freecodecamp-project-on-aws

- https://eks.news/


- https://kerneltalks.com/

- https://amlanscloud.com/cfntoazure/

- https://plainenglish.io/