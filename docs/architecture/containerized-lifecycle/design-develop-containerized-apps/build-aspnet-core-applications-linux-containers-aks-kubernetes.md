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
# <a name="build-aspnet-core-22-applications-deployed-as-linux-containers-into-an-akskubernetes-orchestrator"></a><span data-ttu-id="c1ee5-103">Сборка приложений ASP.NET Core 2.2, развернутых как контейнеры Linux в оркестраторе AKS/Kubernetes</span><span class="sxs-lookup"><span data-stu-id="c1ee5-103">Build ASP.NET Core 2.2 applications deployed as Linux containers into an AKS/Kubernetes orchestrator</span></span>

<span data-ttu-id="c1ee5-104">Служба Azure Kubernetes (AKS) представляет собой службы оркестрации управляемой среды Kubernetes в Azure, упрощающие развертывание контейнеров и управление ими.</span><span class="sxs-lookup"><span data-stu-id="c1ee5-104">Azure Kubernetes Services (AKS) is Azure's managed Kubernetes orchestrations services that simplify container deployment and management.</span></span>

<span data-ttu-id="c1ee5-105">Основные функции AKS:</span><span class="sxs-lookup"><span data-stu-id="c1ee5-105">AKS main features are:</span></span>

- <span data-ttu-id="c1ee5-106">Размещенный в Azure уровень управления</span><span class="sxs-lookup"><span data-stu-id="c1ee5-106">An Azure-hosted control plane</span></span>
- <span data-ttu-id="c1ee5-107">Автоматические обновления</span><span class="sxs-lookup"><span data-stu-id="c1ee5-107">Automated upgrades</span></span>
- <span data-ttu-id="c1ee5-108">самовосстановление;</span><span class="sxs-lookup"><span data-stu-id="c1ee5-108">Self-healing</span></span>
- <span data-ttu-id="c1ee5-109">Настраиваемое пользователем масштабирование</span><span class="sxs-lookup"><span data-stu-id="c1ee5-109">User configurable scaling</span></span>
- <span data-ttu-id="c1ee5-110">Упрощение взаимодействия с пользователем для разработчиков и операторов кластера.</span><span class="sxs-lookup"><span data-stu-id="c1ee5-110">A simpler user experience for both developers and cluster operators.</span></span>

<span data-ttu-id="c1ee5-111">В приведенных ниже примерах рассматривается создание приложения ASP.NET Core 2.2, которое выполняется в Linux и развертывается в кластере AKS в Azure, при этом его разработка осуществляется в Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="c1ee5-111">The following examples explore the creation of an ASP.NET Core 2.2 application that runs on Linux and deploys to an AKS Cluster in Azure, while development is done using Visual Studio 2017.</span></span>

## <a name="creating-the-aspnet-core-22-project-using-visual-studio-2017"></a><span data-ttu-id="c1ee5-112">Создание проекта ASP.NET Core 2.2 с помощью Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="c1ee5-112">Creating the ASP.NET Core 2.2 Project using Visual Studio 2017</span></span>

<span data-ttu-id="c1ee5-113">ASP.NET Core — это универсальная платформа разработки, которая поддерживается корпорацией Майкрософт и сообществом .NET на сайте GitHub.</span><span class="sxs-lookup"><span data-stu-id="c1ee5-113">ASP.NET Core is a general-purpose development platform maintained by Microsoft and the .NET community on GitHub.</span></span> <span data-ttu-id="c1ee5-114">Она является кроссплатформенной, поддерживает Windows, Mac OS и Linux и может использоваться на устройствах, в облаке, во внедренных системах и в сценариях Интернета вещей.</span><span class="sxs-lookup"><span data-stu-id="c1ee5-114">It's cross-platform, supporting Windows, macOS and Linux, and can be used in device, cloud, and embedded/IoT scenarios.</span></span>

<span data-ttu-id="c1ee5-115">В этом примере используется простой проект на основе шаблона веб-API Visual Studio, поэтому вам не нужны дополнительные знания о создании образца.</span><span class="sxs-lookup"><span data-stu-id="c1ee5-115">This example uses a simple project that's based on a Visual Studio Web API template, so you don't need any additional knowledge to create the sample.</span></span> <span data-ttu-id="c1ee5-116">Вам достаточно создать проект с помощью стандартного шаблона, который включает в себя все элементы для запуска небольшого проекта с помощью REST API с использованием технологии ASP.NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="c1ee5-116">You only have to create the project using a standard template that includes all the elements to run a small project with a REST API, using ASP.NET Core 2.2 technology.</span></span>

