---
title: Kubernetes-gRPC для разработчиков WCF
description: Запуск ASP.NET Core gRPC Services в кластере Kubernetes.
ms.date: 09/02/2019
ms.openlocfilehash: 22271343f8f0d0454469b2f35e717f5b7e939294
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74711289"
---
# <a name="kubernetes"></a>Kubernetes

Хотя контейнеры можно запускать вручную на узлах DOCKER, для надежных рабочих систем лучше использовать механизм оркестрации контейнеров для управления несколькими экземплярами, работающими на нескольких серверах в кластере. Доступны различные механизмы оркестрации контейнеров, в том числе Kubernetes, Docker Swarm и Apache Mesos. Но из этих ядер Kubernetes далеко и далеко не самый широко используемый, поэтому он будет посвящен этой главе.

Kubernetes включает следующие функциональные возможности:

- **Планирование** запускает контейнеры на нескольких узлах в кластере, обеспечивая сбалансированное использование доступного ресурса, поддержание работоспособности контейнеров при сбоях и обработку последовательных обновлений для новых версий образов или новых конфигураций.
- **Проверки работоспособности** отслеживают контейнеры, чтобы обеспечить непрерывную работу службы.
- **Обнаружение службы DNS &** обрабатывает маршрутизацию между службами в кластере.
- Входящий трафик **предоставляет доступ к** выбранным службам извне и обычно обеспечивает балансировку нагрузки между экземплярами этих служб.
- **Управление ресурсами** подключает внешние ресурсы, например хранилище, к контейнерам.

В этой главе подробно описано, как развернуть службу ASP.NET Core gRPC и веб-сайт, который использует эту службу в кластере Kubernetes. Пример используемого приложения доступен в репозитории [DotNet-Architecture/GRPC-for-WCF-Developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/KubernetesSample) на сайте GitHub.

## <a name="kubernetes-terminology"></a>Терминология Kubernetes

Kubernetes использует *конфигурацию требуемого состояния*. API используется для *описания таких объектов*, как модули Pod, *развертывания*и *службы*, и *плоскость управления* требует реализации требуемого состояния на всех *узлах* *кластера*. В кластере Kubernetes имеется *главный* узел, на котором работает *API Kubernetes*, который можно взаимодействовать программно или с помощью программы командной строки `kubectl`. `kubectl` может создавать объекты и управлять ими с помощью аргументов командной строки, но лучше подходит для файлов YAML, содержащих данные объявления для объектов Kubernetes.

### <a name="kubernetes-yaml-files"></a>Файлы YAML Kubernetes

Каждый файл YAML Kubernetes будет иметь по крайней мере три свойства верхнего уровня:

```yaml
apiVersion: v1
kind: Namespace
metadata:
  # Object properties
```

Свойство `apiVersion` используется для указания версии (и API), для которой предназначен файл. Свойство `kind` указывает тип объекта, представляемого YAML. Свойство `metadata` содержит свойства объекта, такие как `name`, `namespace`и `labels`.

В большинстве файлов YAML Kubernetes также имеется раздел `spec`, описывающий ресурсы и конфигурацию, необходимые для создания объекта.

### <a name="pods"></a>Модули pod

Модули Pod являются основными единицами выполнения в Kubernetes. Они могут запускать несколько контейнеров, но они также используются для выполнения отдельных контейнеров. Модуль также включает все ресурсы хранилища, необходимые контейнерам, и сетевой IP-адрес.

### <a name="services"></a>Службы

Службы являются мета-объектами, описывающими Pod (или наборы модулей), и предоставляют способ доступа к ним в кластере, например для сопоставления имени службы с набором IP-адресов Pod с помощью службы DNS кластера.

### <a name="deployments"></a>развертывания,

Развертывания — это объекты *требуемого состояния* для модулей Pod. Если вы создаете модуль Pod вручную, он не будет перезапущен после завершения его работы. Развертывания используются для информирования кластера о том, какие модули, и сколько реплик этих модулей следует запускать в настоящее время.

