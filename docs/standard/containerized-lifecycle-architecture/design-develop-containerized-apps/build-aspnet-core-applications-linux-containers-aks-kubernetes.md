---
title: Создавать приложения ASP.NET Core 2.2, разворачиваются как контейнеры Linux в кластерах AKS/Kubernetes
description: Жизненный цикл контейнерного приложения Docker на основе платформы и средств Майкрософт
ms.date: 02/25/2019
ms.openlocfilehash: 89843e0041c12f001f974360da2e5903499155d1
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "65644785"
---
# <a name="build-aspnet-core-22-applications-deployed-as-linux-containers-into-an-akskubernetes-orchestrator"></a><span data-ttu-id="8baa5-103">Создавать приложения ASP.NET Core 2.2, разворачиваются как контейнеры Linux в оркестраторе AKS и Kubernetes</span><span class="sxs-lookup"><span data-stu-id="8baa5-103">Build ASP.NET Core 2.2 applications deployed as Linux containers into an AKS/Kubernetes orchestrator</span></span>

<span data-ttu-id="8baa5-104">Службы Azure Kubernetes (AKS) — службы Azure управляемый Kubernetes оркестрации, которые упрощают развертывание контейнеров и управления.</span><span class="sxs-lookup"><span data-stu-id="8baa5-104">Azure Kubernetes Services (AKS) is Azure's managed Kubernetes orchestrations services that simplify container deployment and management.</span></span>

<span data-ttu-id="8baa5-105">Ниже перечислены возможности основного AKS.</span><span class="sxs-lookup"><span data-stu-id="8baa5-105">AKS main features are:</span></span>

- <span data-ttu-id="8baa5-106">Плоскость управления Azure</span><span class="sxs-lookup"><span data-stu-id="8baa5-106">An Azure-hosted control plane</span></span>
- <span data-ttu-id="8baa5-107">Автоматические обновления</span><span class="sxs-lookup"><span data-stu-id="8baa5-107">Automated upgrades</span></span>
- <span data-ttu-id="8baa5-108">Самостоятельное восстановление</span><span class="sxs-lookup"><span data-stu-id="8baa5-108">Self-healing</span></span>
- <span data-ttu-id="8baa5-109">Можно настроить масштабирование пользователя</span><span class="sxs-lookup"><span data-stu-id="8baa5-109">User configurable scaling</span></span>
- <span data-ttu-id="8baa5-110">Более простую рабочую среду пользователя для разработчиков и операторов кластера.</span><span class="sxs-lookup"><span data-stu-id="8baa5-110">A simpler user experience for both developers and cluster operators.</span></span>

<span data-ttu-id="8baa5-111">Следующие примеры Изучите создание приложения ASP.NET Core 2.2, которое выполняется в системе Linux и развертывание кластера AKS в Azure, хотя разработка ведется с помощью Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="8baa5-111">The following examples explore the creation of an ASP.NET Core 2.2 application that runs on Linux and deploys to an AKS Cluster in Azure, while development is done using Visual Studio 2017.</span></span>

## <a name="creating-the-aspnet-core-22-project-using-visual-studio-2017"></a><span data-ttu-id="8baa5-112">Создание 2.2 проекта ASP.NET Core с помощью Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="8baa5-112">Creating the ASP.NET Core 2.2 Project using Visual Studio 2017</span></span>

<span data-ttu-id="8baa5-113">ASP.NET Core — это платформа разработки общего назначения, поддерживается корпорацией Майкрософт и сообществом .NET на GitHub.</span><span class="sxs-lookup"><span data-stu-id="8baa5-113">ASP.NET Core is a general-purpose development platform maintained by Microsoft and the .NET community on GitHub.</span></span> <span data-ttu-id="8baa5-114">Он работает на разных платформах, которые поддерживают Windows, macOS и Linux и может использоваться в устройство, облака и сценариях внедрения и Интернета вещей.</span><span class="sxs-lookup"><span data-stu-id="8baa5-114">It's cross-platform, supporting Windows, macOS and Linux, and can be used in device, cloud, and embedded/IoT scenarios.</span></span>