![Добавьте окно нового проекта в Visual Studio, выбрав "Веб-приложение ASP.NET Core".](media/create-aspnet-core-application.png)

<span data-ttu-id="c1ee5-118">**Рис. 4-36**.</span><span class="sxs-lookup"><span data-stu-id="c1ee5-118">**Figure 4-36**.</span></span> <span data-ttu-id="c1ee5-119">Создание приложения ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="c1ee5-119">Creating ASP.NET Core Application</span></span>

<span data-ttu-id="c1ee5-120">Чтобы создать пример проекта в Visual Studio, выберите **Файл** > **Создать** > **Проект**, укажите тип проекта **Интернет** в левой области и затем выберите **Веб-приложение ASP.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="c1ee5-120">To create the sample project in Visual Studio, select **File** > **New** > **Project**, select the **Web** project types in the left pane, followed by **ASP.NET Core Web Application**.</span></span>

<span data-ttu-id="c1ee5-121">Visual Studio отображает список шаблонов для веб-проектов.</span><span class="sxs-lookup"><span data-stu-id="c1ee5-121">Visual Studio lists templates for web projects.</span></span> <span data-ttu-id="c1ee5-122">Для нашего примера выберите **API**, чтобы создать приложение веб-API ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="c1ee5-122">For our example, select **API** to create an ASP.NET Web API Application.</span></span>

<span data-ttu-id="c1ee5-123">Убедитесь, что выбрана платформа ASP.NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="c1ee5-123">Verify that you've selected ASP.NET Core 2.2 as the framework.</span></span> <span data-ttu-id="c1ee5-124">Платформа .NET Core 2.2 включена в последнюю версию продукта Visual Studio 2017 и автоматически устанавливается и настраивается при его установке.</span><span class="sxs-lookup"><span data-stu-id="c1ee5-124">.NET Core 2.2 is included in the last version of Visual Studio 2017 and is automatically installed and configured for you when you install Visual Studio 2017.</span></span>

![Диалоговое окно Visual Studio для выбора типа веб-приложения ASP.NET Core с выбранным параметром API.](media/create-web-api-application.png)

<span data-ttu-id="c1ee5-126">**Рис. 4-37**.</span><span class="sxs-lookup"><span data-stu-id="c1ee5-126">**Figure 4-37**.</span></span> <span data-ttu-id="c1ee5-127">Выбор ASP.NET Core 2.2 и типа проекта "Веб-API"</span><span class="sxs-lookup"><span data-stu-id="c1ee5-127">Selecting ASP.NET CORE 2.2 and Web API project type</span></span>

<span data-ttu-id="c1ee5-128">При наличии любой предыдущей версии .NET Core можно скачать и установить версию 2.2 по адресу <https://dotnet.microsoft.com/download>.</span><span class="sxs-lookup"><span data-stu-id="c1ee5-128">If you have any previous version of .NET Core, you can download and install the 2.2 version from <https://dotnet.microsoft.com/download>.</span></span>

<span data-ttu-id="c1ee5-129">Поддержку Docker можно добавить при создании проекта или позднее, то есть преобразовать проект для Docker можно в любое время.</span><span class="sxs-lookup"><span data-stu-id="c1ee5-129">You can add Docker support when creating the project or afterwards, so you can "Dockerize" your project at any time.</span></span> <span data-ttu-id="c1ee5-130">Чтобы добавить поддержку Docker после создания проекта, щелкните узел проекта правой кнопкой мыши в обозревателе решений и выберите в контекстном меню пункт **Добавить** > **Поддержка Docker**.</span><span class="sxs-lookup"><span data-stu-id="c1ee5-130">To add Docker support after project creation, right-click on the project node in Solution Explorer and select **Add** > **Docker support** on the context menu.</span></span>

![Пункт контекстного меню, позволяющий добавить поддержку Docker в существующий проект: Щелкните проект правой кнопкой мыши и выберите "Добавить" > "Поддержка Docker".](media/add-docker-support-to-project.png)

<span data-ttu-id="c1ee5-132">**Рис. 4-38**.</span><span class="sxs-lookup"><span data-stu-id="c1ee5-132">**Figure 4-38**.</span></span> <span data-ttu-id="c1ee5-133">Добавление поддержки Docker в существующий проект</span><span class="sxs-lookup"><span data-stu-id="c1ee5-133">Adding Docker support to existing project</span></span>

