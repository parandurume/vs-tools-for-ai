# 클라우드에서 텐서플로우 모델 훈련하기
본 강의에서는 Azure [Deep Learning Virtual Machine](https://docs.microsoft.com/azure/machine-learning/data-science-virtual-machine/deep-learning-dsvm-overview)의 [MNIST 데이터 셋](http://yann.lecun.com/exdb/mnist/)을 사용하여 텐서플로우 모델을 훈련하도록 하겠습니다. 

MNIST 데이터베이스는 6만개의 예제 훈련 세트와 수기로 짠 1만개의 예제 테스트 셋을 담고 있습니다.

## 사전 준비
시작하기 전에 다음의 사항들이 설치 또는 설정되어 있는 지 확인해주세요.

### 샘플코드 내려받기
텐서플로우, CNTK, Theano 등등을 통해 딥러닝을 시작할 수 있는 샘플을 담고 있는 본 [깃허브 리포지토리](https://github.com/Microsoft/samples-for-ai)를 내려받아 주세요.

### 애저 딥러닝 가상 머신 설정하기
[딥러닝 가상머신 설정하기](https://docs.microsoft.com/azure/machine-learning/data-science-virtual-machine/provision-deep-learning-dsvm) 안내서를 읽어주세요. 

> [!주의] 
> **Location**을 US West 2 (또는 딥러닝 VM을 갖춘 다른 지역)으로 맞춰주시고 **OS type** 은 Linux 해주세요.

### .bashrc 를 업데이트 하셔서 Non-interactive Bash Session을 통해 Remote Job Submission 이 가능하게 해주세요
Login to your Deep Learning VM using a tool like Putty or similar. Execute below to modify your bashrc file to enable remote deep learning job submission (configures remote behavior to work just like if you logged into the VM).

```bash
echo -e ". /etc/profile\n$(cat ~/.bashrc)" > ~/.bashrc
``` 

## Open project

- Launch Visual Studio and select **File > Open > Project/Solution**.

- Select the **examples\tensorflow** folder from the samples repository downloaded  

![Open project](./media/tensorflow-local/open-folder.png)

- Open the **TensorflowExamples.sln** file.

![Open solution](./media/tensorflow-local/open-solution.png)

## Add Azure Remote VM

In Server Explorer, right click the **Remote Machines** node under the AI Tools node and select "Add…". Enter the Remote Machine display name, IP host, SSH port, user name and password/key file. 

![Add a new remote machine](./media/tensorflow-vm/add-remote-vm.png)

## Submit job to Azure VM
Right click on MNIST project in **Solution Explorer** and select **Submit Job**.

![Job submission to a remote machine](./media/tensorflow-vm/job-submission.png)

In the submission window:

- In the list of **Cluster to use**, select the remote machine (with "rm:" prefix) to submit the job to.

- Enter a **Job name**. 

- Click **Submit**. 

![Job submission to Docker container](./media/tensorflow-vm/job-submission-docker.png)

User can also submit jobs to run in a Docker container:

- Check 'Run In Docker' checkbox

- User can select the command to run Docker container: "Docker" or ["NvidiaDocker"](https://github.com/NVIDIA/nvidia-docker)

- User can select the Docker image in "Docker image" combobox, or input his own docker image built in Docker Hub. The default docker registry is [Docker Hub](https://hub.docker.com/)

- User can choose the identity to run Docker container in remote machine. The default user is "root".


## Check status of job 
To see status and details of jobs: expand the virtual machine you submitted the job to in the **Server Explorer**. Double click on **Jobs**.

![Job browser](./media/tensorflow-vm/job-browser.png)

## Clean up resources (optional)

Stop the VM if you plan on using it in the near future. If you are finished with this tutorial, run the following command to clean up your resources:

```azure-interactive
az group delete --name myResourceGroup
```
