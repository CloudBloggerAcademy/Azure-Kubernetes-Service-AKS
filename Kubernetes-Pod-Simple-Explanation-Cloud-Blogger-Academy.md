# Cloud Blogger Academy
## Kubernetes Pod — Simple Explanation

> **Learn Cloud, DevOps & Kubernetes with Cloud Blogger Academy**

[🌐 Cloud Blogger Academy – Explore Courses](https://www.cloudbloggeracademy.com/courses)

---

# 1. What is a Container?

A **container is an isolated environment in which an application runs.**

```text
Application
     ↓
Container
```

The main job of a container is to **run the application**.

A container can be created and run from a container image.

---

# 2. What is a Pod?

A **Pod is the smallest deployable unit in Kubernetes.**

Kubernetes manages **Pods**, and containers run inside Pods.

```text
Kubernetes
     ↓
    Pod
     ↓
Container
     ↓
Application
```

### Remember

> **Container runs the application, while a Pod is the basic unit Kubernetes uses to run and manage containers.**

---

# 3. Why Does Kubernetes Use Pods?

Kubernetes does much more than simply start or stop a container.

Kubernetes needs to manage things such as:

- Where the application should run
- Restarting a container when it fails
- Networking
- Storage
- Running multiple closely related containers together
- Scaling applications
- Maintaining the desired state

Therefore, Kubernetes uses **Pod as an abstraction around containers**.

```text
Container
    ↓
   Pod
    ↓
Kubernetes
```

---

# 4. How Many Containers Can a Pod Have?

A Pod can contain:

```text
1 Container
```

or

```text
Multiple Containers
```

Most commonly, a Pod contains **one main application container**.

Multiple containers are used when they need to work closely together.

---

# 5. What Can a Pod Provide?

A Pod allows containers running inside it to work as a **single unit**.

## Shared Network

Containers inside the same Pod can share the same network namespace.

```text
Container 1
     ↕
  Network
     ↕
Container 2
```

## Shared Storage

Containers inside the same Pod can use shared volumes.

```text
Container 1 ──┐
              ↓
       Shared Volume
              ↑
Container 2 ──┘
```

## Common Management

Kubernetes schedules and manages the containers in a Pod as a common unit.

---

# 6. Pod vs Container

| Container | Pod |
|---|---|
| Runs the application | Kubernetes unit used to run and manage containers |
| Container runtime concept | Kubernetes concept |
| Provides an isolated environment for the application | Provides a Kubernetes execution unit for one or more related containers |
| Usually runs an application process | Can contain one or multiple containers |
| Runs through a container runtime | Managed by Kubernetes |
| Has its own container-level environment | Containers can share network and storage within the Pod |

---

# 7. Does a Pod Support Only Docker Containers?

**No.**

A Pod is **not a Docker feature**.

Kubernetes works with container runtimes such as:

```text
containerd
CRI-O
```

So remember:

> **Pod is a Kubernetes concept, not a Docker concept.**

Also:

> **Docker Engine is not mandatory for Kubernetes to run containers.**

Images built using Docker can commonly be used by Kubernetes through the container runtime.

---

# 8. Image → Container → Pod → Kubernetes

The basic relationship can be understood like this:

```text
Container Image
       ↓
Container Runtime
       ↓
   Container
       ↓
      Pod
       ↓
  Kubernetes
```

More precisely:

> **The container runtime runs the container, while Kubernetes manages the Pod.**

---

# 9. The Most Important Concept

### Container

> **Runs the application.**

### Pod

> **The smallest deployable unit in Kubernetes that contains one or more containers.**

### Kubernetes

> **Manages Pods by scheduling, restarting, scaling, networking, and maintaining the desired state.**

---

# Final Concept

```text
KUBERNETES
     ↓
    POD
     ↓
 CONTAINER
     ↓
APPLICATION
```

> **A Pod is not a replacement for a container. A Pod is a Kubernetes unit that contains one or more containers, while the container actually runs the application.**

---

# Learn Kubernetes & Azure with Cloud Blogger Academy

Want to learn **Azure Kubernetes Service (AKS), Kubernetes, Docker, DevOps and Cloud technologies** in a practical way?

👉 [**Join the Azure Kubernetes Service (AKS) Course – Cloud Blogger Academy**](https://www.cloudbloggeracademy.com/courses/Azure-Kubernetes-Service-AKS-697cdf48a319b53dbaa20bab)

### 🌐 Cloud Blogger Academy

**Learn. Practice. Build. Deploy.**

[**Explore All Courses →**](https://www.cloudbloggeracademy.com/courses)

---

© **Cloud Blogger Academy** | Cloud • DevOps • Kubernetes • Azure
