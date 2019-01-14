# Warsaw University of Technology
### Faculty of Power and Aeronautical Engineering
### Cloud computing introductionary course 2018
> Student: [Krzysztof Wilczynski](https://www.linkedin.com/in/3sztof/)
> Lecturer: [Mateusz Żbikowski PhD](https://www.itc.pw.edu.pl/Pracownicy/Naukowo-dydaktyczni/Zbikowski-Mateusz)


#### Useful resources
| Resource | Description |
| ------ | ------ |
| [AWS Apache Spark](https://docs.aws.amazon.com/emr/latest/ReleaseGuide/emr-spark-launch.html?fbclid=IwAR3GsKrIUiocmdAGu4rKHiEmikA4nLQa9lnaVPbUdjvxx1bEZFmMBk6ra4s) | An introduction to Apache Spark configuration on AWS cloud. |
| [Spark Job Submit](https://aws.amazon.com/premiumsupport/knowledge-center/emr-submit-spark-job-remote-cluster/?fbclid=IwAR0rdkiXlKfh9iacYOV4wlcUsu8YZqbduxvhTYntg7afcIZAUB8kTYD-HWg) | A guide describing the steps needed to deploy a job to the Spark cluster. |
| [Lecturer's Resources ](https://docs.google.com/document/d/1AkiDFotQ2QgK_lsxTNmoq3mXpJUAl89Ekl6nlrApx_I/) | The resources provided by the lecturer @Mateusz Żbikowski PhD. |
| [Apache Spark Examples](https://github.com/apache/spark/tree/master/examples/src/main/) | Apache Spark example deployment scripts github repository. |
| [Dillinger.io](dillinger.io) | Online markdown markup editor. |



#### Steps taken
 - Applied for the AWS Educate financing program to get 40$ cloud experiments financing
 - Studied all of the resources provided by the lecturer in order to gain a basic theoretical knowledge about the vast possibilities of AWS (which gives us much more than just parallel computing)
 - Made serveral attepmts, wasting a lot of time in order to deploy a High Performance Computing (HPC) cloud (see the next section for details)
 - After failing to find any help regarding the HPC cloud deployment, a change of approach was needed - it was decided to go with the Apache Spark cloud environment deployed on three AWS EC2 (Amazon Web Services Elastic Coputer Cloud) machines: one "master" and two "worker" nodes.
   
   
    ```sh
    $ ssh
    ```



#### Encountered problems
 - In the first attempts, many EC2 nodes were deployed in different availability zones in order to properly deploy a High Performance Computing (HPC) cluster. The clusters could only be deployed in US-West and US-East zones but despite trying out every region and many configuration files, all of the attempts were failures. The tutorial ([HPC setup guide](https://aws.amazon.com/hpc/sc15/getting-started/)) provided by AWS contained links to HPC configuration files that were not accesible (such as [this](https://s3.amazonaws.com/cfncluster-public-scripts/cfncluster-simple-cfd.cfn.json)). Other configuration JSONs proved to cause unrealistically high costs. Many hours were wasted trying to find a solution and eventually, the decision was to change the approach to AWS Apache Spark cluster.
 - No financial help ([Amazon Educate](https://aws.amazon.com/education/awseducate/)) has been provided despite many attempts to fill in the forms and contacting the AWS support. This was a serious limitation, as the 40$ grant could really help in deploying experimental clusters.



#### Todo
 - Try again to configure HPC and deploy a Python application there.
 - Make a comparison between parallel computing on a single machine and a cluster of cores - the result should be different depending on the complexity of the calculations. It is expected that the computing will actually take longer on the cluster in case of simple and short task (as the nodes have to communicate via sockets - that takes time). On the other hand, the more complex task should be much faster using a cluster such as HPC as the computation can be dissipated between many more cores than in case of a single machine.
