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
- ★　Kubernetes cluster (một cụm bao gồm một master và một hoặc nhiều worker) bao gồm 2 thành phần (component) chính:
-    Master nodes (control plane)
-    Worker nodes