<span data-ttu-id="8baa5-115">В этом примере используется простой проект на основе шаблона Visual Studio веб-API, поэтому вам не нужны дополнительные сведения для создания образца.</span><span class="sxs-lookup"><span data-stu-id="8baa5-115">This example uses a simple project that's based on a Visual Studio Web API template, so you don't need any additional knowledge to create the sample.</span></span> <span data-ttu-id="8baa5-116">Необходимо создать проект, используя стандартный шаблон, который включает в себя все элементы для запуска небольшого проекта с помощью REST API, с использованием технологии ASP.NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="8baa5-116">You only have to create the project using a standard template that includes all the elements to run a small project with a REST API, using ASP.NET Core 2.2 technology.</span></span>

![Добавьте окно нового проекта в Visual Studio, выбрав веб-приложение ASP.NET Core.](media/create-aspnet-core-application.png)

<span data-ttu-id="8baa5-118">**Рис. 4-36**.</span><span class="sxs-lookup"><span data-stu-id="8baa5-118">**Figure 4-36**.</span></span> <span data-ttu-id="8baa5-119">Создание приложения ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="8baa5-119">Creating ASP.NET Core Application</span></span>

<span data-ttu-id="8baa5-120">Чтобы создать пример проекта в Visual Studio, выберите **файл** > **New** > **проекта**выберите **Web**типы проектов в левой области, за которым следует **веб-приложение ASP.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="8baa5-120">To create the sample project in Visual Studio, select **File** > **New** > **Project**, select the **Web** project types in the left pane, followed by **ASP.NET Core Web Application**.</span></span>

<span data-ttu-id="8baa5-121">Visual Studio список шаблонов для веб-проектов.</span><span class="sxs-lookup"><span data-stu-id="8baa5-121">Visual Studio lists templates for web projects.</span></span> <span data-ttu-id="8baa5-122">В нашем примере выберите **API** для создания API веб-приложения ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="8baa5-122">For our example, select **API** to create an ASP.NET Web API Application.</span></span>

<span data-ttu-id="8baa5-123">Убедитесь, что вы выбрали ASP.NET Core 2.2 как framework.</span><span class="sxs-lookup"><span data-stu-id="8baa5-123">Verify that you've selected ASP.NET Core 2.2 as the framework.</span></span> <span data-ttu-id="8baa5-124">.NET core 2.2 включается в последней версии Visual Studio 2017 и автоматически устанавливается и настроена автоматически при установке Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="8baa5-124">.NET Core 2.2 is included in the last version of Visual Studio 2017 and is automatically installed and configured for you when you install Visual Studio 2017.</span></span>

![Диалоговое окно Visual Studio для выбора типа веб-приложения ASP.NET Core с выбранным параметром API.](media/create-web-api-application.png)

<span data-ttu-id="8baa5-126">**Рис. 4-37**.</span><span class="sxs-lookup"><span data-stu-id="8baa5-126">**Figure 4-37**.</span></span> <span data-ttu-id="8baa5-127">Тип проекта веб-API и выбрав 2.2 ASP.NET CORE</span><span class="sxs-lookup"><span data-stu-id="8baa5-127">Selecting ASP.NET CORE 2.2 and Web API project type</span></span>

<span data-ttu-id="8baa5-128">При наличии любой предыдущей версии .NET Core, можно загрузить и установить версию 2,2 из <https://www.microsoft.com/net/download/core#/sdk>.</span><span class="sxs-lookup"><span data-stu-id="8baa5-128">If you have any previous version of .NET Core, you can download and install the 2.2 version from <https://www.microsoft.com/net/download/core#/sdk>.</span></span>

<span data-ttu-id="8baa5-129">При создании проекта можно добавить поддержку Docker или позже, поэтому вы может «Добавление Docker» проекта в любое время.</span><span class="sxs-lookup"><span data-stu-id="8baa5-129">You can add Docker support when creating the project or afterwards, so you can "Dockerize" your project at any time.</span></span> <span data-ttu-id="8baa5-130">Чтобы добавить поддержку Docker, после создания проекта, щелкните правой кнопкой мыши узел проекта в обозревателе решений и выберите **добавить** > **поддержку Docker** в контекстном меню.</span><span class="sxs-lookup"><span data-stu-id="8baa5-130">To add Docker support after project creation, right-click on the project node in Solution Explorer and select **Add** > **Docker support** on the context menu.</span></span>

![Контекстного меню для добавления поддержки Docker в существующий проект: Щелкнуть правой кнопкой мыши (проект) > Добавить > поддержка Docker.](media/add-docker-support-to-project.png)

