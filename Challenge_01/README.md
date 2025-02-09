# Solutions 

Error : "ImagePullBackOff" due to incorrect image name

# Troubleshooting Steps

```bash
alias k=kubectl
```

Step 1: Check the namespace where the pod is running
```bash
k get ns
```
![image](../images/Challenge_02/ch2_01.png)

Step 2: Check the pod status. We see that the pod is in "ImagePullBackOff" state
```bash
k get pods -n challenge-02
```
![image](../images/Challenge_02/ch2_02.png)

Step 3: Check the pod events using the describe command
```bash
k describe pod <POD_NAME> -n challenge-02
```
![image](../images/Challenge_02/ch2_03.png)

Step 4: Try to pull the image manually
```bash
docker pull prajwal3498/python-ms-crisp-devops-private
```
![image](../images/Challenge_02/ch2_04.png)

## Solution

Edit the deployment and correct the image name. Apply the changes.

```bash
k apply -f . 
```