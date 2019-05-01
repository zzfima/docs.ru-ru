---
title: Создавать приложения ASP.NET Core 2.1, разворачиваются как контейнеры Linux в кластерах AKS/Kubernetes
description: Жизненный цикл контейнерного приложения Docker на основе платформы и средств Майкрософт
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/25/2019
ms.openlocfilehash: c6d778d345466b1b852d06bc01ce40ccfdebf964
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62052753"
---
# <a name="build-aspnet-core-21-applications-deployed-as-linux-containers-into-an-akskubernetes-orchestrator"></a>Создавать приложения ASP.NET Core 2.1, разворачиваются как контейнеры Linux в оркестраторе AKS и Kubernetes

Службы Azure Kubernetes (AKS) — службы Azure управляемый Kubernetes оркестрации, которые упрощают развертывание контейнеров и управления.

Ниже перечислены возможности основного AKS.

- Плоскость управления Azure
- Автоматические обновления
- Самостоятельное восстановление
- Можно настроить масштабирование пользователя
- Более простую рабочую среду пользователя для разработчиков и операторов кластера.

Следующие примеры Изучите создание приложения ASP.NET Core 2.1, выполняется в системе Linux и развертывает в кластере AKS в Azure, хотя разработка ведется с помощью Visual Studio 2017.

## <a name="creating-the-aspnet-core-21-project-using-visual-studio-2017"></a>Создание ASP.NET Core 2.1 проекта с помощью Visual Studio 2017

ASP.NET Core — это платформа разработки общего назначения, поддерживается корпорацией Майкрософт и сообществом .NET на GitHub. Он работает на разных платформах, которые поддерживают Windows, macOS и Linux и может использоваться в устройство, облака и сценариях внедрения и Интернета вещей.

В этом примере используется простой проект на основе шаблона Visual Studio веб-API, поэтому вам не нужны дополнительные сведения для создания образца. Необходимо создать проект, используя стандартный шаблон, который включает в себя все элементы для запуска небольшого проекта с помощью REST API, с использованием технологии ASP.NET Core 2.1.

![Добавьте окно нового проекта в Visual Studio, выбрав веб-приложение ASP.NET Core.](media/create-aspnet-core-application.png)

**Рис. 4-36**. Создание приложения ASP.NET Core

Чтобы создать пример проекта в Visual Studio, выберите **файл** > **New** > **проекта**выберите **Web**типы проектов в левой области, за которым следует **веб-приложение ASP.NET Core**.

Visual Studio список шаблонов для веб-проектов. В нашем примере выберите **API** для создания API веб-приложения ASP.NET.

Убедитесь, что вы выбрали ASP.NET Core 2.1 как framework. .NET core 2.1 включается в последней версии Visual Studio 2017 и автоматически устанавливается и настроена автоматически при установке Visual Studio 2017.

![Диалоговое окно Visual Studio для выбора типа веб-приложения ASP.NET Core с выбранным параметром API.](media/create-web-api-application.png)

**Рис. 4-37**. Тип проекта веб-API и выбрав ASP.NET CORE 2.1

При наличии любой предыдущей версии .NET Core, можно загрузить и установить версию 2.1 из <https://www.microsoft.com/net/download/core#/sdk>.

При создании проекта можно добавить поддержку Docker или позже, поэтому вы может «Добавление Docker» проекта в любое время. Чтобы добавить поддержку Docker, после создания проекта, щелкните правой кнопкой мыши узел проекта в обозревателе решений и выберите **добавить** > **поддержку Docker** в контекстном меню.

![Контекстного меню для добавления поддержки Docker в существующий проект: Щелкнуть правой кнопкой мыши (проект) > Добавить > поддержка Docker.](media/add-docker-support-to-project.png)

**Рис. 4-38**. Добавление поддержки Docker в существующий проект

Чтобы завершить добавление поддержки Docker, можно выбрать Windows или Linux. В этом случае выберите **Linux**, потому что AKS не поддерживает контейнеры Windows (как позднего 2018 г.).

![Параметр диалоговое окно для выбора Целевая операционная система для Dockerfile.](media/select-linux-docker-support.png)

**Рис. 4-39**. Выбор контейнеров Linux.

С помощью этих простых шагов у вас есть приложения ASP.NET Core 2.1, запущенного в контейнере Linux.

Как вы видите, интеграцию между Visual Studio 2017 и Docker, полностью ориентирован для повышения производительности разработчика.

Теперь вы можете запустить приложение с **F5** ключа, либо с помощью **воспроизведение** кнопки.

После запуска проекта, вы можете получить список образов, с помощью `docker images` команды. Вы должны увидеть `mssampleapplication` образ, созданный путем автоматического развертывания проектов в Visual Studio 2017.

```console
docker images
```

![Выходные данные команды образы docker, отображает список с консоли: Репозиторий, тег, идентификатор образа, Created (date) и размер.](media/docker-images-command.png)

**Рис. 4-40**. Просмотр образов Docker

## <a name="register-the-solution-in-the-azure-container-registry"></a>Зарегистрируйте решение в реестре контейнеров Azure