<span data-ttu-id="8baa5-132">**Рис. 4-38**.</span><span class="sxs-lookup"><span data-stu-id="8baa5-132">**Figure 4-38**.</span></span> <span data-ttu-id="8baa5-133">Добавление поддержки Docker в существующий проект</span><span class="sxs-lookup"><span data-stu-id="8baa5-133">Adding Docker support to existing project</span></span>

<span data-ttu-id="8baa5-134">Чтобы завершить добавление поддержки Docker, можно выбрать Windows или Linux.</span><span class="sxs-lookup"><span data-stu-id="8baa5-134">To complete adding Docker support, you can choose Windows or Linux.</span></span> <span data-ttu-id="8baa5-135">В этом случае выберите **Linux**, потому что AKS не поддерживает контейнеры Windows (как позднего 2018 г.).</span><span class="sxs-lookup"><span data-stu-id="8baa5-135">In this case, select **Linux**, because AKS doesn’t support Windows Containers (as of late 2018).</span></span>

![Параметр диалоговое окно для выбора Целевая операционная система для Dockerfile.](media/select-linux-docker-support.png)

<span data-ttu-id="8baa5-137">**Рис. 4-39**.</span><span class="sxs-lookup"><span data-stu-id="8baa5-137">**Figure 4-39**.</span></span> <span data-ttu-id="8baa5-138">Выбор контейнеров Linux.</span><span class="sxs-lookup"><span data-stu-id="8baa5-138">Selecting Linux containers.</span></span>

<span data-ttu-id="8baa5-139">С помощью этих простых шагов у вас есть приложения ASP.NET Core 2.2, запущенного в контейнере Linux.</span><span class="sxs-lookup"><span data-stu-id="8baa5-139">With these simple steps, you have your ASP.NET Core 2.2 application running on a Linux container.</span></span>

<span data-ttu-id="8baa5-140">Как вы видите, интеграцию между Visual Studio 2017 и Docker, полностью ориентирован для повышения производительности разработчика.</span><span class="sxs-lookup"><span data-stu-id="8baa5-140">As you can see, the integration between Visual Studio 2017 and Docker is totally oriented to the developer’s productivity.</span></span>

<span data-ttu-id="8baa5-141">Теперь вы можете запустить приложение с **F5** ключа, либо с помощью **воспроизведение** кнопки.</span><span class="sxs-lookup"><span data-stu-id="8baa5-141">Now you can run your application with the **F5** key or by using the **Play** button.</span></span>

<span data-ttu-id="8baa5-142">После запуска проекта, вы можете получить список образов, с помощью `docker images` команды.</span><span class="sxs-lookup"><span data-stu-id="8baa5-142">After running the project, you can list the images using the `docker images` command.</span></span> <span data-ttu-id="8baa5-143">Вы должны увидеть `mssampleapplication` образ, созданный путем автоматического развертывания проектов в Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="8baa5-143">You should see the `mssampleapplication` image created by the automatic deployment of our project with Visual Studio 2017.</span></span>

```console
docker images
```

![Выходные данные команды образы docker, отображает список с консоли: Репозиторий, тег, идентификатор образа, Created (date) и размер.](media/docker-images-command.png)

<span data-ttu-id="8baa5-145">**Рис. 4-40**.</span><span class="sxs-lookup"><span data-stu-id="8baa5-145">**Figure 4-40**.</span></span> <span data-ttu-id="8baa5-146">Просмотр образов Docker</span><span class="sxs-lookup"><span data-stu-id="8baa5-146">View of Docker images</span></span>

## <a name="register-the-solution-in-the-azure-container-registry"></a><span data-ttu-id="8baa5-147">Зарегистрируйте решение в реестре контейнеров Azure</span><span class="sxs-lookup"><span data-stu-id="8baa5-147">Register the Solution in the Azure Container Registry</span></span>

