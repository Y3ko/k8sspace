## Sıfırdan Kubernetes Test Ortamı Kurulum Rehberi

Bu belge, Ubuntu 20.04 sunucuları kullanarak sıfırdan bir Kubernetes test ortamı kurmak için adım adım bir rehber sunmaktadır. Rehber, birer adet Master ve Worker node ve bir adet NFS server kurulumunu kapsamaktadır.

**Donanım Gereksinimleri:**

- **Master Node:**
  - 4 GB RAM
  - 2 CPU
  - 25 GB disk
- **Worker Node:**
  - 6 GB RAM
  - 3 CPU
  - 50 GB disk
- **NFS Server:**
  - 1 GB RAM
  - 1 CPU
  - 125 GB disk

**Kurulum Adımları:**

### 1. Script Kurulumu:

1. Master ve Worker node'lara [install.sh scriptini buradan indirin](https://github.com/omerbsezer/Fast-Kubernetes/blob/main/create_real_cluster/install.sh).
2. Her iki node'da da scripti çalıştırın:

    ```bash
    bash install.sh
    ```

### 2. Master Node Kurulumu:

1. Master node'da [master.sh scriptini buradan indirin](https://github.com/omerbsezer/Fast-Kubernetes/blob/main/create_real_cluster/master.sh).
2. Scripti çalıştırın:

    ```bash
    bash master.sh
    ```

### 3. MetalLB Kurulumu:

1. Master node'da MetalLB kurulumu için [MetalLB kurulum dökümanını buradan takip edin](https://akyriako.medium.com/load-balancing-with-metallb-in-bare-metal-kubernetes-271aab751fb8).

### 4. Ingress Kurulumu:

1. MetalLB ile birlikte Ingress kurulumu için [Ingress kurulum dökümanını buradan takip edin](https://onurbolatoglu.medium.com/kubernetes-ingress-for-kubeadm-2fba18e9ba45).

### 5. NFS Server Kurulumu:

1. NFS server kurulumu için [NFS kurulum dökümanını buradan takip edin](https://github.com/kubernetes-sigs/nfs-subdir-external-provisioner?tab=readme-ov-file) ve [NFS kurulum dökümanını buradan takip edin](https://medium.com/@shatoddruh/kubernetes-how-to-install-the-nfs-server-and-nfs-dynamic-provisioning-on-azure-virtual-machines-e85f918c7f4b).

**Notlar:**

- Bu belge, bilgi amaçlıdır ve ortamdan ortama değişiklik gösterebilir.
- Kurulum sırasında herhangi bir sorunla karşılaşırsanız, lütfen ilgili dökümanlarda yer alan hata ayıklama adımlarını takip edin.
- Daha fazla bilgi için Kubernetes ve ilgili araçların resmi belgelerine bakabilirsiniz.

## Ek Hususlar

- Bu belgede sunulan kurulum adımları temel bir Kubernetes test ortamı oluşturmak için yeterlidir. Daha karmaşık kurulumlar için Kubernetes'in resmi belgelerine bakabilirsiniz.
- Kubernetes, sürekli gelişen bir platformdur. Bu nedenle, en güncel bilgiler için Kubernetes belgelerini ve topluluk forumlarını takip etmeniz önemlidir.

## Faydalı Kaynaklar

- Kubernetes Resmi Belgeleri: [https://kubernetes.io/docs/home/](https://kubernetes.io/docs/home/)
- Kubernetes Kurulum Rehberi: [https://kubernetes.io/docs/setup/](https://kubernetes.io/docs/setup/)
- Kubernetes Topluluk Forumları: [https://kubernetes.io/community/](https://kubernetes.io/community/)
- MetalLB Kurulum Dökümanı: [https://akyriako.medium.com/load-balancing-with-metallb-in-bare-metal-kubernetes-271aab751fb8](https://akyriako.medium.com/load-balancing-with-metallb-in-bare-metal-kubernetes-271aab751fb8)
- Ingress Kurulum Dökümanı: [https://medium.com/tektutor/using-nginx-ingress-controller-in-kubernetes-bare-metal-setup-890eb4e7772](https://medium.com/tektutor/using-nginx-ingress-controller-in-kubernetes-bare-metal-setup-890eb4e7772)
- NFS Kurulum Dökümanı: [https://github.com/kubernetes-sigs/nfs-subdir-external-provisioner?tab=readme-ov-file](https://github.com/kubernetes-sigs/nfs-subdir-external-provisioner?tab=readme-ov-file), [https://medium.com/@shatoddruh/kubernetes-how-to-install-the-nfs-server-and-nfs-dynamic-provisioning-on-azure-virtual-machines-e85f918c7f4b](https://medium.com/@shatoddruh/kubernetes-how-to-install-the-nfs-server-and-nfs-dynamic-provisioning-on-azure-virtual-machines-e85f918c7f4b)
