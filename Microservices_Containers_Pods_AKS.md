# Cloud Blogger Academy

## Microservices → Containers → Pods → AKS

Learn Azure Kubernetes Service (AKS) with practical, hands-on training
from **Cloud Blogger Academy**.

👉 [Explore the Azure Kubernetes Service (AKS)
Course](https://www.cloudbloggeracademy.com/courses/Azure-Kubernetes-Service-AKS-697cdf48a319b53dbaa20bab)

------------------------------------------------------------------------

# 1. Start with a Monolithic Application

Imagine we have an **E-Commerce Application**.

``` text
                 E-Commerce Application
                         |
        --------------------------------------
        |          |          |              |
      Login      Product      Order        Payment
```

In a **Monolithic Architecture**, all these functionalities are part of
one application.

------------------------------------------------------------------------

# 2. Divide the Application into Microservices

Now, we divide the application into smaller, independently manageable
services.

``` text
                 E-Commerce Application
                         |
        --------------------------------------
        |          |          |              |
   User Service Product Service Order Service Payment Service
```

Each service has its own responsibility:

-   **User Service** → Manages users and authentication
-   **Product Service** → Manages products
-   **Order Service** → Manages orders
-   **Payment Service** → Manages payments

This approach is called **Microservices Architecture**.

------------------------------------------------------------------------

# 3. Package Each Microservice into a Container

Each microservice can be packaged into its own container.

``` text
User Service
     ↓
User Container

Product Service
     ↓
Product Container

Order Service
     ↓
Order Container

Payment Service
     ↓
Payment Container
```

Overall:

``` text
Microservices
     |
     ├── User Service     → Container
     ├── Product Service  → Container
     ├── Order Service    → Container
     └── Payment Service  → Container
```

The container provides a consistent environment in which the application
can run.

------------------------------------------------------------------------

# 4. Run Containers inside Pods

Kubernetes uses a **Pod** as its smallest deployable unit.

In a simple architecture, we can run one main application container
inside one Pod.

``` text
User Container
      ↓
    Pod 1

Product Container
      ↓
    Pod 2

Order Container
      ↓
    Pod 3

Payment Container
      ↓
    Pod 4
```

The basic relationship is:

``` text
Microservice
     ↓
Container
     ↓
Pod
```

## Important

**Pod and Container are not the same thing.**

A Pod can contain one or more containers.

``` text
Pod
 |
 ├── Container
 └── Container
```

In many application deployments, one main application container is
placed inside a Pod. Multiple containers can also be placed in the same
Pod when they need to work closely together.

------------------------------------------------------------------------

# 5. Run the Pods on AKS

Now we can run these Pods on **Azure Kubernetes Service (AKS)**.

``` text
                         Azure
                           |
                          AKS
                           |
                  Kubernetes Cluster
                           |
       ---------------------------------------
       |          |          |               |
     Pod 1      Pod 2      Pod 3           Pod 4
       |          |          |               |
     User       Product     Order          Payment
   Service      Service    Service         Service
```

**AKS** is Microsoft's managed Kubernetes service for running Kubernetes
workloads on Azure.

------------------------------------------------------------------------

# 6. Complete Architecture

The complete flow looks like this:

``` text
              E-Commerce Application
                        ↓
                  Microservices
                        ↓
        ---------------------------------
        |        |        |             |
       User    Product   Order        Payment
      Service  Service   Service       Service
        ↓        ↓        ↓             ↓
    Container Container Container    Container
        ↓        ↓        ↓             ↓
       Pod      Pod      Pod           Pod
        \        |        |            /
         \       |        |           /
              Kubernetes
                   ↓
                  AKS
                   ↓
                 Azure
```

------------------------------------------------------------------------

# 7. What Happens When Traffic Increases?

Suppose the **Payment Service** receives more traffic.

Initially:

``` text
Payment Service
       ↓
   Payment Pod
```

When the workload increases, Kubernetes can run additional Pods
according to the configured scaling strategy.

``` text
          Payment Service
                 |
        -------------------
        |        |        |
      Pod 1    Pod 2    Pod 3
```

The multiple Pods allow the application workload to be distributed
across instances.

------------------------------------------------------------------------

# 8. The Complete Sequence

Remember this sequence:

``` text
Application
     ↓
Microservices
     ↓
Containers
     ↓
Pods
     ↓
Kubernetes
     ↓
AKS
```

### In one sentence

> We divide an application into Microservices → package each
> Microservice into Containers → run those Containers inside Pods → use
> Kubernetes to manage the Pods → run Kubernetes on Azure using AKS.

------------------------------------------------------------------------

# 9. Quick Revision

  -----------------------------------------------------------------------
  Component                           Purpose
  ----------------------------------- -----------------------------------
  **Microservice**                    A small, independently manageable
                                      part of an application

  **Container**                       Packages the application and its
                                      dependencies

  **Pod**                             Kubernetes' smallest deployable
                                      unit

  **Kubernetes**                      Orchestrates and manages workloads
                                      through Pods

  **AKS**                             Microsoft's managed Kubernetes
                                      service on Azure
  -----------------------------------------------------------------------

------------------------------------------------------------------------

# 10. Final Mental Model

``` text
                 APPLICATION
                      ↓
              ┌───────────────┐
              │ Microservices │
              └───────────────┘
                      ↓
              ┌───────────────┐
              │  Containers   │
              └───────────────┘
                      ↓
              ┌───────────────┐
              │     Pods      │
              └───────────────┘
                      ↓
              ┌───────────────┐
              │  Kubernetes   │
              └───────────────┘
                      ↓
              ┌───────────────┐
              │      AKS      │
              └───────────────┘
                      ↓
                   AZURE
```

------------------------------------------------------------------------

# Learn Azure Kubernetes Service (AKS)

**Cloud Blogger Academy** provides practical Azure and Kubernetes
training designed to help students understand concepts from fundamentals
to real-world implementation.

👉 [Cloud Blogger Academy --- Azure Kubernetes Service (AKS)
Course](https://www.cloudbloggeracademy.com/courses/Azure-Kubernetes-Service-AKS-697cdf48a319b53dbaa20bab)