<span data-ttu-id="c1ee5-134">Чтобы завершить добавление поддержки Docker, можно выбрать платформу Windows или Linux.</span><span class="sxs-lookup"><span data-stu-id="c1ee5-134">To complete adding Docker support, you can choose Windows or Linux.</span></span> <span data-ttu-id="c1ee5-135">В данном случае выберите **Linux**, так как AKS не поддерживает контейнеры Windows (на конец 2018 г.).</span><span class="sxs-lookup"><span data-stu-id="c1ee5-135">In this case, select **Linux**, because AKS doesn’t support Windows Containers (as of late 2018).</span></span>

![Параметр диалогового окна для выбора целевой операционной системы для Dockerfile.](media/select-linux-docker-support.png)

<span data-ttu-id="c1ee5-137">**Рис. 4-39**.</span><span class="sxs-lookup"><span data-stu-id="c1ee5-137">**Figure 4-39**.</span></span> <span data-ttu-id="c1ee5-138">Выбор контейнеров Linux.</span><span class="sxs-lookup"><span data-stu-id="c1ee5-138">Selecting Linux containers.</span></span>

<span data-ttu-id="c1ee5-139">Выполнив эти простые шаги, вы запустите свое приложение ASP.NET Core 2.2 в контейнере Linux.</span><span class="sxs-lookup"><span data-stu-id="c1ee5-139">With these simple steps, you have your ASP.NET Core 2.2 application running on a Linux container.</span></span>

<span data-ttu-id="c1ee5-140">Как видно, интеграцию между Visual Studio 2017 и Docker полностью ориентирована на обеспечение продуктивной работы разработчика.</span><span class="sxs-lookup"><span data-stu-id="c1ee5-140">As you can see, the integration between Visual Studio 2017 and Docker is totally oriented to the developer’s productivity.</span></span>

<span data-ttu-id="c1ee5-141">Теперь вы можете запустить приложение с помощью клавиши **F5** или кнопки **Воспроизвести**.</span><span class="sxs-lookup"><span data-stu-id="c1ee5-141">Now you can run your application with the **F5** key or by using the **Play** button.</span></span>

<span data-ttu-id="c1ee5-142">После выполнения проекта вы можете получить список образов с помощью команды `docker images`.</span><span class="sxs-lookup"><span data-stu-id="c1ee5-142">After running the project, you can list the images using the `docker images` command.</span></span> <span data-ttu-id="c1ee5-143">Вы должны увидеть образ `mssampleapplication`, созданный при автоматическом развертывании вашего проекта с помощью Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="c1ee5-143">You should see the `mssampleapplication` image created by the automatic deployment of our project with Visual Studio 2017.</span></span>

```console
docker images
```

![Выходные данные команды docker images в консоли представляют собой список, содержащий следующее: репозиторий, тег, идентификатор образа, дата создания и размер.](media/docker-images-command.png)

<span data-ttu-id="c1ee5-145">**Рис. 4-40**.</span><span class="sxs-lookup"><span data-stu-id="c1ee5-145">**Figure 4-40**.</span></span> <span data-ttu-id="c1ee5-146">Представление образов Docker</span><span class="sxs-lookup"><span data-stu-id="c1ee5-146">View of Docker images</span></span>

## <a name="register-the-solution-in-the-azure-container-registry"></a><span data-ttu-id="c1ee5-147">Регистрация решения в Реестре контейнеров Azure</span><span class="sxs-lookup"><span data-stu-id="c1ee5-147">Register the Solution in the Azure Container Registry</span></span>

