---
title: Kubernetes-gRPC для разработчиков WCF
description: Запуск ASP.NET Core gRPC Services в кластере Kubernetes.
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 819c761a7a55485612b7fb0c8b392971751d8724
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841579"
---
# <a name="kubernetes"></a><span data-ttu-id="dd419-103">Kubernetes</span><span class="sxs-lookup"><span data-stu-id="dd419-103">Kubernetes</span></span>

<span data-ttu-id="dd419-104">Хотя контейнеры можно запускать вручную на узлах DOCKER, для надежных рабочих систем лучше использовать механизм оркестрации контейнеров для управления несколькими экземплярами, работающими на нескольких серверах в кластере.</span><span class="sxs-lookup"><span data-stu-id="dd419-104">Although it's possible to run containers manually on Docker hosts, for reliable production systems it's preferable to use a Container Orchestration Engine to manage multiple instances running across several servers in a cluster.</span></span> <span data-ttu-id="dd419-105">Доступны различные механизмы оркестрации контейнеров, в том числе Kubernetes, Docker Swarm и Apache Mesos.</span><span class="sxs-lookup"><span data-stu-id="dd419-105">There are various Container Orchestration Engines available, including Kubernetes, Docker Swarm and Apache Mesos.</span></span> <span data-ttu-id="dd419-106">Но из этих ядер Kubernetes далеко и далеко не самый широко используемый, поэтому он будет посвящен этой главе.</span><span class="sxs-lookup"><span data-stu-id="dd419-106">But of these engines, Kubernetes is far and away the most widely used, so it will be the focus of this chapter.</span></span>

<span data-ttu-id="dd419-107">Kubernetes включает следующие функциональные возможности:</span><span class="sxs-lookup"><span data-stu-id="dd419-107">Kubernetes includes the following functionality:</span></span>

- <span data-ttu-id="dd419-108">**Планирование** запускает контейнеры на нескольких узлах в кластере, обеспечивая сбалансированное использование доступного ресурса, поддержание работоспособности контейнеров при сбоях и обработку последовательных обновлений для новых версий образов или новых конфигураций.</span><span class="sxs-lookup"><span data-stu-id="dd419-108">**Scheduling** runs containers on multiple nodes within a cluster, ensuring balanced usage of the available resource, keeping containers running if there are outages, and handling rolling updates to new versions of images or new configurations.</span></span>
- <span data-ttu-id="dd419-109">**Проверки работоспособности** отслеживают контейнеры, чтобы обеспечить непрерывную работу службы.</span><span class="sxs-lookup"><span data-stu-id="dd419-109">**Health checks** monitor containers to ensure continued service.</span></span>
- <span data-ttu-id="dd419-110">**Обнаружение службы DNS &** обрабатывает маршрутизацию между службами в кластере.</span><span class="sxs-lookup"><span data-stu-id="dd419-110">**DNS & service discovery** handles routing between services within a cluster.</span></span>
- <span data-ttu-id="dd419-111">Входящий трафик **предоставляет доступ к** выбранным службам извне и обычно обеспечивает балансировку нагрузки между экземплярами этих служб.</span><span class="sxs-lookup"><span data-stu-id="dd419-111">**Ingress** exposes selected services externally, and generally provides load-balancing across instances of those services.</span></span>
- <span data-ttu-id="dd419-112">**Управление ресурсами** подключает внешние ресурсы, такие как хранилище, к контейнерам.</span><span class="sxs-lookup"><span data-stu-id="dd419-112">**Resource management** attaches external resources such as storage to containers.</span></span>

<span data-ttu-id="dd419-113">В этой главе подробно описано, как развернуть службу ASP.NET Core gRPC и веб-сайт, который использует эту службу в кластере Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="dd419-113">This chapter will detail how to deploy an ASP.NET Core gRPC service and a website that consumes the service into a Kubernetes cluster.</span></span> <span data-ttu-id="dd419-114">Пример используемого приложения доступен в репозитории [DotNet-Architecture/GRPC-for-WCF-Developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/KubernetesSample) на сайте GitHub.</span><span class="sxs-lookup"><span data-stu-id="dd419-114">The sample application used is available from on the [dotnet-architecture/grpc-for-wcf-developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/KubernetesSample) repository on GitHub,</span></span>

## <a name="kubernetes-terminology"></a><span data-ttu-id="dd419-115">Терминология Kubernetes</span><span class="sxs-lookup"><span data-stu-id="dd419-115">Kubernetes terminology</span></span>

<span data-ttu-id="dd419-116">Kubernetes использует *конфигурацию требуемого состояния*. API используется для описания таких объектов *, как модули*Pod, *развертывания* и *службы*, а *плоскость управления* требует реализации требуемого состояния на всех *узлах* *кластера*.</span><span class="sxs-lookup"><span data-stu-id="dd419-116">Kubernetes uses *desired state configuration*: the API is used to describe objects such as *Pods*, *Deployments* and *Services*, and the *Control Plane* takes care of implementing the desired state across all the *nodes* in a *cluster*.</span></span> <span data-ttu-id="dd419-117">В кластере Kubernetes имеется *главный* узел, на котором работает *API Kubernetes*, который можно передавать с помощью программных средств или с помощью программы командной строки `kubectl`.</span><span class="sxs-lookup"><span data-stu-id="dd419-117">A Kubernetes cluster has a *Master* node that runs the *Kubernetes API*, which can be communicated with programmatically or using the `kubectl` command-line tool.</span></span> <span data-ttu-id="dd419-118">`kubectl` может создавать объекты и управлять ими с помощью аргументов командной строки, но лучше подходит для файлов YAML, содержащих данные объявления для объектов Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="dd419-118">`kubectl` can create and manage objects using command-line arguments, but works best with YAML files that contain declaration data for Kubernetes objects.</span></span>

