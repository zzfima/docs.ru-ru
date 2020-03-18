---
title: Сборка приложений ASP.NET Core 2.2, развернутых как контейнеры Linux в кластерах AKS/Kubernetes
description: Жизненный цикл контейнерного приложения Docker на основе платформы и средств Майкрософт
ms.date: 02/25/2019
ms.openlocfilehash: ab64a0423ceceb8285c159af276d6d97e12379d8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "70848755"
---
# <a name="build-aspnet-core-22-applications-deployed-as-linux-containers-into-an-akskubernetes-orchestrator"></a>Сборка приложений ASP.NET Core 2.2, развернутых как контейнеры Linux в оркестраторе AKS/Kubernetes

Служба Azure Kubernetes (AKS) представляет собой службы оркестрации управляемой среды Kubernetes в Azure, упрощающие развертывание контейнеров и управление ими.

Основные функции AKS:

- Размещенный в Azure уровень управления
- Автоматические обновления
- самовосстановление;
- Настраиваемое пользователем масштабирование
- Упрощение взаимодействия с пользователем для разработчиков и операторов кластера.

В приведенных ниже примерах рассматривается создание приложения ASP.NET Core 2.2, которое выполняется в Linux и развертывается в кластере AKS в Azure, при этом его разработка осуществляется в Visual Studio 2017.

## <a name="creating-the-aspnet-core-22-project-using-visual-studio-2017"></a>Создание проекта ASP.NET Core 2.2 с помощью Visual Studio 2017

ASP.NET Core — это универсальная платформа разработки, которая поддерживается корпорацией Майкрософт и сообществом .NET на сайте GitHub. Она является кроссплатформенной, поддерживает Windows, Mac OS и Linux и может использоваться на устройствах, в облаке, во внедренных системах и в сценариях Интернета вещей.

В этом примере используется простой проект на основе шаблона веб-API Visual Studio, поэтому вам не нужны дополнительные знания о создании образца. Вам достаточно создать проект с помощью стандартного шаблона, который включает в себя все элементы для запуска небольшого проекта с помощью REST API с использованием технологии ASP.NET Core 2.2.

![Добавьте окно нового проекта в Visual Studio, выбрав "Веб-приложение ASP.NET Core".](media/create-aspnet-core-application.png)

**Рис. 4-36**. Создание приложения ASP.NET Core

Чтобы создать пример проекта в Visual Studio, выберите **Файл** > **Создать** > **Проект**, укажите тип проекта **Интернет** в левой области и затем выберите **Веб-приложение ASP.NET Core**.

Visual Studio отображает список шаблонов для веб-проектов. Для нашего примера выберите **API**, чтобы создать приложение веб-API ASP.NET.

Убедитесь, что выбрана платформа ASP.NET Core 2.2. Платформа .NET Core 2.2 включена в последнюю версию продукта Visual Studio 2017 и автоматически устанавливается и настраивается при его установке.

![Диалоговое окно Visual Studio для выбора типа веб-приложения ASP.NET Core с выбранным параметром API.](media/create-web-api-application.png)

**Рис. 4-37**. Выбор ASP.NET Core 2.2 и типа проекта "Веб-API"

При наличии любой предыдущей версии .NET Core можно скачать и установить версию 2.2 по адресу <https://dotnet.microsoft.com/download>.

Поддержку Docker можно добавить при создании проекта или позднее, то есть преобразовать проект для Docker можно в любое время. Чтобы добавить поддержку Docker после создания проекта, щелкните узел проекта правой кнопкой мыши в обозревателе решений и выберите в контекстном меню пункт **Добавить** > **Поддержка Docker**.

![Пункт контекстного меню, позволяющий добавить поддержку Docker в существующий проект: Щелкните проект правой кнопкой мыши и выберите "Добавить" > "Поддержка Docker".](media/add-docker-support-to-project.png)

**Рис. 4-38**. Добавление поддержки Docker в существующий проект

Чтобы завершить добавление поддержки Docker, можно выбрать платформу Windows или Linux. В данном случае выберите **Linux**, так как AKS не поддерживает контейнеры Windows (на конец 2018 г.).

![Параметр диалогового окна для выбора целевой операционной системы для Dockerfile.](media/select-linux-docker-support.png)

**Рис. 4-39**. Выбор контейнеров Linux.

Выполнив эти простые шаги, вы запустите свое приложение ASP.NET Core 2.2 в контейнере Linux.

Как видно, интеграцию между Visual Studio 2017 и Docker полностью ориентирована на обеспечение продуктивной работы разработчика.

Теперь вы можете запустить приложение с помощью клавиши **F5** или кнопки **Воспроизвести**.

После выполнения проекта вы можете получить список образов с помощью команды `docker images`. Вы должны увидеть образ `mssampleapplication`, созданный при автоматическом развертывании вашего проекта с помощью Visual Studio 2017.

```console
docker images
```

![Выходные данные команды docker images в консоли представляют собой список, содержащий следующее: репозиторий, тег, идентификатор образа, дата создания и размер.](media/docker-images-command.png)

**Рис. 4-40**. Представление образов Docker

## <a name="register-the-solution-in-the-azure-container-registry"></a>Регистрация решения в Реестре контейнеров Azure

