
# 로컬에서 텐서플로우(TensorFlow) 훈련하기 

이번 빠른 시작에서 텐서플로우 모델과 [MNIST](http://yann.lecun.com/exdb/mnist/) 데이턴 세을 통해 AI 툴을 로컬에서 실행해보겠습니다. 
MNIST 데이터베이스는 6만개의 예제로 훈련 세트를 갖추고 있으며 1만개의 수기 예제 실험용 세트를 갖추고 있습니다. 

## 사전 준비

시작하기 전에 아래 사항이 설치되었는 지 확인 해주세요.

### 구글 텐서플로우(Google TensorFlow) 

터미널 창에서 아래 명령을 실행해주세요. 


```cmd
pip install tensorflow
```

또는 만약 Nvidia GPU가 설치되어 있다면

```cmd
pip install tensorflow-gpu
```

### NumPy 와 SciPy 

터미널에서 아래 명령을 실행해주세요:

```cmd
pip install numpy scipy
``` 

### 샘플코드 다운 받기

[GitHub repository](https://github.com/Microsoft/samples-for-ai) 다운받기 
텐서플로우, CNTK, Theano 등등의 딥러닝 시작울 위한 예제들을 포함하고 있습니다. 

## 솔루션을 열고 모델을 훈련하기 

- Visual Studio를 실행하셔서 **File > Open > Project/Solution** 를 선택해주세요.

- 다운받은 예제 리포지터리에서 하위폴더 **examples\tensorflow**를 선택하시고 **TensorflowExamples.sln** 파일을 열어주세요.

![Open folder](./media/tensorflow-local/open-folder.png)

![Open solution](./media/tensorflow-local/open-solution.png)

- **Solution Explorer**에서 MNIST 프로젝트를 찾아, 마우스 오른쪽을 클릭해서 **Set as StartUp Project** 를 선택합니다.

- **Start** 를 누릅니다. 

- 콘솔창에 결과가 나타납니다.

![콘솔에서 도출된 예제](./media/tensorflow-local/console-output.png)

> [클라우드에서 텐서플로우 모델 훈련하기](tensorflow-vm.md)
