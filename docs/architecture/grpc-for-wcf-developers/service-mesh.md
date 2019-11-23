---
title: Сети службы — gRPC для разработчиков WCF
description: Использование сети службы для маршрутизации и балансировки запросов к gRPC службам в кластере Kubernetes.
ms.date: 09/02/2019
ms.openlocfilehash: d20275082973f30bddbb342da90454401d4f019b
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73966973"
---
# <a name="service-meshes"></a><span data-ttu-id="e0c6e-103">Сети службы</span><span class="sxs-lookup"><span data-stu-id="e0c6e-103">Service meshes</span></span>

<span data-ttu-id="e0c6e-104">Сетка служб — это компонент инфраструктуры, который принимает Управление запросами службы маршрутизации в сети.</span><span class="sxs-lookup"><span data-stu-id="e0c6e-104">A service mesh is an infrastructure component that takes control of routing service requests within a network.</span></span> <span data-ttu-id="e0c6e-105">Сети служб могут обслуживать все виды сетевых проблем в кластере Kubernetes, в том числе:</span><span class="sxs-lookup"><span data-stu-id="e0c6e-105">Service meshes can handle all kinds of network-level concerns within a Kubernetes cluster, including:</span></span>

- <span data-ttu-id="e0c6e-106">Обнаружение службы</span><span class="sxs-lookup"><span data-stu-id="e0c6e-106">Service discovery</span></span>
- <span data-ttu-id="e0c6e-107">Балансировка нагрузки</span><span class="sxs-lookup"><span data-stu-id="e0c6e-107">Load balancing</span></span>
- <span data-ttu-id="e0c6e-108">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="e0c6e-108">Fault tolerance</span></span>
- <span data-ttu-id="e0c6e-109">Шифрование</span><span class="sxs-lookup"><span data-stu-id="e0c6e-109">Encryption</span></span>
- <span data-ttu-id="e0c6e-110">Мониторинг</span><span class="sxs-lookup"><span data-stu-id="e0c6e-110">Monitoring</span></span>

<span data-ttu-id="e0c6e-111">Сети службы Kubernetes работают путем добавления дополнительного контейнера, именуемого *прокси-сервером расширения*, в каждый модуль, входящий в эту сеть.</span><span class="sxs-lookup"><span data-stu-id="e0c6e-111">Kubernetes service meshes work by adding an extra container, called a *sidecar proxy*, to each pod included in the mesh.</span></span> <span data-ttu-id="e0c6e-112">Прокси-сервер берет на себя обработку всех входящих и исходящих сетевых запросов, позволяя настраивать и управлять сетями, которые следует хранить отдельно от контейнеров приложений, и во многих случаях не требуя внесения изменений в код приложения.</span><span class="sxs-lookup"><span data-stu-id="e0c6e-112">The proxy takes over handling all inbound and outbound network requests, allowing configuration and management of networking matters to be kept separate from the application containers and, in many cases, without requiring any changes to the application code.</span></span>

