# Kubernetes-tutorial
Trang chủ kubernetes
- https://kubernetes.io/docs/home/
1. Kubernetes là gì? 
- Kubernetes (hay k8s) là một nền tảng open-source được dùng để chạy, quản lý, điều phối các ứng dụng được container hóa container và được phát triển bởi google. 
- Có thể dùng kubernetes để phát triển ứng dụng trên nhiều nền tảng khác nhau như on-premise, cloud, or virtual machines.
- Bạn có thể điều chỉnh tăng giảm tài nguyên, bản chạy phục vụ cho dịch vụ (scale), bạn có thể cập nhật (update), thu hồi update khi có vấn đề... 
- ==> hạn chế thời gian downtime của ứng dụng, Tối ưu hóa được tài nguyên hệ thống.
- Kubernetes cho phép chúng ta group và quản lý container theo ứng dụng và project, nó cũng cung cấp tính năng Service Discovery and Load Balancing để chúng ta có thể dẫn request của ứng dụng tới đúng container, và cũng có tính năng giúp ứng dụng của chúng ta high available nhất có thể, khi một server vật lý gặp sự cố, nó có thể chuyển container của ta sang server vật lý khác. 
- Ngoài ra kubernetes còn nhiều tính năng khác như: auto scale resource, auto restart application when failure, zero downtime deployment, automated rollouts and rollbacks application, v...v...

2. Kiến trúc của Kubernetes 
★　Kubernetes cluster (một cụm bao gồm một master và một hoặc nhiều worker) bao gồm 2 thành phần (component) chính:
  -    Master nodes (control plane)
  -    Worker nodes
★　 Master nodes (control plane)：
  Master node chỉ có nhiệm vụ control state của cluster, nó không có chạy ứng dụng trên đó, ứng dụng của chúng ta sẽ được chạy trên worker node. 
  Master nodes bao gồm 4 thành phần chính:
    ●　API server: thành phần chính để giao tiếp với các thành phần khác
    ●　Controller manager: gồm nhiều controller riêng cụ thể cho từng resource và thực hiện các chứng năng cụ thể cho từng thằng resource trong kube như create pod, create deployment,v.v.
    ●　Scheduler: schedules ứng dụng tới node nào
    ●　Etcd: là một database để lưu giữ trạng thái và resource của cluster
★　 Worker node：
  Là nơi chạy các ứng dụng
  Gồm 3 thành phần chính:
    ●  Container runtime (docker, rkt hoặc nền tảng khác): chạy container
    ●  Kubelet: giao tiếp với API server và quản lý container trong một worker node
    ●  Kubernetes Service Proxy (kube-proxy): quản lý network và traffic của các ứng dụng trong woker node

3. Cài đặt
  Bạn phải cài đặt các packages sau đây trên tất cả các node.
    ●  docker
    ●  kubelet   : component chạy trên tất cả các máy trong Cluster và thực hiện những việc như khởi động pods và container
    ●  kubectl   : giao tiếp với cluster
    ●  kubeadm   : lệnh để khởi động cluster
    

★ Note: Nếu bạn dự định chạy 1 Kubernetes cluster trên laptop (locally), bạn cần phải có 1 tool được cài đặt trước giống như là  Minikube và sau đó re-run the commands kubectl cluster-info.
★ Nếu lỗi xuất hiện "validate service connection: CRI v1 runtime API is not implemented for endpoint \"unix:///var/run/containerd/containerd.sock\": rpc error: code = Unimplemented desc = unknown service runtime.v1.RuntimeService " 
=> rm /etc/containerd/config.toml
systemctl restart containerd
kubeadm init

