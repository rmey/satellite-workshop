# 5. Connect the IBM Cloud Object Storage with the Backend Service

## Create an new IBM Cloud Object Storage Bucket

In the Cloud Account we have a predefined IBM Cloud Object Storage Instance which support S3 API which we will utilise to store text files to be analysed. In this instance we create a **unique bucket** using the following command in the Cloud shell. Please use small capitals to create a unique bucket name, see screenshot, note your bucket name for later reference.

```
ibmcloud cos bucket-create \
--ibm-service-instance-id crn:v1:bluemix:public:cloud-object-storage:global:a/e97a8c01ac694e308ef3ad77957bb960:1ef3fc71-c501-4369-be8b-dfe99c0c7954:: \
--class Standard --region eu-geo --bucket <YOURUNIQUEBUCKETNAME>
```

![](<.gitbook/assets/image (20).png>)

## Create API Key/ Service Credentials

We create now Service credential of our  Cloud Object Storage Service instance **code-engine-cos** which holds our bucket our bucket.

1. We create a new credential for our COS Bucket using the CLI

```
ibmcloud resource service-key-create <YOUR-UNIQUE-KEY-NAME> Writer --instance-name code-engine-cos
```

We will receive an output and need to save the **COS API Key** in the form of "3zGZ07bpyUTRjOyE0YAYQeHA....." for later use, see screenshot. You should copy the API Key to a text editor for later use in the next steps of the workshop.

![](<.gitbook/assets/image (21).png>)

## Create a Secret for the Backend Application

Adopt the following command in your editor of choice with your **COS** **bucket name** and **COS** **API key** and execute in Cloud Shell, this will create a file cos.env.

```
cat << 'EOF' > cos.env
COS_ENDPOINT=https://s3.eu.cloud-object-storage.appdomain.cloud
COS_APIKEY=<YOUR COS API KEY>
COS_RESOURCE_INSTANCE_ID=crn:v1:bluemix:public:cloud-object-storage:global:a/e97a8c01ac694e308ef3ad77957bb960:1ef3fc71-c501-4369-be8b-dfe99c0c7954::
COS_BUCKETNAME=<YOUR BUCKET NAME>
EOF
```

![](<.gitbook/assets/image (22).png>)

Now we create a secret from the text file:

```
ibmcloud ce secret create -name cos-secret --from-env-file cos.env
```

![](<.gitbook/assets/image (23).png>)

Finally we bind the Secret to the backend application.

```
ibmcloud ce application update --name backend --env-from-secret cos-secret
```

![](<.gitbook/assets/image (24).png>)

## Testing the upload of text files

Navigate to your front-end application in the Browser and upload a text file with english language of your choice or use the samples below.&#x20;

{% file src=".gitbook/assets/example-1.txt" %}

{% file src=".gitbook/assets/example-2.txt" %}
example-2.txt
{% endfile %}

{% file src=".gitbook/assets/example-3.txt" %}
example-3.txt
{% endfile %}

![](<.gitbook/assets/image (25).png>)

![](<.gitbook/assets/image (26).png>)
