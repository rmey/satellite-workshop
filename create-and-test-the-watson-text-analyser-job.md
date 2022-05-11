# 6. Create and test the Watson Text Analyser Job

In our final chapter of the Tutorial we would like to create the Code Engine Job which analyses the uploaded text files with the IBM Cloud [Watson Natural Language Understanding](https://www.ibm.com/cloud/watson-natural-language-understanding) Service (NLU).

## Create an Watson NLU API Key

```
ibmcloud resource service-key-create <YOUR-UNIQUE-NLU-KEY-NAME> Manager --instance-name code-engine-nlu
```

![](<.gitbook/assets/image (27).png>)

Please copy the **NLU API Key** in the form of "3zGZ07bpyUTRjOyE0YAYQeHA..." in your text editor of choice for later steps in this tutorial.

## Create a Secret for COS and Watson NLU Services for the Backend Job

Adopt the following command in your editor of choice with your **COS** **bucket name** and **COS** **API key** (from previous chapter) to be able to connect the Job to the COS instance accessing the uploaded files, see previous chapter 5 (in the form of "3zGZ07bpyUTRjOyE0YAYQeHA....."). You also need add the **Watson NLU API Key** and execute the modified command below in the Cloud Shell, this will create a file nlu.env.

```
cat << 'EOF' > nlu.env
NLU_JOB_APIKEY=<YOUR NLU API KEY>
NLU_JOB_URL=https://api.eu-de.natural-language-understanding.watson.cloud.ibm.com/instances/f4c4e4d9-f8dc-49fe-b7b3-15f6fcf44d51
COS_ENDPOINT=https://s3.eu.cloud-object-storage.appdomain.cloud
COS_JOB_APIKEY=<YOUR COS API Key>
COS_JOB_RESOURCE_INSTANCE_ID=crn:v1:bluemix:public:cloud-object-storage:global:a/e97a8c01ac694e308ef3ad77957bb960:1ef3fc71-c501-4369-be8b-dfe99c0c7954::
COS_BUCKETNAME=<YOUR BUCKET NAME>
EOF
```

![](<.gitbook/assets/image (28).png>)

Create the Secret for the Job in executing the command.

```
ibmcloud ce secret create -name nlu-secret --from-env-file nlu.env
```

![](<.gitbook/assets/image (33).png>)

## Create a Job Definition

Now we create a job definition which is using our secret.

```
ibmcloud code-engine job create --name backend-job --image ibmcom/backend-job  --env-from-secret nlu-secret
```

![](<.gitbook/assets/image (30).png>)

## Test the Job/Application

Now we create a job run which will load the text files from the COS bucket, analyses the content with Watson NLU and writes the results back to the COS bucket. &#x20;

```
ibmcloud code-engine jobrun submit --name backend-jobrun --job backend-job
```

![](<.gitbook/assets/image (31).png>)

You also see in the screenshot the capability to access the Code Engine project with usual kubectl commands to get access to lower level Kubernetes Objects. This is because Code Engine abstracts Kubernetes for the user at one time, but gives also access up to a certain degree if needed. &#x20;

## Check the results in the Frontend Webapp

Refresh the page of the Frontend Application

Your Text Files are now analysed - Congratulations!

![](<.gitbook/assets/image (32).png>)