### <a name="other-objects"></a>Другие объекты

Модули Pod, службы и развертывания — это всего три основных типа объектов. Существуют десятки других типов объектов, управляемых кластерами Kubernetes. Дополнительные сведения см. в документации по [основным понятиям Kubernetes](https://kubernetes.io/docs/concepts/) .

### <a name="namespaces"></a>Пространства имен

Кластеры Kubernetes предназначены для масштабирования до сотен или тысяч узлов и для запуска аналогичного числа служб. Чтобы избежать конфликта между именами объектов, пространства имен используются для группирования объектов вместе в составе более крупных приложений. Собственные службы Kubernetes выполняются в пространстве имен `default`. Все объекты пользователя должны создаваться в собственных пространствах имен, чтобы избежать возможных конфликт с объектами по умолчанию или другими клиентами в кластере.

## <a name="get-started-with-kubernetes"></a>Начало работы с Kubernetes

Если вы используете DOCKER Desktop для Windows или DOCKER Desktop для Mac, Kubernetes уже доступен. Просто включите его в разделе **Kubernetes** окна **Параметры** :

![Включение Kubernetes в DOCKER Desktop](media/kubernetes/enable-kubernetes-docker-desktop.png)

Чтобы запустить локальный кластер Kubernetes в Linux, рассмотрите возможность [minikube](https://github.com/kubernetes/minikube)или [MicroK8s](https://microk8s.io/) , если дистрибутив Linux поддерживает [привязку](https://snapcraft.io/).

Чтобы убедиться, что кластер работает и доступен, выполните команду `kubectl version`.

```console
kubectl version
Client Version: version.Info{Major:"1", Minor:"14", GitVersion:"v1.14.6", GitCommit:"96fac5cd13a5dc064f7d9f4f23030a6aeface6cc", GitTreeState:"clean", BuildDate:"2019-08-19T11:13:49Z", GoVersion:"go1.12.9", Compiler:"gc", Platform:"windows/amd64"}
Server Version: version.Info{Major:"1", Minor:"14", GitVersion:"v1.14.6", GitCommit:"96fac5cd13a5dc064f7d9f4f23030a6aeface6cc", GitTreeState:"clean", BuildDate:"2019-08-19T11:05:16Z", GoVersion:"go1.12.9", Compiler:"gc", Platform:"linux/amd64"}
```

В этом примере как `kubectl` CLI, так и сервер Kubernetes работают под управлением версии 1.14.6. Каждая версия `kubectl` должна поддерживать предыдущую и следующую версии сервера, поэтому `kubectl` 1,14 должны работать и с серверными версиями 1,13 и 1,15.

## <a name="run-services-on-kubernetes"></a>Запуск служб на Kubernetes

В примере приложения имеется каталог `kube`, содержащий три файла YAML. Файл `namespace.yml` объявляет пользовательское пространство имен: `stocks`. Файл `stockdata.yml` объявляет развертывание и службу для приложения gRPC, а `stockweb.yml` файл объявляет развертывание и службу для веб-приложения ASP.NET Core 3,0, которое использует службу gRPC.

Чтобы использовать `YAML` файл с `kubectl`, выполните команду `apply -f`:

```console
kubectl apply -f object.yml
```

Команда `apply` проверит допустимость файла YAML и отобразит все ошибки, полученные от API, но не ждет, пока все объекты, объявленные в файле, не будут созданы, так как это может занять некоторое время. Используйте команду `kubectl get` с соответствующими типами объектов для проверки создания объекта в кластере.

### <a name="the-namespace-declaration"></a>Объявление пространства имен

Объявление пространства имен является простым и требует только присваивания `name`:

```yaml
apiVersion: v1
kind: Namespace
metadata:
  name: stocks
```

Используйте `kubectl`, чтобы применить файл `namespace.yml` и убедиться, что пространство имен успешно создано:

```console
> kubectl apply -f namespace.yml
namespace/stocks created

> kubectl get namespaces
NAME              STATUS   AGE
stocks            Active   2m53s
```

### <a name="the-stockdata-application"></a>Приложение Стоккдата

В файле `stockdata.yml` объявляются два объекта: развертывание и служба.

#### <a name="the-stockdata-deployment"></a>Развертывание Стоккдата

Часть развертывания файла YAML предоставляет `spec` для самого развертывания, включая необходимое количество реплик, и `template` для объектов Pod, создаваемых и управляемых развертыванием. Обратите внимание, что объекты развертывания управляются `apps` API, как указано в `apiVersion`, а не в основном API Kubernetes.

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

Свойство `spec.selector` используется для сопоставления выполняющихся модулей Pod с развертыванием. Свойство `metadata.labels` Pod должно соответствовать свойству `matchLabels`, иначе вызов API завершится ошибкой.

В разделе `template.spec` объявляется контейнер для выполнения. При работе с локальным кластером Kubernetes, например, предоставленным с помощью DOCKER Desktop, можно указать образы, которые были собраны локально, если у них есть тег версии.

> [!IMPORTANT]
> По умолчанию Kubernetes всегда проверяет и пытается извлечь новый образ. Если образ не удается найти ни в одном из известных репозиториев, создание Pod завершится ошибкой. Для работы с локальными образами задайте для `imagePullPolicy` значение `Never`.

Свойство `ports` указывает, какие порты контейнера должны быть опубликованы в модуле Pod. Образ `stockservice` запускает службу на стандартном HTTP-порте, поэтому порт 80 публикуется.

Раздел `resources` применяет ограничения ресурсов к контейнеру, выполняющемуся в модуле Pod. Это хороший подход, так как он предотвращает использование всеми доступными ЦП или памяти на узле отдельным модулем.

> [!NOTE]
> ASP.NET Core 3,0 оптимизирована и настроена для работы в контейнерах с ограниченными ресурсами. Образ DOCKER `dotnet/core/aspnet` задает переменную среды, чтобы сообщить среде выполнения `dotnet` о том, что она находится в контейнере.

#### <a name="the-stockdata-service"></a>Служба Стоккдата

Часть службы файла YAML объявляет службу, которая предоставляет доступ к модулям Pod в кластере.

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

`spec` службы использует свойство `selector` для сопоставления с выполняемым `Pods`, в данном случае поиск модулей Pod с меткой `run: stockdata`. Указанный `port` в соответствующих модулях Pod публикуется с помощью именованной службы. Другие модули, работающие в пространстве имен `stocks`, могут получить доступ к HTTP для этой службы, используя `http://stockdata` в качестве адреса. Модули Pod, выполняющиеся в других пространствах имен, могут использовать `http://stockdata.stocks` имя узла. Управлять доступом к службам между пространствами имен можно с помощью [политик сети](https://kubernetes.io/docs/concepts/services-networking/network-policies/).

#### <a name="deploy-the-stockdata-application"></a>Развертывание приложения Стоккдата

Используйте `kubectl`, чтобы применить файл `stockdata.yml` и убедиться, что развертывание и служба созданы:

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

### <a name="the-stockweb-application"></a>Приложение Стокквеб

Файл `stockweb.yml` объявляет развертывание и службу для приложения MVC.

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

#### <a name="environment-variables"></a>Переменные среды

В разделе `env` объекта развертывания указываются переменные среды, которые должны быть заданы в контейнере, где выполняются образы `stockweb:1.0.0`.

**`StockData__Address`** переменная среды будет сопоставляться с параметром конфигурации `StockData:Address`, благодаря поставщику конфигурации EnvironmentVariables. Этот параметр использует двойные подчеркивания между именами, чтобы разделить разделы. Адрес использует имя службы `stockdata` службы, которая выполняется в том же пространстве имен Kubernetes.

Переменная среды **`DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2UNENCRYPTEDSUPPORT`** задает параметр <xref:System.AppContext>, который включает незашифрованные соединения HTTP/2 для <xref:System.Net.Http.HttpClient>. Эта переменная среды выполняет те же действия, что и установка переключателя в коде, как показано ниже:

```csharp
AppContext.SetSwitch("System.Net.Http.SocketsHttpHandler.Http2UnencryptedSupport", true);
```

Если для параметра используется переменная среды, контекст можно легко изменить в зависимости от контекста, в котором выполняется приложение.

#### <a name="service-types"></a>Типы служб

Свойство `type: NodePort` используется, чтобы сделать веб-приложение доступным извне кластера. Этот тип свойства приводит к тому, что Kubernetes публикует порт 80 в службе на произвольный порт в внешних сетевых сокетах кластера. Назначенный порт можно найти с помощью команды `kubectl get service`.

Служба `stockdata` не должна быть доступна извне кластера, поэтому она использует тип по умолчанию `ClusterIP`.

В рабочих системах, скорее всего, будет использоваться интегрированная подсистема балансировки нагрузки для предоставления доступа к общедоступным приложениям внешним потребителям. Службы, предоставляемые таким образом, должны использовать тип `LoadBalancer`.

Дополнительные сведения о типах служб см. в документации по [службам Kubernetes Publishing Services](https://kubernetes.io/docs/concepts/services-networking/service/#publishing-services-service-types) .

#### <a name="deploy-the-stockweb-application"></a>Развертывание приложения Стокквеб

Используйте `kubectl`, чтобы применить файл `stockweb.yml` и убедиться, что развертывание и служба созданы:

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

Выходные данные команды `get service` показывают, что HTTP-порт был опубликован на порту 32564 во внешней сети. Для приложения DOCKER Desktop это будет localhost. Доступ к приложению можно получить, перейдя по адресу `http://localhost:32564`.

### <a name="test-the-application"></a>Тестирование приложения

В приложении Стокквеб отображается список акций НАСДАК, полученных из простой службы "запрос-ответ". В этой демонстрации каждая строка также показывает уникальный идентификатор экземпляра службы, который его вернул.

![Снимок экрана Стокквеб](media/kubernetes/stockweb-screenshot.png)

Если количество реплик службы `stockdata` увеличилось, можно ожидать, что значение **сервера** изменится с line на Line, но на самом деле все записи 100 всегда возвращаются из одного и того же экземпляра. Если страница обновляется каждые несколько секунд, идентификатор сервера остается прежним. Почему это происходит? Здесь можно воспроизвести два фактора.

Во-первых, система обнаружения службы Kubernetes по умолчанию использует балансировку нагрузки с циклическим перебором. При первом запросе DNS-сервера он вернет первый соответствующий IP-адрес для службы. В следующий раз он вернет следующий IP-адрес в списке и т. д. до конца. В этот момент он перебирается обратно в начало.

Во-вторых, `HttpClient`, используемый для клиента gRPC приложения Стокквеб, создается и управляется [ASP.NET Core хттпклиентфактори](../microservices/implement-resilient-applications/use-httpclientfactory-to-implement-resilient-http-requests.md), а один экземпляр этого клиента используется для каждого вызова страницы. Клиент выполняет только один поиск DNS, поэтому все запросы направляются на один и тот же IP-адрес. Так как `HttpClientHandler` кэшируется по соображениям производительности, несколько запросов в быстром выполнении будут *использовать один* и тот же IP-адрес, пока не истечет кэшированная запись DNS или экземпляр обработчика не будет удален по каким-либо причинам.

В результате запросы по умолчанию к службе gRPC не сбалансированы по всем экземплярам этой службы в кластере. Разные потребители будут использовать разные экземпляры, но это не гарантирует хорошее распределение запросов или сбалансированное использование ресурсов.

Следующая глава, « [сети службы](service-mesh.md)», будет решать эту проблему.

>[!div class="step-by-step"]
>[Назад](docker.md)
>[Вперед](service-mesh.md)