Отправьте образ в любой реестр Docker, например [Реестр контейнеров Azure (ACR)](https://azure.microsoft.com/services/container-registry/) или Docker Hub, чтобы оттуда образы можно было развернуть в кластере AKS. В данном случае мы отправляем образ в Реестр контейнеров Azure.

### <a name="create-the-image-in-release-mode"></a>Создание образа в режиме выпуска

Теперь мы создадим образ в режиме **Выпуск** (готовым к выпуску), заменив значение на **Выпуск**, как показано на рис. 4-41, и запустив приложение, как и раньше.

![Параметр панели инструментов в Visual Studio для сборки в режиме выпуска.](media/select-release-mode.png)

**Рис. 4-41**. Выбор режима выпуска

При выполнении команды `docker image` вы увидите создание обоих образов — одного для режима `debug` и другого для режима `release`.

### <a name="create-a-new-tag-for-the-image"></a>Создание тега образа

Каждый образ контейнера должен быть помечен именем `loginServer` реестра. Данный тег используется для маршрутизации при отправке образов контейнеров в реестр образов.

Вы можете просмотреть имя `loginServer` на портале Azure, используя сведения из Реестра контейнеров Azure.

![Представление имени Реестра контейнеров Azure в правом верхнем углу браузера.](media/loginServer-name.png)

**Рис. 4-42**. Представление имени реестра

Кроме того, можно выполнить следующую команду:

```console
az acr list --resource-group MSSampleResourceGroup --query "[].{acrLoginServer:loginServer}" --output table
```

![Выходные данные консоли для указанной выше команды.](media/az-cli-loginServer-name.png)

**Рис. 4-43**. Получение имени реестра с помощью PowerShell

В обоих случаях вы получите нужное имя. В нашем примере это `mssampleacr.azurecr.io`.

Теперь вы можете пометить образ, используя самый последний образ (образ выпуска), с помощью команды:

```console
docker tag mssampleaksapplication:latest mssampleacr.azurecr.io/mssampleaksapplication:v1
```

После выполнения команды `docker tag` выведите список образов с помощью команды `docker images`, при этом вы должны увидеть образ с новым тегом.

![Выходные данные команды docker images в консоли.](media/tagged-docker-images-list.png)

**Рис. 4-44**. Представление помеченных образов

### <a name="push-the-image-into-the-azure-acr"></a>Отправка образа в Azure ACR

Войдите в Реестр контейнеров Azure:

```console
az acr login --name mssampleacr
```

Отправьте образ в Реестр контейнеров Azure с помощью следующей команды:

```console
docker push mssampleacr.azurecr.io/mssampleaksapplication:v1
```

Этой команде требуется некоторое время на отправку образа, при этом она предоставляет вам сведения о выполняемой операции.

![Выходные данные команды docker push в консоли представляют собой основанный на символах индикатор выполнения для каждого уровня.](media/uploading-image-to-acr.png)

**Рис. 4-45**. Отправка образа в ACR

Ниже приведен результат, который вы должны получить после завершения процесса:

![Выходные данные после завершения команды docker push в консоли, содержащие все уровни и узлы.](media/uploading-docker-images-complete.png)

**Рис. 4-46**. Представление узлов

Следующим шагом является развертывание контейнера в кластере Kubernetes в AKS. Для этого нужен файл (файл развертывания **.yml**), содержащий следующее:

```yml
apiVersion: apps/v1beta1
kind: Deployment
metadata:
  name: mssamplesbook
spec:
  replicas: 1
  template:
    metadata:
      labels:
        app: mssample-kub-app
    spec:
      containers:
        - name: mssample-services-app
          image: mssampleacr.azurecr.io/mssampleaksapplication:v1
          ports:
            - containerPort: 80
---
apiVersion: v1
kind: Service
metadata:
    name: mssample-kub-app
spec:
  ports:
    - name: http-port
      port: 80
      targetPort: 80
  selector:
    app: mssample-kub-app
  type: LoadBalancer
```

> [!NOTE]
> Дополнительные сведения о развертывании с использованием Kubernetes см. в статье <https://kubernetes.io/docs/reference/kubectl/cheatsheet/>

Теперь почти все готово для развертывания с помощью **Kubectl**, но сначала нужно получить учетные данные для кластера AKS с помощью следующей команды:

```console
az aks get-credentials --resource-group MSSampleResourceGroupAKS --name mssampleclusterk801
```

![Выходные данные указанной выше команды в консоли: Произведено слияние MSSampleK8Cluster в качестве текущего контекста в /root/.kube/config](media/getting-aks-credentials.png)

**Рис. 4-47**. Получение учетных данных

Затем запустите развертывание с помощью команды `kubectl create`.

```console
kubectl create -f mssample-deploy.yml
```

![Выходные данные указанной выше команды в консоли: развертывание "mssamplesbook" создано. служба "mssample-kub-app" создана.](media/kubectl-create-command.png)

**Рис. 4-48**. Развертывание в Kubernetes

После завершения развертывания вы можете обратиться к консоли Kubernetes через локальный прокси-сервер, к которому можно временно получить доступ с помощью следующей команды:

```console
az aks browse --resource-group MSSampleResourceGroupAKS --name mssampleclusterk801
```

При этом нужно перейти по URL-адресу `http://127.0.0.1:8001`.

![Представление панели мониторинга Kubernetes в браузере, показывающее развертывания, объекты pod, наборы реплик и службы.](media/kubernetes-cluster-information.png)

**Рис. 4-49**. Просмотр сведений о кластере Kubernetes

Теперь у вас есть приложение, развернутое в Azure с использованием контейнера Linux и кластера Kubernetes в AKS. Вы сможете обратиться к приложению, перейдя на общедоступный IP-адрес своей службы, который можно получить на портале Azure.

> [!NOTE]
> Сведения о том, как создать кластер AKS для этого примера, см. в разделе [**Развертывание в службе Azure Kubernetes (AKS)** ](deploy-azure-kubernetes-service.md) этого руководства.

>[!div class="step-by-step"]
>[Назад](set-up-windows-containers-with-powershell.md)
>[Вперед](../docker-devops-workflow/index.md)
