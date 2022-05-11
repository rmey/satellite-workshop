# 2. Create Code Engine Project

1. In the IBM Cloud Shell execute the following command to create a new code engine project:

```
ibmcloud ce project create -n <YOUR UNIQUE PROJECT NAME>
```

![](<.gitbook/assets/image (12).png>)

2\. Connect to the Code Engine Project using the following command

```
ibmcloud ce project select -n <YOUR UNIQUE PROJECT NAME>
```

3\. Connect the kubectl CLI to the Knative Project of Code Engine

```
$(ibmcloud ce project current | grep export) 
```

4\. Check that kubectl works

```
kubectl get po
```

![](<.gitbook/assets/image (13).png>)

{% hint style="info" %}
You have now also connected kubectl Kubernetes CLI to your Code Engine project giving you access to deeper diagnostics functions.
{% endhint %}