<span data-ttu-id="e0c6e-113">Возьмем [пример из предыдущей главы](kubernetes.md#testing-the-application), где запросы gRPC из веб-приложения были направлены на один экземпляр службы gRPC.</span><span class="sxs-lookup"><span data-stu-id="e0c6e-113">Take the [previous chapter's example](kubernetes.md#testing-the-application), where the gRPC requests from the web application were all routed to a single instance of the gRPC service.</span></span> <span data-ttu-id="e0c6e-114">Это происходит потому, что имя узла службы разрешается в IP-адрес, и этот IP-адрес кэшируется в течение времени существования экземпляра `HttpClientHandler`.</span><span class="sxs-lookup"><span data-stu-id="e0c6e-114">This happens because the service's hostname is resolved to an IP address, and that IP address is cached for the lifetime of the `HttpClientHandler` instance.</span></span> <span data-ttu-id="e0c6e-115">Это можно обойти, обрабатывая поиск DNS вручную или создав несколько клиентов, но это сильно усложняет код приложения, не добавляя никаких бизнес-значений или клиентов.</span><span class="sxs-lookup"><span data-stu-id="e0c6e-115">It might be possible to work around this by handling DNS lookups manually or creating multiple clients, but this would complicate the application code considerably without adding any business or customer value.</span></span>

<span data-ttu-id="e0c6e-116">С помощью сетки служб запросы из контейнера приложения отправляются на прокси-сервер расширения, который может распространять их на все экземпляры другой службы.</span><span class="sxs-lookup"><span data-stu-id="e0c6e-116">Using a service mesh, the requests from the application container are sent to the sidecar proxy, which can distribute them intelligently across all instances of the other service.</span></span> <span data-ttu-id="e0c6e-117">Сетка также может:</span><span class="sxs-lookup"><span data-stu-id="e0c6e-117">The mesh can also:</span></span>

- <span data-ttu-id="e0c6e-118">Беспрепятственное реагирование на сбои отдельных экземпляров службы.</span><span class="sxs-lookup"><span data-stu-id="e0c6e-118">Respond seamlessly to failures of individual instances of a service.</span></span>
- <span data-ttu-id="e0c6e-119">Обрабатывает семантику повторных попыток для вызовов или тайм-аутов</span><span class="sxs-lookup"><span data-stu-id="e0c6e-119">Handle retry semantics for failed calls or timeouts</span></span>
- <span data-ttu-id="e0c6e-120">Перенаправление невыполненных запросов на альтернативный экземпляр без возврата в клиентское приложение.</span><span class="sxs-lookup"><span data-stu-id="e0c6e-120">Reroute failed requests to an alternate instance without returning to the client application at all.</span></span>

<span data-ttu-id="e0c6e-121">На следующем снимке экрана показано приложение Стокквеб, работающее с сеткой службы Linkerd, без изменений в коде приложения или даже на используемом образе DOCKER.</span><span class="sxs-lookup"><span data-stu-id="e0c6e-121">The following screenshot shows the StockWeb application running with the Linkerd service mesh, with no changes to the application code, or even the Docker image being used.</span></span> <span data-ttu-id="e0c6e-122">Единственным необходимым изменением было Добавление заметки к развертыванию в файлах YAML для служб `stockdata` и `stockweb`.</span><span class="sxs-lookup"><span data-stu-id="e0c6e-122">The only change required was the addition of an annotation to the Deployment in the YAML files for the `stockdata` and `stockweb` services.</span></span>

![Стокквеб с сетчатой службой](media/service-mesh/stockweb-servicemesh-screenshot.png)

<span data-ttu-id="e0c6e-124">Из столбца сервера можно увидеть, что запросы из приложения Стокквеб были направлены в обе реплики службы Стоккдата, несмотря на то, что исходит от одного `HttpClient` экземпляра в коде приложения.</span><span class="sxs-lookup"><span data-stu-id="e0c6e-124">You can see from the Server column that the requests from the StockWeb application have been routed to both replicas of the StockData service, despite originating from a single `HttpClient` instance in the application code.</span></span> <span data-ttu-id="e0c6e-125">На самом деле, если вы просматриваете код, вы увидите, что все 100 запросов к службе Стоккдата, выполняемые одновременно с помощью одного и того же экземпляра `HttpClient`, но с использованием сетки службы, эти запросы будут сбалансированы по тем множеству, что доступны многие экземпляры служб.</span><span class="sxs-lookup"><span data-stu-id="e0c6e-125">In fact, if you review the code, you'll see that all 100 requests to the StockData service are made simultaneously using the same `HttpClient` instance, yet with the service mesh, those requests will be balanced across however many service instances are available.</span></span>

<span data-ttu-id="e0c6e-126">Сети служб применяются только к трафику в кластере.</span><span class="sxs-lookup"><span data-stu-id="e0c6e-126">Service meshes only apply to traffic within a cluster.</span></span> <span data-ttu-id="e0c6e-127">Сведения о внешних клиентах см. [в следующей главе балансировка нагрузки](load-balancing.md).</span><span class="sxs-lookup"><span data-stu-id="e0c6e-127">For external clients, see [the next chapter, Load Balancing](load-balancing.md).</span></span>

## <a name="service-mesh-options"></a><span data-ttu-id="e0c6e-128">Параметры сетки служб</span><span class="sxs-lookup"><span data-stu-id="e0c6e-128">Service mesh options</span></span>

<span data-ttu-id="e0c6e-129">В настоящее время доступно три реализации универсальной сетки служб для использования с Kubernetes: Istio, Linkerd и Consul Connect.</span><span class="sxs-lookup"><span data-stu-id="e0c6e-129">There are three general-purpose service mesh implementations currently available for use with Kubernetes: Istio, Linkerd, and Consul Connect.</span></span> <span data-ttu-id="e0c6e-130">Все три предоставляют маршрутизацию запросов и прокси-серверы, шифрование трафика, устойчивость, аутентификацию между узлами и управление трафиком.</span><span class="sxs-lookup"><span data-stu-id="e0c6e-130">All three provide request routing/proxying, traffic encryption, resilience, host-to-host authentication, and traffic control.</span></span>

<span data-ttu-id="e0c6e-131">Выбор сетки службы зависит от нескольких факторов:</span><span class="sxs-lookup"><span data-stu-id="e0c6e-131">Choosing a service mesh depends multiple factors:</span></span>

- <span data-ttu-id="e0c6e-132">Конкретные требования Организации к затратам, соответствию требованиям, платным тарифным планам и т. д.</span><span class="sxs-lookup"><span data-stu-id="e0c6e-132">The organization's specific requirements around costs, compliance, paid support plans, and so on.</span></span>
- <span data-ttu-id="e0c6e-133">Характер кластера, его размер, количество развернутых служб и объем трафика в сети кластера.</span><span class="sxs-lookup"><span data-stu-id="e0c6e-133">The nature of the cluster, its size, the number of services deployed, and the volume of traffic within the cluster network.</span></span>
- <span data-ttu-id="e0c6e-134">Простота развертывания и управления сеткой и ее использование со службами.</span><span class="sxs-lookup"><span data-stu-id="e0c6e-134">Ease of deploying and managing the mesh and using it with services.</span></span>

<span data-ttu-id="e0c6e-135">Дополнительные сведения о каждой сети службы можно найти на соответствующих веб-сайтах.</span><span class="sxs-lookup"><span data-stu-id="e0c6e-135">More information on each service mesh is available from their respective websites.</span></span>

- [<span data-ttu-id="e0c6e-136">**Istio** — istio.IO</span><span class="sxs-lookup"><span data-stu-id="e0c6e-136">**Istio** - istio.io</span></span>](https://istio.io)
- [<span data-ttu-id="e0c6e-137">**Linkerd** — linkerd.IO</span><span class="sxs-lookup"><span data-stu-id="e0c6e-137">**Linkerd** - linkerd.io</span></span>](https://linkerd.io)
- [<span data-ttu-id="e0c6e-138">**Consul** — Consul.IO/Mesh.HTML</span><span class="sxs-lookup"><span data-stu-id="e0c6e-138">**Consul** - consul.io/mesh.html</span></span>](https://consul.io/mesh.html)

## <a name="example-add-linkerd-to-a-deployment"></a><span data-ttu-id="e0c6e-139">Пример. Добавление Linkerd в развертывание</span><span class="sxs-lookup"><span data-stu-id="e0c6e-139">Example: add Linkerd to a deployment</span></span>

<span data-ttu-id="e0c6e-140">В этом примере вы узнаете, как использовать сетку службы Linkerd с приложением *стокккубе* из [предыдущего раздела](kubernetes.md).</span><span class="sxs-lookup"><span data-stu-id="e0c6e-140">In this example, you'll learn how to use the Linkerd service mesh with the *StockKube* application from [the previous section](kubernetes.md).</span></span>
<span data-ttu-id="e0c6e-141">Чтобы выполнить этот пример, необходимо [установить интерфейс командной строки Linkerd](https://linkerd.io/2/getting-started/#step-1-install-the-cli).</span><span class="sxs-lookup"><span data-stu-id="e0c6e-141">To follow this example, you'll need to [install the Linkerd CLI](https://linkerd.io/2/getting-started/#step-1-install-the-cli).</span></span> <span data-ttu-id="e0c6e-142">Двоичные файлы Windows можно скачать из раздела "выпуски GitHub"; Убедитесь, что используется последний **стабильный** выпуск, а не один из выпусков.</span><span class="sxs-lookup"><span data-stu-id="e0c6e-142">Windows binaries can be downloaded from the GitHub releases section; make sure to use the most recent **stable** release and not one of the edge releases.</span></span>

<span data-ttu-id="e0c6e-143">После установки интерфейса командной строки Linkerd следуйте инструкциям [*Начало работы* на веб-сайте Linkerd], чтобы установить компоненты Linkerd в кластере Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="e0c6e-143">With the Linkerd CLI installed, follow the [*Getting Started* instructions on the Linkerd web site] to install the Linkerd components on your Kubernetes cluster.</span></span> <span data-ttu-id="e0c6e-144">Инструкции прямо вперед и установка на локальном экземпляре Kubernetes займет всего несколько минут.</span><span class="sxs-lookup"><span data-stu-id="e0c6e-144">The instructions are straight-forward and installation should only take a couple of minutes on a local Kubernetes instance.</span></span>

### <a name="add-linkerd-to-kubernetes-deployments"></a><span data-ttu-id="e0c6e-145">Добавление Linkerd в развертывания Kubernetes</span><span class="sxs-lookup"><span data-stu-id="e0c6e-145">Add Linkerd to Kubernetes deployments</span></span>

<span data-ttu-id="e0c6e-146">Linkerd CLI предоставляет команду `inject`, чтобы добавить необходимые разделы и свойства в файлы Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="e0c6e-146">The Linkerd CLI provides an `inject` command to add the necessary sections and properties to Kubernetes files.</span></span> <span data-ttu-id="e0c6e-147">Можно выполнить команду и записать выходные данные в новый файл.</span><span class="sxs-lookup"><span data-stu-id="e0c6e-147">You can run the command and write the output to a new file.</span></span>

```console
linkerd inject stockdata.yml > stockdata-with-mesh.yml
linkerd inject stockweb.yml > stockweb-with-mesh.yml
```

<span data-ttu-id="e0c6e-148">Вы можете просмотреть новые файлы, чтобы узнать, какие изменения были сделаны.</span><span class="sxs-lookup"><span data-stu-id="e0c6e-148">You can inspect the new files to see what changes have been made.</span></span> <span data-ttu-id="e0c6e-149">Для объектов развертывания добавляется заметка метаданных, указывающая Linkerd вставить в модуль расширения контейнер прокси-сервера при его создании.</span><span class="sxs-lookup"><span data-stu-id="e0c6e-149">For Deployment objects, a metadata annotation is added to tell Linkerd to inject a sidecar proxy container into the Pod when it's created.</span></span>

<span data-ttu-id="e0c6e-150">Также можно передать выходные данные команды `linkerd inject` для `kubectl` напрямую.</span><span class="sxs-lookup"><span data-stu-id="e0c6e-150">It's also possible to pipe the output of the `linkerd inject` command to `kubectl` directly.</span></span> <span data-ttu-id="e0c6e-151">Следующие команды будут работать в PowerShell или в любой оболочке Linux.</span><span class="sxs-lookup"><span data-stu-id="e0c6e-151">The following commands will work in PowerShell or any Linux shell.</span></span>

```console
linkerd inject stockdata.yml | kubectl apply -f -
linkerd inject stockweb.yml | kubectl apply -f -
```

### <a name="inspect-services-in-the-linkerd-dashboard"></a><span data-ttu-id="e0c6e-152">Проверка служб на панели мониторинга Linkerd</span><span class="sxs-lookup"><span data-stu-id="e0c6e-152">Inspect services in the Linkerd dashboard</span></span>

<span data-ttu-id="e0c6e-153">Запустите панель мониторинга Linkerd с помощью интерфейса командной строки `linkerd`.</span><span class="sxs-lookup"><span data-stu-id="e0c6e-153">Launch the Linkerd dashboard using the `linkerd` CLI.</span></span>

```console
linkerd dashboard
```

<span data-ttu-id="e0c6e-154">На панели мониторинга содержатся подробные сведения обо всех службах, подключенных к сети.</span><span class="sxs-lookup"><span data-stu-id="e0c6e-154">The dashboard provides detailed information about all services that are connected to the mesh.</span></span>

![Панель мониторинга Linkerd, показывающая приложения Стокккубе](media/service-mesh/linkerd-screenshot.png)

<span data-ttu-id="e0c6e-156">Если вы увеличите число реплик службы Стоккдата gRPC, как показано в следующем примере, и обновите страницу Стокквеб в браузере, вы увидите сочетание идентификаторов в столбце Server, указывающее, что запросы обслуживаются всеми доступными экземплярами. .</span><span class="sxs-lookup"><span data-stu-id="e0c6e-156">If you increase the number of replicas of the StockData gRPC service as shown in the following example, and refresh the StockWeb page in the browser, you should see a mix of IDs in the Server column, indicating that requests are being served by all the available instances.</span></span>

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
  replicas: 2 # Increase the target number of instances
  template:
    metadata:
      annotations:
        linkerd.io/inject: enabled
      creationTimestamp: null
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

>[!div class="step-by-step"]
><span data-ttu-id="e0c6e-157">[Назад](kubernetes.md)
>[Вперед](load-balancing.md)</span><span class="sxs-lookup"><span data-stu-id="e0c6e-157">[Previous](kubernetes.md)
[Next](load-balancing.md)</span></span>