### <a name="kubernetes-yaml-files"></a><span data-ttu-id="dd419-119">Файлы YAML Kubernetes</span><span class="sxs-lookup"><span data-stu-id="dd419-119">Kubernetes YAML files</span></span>

<span data-ttu-id="dd419-120">Каждый файл YAML Kubernetes будет иметь по крайней мере три свойства верхнего уровня.</span><span class="sxs-lookup"><span data-stu-id="dd419-120">Every Kubernetes YAML file will have at least three top-level properties.</span></span>

```yaml
apiVersion: v1
kind: Namespace
metadata:
  # Object properties
```

<span data-ttu-id="dd419-121">Свойство `apiVersion` используется для указания версии (и API), для которой предназначен файл.</span><span class="sxs-lookup"><span data-stu-id="dd419-121">The `apiVersion` property is used to specify which version (and which API) the file is intended for.</span></span> <span data-ttu-id="dd419-122">Свойство `kind` указывает тип объекта, представляемого YAML.</span><span class="sxs-lookup"><span data-stu-id="dd419-122">The `kind` property specifies the kind of object the YAML represents.</span></span> <span data-ttu-id="dd419-123">Свойство `metadata` содержит свойства объекта, такие как `name`, `namespace`или `labels`.</span><span class="sxs-lookup"><span data-stu-id="dd419-123">The `metadata` property contains object properties such as `name`, `namespace`, or `labels`.</span></span>

<span data-ttu-id="dd419-124">В большинстве файлов YAML Kubernetes также имеется раздел `spec`, описывающий ресурсы и конфигурацию, необходимые для создания объекта.</span><span class="sxs-lookup"><span data-stu-id="dd419-124">Most Kubernetes YAML files will also have a `spec` section that describes the resources and configuration necessary to create the object.</span></span>

### <a name="pods"></a><span data-ttu-id="dd419-125">Модули pod</span><span class="sxs-lookup"><span data-stu-id="dd419-125">Pods</span></span>

<span data-ttu-id="dd419-126">Модули Pod являются основными единицами выполнения в Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="dd419-126">Pods are the basic units of execution in Kubernetes.</span></span> <span data-ttu-id="dd419-127">Они могут запускать несколько контейнеров, но они также используются для выполнения отдельных контейнеров.</span><span class="sxs-lookup"><span data-stu-id="dd419-127">They can run multiple containers, but are also used to run single containers.</span></span> <span data-ttu-id="dd419-128">Модуль также включает все ресурсы хранилища, необходимые для контейнеров и IP-адрес сети.</span><span class="sxs-lookup"><span data-stu-id="dd419-128">The pod also includes any storage resources required by the container(s), and the network IP address.</span></span>

### <a name="services"></a><span data-ttu-id="dd419-129">Службы</span><span class="sxs-lookup"><span data-stu-id="dd419-129">Services</span></span>

<span data-ttu-id="dd419-130">Службы являются мета-объектами, описывающими Pod (или наборы модулей), и предоставляют способ доступа к ним в кластере, например для сопоставления имени службы с набором IP-адресов Pod с помощью службы DNS кластера.</span><span class="sxs-lookup"><span data-stu-id="dd419-130">Services are meta-objects that describe pods (or sets of pods) and provide a way to access them within the cluster, such as mapping a service name to a set of pod IP addresses using the cluster DNS service.</span></span>

### <a name="deployments"></a><span data-ttu-id="dd419-131">развертывания,</span><span class="sxs-lookup"><span data-stu-id="dd419-131">Deployments</span></span>

<span data-ttu-id="dd419-132">Развертывания — это *описанные объекты состояния* для модулей Pod.</span><span class="sxs-lookup"><span data-stu-id="dd419-132">Deployments are the *described state* objects for Pods.</span></span> <span data-ttu-id="dd419-133">Если вы создаете модуль Pod вручную, то при его завершении он не будет перезапущен.</span><span class="sxs-lookup"><span data-stu-id="dd419-133">If you create a Pod manually, when it terminates it won't be restarted.</span></span> <span data-ttu-id="dd419-134">Развертывания используются для информирования кластера о том, какие модули, и сколько реплик этих модулей следует запускать в настоящее время.</span><span class="sxs-lookup"><span data-stu-id="dd419-134">Deployments are used to tell the cluster which pods, and how many replicas of those pods, should be running at the present time.</span></span>

### <a name="other-objects"></a><span data-ttu-id="dd419-135">Другие объекты</span><span class="sxs-lookup"><span data-stu-id="dd419-135">Other objects</span></span>