Передача образа в реестре Docker, например [реестр контейнеров Azure (ACR)](https://azure.microsoft.com/services/container-registry/) или Docker Hub, чтобы можно было развернуть в кластере AKS образы из реестра. В этом случае мы отправляете образ в реестр контейнеров Azure.

### <a name="create-the-image-in-release-mode"></a>Создать образ в режиме выпуска

Теперь мы создадим образ в **выпуска** режим (готова к выпуску), заменив **выпуска**, как показано на рис. 4-41 и запуск приложения, как мы делали раньше.

![Параметр панели инструментов в Visual STUDIO для построения в режиме выпуска.](media/select-release-mode.png)

**Рис. 4-41**. Выбор режима выпуска

При выполнении `docker image` команды, вы увидите обоих создания образов, один для `debug` , а другой для `release` режим.

### <a name="create-a-new-tag-for-the-image"></a>Создать тег для образа

Каждый образ контейнера должен следует пометить как `loginServer` имя реестра. Данный тег используется для маршрутизации при отправке образов контейнеров в реестр образов.

Можно просмотреть `loginServer` имя на портале Azure, используя сведения из реестра контейнеров Azure

![Представление браузера имени реестра контейнеров Azure, в правом верхнем углу.](media/loginServer-name.png)

**Рис. 4-42**. Просмотр имени реестра

Или с помощью следующей команды:

```console
az acr list --resource-group MSSampleResourceGroup --query "[].{acrLoginServer:loginServer}" --output table
```

![Выходные данные этой команды консоли.](media/az-cli-loginServer-name.png)

**Рис. 4-43**. Получите имя реестра, с помощью PowerShell

В обоих случаях будет получить имя. В нашем примере `mssampleacr.azurecr.io`.

Теперь вы можете пометить изображения, используя последний образ (образ выпуска), с помощью команды:

```console
docker tag mssampleaksapplication:latest mssampleacr.azurecr.io/mssampleaksapplication:v1
```

После выполнения команды `docker tag` команды, список образов с `docker images` команда и вы должны увидеть изображение с новым тегом.

![Выходные данные консоли из команды образы docker.](media/tagged-docker-images-list.png)

**Рис. 4-44**. Представление, заключенные в теги образов

### <a name="push-the-image-into-the-azure-acr"></a>Отправка образа в Azure ACR

Отправьте образ в Azure ACR, выполнив следующую команду:

```console
docker push mssampleacr.azurecr.io/mssampleaksapplication:v1
```

Эта команда может занять некоторое время передачи изображений, но предоставляет отзывы в процесс.

![Консоли выходных данных команды docker Push-уведомлений: отображает символьно ориентированную индикатор выполнения для каждого слоя.](media/uploading-image-to-acr.png)

**Рис. 4-45**. Отправка образа в ACR.

Ниже вы видите результат, вы должны получить после завершения процесса:

![Выходные данные из команды docker Push-уведомлений, завершения работы, показывающий все слои или узлов консоли.](media/uploading-docker-images-complete.png)

**Рис. 4-46**. Представление узлов

Следующим шагом является развертывание контейнера в кластере Kubernetes в AKS. Для этого необходимо получить (**.yml развертывание файла**), содержащий указанные ниже:

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
        - mane: mssample-services-app
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
> Дополнительные сведения о развертывании с помощью Kubernetes см. в разделе: <https://kubernetes.io/docs/reference/kubectl/cheatsheet/>

Теперь почти все готово для развертывания с помощью **Kubectl**, но сначала необходимо получить учетные данные для кластера AKS с помощью следующей команды:

```console
az aks get-credentials --resource-group MSSampleResourceGroupAKS --name mssampleclusterk801
```

![Выходные данные этой команды консоли: Объединенные MSSampleK8Cluster «как текущий контекст в /root/.kube/config](media/getting-aks-credentials.png)

**Рис. 4-47**. Получение учетных данных

Затем с помощью `kubectl create` команда для запуска развертывания.

```console
kubectl create -f mssample-deploy.yml
```

![Выходных данных этой команды консоли: развертывание «mssamplesbook» создан. Служба «mssample-kub-app» создан.](media/kubectl-create-command.png)

**Рис. 4-48**. Развертывание в Kubernetes

После завершения развертывания, можно получить доступ к консоли Kubernetes с локального прокси-сервера, можно временно получить доступ с помощью следующей команды:

```console
az aks browse --resource-group MSSampleResourceGroupAKS --name mssampleclusterk801
```

И доступ к URL-адрес `http://127.0.0.1:8001`.

![Представление панели мониторинга Kubernetes, показывающий развертываний, модулей, наборов реплик и служб в браузере.](media/kubernetes-cluster-information.png)

**Рис. 4-49**. Просмотреть сведения о кластере Kubernetes

Теперь у вас есть приложение, развернутое в Azure с использованием контейнера Linux и кластер Kubernetes службы контейнеров AZURE. Вы сможете обращаться к приложению, перейдя к общедоступным IP-адресом службы, которую можно получить на портале Azure.

> [!NOTE]
> Можно узнать, как создать кластер AKS для этого примера в разделе [ **развертывание для службы Azure Kubernetes (AKS)** ](deploy-azure-kubernetes-service.md) в этом руководстве.

>[!div class="step-by-step"]
>[Назад](set-up-windows-containers-with-powershell.md)
>[Вперед](../docker-devops-workflow/index.md)