<span data-ttu-id="8baa5-148">Передача образа в реестре Docker, например [реестр контейнеров Azure (ACR)](https://azure.microsoft.com/services/container-registry/) или Docker Hub, чтобы можно было развернуть в кластере AKS образы из реестра.</span><span class="sxs-lookup"><span data-stu-id="8baa5-148">Upload the image to any Docker registry, like [Azure Container Registry (ACR)](https://azure.microsoft.com/services/container-registry/) or Docker Hub, so the images can be deployed to the AKS cluster from that registry.</span></span> <span data-ttu-id="8baa5-149">В этом случае мы отправляете образ в реестр контейнеров Azure.</span><span class="sxs-lookup"><span data-stu-id="8baa5-149">In this case, we’re uploading the image to Azure Container Registry.</span></span>

### <a name="create-the-image-in-release-mode"></a><span data-ttu-id="8baa5-150">Создать образ в режиме выпуска</span><span class="sxs-lookup"><span data-stu-id="8baa5-150">Create the image in Release mode</span></span>

<span data-ttu-id="8baa5-151">Теперь мы создадим образ в **выпуска** режим (готова к выпуску), заменив **выпуска**, как показано на рис. 4-41 и запуск приложения, как мы делали раньше.</span><span class="sxs-lookup"><span data-stu-id="8baa5-151">We'll now create the image in **Release** mode (ready for production) by changing to **Release**, as shown in Figure 4-41, and running the application as we did before.</span></span>

![Параметр панели инструментов в Visual STUDIO для построения в режиме выпуска.](media/select-release-mode.png)

<span data-ttu-id="8baa5-153">**Рис. 4-41**.</span><span class="sxs-lookup"><span data-stu-id="8baa5-153">**Figure 4-41**.</span></span> <span data-ttu-id="8baa5-154">Выбор режима выпуска</span><span class="sxs-lookup"><span data-stu-id="8baa5-154">Selecting Release Mode</span></span>

<span data-ttu-id="8baa5-155">При выполнении `docker image` команды, вы увидите обоих создания образов, один для `debug` , а другой для `release` режим.</span><span class="sxs-lookup"><span data-stu-id="8baa5-155">If you execute the `docker image` command, you'll see both images created, one for `debug` and the other for `release` mode.</span></span>

### <a name="create-a-new-tag-for-the-image"></a><span data-ttu-id="8baa5-156">Создать тег для образа</span><span class="sxs-lookup"><span data-stu-id="8baa5-156">Create a new Tag for the Image</span></span>

<span data-ttu-id="8baa5-157">Каждый образ контейнера должен следует пометить как `loginServer` имя реестра.</span><span class="sxs-lookup"><span data-stu-id="8baa5-157">Each container image needs to be tagged with the `loginServer` name of the registry.</span></span> <span data-ttu-id="8baa5-158">Данный тег используется для маршрутизации при отправке образов контейнеров в реестр образов.</span><span class="sxs-lookup"><span data-stu-id="8baa5-158">This tag is used for routing when pushing container images to an image registry.</span></span>

<span data-ttu-id="8baa5-159">Можно просмотреть `loginServer` имя на портале Azure, используя сведения из реестра контейнеров Azure</span><span class="sxs-lookup"><span data-stu-id="8baa5-159">You can view the `loginServer` name from the Azure portal, taking the information from the Azure Container Registry</span></span>

![Представление браузера имени реестра контейнеров Azure, в правом верхнем углу.](media/loginServer-name.png)

<span data-ttu-id="8baa5-161">**Рис. 4-42**.</span><span class="sxs-lookup"><span data-stu-id="8baa5-161">**Figure 4-42**.</span></span> <span data-ttu-id="8baa5-162">Просмотр имени реестра</span><span class="sxs-lookup"><span data-stu-id="8baa5-162">View of the name of the Registry</span></span>

<span data-ttu-id="8baa5-163">Или с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="8baa5-163">Or by running the following command:</span></span>

```console
az acr list --resource-group MSSampleResourceGroup --query "[].{acrLoginServer:loginServer}" --output table
```

![Выходные данные этой команды консоли.](media/az-cli-loginServer-name.png)

<span data-ttu-id="8baa5-165">**Рис. 4-43**.</span><span class="sxs-lookup"><span data-stu-id="8baa5-165">**Figure 4-43**.</span></span> <span data-ttu-id="8baa5-166">Получите имя реестра, с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="8baa5-166">Get the name of the registry using PowerShell</span></span>

<span data-ttu-id="8baa5-167">В обоих случаях будет получить имя.</span><span class="sxs-lookup"><span data-stu-id="8baa5-167">In both cases, you'll obtain the name.</span></span> <span data-ttu-id="8baa5-168">В нашем примере `mssampleacr.azurecr.io`.</span><span class="sxs-lookup"><span data-stu-id="8baa5-168">In our example, `mssampleacr.azurecr.io`.</span></span>

<span data-ttu-id="8baa5-169">Теперь вы можете пометить изображения, используя последний образ (образ выпуска), с помощью команды:</span><span class="sxs-lookup"><span data-stu-id="8baa5-169">Now you can tag the image, taking the latest image (the Release image), with the command:</span></span>

```console
docker tag mssampleaksapplication:latest mssampleacr.azurecr.io/mssampleaksapplication:v1
```

<span data-ttu-id="8baa5-170">После выполнения команды `docker tag` команды, список образов с `docker images` команда и вы должны увидеть изображение с новым тегом.</span><span class="sxs-lookup"><span data-stu-id="8baa5-170">After running the `docker tag` command, list the images with the `docker images` command, and you should see the image with the new tag.</span></span>

![Выходные данные консоли из команды образы docker.](media/tagged-docker-images-list.png)

<span data-ttu-id="8baa5-172">**Рис. 4-44**.</span><span class="sxs-lookup"><span data-stu-id="8baa5-172">**Figure 4-44**.</span></span> <span data-ttu-id="8baa5-173">Представление, заключенные в теги образов</span><span class="sxs-lookup"><span data-stu-id="8baa5-173">View of tagged images</span></span>

### <a name="push-the-image-into-the-azure-acr"></a><span data-ttu-id="8baa5-174">Отправка образа в Azure ACR</span><span class="sxs-lookup"><span data-stu-id="8baa5-174">Push the image into the Azure ACR</span></span>

<span data-ttu-id="8baa5-175">Вход в реестр контейнеров Azure</span><span class="sxs-lookup"><span data-stu-id="8baa5-175">Log in to the Azure Container Registry</span></span>

```console
az acr login --name mssampleacr
```

<span data-ttu-id="8baa5-176">Отправьте образ в Azure ACR, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="8baa5-176">Push the image into the Azure ACR, using the following command:</span></span>

```console
docker push mssampleacr.azurecr.io/mssampleaksapplication:v1
```

<span data-ttu-id="8baa5-177">Эта команда может занять некоторое время передачи изображений, но предоставляет отзывы в процесс.</span><span class="sxs-lookup"><span data-stu-id="8baa5-177">This command takes a while uploading the images but gives you feedback in the process.</span></span>

![Консоли выходных данных команды docker Push-уведомлений: отображает символьно ориентированную индикатор выполнения для каждого слоя.](media/uploading-image-to-acr.png)

<span data-ttu-id="8baa5-179">**Рис. 4-45**.</span><span class="sxs-lookup"><span data-stu-id="8baa5-179">**Figure 4-45**.</span></span> <span data-ttu-id="8baa5-180">Отправка образа в ACR.</span><span class="sxs-lookup"><span data-stu-id="8baa5-180">Uploading the image to the ACR</span></span>

<span data-ttu-id="8baa5-181">Ниже вы видите результат, вы должны получить после завершения процесса:</span><span class="sxs-lookup"><span data-stu-id="8baa5-181">You can see below the result you should get when the process completes:</span></span>

![Выходные данные из команды docker Push-уведомлений, завершения работы, показывающий все слои или узлов консоли.](media/uploading-docker-images-complete.png)

<span data-ttu-id="8baa5-183">**Рис. 4-46**.</span><span class="sxs-lookup"><span data-stu-id="8baa5-183">**Figure 4-46**.</span></span> <span data-ttu-id="8baa5-184">Представление узлов</span><span class="sxs-lookup"><span data-stu-id="8baa5-184">View of nodes</span></span>

<span data-ttu-id="8baa5-185">Следующим шагом является развертывание контейнера в кластере Kubernetes в AKS.</span><span class="sxs-lookup"><span data-stu-id="8baa5-185">The next step is to deploy your container into your AKS Kubernetes cluster.</span></span> <span data-ttu-id="8baa5-186">Для этого необходимо получить (**.yml развертывание файла**), содержащий указанные ниже:</span><span class="sxs-lookup"><span data-stu-id="8baa5-186">For that, you need a file (**.yml deploy file**) that contains the following:</span></span>

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
> <span data-ttu-id="8baa5-187">Дополнительные сведения о развертывании с помощью Kubernetes см. в разделе: <https://kubernetes.io/docs/reference/kubectl/cheatsheet/></span><span class="sxs-lookup"><span data-stu-id="8baa5-187">For more information on deployment with Kubernetes see: <https://kubernetes.io/docs/reference/kubectl/cheatsheet/></span></span>

<span data-ttu-id="8baa5-188">Теперь почти все готово для развертывания с помощью **Kubectl**, но сначала необходимо получить учетные данные для кластера AKS с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="8baa5-188">Now you're almost ready to deploy using **Kubectl**, but first you must get the credentials to the AKS Cluster with this command:</span></span>

```console
az aks get-credentials --resource-group MSSampleResourceGroupAKS --name mssampleclusterk801
```

![Выходные данные этой команды консоли: Объединенные MSSampleK8Cluster «как текущий контекст в /root/.kube/config](media/getting-aks-credentials.png)

<span data-ttu-id="8baa5-190">**Рис. 4-47**.</span><span class="sxs-lookup"><span data-stu-id="8baa5-190">**Figure 4-47**.</span></span> <span data-ttu-id="8baa5-191">Получение учетных данных</span><span class="sxs-lookup"><span data-stu-id="8baa5-191">getting credentials</span></span>

<span data-ttu-id="8baa5-192">Затем с помощью `kubectl create` команда для запуска развертывания.</span><span class="sxs-lookup"><span data-stu-id="8baa5-192">Then, use the `kubectl create` command to launch the deployment.</span></span>

```console
kubectl create -f mssample-deploy.yml
```

![Выходных данных этой команды консоли: развертывание «mssamplesbook» создан.](media/kubectl-create-command.png)

<span data-ttu-id="8baa5-195">**Рис. 4-48**.</span><span class="sxs-lookup"><span data-stu-id="8baa5-195">**Figure 4-48**.</span></span> <span data-ttu-id="8baa5-196">Развертывание в Kubernetes</span><span class="sxs-lookup"><span data-stu-id="8baa5-196">Deploy to Kubernetes</span></span>

<span data-ttu-id="8baa5-197">После завершения развертывания, можно получить доступ к консоли Kubernetes с локального прокси-сервера, можно временно получить доступ с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="8baa5-197">When the deployment completes, you can access the Kubernetes console with a local proxy that you can temporally access with this command:</span></span>

```console
az aks browse --resource-group MSSampleResourceGroupAKS --name mssampleclusterk801
```

<span data-ttu-id="8baa5-198">И доступ к URL-адрес `http://127.0.0.1:8001`.</span><span class="sxs-lookup"><span data-stu-id="8baa5-198">And accessing the url `http://127.0.0.1:8001`.</span></span>

![Представление панели мониторинга Kubernetes, показывающий развертываний, модулей, наборов реплик и служб в браузере.](media/kubernetes-cluster-information.png)

<span data-ttu-id="8baa5-200">**Рис. 4-49**.</span><span class="sxs-lookup"><span data-stu-id="8baa5-200">**Figure 4-49**.</span></span> <span data-ttu-id="8baa5-201">Просмотреть сведения о кластере Kubernetes</span><span class="sxs-lookup"><span data-stu-id="8baa5-201">View Kubernetes cluster information</span></span>

<span data-ttu-id="8baa5-202">Теперь у вас есть приложение, развернутое в Azure с использованием контейнера Linux и кластер Kubernetes службы контейнеров AZURE.</span><span class="sxs-lookup"><span data-stu-id="8baa5-202">Now you have your application deployed on Azure, using a Linux Container, and an AKS Kubernetes Cluster.</span></span> <span data-ttu-id="8baa5-203">Вы сможете обращаться к приложению, перейдя к общедоступным IP-адресом службы, которую можно получить на портале Azure.</span><span class="sxs-lookup"><span data-stu-id="8baa5-203">You can access your app browsing to the public IP of your service, which you can get from the Azure portal.</span></span>

> [!NOTE]
> <span data-ttu-id="8baa5-204">Можно узнать, как создать кластер AKS для этого примера в разделе [ **развертывание для службы Azure Kubernetes (AKS)** ](deploy-azure-kubernetes-service.md) в этом руководстве.</span><span class="sxs-lookup"><span data-stu-id="8baa5-204">You can see how to create the AKS Cluster for this sample in section [**Deploy to Azure Kubernetes Service (AKS)**](deploy-azure-kubernetes-service.md) on this guide.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="8baa5-205">[Назад](set-up-windows-containers-with-powershell.md)
>[Вперед](../docker-devops-workflow/index.md)</span><span class="sxs-lookup"><span data-stu-id="8baa5-205">[Previous](set-up-windows-containers-with-powershell.md)
[Next](../docker-devops-workflow/index.md)</span></span>