<span data-ttu-id="dd419-136">Модули Pod, службы и развертывания — это всего три основных типа объектов.</span><span class="sxs-lookup"><span data-stu-id="dd419-136">Pods, Services, and Deployments are just three of the most basic object types.</span></span> <span data-ttu-id="dd419-137">Существует множество других типов объектов, управляемых кластером Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="dd419-137">There are dozens of other types of object that are managed by a Kubernetes cluster.</span></span> <span data-ttu-id="dd419-138">Дополнительные сведения см. в документации по [основным понятиям Kubernetes](https://kubernetes.io/docs/concepts/) .</span><span class="sxs-lookup"><span data-stu-id="dd419-138">For more information, see the [Kubernetes Concepts](https://kubernetes.io/docs/concepts/) documentation.</span></span>

### <a name="namespaces"></a><span data-ttu-id="dd419-139">Пространства имен</span><span class="sxs-lookup"><span data-stu-id="dd419-139">Namespaces</span></span>

<span data-ttu-id="dd419-140">Кластеры Kubernetes предназначены для масштабирования с сотнями или тысячами узлов и запуска аналогичного числа служб.</span><span class="sxs-lookup"><span data-stu-id="dd419-140">Kubernetes clusters are designed to scale to hundreds or thousands of nodes, and run similar numbers of services.</span></span> <span data-ttu-id="dd419-141">Чтобы избежать конфликта между именами объектов, пространства имен используются для группирования объектов вместе в составе более крупных приложений.</span><span class="sxs-lookup"><span data-stu-id="dd419-141">To avoid clashes between object names, namespaces are used to group objects together as part of larger applications.</span></span> <span data-ttu-id="dd419-142">Kubernetes службы выполняются в пространстве имен `default`.</span><span class="sxs-lookup"><span data-stu-id="dd419-142">Kubernetes own services run in a `default` namespace.</span></span> <span data-ttu-id="dd419-143">Все объекты пользователя должны создаваться в собственных пространствах имен, чтобы избежать возможных конфликт с объектами по умолчанию или другими клиентами в кластере.</span><span class="sxs-lookup"><span data-stu-id="dd419-143">All user objects should be created in their own namespaces to avoid potential clashes with default objects or other tenants in the cluster.</span></span>

## <a name="get-started-with-kubernetes"></a><span data-ttu-id="dd419-144">Начало работы с Kubernetes</span><span class="sxs-lookup"><span data-stu-id="dd419-144">Get started with Kubernetes</span></span>

<span data-ttu-id="dd419-145">Если вы используете DOCKER Desktop для Windows или macOS, Kubernetes уже доступен.</span><span class="sxs-lookup"><span data-stu-id="dd419-145">If you're running Docker Desktop for Windows or macOS, Kubernetes is already available.</span></span> <span data-ttu-id="dd419-146">Просто включите его в разделе Kubernetes окна Параметры.</span><span class="sxs-lookup"><span data-stu-id="dd419-146">Just enable it in the Kubernetes section of the Settings window.</span></span>

![Включение Kubernetes в DOCKER Desktop](media/kubernetes/enable-kubernetes-docker-desktop.png)

<span data-ttu-id="dd419-148">Чтобы запустить локальный кластер Kubernetes в Linux, просмотрите [minikube](https://github.com/kubernetes/minikube)или [MicroK8s](https://microk8s.io/) , если дистрибутив Linux поддерживает [привязку](https://snapcraft.io/).</span><span class="sxs-lookup"><span data-stu-id="dd419-148">To run a local Kubernetes cluster in Linux, look at [minikube](https://github.com/kubernetes/minikube), or [MicroK8s](https://microk8s.io/) if your Linux distribution supports [snaps](https://snapcraft.io/).</span></span>

<span data-ttu-id="dd419-149">Чтобы убедиться, что кластер работает и доступен, выполните команду `kubectl version`.</span><span class="sxs-lookup"><span data-stu-id="dd419-149">To check that your cluster is running and accessible, run the `kubectl version` command.</span></span>

```console
kubectl version
Client Version: version.Info{Major:"1", Minor:"14", GitVersion:"v1.14.6", GitCommit:"96fac5cd13a5dc064f7d9f4f23030a6aeface6cc", GitTreeState:"clean", BuildDate:"2019-08-19T11:13:49Z", GoVersion:"go1.12.9", Compiler:"gc", Platform:"windows/amd64"}
Server Version: version.Info{Major:"1", Minor:"14", GitVersion:"v1.14.6", GitCommit:"96fac5cd13a5dc064f7d9f4f23030a6aeface6cc", GitTreeState:"clean", BuildDate:"2019-08-19T11:05:16Z", GoVersion:"go1.12.9", Compiler:"gc", Platform:"linux/amd64"}
```

<span data-ttu-id="dd419-150">В этом примере как `kubectl` CLI, так и сервер Kubernetes работают под управлением версии 1.14.6.</span><span class="sxs-lookup"><span data-stu-id="dd419-150">In this example, both the `kubectl` CLI and the Kubernetes server are running version 1.14.6.</span></span> <span data-ttu-id="dd419-151">Каждая версия `kubectl` должна поддерживать предыдущую и следующую версии сервера, поэтому `kubectl` 1,14 должны работать и с серверными версиями 1,13 и 1,15.</span><span class="sxs-lookup"><span data-stu-id="dd419-151">Each version of `kubectl` is supposed to support the previous and next version of the server, so `kubectl` 1.14 should work with server versions 1.13 and 1.15 as well.</span></span>

## <a name="run-services-on-kubernetes"></a><span data-ttu-id="dd419-152">Запуск служб на Kubernetes</span><span class="sxs-lookup"><span data-stu-id="dd419-152">Run services on Kubernetes</span></span>

<span data-ttu-id="dd419-153">Пример приложения имеет `kube` каталог, содержащий три файла YAML.</span><span class="sxs-lookup"><span data-stu-id="dd419-153">The sample application has a `kube` directory containing three YAML files.</span></span> <span data-ttu-id="dd419-154">Файл `namespace.yml` объявляет пользовательское пространство имен `stocks`.</span><span class="sxs-lookup"><span data-stu-id="dd419-154">The `namespace.yml` file declares a custom namespace, `stocks`.</span></span> <span data-ttu-id="dd419-155">Файл `stockdata.yml` объявляет развертывание и службу для приложения gRPC, а `stockweb.yml` файл объявляет развертывание и службу для веб-приложения ASP.NET Core 3,0, которое использует службу gRPC.</span><span class="sxs-lookup"><span data-stu-id="dd419-155">The `stockdata.yml` file declares the Deployment and the Service for the gRPC application, and the `stockweb.yml` file declares the Deployment and Service for an ASP.NET Core 3.0 MVC web application that consumes the gRPC service.</span></span>

<span data-ttu-id="dd419-156">Чтобы использовать `YAML` файл с `kubectl`, используйте команду `apply -f`.</span><span class="sxs-lookup"><span data-stu-id="dd419-156">To use a `YAML` file with `kubectl`, use the `apply -f` command.</span></span>

```console
kubectl apply -f object.yml
```

<span data-ttu-id="dd419-157">Команда `apply` проверит допустимость файла YAML и отобразит все ошибки, полученные от API, но не ждет, пока все объекты, объявленные в файле, не будут созданы, так как это может занять некоторое время.</span><span class="sxs-lookup"><span data-stu-id="dd419-157">The `apply` command will check the validity of the YAML file and display any errors received from the API, but doesn't wait until all the objects declared in the file have been created as this can take some time.</span></span> <span data-ttu-id="dd419-158">Используйте команду `kubectl get` с соответствующими типами объектов для проверки создания объекта в кластере.</span><span class="sxs-lookup"><span data-stu-id="dd419-158">Use the `kubectl get` command with the relevant object types to check on object creation in the cluster.</span></span>

### <a name="the-namespace-declaration"></a><span data-ttu-id="dd419-159">Объявление пространства имен</span><span class="sxs-lookup"><span data-stu-id="dd419-159">The namespace declaration</span></span>

<span data-ttu-id="dd419-160">Объявление пространства имен является простым и требует только присваивания `name`.</span><span class="sxs-lookup"><span data-stu-id="dd419-160">Namespace declaration is simple and requires only assigning a `name`.</span></span>

```yaml
apiVersion: v1
kind: Namespace
metadata:
  name: stocks
```

<span data-ttu-id="dd419-161">Используйте `kubectl`, чтобы применить `namespace.yml` файл, и убедитесь, что пространство имен успешно создано.</span><span class="sxs-lookup"><span data-stu-id="dd419-161">Use `kubectl` to apply the `namespace.yml` file and check the namespace is created successfully.</span></span>

```console
> kubectl apply -f namespace.yml
namespace/stocks created

> kubectl get namespaces
NAME              STATUS   AGE
stocks            Active   2m53s
```

### <a name="the-stockdata-application"></a><span data-ttu-id="dd419-162">Приложение Стоккдата</span><span class="sxs-lookup"><span data-stu-id="dd419-162">The StockData application</span></span>

<span data-ttu-id="dd419-163">В файле `stockdata.yml` объявляются два объекта: развертывание и служба.</span><span class="sxs-lookup"><span data-stu-id="dd419-163">The `stockdata.yml` file declares two objects: a Deployment and a Service.</span></span>

#### <a name="the-stockdata-deployment"></a><span data-ttu-id="dd419-164">Развертывание Стоккдата</span><span class="sxs-lookup"><span data-stu-id="dd419-164">The StockData Deployment</span></span>

<span data-ttu-id="dd419-165">Часть развертывания предоставляет `spec` для самого развертывания, включая необходимое количество реплик, а также `template` для объектов Pod, которые будут созданы и управляются развертыванием.</span><span class="sxs-lookup"><span data-stu-id="dd419-165">The Deployment part provides the `spec` for the deployment itself, including the number of replicas required, and a `template` for the Pod objects to be created and managed by the deployment.</span></span> <span data-ttu-id="dd419-166">Обратите внимание, что объекты развертывания управляются с помощью `apps` API, как указано в `apiVersion`, а не в основном API Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="dd419-166">Note that Deployment objects are managed with the `apps` API, as specified in `apiVersion`, rather than the main Kubernetes API.</span></span>

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: stockdata
  namespace: stocks
spec:
  selector:
    matchLabels:
      run: stockdata
  replicas: 1
  template:
    metadata:
      labels:
        run: stockdata
    spec:
      containers:
      - name: stockdata
        image: stockdata:1.0.0
        imagePullPolicy: Never
        resources:
          limits:
            cpu: 100m
            memory: 100Mi
        ports:
        - containerPort: 80
```

<span data-ttu-id="dd419-167">Свойство `spec.selector` используется для сопоставления выполняющихся модулей Pod с развертыванием.</span><span class="sxs-lookup"><span data-stu-id="dd419-167">The `spec.selector` property is used to match running Pods to the Deployment.</span></span> <span data-ttu-id="dd419-168">Свойство `metadata.labels` Pod должно соответствовать свойству `matchLabels`, иначе вызов API завершится ошибкой.</span><span class="sxs-lookup"><span data-stu-id="dd419-168">The Pod's `metadata.labels` property must match the `matchLabels` property or the API call will fail.</span></span>

<span data-ttu-id="dd419-169">В разделе `template.spec` объявляется контейнер для выполнения.</span><span class="sxs-lookup"><span data-stu-id="dd419-169">The `template.spec` section declares the container to be run.</span></span> <span data-ttu-id="dd419-170">При работе с локальным кластером Kubernetes, например, предоставленным на рабочем столе DOCKER, можно указать образы, созданные локально, если у них есть тег версии.</span><span class="sxs-lookup"><span data-stu-id="dd419-170">When working with a local Kubernetes cluster, such as the one provided by Docker Desktop, you can specify images that were built locally as long as they have a version tag.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dd419-171">По умолчанию Kubernetes всегда проверяет и пытается извлечь новый образ.</span><span class="sxs-lookup"><span data-stu-id="dd419-171">By default, Kubernetes will always check for and try to pull a new image.</span></span> <span data-ttu-id="dd419-172">Если образ не удается найти ни в одном из известных репозиториев, создание Pod завершится ошибкой.</span><span class="sxs-lookup"><span data-stu-id="dd419-172">If it can't find the image in any of its known repositories, the Pod creation will fail.</span></span> <span data-ttu-id="dd419-173">Для работы с локальными образами задайте для `imagePullPolicy` значение `Never`.</span><span class="sxs-lookup"><span data-stu-id="dd419-173">To work with local images, set the `imagePullPolicy` to `Never`.</span></span>

<span data-ttu-id="dd419-174">Свойство `ports` указывает, какие порты контейнера должны быть опубликованы в модуле Pod.</span><span class="sxs-lookup"><span data-stu-id="dd419-174">The `ports` property specifies which container ports should be published on the Pod.</span></span>  <span data-ttu-id="dd419-175">Образ `stockservice` запускает службу на стандартном HTTP-порте, поэтому порт 80 публикуется.</span><span class="sxs-lookup"><span data-stu-id="dd419-175">The `stockservice` image runs the service on the standard HTTP port, so port 80 is published.</span></span>

<span data-ttu-id="dd419-176">Раздел `resources` применяет ограничения ресурсов к контейнеру, выполняющемуся в модуле Pod.</span><span class="sxs-lookup"><span data-stu-id="dd419-176">The `resources` section applies resource limits to the container running within the pod.</span></span> <span data-ttu-id="dd419-177">Это хороший подход, так как он предотвращает использование всеми доступными ресурсами ЦП или памяти на узле отдельным Pod.</span><span class="sxs-lookup"><span data-stu-id="dd419-177">This is good practice as it prevents an individual pod from consuming all the available CPU or memory on a node.</span></span>

> [!NOTE]
> <span data-ttu-id="dd419-178">ASP.NET Core 3,0 оптимизирована и настроена для работы в контейнерах с ограниченными ресурсами, а `dotnet/core/aspnet` образ DOCKER задает переменную среды, чтобы сообщить `dotnet` среде выполнения о том, что она находится в контейнере.</span><span class="sxs-lookup"><span data-stu-id="dd419-178">ASP.NET Core 3.0 has been optimized and tuned to run in resource-limited containers, and the `dotnet/core/aspnet` Docker image sets an environment variable to tell the `dotnet` runtime that it's in a container.</span></span>

#### <a name="the-stockdata-service"></a><span data-ttu-id="dd419-179">Служба Стоккдата</span><span class="sxs-lookup"><span data-stu-id="dd419-179">The StockData Service</span></span>

<span data-ttu-id="dd419-180">Часть службы файла YAML объявляет службу, которая предоставляет доступ к модулям Pod в кластере.</span><span class="sxs-lookup"><span data-stu-id="dd419-180">The Service part of the YAML file declares the service that provides access to the Pods within the cluster.</span></span>

```yaml
apiVersion: v1
kind: Service
metadata:
  name: stockdata
  namespace: stocks
spec:
  ports:
  - port: 80
  selector:
    run: stockdata
```

<span data-ttu-id="dd419-181">Спецификация службы использует свойство `selector` для сопоставления с выполняемым `Pods`, в данном случае поиск модулей Pod с меткой `run: stockdata`.</span><span class="sxs-lookup"><span data-stu-id="dd419-181">The Service spec uses the `selector` property to match running `Pods`, in this case looking for Pods with a label `run: stockdata`.</span></span> <span data-ttu-id="dd419-182">Указанный `port` в соответствующих модулях Pod публикуются с помощью именованной службы.</span><span class="sxs-lookup"><span data-stu-id="dd419-182">The specified `port` on matching Pods are published by the named service.</span></span> <span data-ttu-id="dd419-183">Другие модули, выполняющиеся в пространстве имен `stocks`, могут получить доступ к HTTP в этой службе, используя `http://stockdata` в качестве адреса.</span><span class="sxs-lookup"><span data-stu-id="dd419-183">Other Pods running in the `stocks` namespace can access HTTP on this service using `http://stockdata` as the address.</span></span> <span data-ttu-id="dd419-184">Модули Pod, работающие в других пространствах имен, могут использовать имя узла `http://stockdata.stocks`.</span><span class="sxs-lookup"><span data-stu-id="dd419-184">Pods running in other namespaces can use the `http://stockdata.stocks` hostname.</span></span> <span data-ttu-id="dd419-185">Можно управлять доступом к службам между пространствами имен с помощью [сетевых политик](https://kubernetes.io/docs/concepts/services-networking/network-policies/).</span><span class="sxs-lookup"><span data-stu-id="dd419-185">You can control cross-namespace service access using [Network Policies](https://kubernetes.io/docs/concepts/services-networking/network-policies/).</span></span>

#### <a name="deploy-the-stockdata-application"></a><span data-ttu-id="dd419-186">Развертывание приложения Стоккдата</span><span class="sxs-lookup"><span data-stu-id="dd419-186">Deploy the StockData application</span></span>

<span data-ttu-id="dd419-187">Используйте `kubectl`, чтобы применить файл `stockdata.yml` и проверить, были ли созданы развертывание и служба.</span><span class="sxs-lookup"><span data-stu-id="dd419-187">Use `kubectl` to apply the `stockdata.yml` file and check that the Deployment and Service were created.</span></span>

```console
> kubectl apply -f .\stockdata.yml
deployment.apps/stockdata created
service/stockdata created

> kubectl get deployment stockdata --namespace stocks
NAME        READY   UP-TO-DATE   AVAILABLE   AGE
stockdata   1/1     1            1           17s

> kubectl get service stockdata --namespace stocks
NAME        TYPE        CLUSTER-IP      EXTERNAL-IP   PORT(S)   AGE
stockdata   ClusterIP   10.97.132.103   <none>        80/TCP    33s
```

### <a name="the-stockweb-application"></a><span data-ttu-id="dd419-188">Приложение Стокквеб</span><span class="sxs-lookup"><span data-stu-id="dd419-188">The StockWeb application</span></span>

<span data-ttu-id="dd419-189">Файл `stockweb.yml` объявляет развертывание и службу для приложения MVC.</span><span class="sxs-lookup"><span data-stu-id="dd419-189">The `stockweb.yml` file declares the Deployment and Service for the MVC application.</span></span>

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: stockweb
  namespace: stocks
spec:
  selector:
    matchLabels:
      run: stockweb
  replicas: 1
  template:
    metadata:
      labels:
        run: stockweb
    spec:
      containers:
      - name: stockweb
        image: stockweb:1.0.0
        imagePullPolicy: Never
        resources:
          limits:
            cpu: 100m
            memory: 100Mi
        ports:
        - containerPort: 80
        env:
        - name: StockData__Address
          value: "http://stockdata"
        - name: DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2UNENCRYPTEDSUPPORT
          value: "true"

---

apiVersion: v1
kind: Service
metadata:
  name: stockweb
  namespace: stocks
spec:
  type: NodePort
  ports:
  - port: 80
  selector:
    run: stockweb
```

#### <a name="environment-variables"></a><span data-ttu-id="dd419-190">Переменные среды</span><span class="sxs-lookup"><span data-stu-id="dd419-190">Environment variables</span></span>

<span data-ttu-id="dd419-191">В разделе `env` объекта развертывания указываются переменные среды, которые должны быть заданы в контейнере, выполняющем образы `stockweb:1.0.0`.</span><span class="sxs-lookup"><span data-stu-id="dd419-191">The `env` section of the Deployment object specifies environment variables to be set in the container running the `stockweb:1.0.0` images.</span></span>

<span data-ttu-id="dd419-192">**`StockData__Address`** переменная среды будет сопоставляться с параметром конфигурации `StockData:Address`, благодаря поставщику конфигурации EnvironmentVariables.</span><span class="sxs-lookup"><span data-stu-id="dd419-192">The **`StockData__Address`** environment variable will map to the `StockData:Address` configuration setting thanks to the EnvironmentVariables configuration provider.</span></span> <span data-ttu-id="dd419-193">Этот параметр использует двойные подчеркивания между именами, чтобы разделить разделы.</span><span class="sxs-lookup"><span data-stu-id="dd419-193">This setting uses double underscores between names to separate sections.</span></span> <span data-ttu-id="dd419-194">Адрес использует имя службы `stockdata` службы, которая выполняется в том же пространстве имен Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="dd419-194">The address uses the service name of the `stockdata` Service, which is running in the same Kubernetes namespace.</span></span>

<span data-ttu-id="dd419-195">Переменная среды **`DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2UNENCRYPTEDSUPPORT`** задает параметр <xref:System.AppContext>, который включает незашифрованные соединения HTTP/2 для <xref:System.Net.Http.HttpClient>.</span><span class="sxs-lookup"><span data-stu-id="dd419-195">The **`DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2UNENCRYPTEDSUPPORT`** environment variable sets an <xref:System.AppContext> switch that enables unencrypted HTTP/2 connections for <xref:System.Net.Http.HttpClient>.</span></span> <span data-ttu-id="dd419-196">Эта переменная среды эквивалентна установке параметра в коде, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="dd419-196">This environment variable is the equivalent of setting the switch in code as shown here.</span></span>

```csharp
AppContext.SetSwitch("System.Net.Http.SocketsHttpHandler.Http2UnencryptedSupport", true);
```

<span data-ttu-id="dd419-197">Использование переменной среды для параметра означает, что этот параметр можно легко изменить в зависимости от контекста, в котором выполняется приложение.</span><span class="sxs-lookup"><span data-stu-id="dd419-197">Using an environment variable for the switch means the setting can easily be changed depending on the context in which the application is running.</span></span>

#### <a name="service-types"></a><span data-ttu-id="dd419-198">Типы служб</span><span class="sxs-lookup"><span data-stu-id="dd419-198">Service types</span></span>

<span data-ttu-id="dd419-199">Чтобы сделать веб-приложение доступным извне кластера, используется свойство `type: NodePort`.</span><span class="sxs-lookup"><span data-stu-id="dd419-199">To make the Web application accessible from outside the cluster, the `type: NodePort` property is used.</span></span> <span data-ttu-id="dd419-200">Этот тип свойства приводит к тому, что Kubernetes публикует порт 80 в службе на произвольный порт в внешних сетевых сокетах кластера.</span><span class="sxs-lookup"><span data-stu-id="dd419-200">This property type causes Kubernetes to publish port 80 on the Service to an arbitrary port on the cluster's external network sockets.</span></span> <span data-ttu-id="dd419-201">Назначенный порт можно найти с помощью команды `kubectl get service`.</span><span class="sxs-lookup"><span data-stu-id="dd419-201">The port assigned can be found using the `kubectl get service` command.</span></span>

<span data-ttu-id="dd419-202">Служба `stockdata` не должна быть доступна извне кластера, поэтому для нее использовался тип по умолчанию `ClusterIP`.</span><span class="sxs-lookup"><span data-stu-id="dd419-202">The `stockdata` service shouldn't be accessible from outside the cluster, so it used the default type, `ClusterIP`.</span></span>

<span data-ttu-id="dd419-203">В рабочих системах, скорее всего, будет использоваться интегрированная подсистема балансировки нагрузки для предоставления доступа к общедоступным приложениям внешним потребителям.</span><span class="sxs-lookup"><span data-stu-id="dd419-203">Production systems will most likely use an integrated load-balancer to expose public applications to external consumers.</span></span> <span data-ttu-id="dd419-204">Службы, предоставляемые таким образом, должны использовать тип `LoadBalancer`.</span><span class="sxs-lookup"><span data-stu-id="dd419-204">Services exposed in this way should use the `LoadBalancer` type.</span></span>

<span data-ttu-id="dd419-205">Дополнительные сведения о типах служб см. в документации по [службам публикации Kubernetes](https://kubernetes.io/docs/concepts/services-networking/service/#publishing-services-service-types) .</span><span class="sxs-lookup"><span data-stu-id="dd419-205">For more information on service types, see the [Kubernetes' Publishing Services](https://kubernetes.io/docs/concepts/services-networking/service/#publishing-services-service-types) documentation.</span></span>

#### <a name="deploy-the-stockweb-application"></a><span data-ttu-id="dd419-206">Развертывание приложения Стокквеб</span><span class="sxs-lookup"><span data-stu-id="dd419-206">Deploy the StockWeb application</span></span>

<span data-ttu-id="dd419-207">Используйте `kubectl`, чтобы применить файл `stockweb.yml` и проверить, были ли созданы развертывание и служба.</span><span class="sxs-lookup"><span data-stu-id="dd419-207">Use `kubectl` to apply the `stockweb.yml` file and check that the Deployment and Service were created.</span></span>

```console
> kubectl apply -f .\stockweb.yml
deployment.apps/stockweb created
service/stockweb created

> kubectl get deployment stockweb --namespace stocks
NAME       READY   UP-TO-DATE   AVAILABLE   AGE
stockweb   1/1     1            1           8s

> kubectl get service stockweb --namespace stocks
NAME       TYPE       CLUSTER-IP     EXTERNAL-IP   PORT(S)        AGE
stockweb   NodePort   10.106.141.5   <none>        80:32564/TCP   13s
```

<span data-ttu-id="dd419-208">Выходные данные команды `get service` показывают, что HTTP-порт был опубликован в порте `32564` во внешней сети. для приложения DOCKER Desktop это будет localhost.</span><span class="sxs-lookup"><span data-stu-id="dd419-208">The output from the `get service` command shows that the HTTP port has been published to port `32564` on the external network; for Docker Desktop, this will be localhost.</span></span> <span data-ttu-id="dd419-209">Доступ к приложению можно получить, перейдя по адресу `http://localhost:32564`.</span><span class="sxs-lookup"><span data-stu-id="dd419-209">The application can be accessed by browsing to `http://localhost:32564`.</span></span>

### <a name="testing-the-application"></a><span data-ttu-id="dd419-210">Тестирование приложения</span><span class="sxs-lookup"><span data-stu-id="dd419-210">Testing the application</span></span>

<span data-ttu-id="dd419-211">В приложении Стокквеб отображается список акций НАСДАК, полученных из простой службы "запрос-ответ".</span><span class="sxs-lookup"><span data-stu-id="dd419-211">The StockWeb application displays a list of NASDAQ stocks that are retrieved from a simple request-reply service.</span></span> <span data-ttu-id="dd419-212">В демонстрационных целях каждая строка также показывает уникальный идентификатор экземпляра службы, который его вернул.</span><span class="sxs-lookup"><span data-stu-id="dd419-212">For demonstration purposes, each line also shows the unique ID of the service instance that returned it.</span></span>

![Снимок экрана Стокквеб](media/kubernetes/stockweb-screenshot.png)

<span data-ttu-id="dd419-214">Если количество реплик службы `stockdata` увеличилось, можно ожидать, что значение **сервера** изменится с line на Line, но на самом деле все записи 100 всегда возвращаются из одного и того же экземпляра.</span><span class="sxs-lookup"><span data-stu-id="dd419-214">If the number of replicas of the `stockdata` service were increased, you might expect the **Server** value to change from line to line, but in fact all 100 records are always returned from the same instance.</span></span> <span data-ttu-id="dd419-215">Если страница обновляется каждые несколько секунд, идентификатор сервера остается прежним.</span><span class="sxs-lookup"><span data-stu-id="dd419-215">If you refresh the page every few seconds, the server ID remains the same.</span></span> <span data-ttu-id="dd419-216">Почему это происходит?</span><span class="sxs-lookup"><span data-stu-id="dd419-216">Why does this happen?</span></span> <span data-ttu-id="dd419-217">Здесь можно воспроизвести два фактора.</span><span class="sxs-lookup"><span data-stu-id="dd419-217">There are two factors at play here.</span></span>

<span data-ttu-id="dd419-218">Во-первых, система обнаружения службы Kubernetes по умолчанию использует балансировку нагрузки "циклический перебор".</span><span class="sxs-lookup"><span data-stu-id="dd419-218">First, the Kubernetes service discovery system uses "round-robin" load-balancing by default.</span></span> <span data-ttu-id="dd419-219">При первом запросе DNS-сервера он вернет первый соответствующий IP-адрес для службы.</span><span class="sxs-lookup"><span data-stu-id="dd419-219">The first time the DNS server is queried, it will return the first matching IP address for the service.</span></span> <span data-ttu-id="dd419-220">В следующий раз следующий IP-адрес в списке и т. д. до конца, после чего он вернется к началу.</span><span class="sxs-lookup"><span data-stu-id="dd419-220">The next time, the next IP address in the list, and so on, until the end, at which point it loops back to the start.</span></span>

<span data-ttu-id="dd419-221">Во-вторых, `HttpClient`, используемый для клиента gRPC приложения Стокквеб, создается и управляется [ASP.NET Core хттпклиентфактори](../microservices/implement-resilient-applications/use-httpclientfactory-to-implement-resilient-http-requests.md), а один экземпляр этого клиента используется для каждого вызова страницы.</span><span class="sxs-lookup"><span data-stu-id="dd419-221">Second, the `HttpClient` used for the StockWeb application's gRPC client is created and managed by the [ASP.NET Core HttpClientFactory](../microservices/implement-resilient-applications/use-httpclientfactory-to-implement-resilient-http-requests.md), and a single instance of this client is used for every call to the page.</span></span> <span data-ttu-id="dd419-222">Клиент выполняет только один поиск DNS, поэтому все запросы направляются на один и тот же IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="dd419-222">The client only does one DNS lookup, so all requests are routed to the same IP address.</span></span> <span data-ttu-id="dd419-223">Более того, поскольку `HttpClientHandler` кэшируется по соображениям производительности, для нескольких запросов в быстром *выполнении будет использоваться* один и тот же IP-адрес, пока не истечет кэшированная запись DNS или экземпляр обработчика не будет удален по каким-либо причинам.</span><span class="sxs-lookup"><span data-stu-id="dd419-223">Furthermore, because the `HttpClientHandler` is cached for performance reasons, multiple requests in quick succession will *all* use the same IP address, until the cached DNS entry expires or the handler instance is disposed for some reason.</span></span>

<span data-ttu-id="dd419-224">Это означает, что по умолчанию запросы к службе gRPC не сбалансированы по всем экземплярам этой службы в кластере.</span><span class="sxs-lookup"><span data-stu-id="dd419-224">This means that by default requests to a gRPC service aren't balanced across all instances of that service in the cluster.</span></span> <span data-ttu-id="dd419-225">Разные потребители будут использовать разные экземпляры, но это не гарантирует хорошее распределение запросов и сбалансированное использование ресурсов.</span><span class="sxs-lookup"><span data-stu-id="dd419-225">Different consumers will use different instances, but that doesn't guarantee a good distribution of requests and a balanced use of resources.</span></span>

<span data-ttu-id="dd419-226">В следующей главе « [сети службы](service-mesh.md)» рассматриваются способы решения этой проблемы.</span><span class="sxs-lookup"><span data-stu-id="dd419-226">The next chapter, [Service Meshes](service-mesh.md), will look at how to address this problem.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="dd419-227">[Назад](docker.md)
>[Вперед](service-mesh.md)</span><span class="sxs-lookup"><span data-stu-id="dd419-227">[Previous](docker.md)
[Next](service-mesh.md)</span></span>
