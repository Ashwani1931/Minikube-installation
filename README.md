# Minikube-installation
How to install Minikube in local machine and how to run a pod also


Install kubectl binary on Windows by using curl method

STEP 1: Use Win+S and search Power Shell .

STEP 2: Do right click on Powershell and Run as Adminstrator.

STEP 3: To install Minikube , We need to setup Kubectl in Windows.

STEP 4: SETUP OF Kubectl.

  (a) If you have curl installed, use this command:

            curl.exe -LO "https://dl.k8s.io/release/v1.33.0/bin/windows/amd64/k

 (b) Test to ensure the version of kubectl is the same as downloaded:

            kubectl version --client  

  If its verified ,then we are good to go for Minikube installation

STEP 5: MINIKUBE INSTALLATION

  Minikube is local Kubernetes, focusing on making it easy to learn and develop for Kubernetes.

  What we need for installation process?

  2 CPUs or more
  
2GB of free memory

20GB of free disk space

Internet connection

Container or virtual machine manager, such as: Docker, QEMU, Hyperkit, Hyper-V, KVM, Parallels, Podman, VirtualBox, or VMware Fusion/Workstation
We are using here VirtualBox.

(a) By using powershell , we will use this command for download minikube

               New-Item -Path 'c:\' -Name 'minikube' -ItemType Directory -Force
               Invoke-WebRequest -OutFile 'c:\minikube\minikube.exe' -Uri 'https://github.com/kubernetes/minikube/releases/latest/download/minikube-windows-amd64.exe' -UseBasicParsing

(b) Add the minikube.exe binary to your PATH.
Make sure to run PowerShell as Administrator.

               $oldPath = [Environment]::GetEnvironmentVariable('Path', [EnvironmentVariableTarget]::Machine)
               if ($oldPath.Split(';') -inotcontains 'C:\minikube'){
               [Environment]::SetEnvironmentVariable('Path', $('{0};C:\minikube' -f $oldPath), [EnvironmentVariableTarget]::Machine)
               }

  # If you used a powershell for the installation, please close the terminal and reopen it before running minikube.

  (c) Now, Run the Minikube Cluster

  using,

          minikube start

  (d) To verify Minikube is working or not , use 

          minikube status

  STEP 6: We run a Pod in cluster.By using,

          kubectl run mypod --image=nginx:latest

  STEP 7: To verify pod is running or not . we use ,

           kubectl get pod
           
           ![Screenshot 2025-04-30 204820](https://github.com/user-attachments/assets/4d2ebd9f-39c3-4e5a-89a5-92e53dd6df6d)


  Here we completed our Minikube installation as well as run a Pod too.

  