<span data-ttu-id="c1ee5-148">Отправьте образ в любой реестр Docker, например [Реестр контейнеров Azure (ACR)](https://azure.microsoft.com/services/container-registry/) или Docker Hub, чтобы оттуда образы можно было развернуть в кластере AKS.</span><span class="sxs-lookup"><span data-stu-id="c1ee5-148">Upload the image to any Docker registry, like [Azure Container Registry (ACR)](https://azure.microsoft.com/services/container-registry/) or Docker Hub, so the images can be deployed to the AKS cluster from that registry.</span></span> <span data-ttu-id="c1ee5-149">В данном случае мы отправляем образ в Реестр контейнеров Azure.</span><span class="sxs-lookup"><span data-stu-id="c1ee5-149">In this case, we’re uploading the image to Azure Container Registry.</span></span>

### <a name="create-the-image-in-release-mode"></a><span data-ttu-id="c1ee5-150">Создание образа в режиме выпуска</span><span class="sxs-lookup"><span data-stu-id="c1ee5-150">Create the image in Release mode</span></span>

<span data-ttu-id="c1ee5-151">Теперь мы создадим образ в режиме **Выпуск** (готовым к выпуску), заменив значение на **Выпуск**, как показано на рис. 4-41, и запустив приложение, как и раньше.</span><span class="sxs-lookup"><span data-stu-id="c1ee5-151">We'll now create the image in **Release** mode (ready for production) by changing to **Release**, as shown in Figure 4-41, and running the application as we did before.</span></span>

![Параметр панели инструментов в Visual Studio для сборки в режиме выпуска.](media/select-release-mode.png)

<span data-ttu-id="c1ee5-153">**Рис. 4-41**.</span><span class="sxs-lookup"><span data-stu-id="c1ee5-153">**Figure 4-41**.</span></span> <span data-ttu-id="c1ee5-154">Выбор режима выпуска</span><span class="sxs-lookup"><span data-stu-id="c1ee5-154">Selecting Release Mode</span></span>

<span data-ttu-id="c1ee5-155">При выполнении команды `docker image` вы увидите создание обоих образов — одного для режима `debug` и другого для режима `release`.</span><span class="sxs-lookup"><span data-stu-id="c1ee5-155">If you execute the `docker image` command, you'll see both images created, one for `debug` and the other for `release` mode.</span></span>

### <a name="create-a-new-tag-for-the-image"></a><span data-ttu-id="c1ee5-156">Создание тега образа</span><span class="sxs-lookup"><span data-stu-id="c1ee5-156">Create a new Tag for the Image</span></span>

<span data-ttu-id="c1ee5-157">Каждый образ контейнера должен быть помечен именем `loginServer` реестра.</span><span class="sxs-lookup"><span data-stu-id="c1ee5-157">Each container image needs to be tagged with the `loginServer` name of the registry.</span></span> <span data-ttu-id="c1ee5-158">Данный тег используется для маршрутизации при отправке образов контейнеров в реестр образов.</span><span class="sxs-lookup"><span data-stu-id="c1ee5-158">This tag is used for routing when pushing container images to an image registry.</span></span>

<span data-ttu-id="c1ee5-159">Вы можете просмотреть имя `loginServer` на портале Azure, используя сведения из Реестра контейнеров Azure.</span><span class="sxs-lookup"><span data-stu-id="c1ee5-159">You can view the `loginServer` name from the Azure portal, taking the information from the Azure Container Registry</span></span>

![Представление имени Реестра контейнеров Azure в правом верхнем углу браузера.](media/loginServer-name.png)

<span data-ttu-id="c1ee5-161">**Рис. 4-42**.</span><span class="sxs-lookup"><span data-stu-id="c1ee5-161">**Figure 4-42**.</span></span> <span data-ttu-id="c1ee5-162">Представление имени реестра</span><span class="sxs-lookup"><span data-stu-id="c1ee5-162">View of the name of the Registry</span></span>

<span data-ttu-id="c1ee5-163">Кроме того, можно выполнить следующую команду:</span><span class="sxs-lookup"><span data-stu-id="c1ee5-163">Or by running the following command:</span></span>

```console
az acr list --resource-group MSSampleResourceGroup --query "[].{acrLoginServer:loginServer}" --output table
```

![Выходные данные консоли для указанной выше команды.](media/az-cli-loginServer-name.png)

<span data-ttu-id="c1ee5-165">**Рис. 4-43**.</span><span class="sxs-lookup"><span data-stu-id="c1ee5-165">**Figure 4-43**.</span></span> <span data-ttu-id="c1ee5-166">Получение имени реестра с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="c1ee5-166">Get the name of the registry using PowerShell</span></span>

<span data-ttu-id="c1ee5-167">В обоих случаях вы получите нужное имя.</span><span class="sxs-lookup"><span data-stu-id="c1ee5-167">In both cases, you'll obtain the name.</span></span> <span data-ttu-id="c1ee5-168">В нашем примере это `mssampleacr.azurecr.io`.</span><span class="sxs-lookup"><span data-stu-id="c1ee5-168">In our example, `mssampleacr.azurecr.io`.</span></span>

<span data-ttu-id="c1ee5-169">Теперь вы можете пометить образ, используя самый последний образ (образ выпуска), с помощью команды:</span><span class="sxs-lookup"><span data-stu-id="c1ee5-169">Now you can tag the image, taking the latest image (the Release image), with the command:</span></span>

```console
docker tag mssampleaksapplication:latest mssampleacr.azurecr.io/mssampleaksapplication:v1
```

<span data-ttu-id="c1ee5-170">После выполнения команды `docker tag` выведите список образов с помощью команды `docker images`, при этом вы должны увидеть образ с новым тегом.</span><span class="sxs-lookup"><span data-stu-id="c1ee5-170">After running the `docker tag` command, list the images with the `docker images` command, and you should see the image with the new tag.</span></span>

![Выходные данные команды docker images в консоли.](media/tagged-docker-images-list.png)

<span data-ttu-id="c1ee5-172">**Рис. 4-44**.</span><span class="sxs-lookup"><span data-stu-id="c1ee5-172">**Figure 4-44**.</span></span> <span data-ttu-id="c1ee5-173">Представление помеченных образов</span><span class="sxs-lookup"><span data-stu-id="c1ee5-173">View of tagged images</span></span>

### <a name="push-the-image-into-the-azure-acr"></a><span data-ttu-id="c1ee5-174">Отправка образа в Azure ACR</span><span class="sxs-lookup"><span data-stu-id="c1ee5-174">Push the image into the Azure ACR</span></span>

<span data-ttu-id="c1ee5-175">Войдите в Реестр контейнеров Azure:</span><span class="sxs-lookup"><span data-stu-id="c1ee5-175">Log in to the Azure Container Registry</span></span>

```console
az acr login --name mssampleacr
```

<span data-ttu-id="c1ee5-176">Отправьте образ в Реестр контейнеров Azure с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="c1ee5-176">Push the image into the Azure ACR, using the following command:</span></span>

```console
docker push mssampleacr.azurecr.io/mssampleaksapplication:v1
```

<span data-ttu-id="c1ee5-177">Этой команде требуется некоторое время на отправку образа, при этом она предоставляет вам сведения о выполняемой операции.</span><span class="sxs-lookup"><span data-stu-id="c1ee5-177">This command takes a while uploading the images but gives you feedback in the process.</span></span>

![Выходные данные команды docker push в консоли представляют собой основанный на символах индикатор выполнения для каждого уровня.](media/uploading-image-to-acr.png)

<span data-ttu-id="c1ee5-179">**Рис. 4-45**.</span><span class="sxs-lookup"><span data-stu-id="c1ee5-179">**Figure 4-45**.</span></span> <span data-ttu-id="c1ee5-180">Отправка образа в ACR</span><span class="sxs-lookup"><span data-stu-id="c1ee5-180">Uploading the image to the ACR</span></span>

<span data-ttu-id="c1ee5-181">Ниже приведен результат, который вы должны получить после завершения процесса:</span><span class="sxs-lookup"><span data-stu-id="c1ee5-181">You can see below the result you should get when the process completes:</span></span>

![Выходные данные после завершения команды docker push в консоли, содержащие все уровни и узлы.](media/uploading-docker-images-complete.png)

<span data-ttu-id="c1ee5-183">**Рис. 4-46**.</span><span class="sxs-lookup"><span data-stu-id="c1ee5-183">**Figure 4-46**.</span></span> <span data-ttu-id="c1ee5-184">Представление узлов</span><span class="sxs-lookup"><span data-stu-id="c1ee5-184">View of nodes</span></span>

<span data-ttu-id="c1ee5-185">Следующим шагом является развертывание контейнера в кластере Kubernetes в AKS.</span><span class="sxs-lookup"><span data-stu-id="c1ee5-185">The next step is to deploy your container into your AKS Kubernetes cluster.</span></span> <span data-ttu-id="c1ee5-186">Для этого нужен файл (файл развертывания **.yml**), содержащий следующее:</span><span class="sxs-lookup"><span data-stu-id="c1ee5-186">For that, you need a file (**.yml deploy file**) that contains the following:</span></span>

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
> <span data-ttu-id="c1ee5-187">Дополнительные сведения о развертывании с использованием Kubernetes см. в статье <https://kubernetes.io/docs/reference/kubectl/cheatsheet/></span><span class="sxs-lookup"><span data-stu-id="c1ee5-187">For more information on deployment with Kubernetes see: <https://kubernetes.io/docs/reference/kubectl/cheatsheet/></span></span>

<span data-ttu-id="c1ee5-188">Теперь почти все готово для развертывания с помощью **Kubectl**, но сначала нужно получить учетные данные для кластера AKS с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="c1ee5-188">Now you're almost ready to deploy using **Kubectl**, but first you must get the credentials to the AKS Cluster with this command:</span></span>

```console
az aks get-credentials --resource-group MSSampleResourceGroupAKS --name mssampleclusterk801
```

![Выходные данные указанной выше команды в консоли: Произведено слияние MSSampleK8Cluster в качестве текущего контекста в /root/.kube/config](media/getting-aks-credentials.png)

<span data-ttu-id="c1ee5-190">**Рис. 4-47**.</span><span class="sxs-lookup"><span data-stu-id="c1ee5-190">**Figure 4-47**.</span></span> <span data-ttu-id="c1ee5-191">Получение учетных данных</span><span class="sxs-lookup"><span data-stu-id="c1ee5-191">getting credentials</span></span>

<span data-ttu-id="c1ee5-192">Затем запустите развертывание с помощью команды `kubectl create`.</span><span class="sxs-lookup"><span data-stu-id="c1ee5-192">Then, use the `kubectl create` command to launch the deployment.</span></span>

```console
kubectl create -f mssample-deploy.yml
```

![Выходные данные указанной выше команды в консоли: развертывание "mssamplesbook" создано.](media/kubectl-create-command.png)

<span data-ttu-id="c1ee5-195">**Рис. 4-48**.</span><span class="sxs-lookup"><span data-stu-id="c1ee5-195">**Figure 4-48**.</span></span> <span data-ttu-id="c1ee5-196">Развертывание в Kubernetes</span><span class="sxs-lookup"><span data-stu-id="c1ee5-196">Deploy to Kubernetes</span></span>

<span data-ttu-id="c1ee5-197">После завершения развертывания вы можете обратиться к консоли Kubernetes через локальный прокси-сервер, к которому можно временно получить доступ с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="c1ee5-197">When the deployment completes, you can access the Kubernetes console with a local proxy that you can temporally access with this command:</span></span>

```console
az aks browse --resource-group MSSampleResourceGroupAKS --name mssampleclusterk801
```

<span data-ttu-id="c1ee5-198">При этом нужно перейти по URL-адресу `http://127.0.0.1:8001`.</span><span class="sxs-lookup"><span data-stu-id="c1ee5-198">And accessing the url `http://127.0.0.1:8001`.</span></span>

![Представление панели мониторинга Kubernetes в браузере, показывающее развертывания, объекты pod, наборы реплик и службы.](media/kubernetes-cluster-information.png)

<span data-ttu-id="c1ee5-200">**Рис. 4-49**.</span><span class="sxs-lookup"><span data-stu-id="c1ee5-200">**Figure 4-49**.</span></span> <span data-ttu-id="c1ee5-201">Просмотр сведений о кластере Kubernetes</span><span class="sxs-lookup"><span data-stu-id="c1ee5-201">View Kubernetes cluster information</span></span>

<span data-ttu-id="c1ee5-202">Теперь у вас есть приложение, развернутое в Azure с использованием контейнера Linux и кластера Kubernetes в AKS.</span><span class="sxs-lookup"><span data-stu-id="c1ee5-202">Now you have your application deployed on Azure, using a Linux Container, and an AKS Kubernetes Cluster.</span></span> <span data-ttu-id="c1ee5-203">Вы сможете обратиться к приложению, перейдя на общедоступный IP-адрес своей службы, который можно получить на портале Azure.</span><span class="sxs-lookup"><span data-stu-id="c1ee5-203">You can access your app browsing to the public IP of your service, which you can get from the Azure portal.</span></span>

> [!NOTE]
> <span data-ttu-id="c1ee5-204">Сведения о том, как создать кластер AKS для этого примера, см. в разделе [**Развертывание в службе Azure Kubernetes (AKS)** ](deploy-azure-kubernetes-service.md) этого руководства.</span><span class="sxs-lookup"><span data-stu-id="c1ee5-204">You can see how to create the AKS Cluster for this sample in section [**Deploy to Azure Kubernetes Service (AKS)**](deploy-azure-kubernetes-service.md) on this guide.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="c1ee5-205">[Назад](set-up-windows-containers-with-powershell.md)
>[Вперед](../docker-devops-workflow/index.md)</span><span class="sxs-lookup"><span data-stu-id="c1ee5-205">[Previous](set-up-windows-containers-with-powershell.md)
[Next](../docker-devops-workflow/index.md)</span></span>
