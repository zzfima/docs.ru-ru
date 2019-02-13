---
title: Создавать приложения ASP.NET Core 2.1, разворачиваются как контейнеры Linux в кластерах AKS/Kubernetes
description: Жизненный цикл контейнерного приложения Docker на основе платформы и средств Майкрософт
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 11/23/2018
ms.openlocfilehash: b03b6fab9dcd53e97c2bc4d7e5c958ca4b931077
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/13/2019
ms.locfileid: "56221516"
---
# <a name="build-aspnet-core-21-applications-deployed-as-linux-containers-into-akskubernetes-orchestrator"></a><span data-ttu-id="04155-103">Создавать приложения ASP.NET Core 2.1, разворачиваются как контейнеры Linux в AKS/Kubernetes orchestrator</span><span class="sxs-lookup"><span data-stu-id="04155-103">Build ASP.NET Core 2.1 applications deployed as Linux containers into AKS/Kubernetes orchestrator</span></span>

<span data-ttu-id="04155-104">Службы Azure Kubernetes (AKS) — службы Azure управляемый Kubernetes оркестрации, которые упрощают развертывание контейнеров и управления.</span><span class="sxs-lookup"><span data-stu-id="04155-104">Azure Kubernetes Services (AKS) is Azure's managed Kubernetes orchestrations services that simplify container deployment and management.</span></span>

<span data-ttu-id="04155-105">Ниже перечислены возможности основного AKS.</span><span class="sxs-lookup"><span data-stu-id="04155-105">AKS main features are:</span></span>

- <span data-ttu-id="04155-106">Плоскость управления Azure</span><span class="sxs-lookup"><span data-stu-id="04155-106">An Azure-hosted control plane</span></span>
- <span data-ttu-id="04155-107">Автоматические обновления</span><span class="sxs-lookup"><span data-stu-id="04155-107">Automated upgrades</span></span>
- <span data-ttu-id="04155-108">Самостоятельное восстановление</span><span class="sxs-lookup"><span data-stu-id="04155-108">Self-healing</span></span>
- <span data-ttu-id="04155-109">Можно настроить масштабирование пользователя</span><span class="sxs-lookup"><span data-stu-id="04155-109">User configurable scaling</span></span>
- <span data-ttu-id="04155-110">Более простую рабочую среду пользователя для разработчиков и операторов кластера.</span><span class="sxs-lookup"><span data-stu-id="04155-110">A simpler user experience for both developers and cluster operators.</span></span>

<span data-ttu-id="04155-111">Следующие примеры Изучите создание приложения ASP.NET Core 2.1, выполняется в системе Linux и развертывает в кластере AKS в Azure, хотя разработка ведется с помощью Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="04155-111">The following examples explore the creation of an ASP.NET Core 2.1 application that runs on Linux and deploys to an AKS Cluster in Azure, while development is done using Visual Studio 2017.</span></span>

## <a name="creating-the-aspnet-core-21-project-using-visual-studio-2017"></a><span data-ttu-id="04155-112">Создание ASP.NET Core 2.1 проекта с помощью Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="04155-112">Creating the ASP.NET Core 2.1 Project using Visual Studio 2017</span></span>

<span data-ttu-id="04155-113">ASP.NET Core — это платформа разработки общего назначения, поддерживается корпорацией Майкрософт и сообществом .NET на GitHub.</span><span class="sxs-lookup"><span data-stu-id="04155-113">ASP.NET Core is a general-purpose development platform maintained by Microsoft and the .NET community on GitHub.</span></span> <span data-ttu-id="04155-114">Она является кроссплатформенной, поддерживает Windows, Mac OS и Linux и может использоваться на устройствах, в облаке, во внедренных системах и в сценариях Интернета вещей.</span><span class="sxs-lookup"><span data-stu-id="04155-114">It is cross-platform, supporting Windows, macOS and Linux, and can be used in device, cloud, and embedded/IoT scenarios.</span></span>

<span data-ttu-id="04155-115">В этом примере используется простой проект, основанный на основе Visual Studio веб-API шаблона, поэтому вам не нужны дополнительные сведения для создания образца.</span><span class="sxs-lookup"><span data-stu-id="04155-115">This example uses a simple project that's based based on a Visual Studio Web API template, so you don't need any additional knowledge to create the sample.</span></span> <span data-ttu-id="04155-116">Необходимо создать проект, используя стандартный шаблон, который включает в себя все элементы для запуска небольшого проекта с помощью REST API, с использованием технологии ASP.NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="04155-116">You only have to create the project using a standard template that includes all the elements to run a small project with a REST API, using ASP.NET Core 2.1 technology.</span></span>

![Добавьте окно нового проекта в Visual Studio, выбрав веб-приложение ASP.NET Core.](media/create-aspnet-core-application.png)

<span data-ttu-id="04155-118">**Рис. 4-36**.</span><span class="sxs-lookup"><span data-stu-id="04155-118">**Figure 4-36**.</span></span> <span data-ttu-id="04155-119">Создание приложения ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="04155-119">Creating ASP.NET Core Application</span></span>

<span data-ttu-id="04155-120">Чтобы создать пример проекта, необходимо выбрать **файл** > **New** > **проекта** на Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="04155-120">To create the sample project, you have to select **File** > **New** > **Project** on Visual Studio.</span></span> <span data-ttu-id="04155-121">Затем вы увидите список шаблонов для различных типов проектов, где нужно искать **Web** > **.NET Core** на левой панели.</span><span class="sxs-lookup"><span data-stu-id="04155-121">Then you'll see a list of templates for several types of projects, where you have to look for **Web** > **.NET Core** on the left panel.</span></span> <span data-ttu-id="04155-122">В этом примере выберите **веб-приложение ASP.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="04155-122">For this example select **ASP.NET Core Web Application**.</span></span>

<span data-ttu-id="04155-123">В следующем диалоговом окне убедитесь, что выбранной .NET Core и ASP.NET Core 2.1 в качестве целевой платформы в верхнем pulldowns, как показано на рисунке 4-37, а затем параметр API, чтобы создать приложение веб-API ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="04155-123">In the next dialog ensure that you have selected .NET Core and ASP.NET Core 2.1 as the target framework in the top pulldowns, as shown in figure 4-37, and then select the API option, to create an ASP.NET Core Web API application.</span></span>

<span data-ttu-id="04155-124">.NET Core 2.1, включенные в Visual Studio 2017 версии 15.7.0 или более поздней версии и автоматически устанавливается и настраивается автоматически при выборе **кросс Платформенная разработка .NET Core** рабочей нагрузки во время установки.</span><span class="sxs-lookup"><span data-stu-id="04155-124">The .NET Core 2.1 is included in Visual Studio 2017 version 15.7.0 or higher and is automatically installed and configured for you when you select the **.NET Core cross-platform development** workload during installation.</span></span>

![Диалоговое окно Visual Studio для выбора типа веб-приложения ASP.NET Core с выбранным параметром API.](media/create-web-api-application.png)

<span data-ttu-id="04155-126">**Рис. 4-37**.</span><span class="sxs-lookup"><span data-stu-id="04155-126">**Figure 4-37**.</span></span> <span data-ttu-id="04155-127">Тип проекта веб-API и выбрав ASP.NET CORE 2.1</span><span class="sxs-lookup"><span data-stu-id="04155-127">Selecting ASP.NET CORE 2.1 and Web API project type</span></span>

<span data-ttu-id="04155-128">При наличии любой предыдущей версии .NET Core, можно загрузить и установить версию 2.1 из <https://www.microsoft.com/net/download/core#/sdk>.</span><span class="sxs-lookup"><span data-stu-id="04155-128">If you have any previous version of .NET Core, you can download and install the 2.1 version from <https://www.microsoft.com/net/download/core#/sdk>.</span></span>

<span data-ttu-id="04155-129">При создании проекта на предыдущем шаге, или более поздней версии, при необходимости после запуска проекта можно добавить поддержку Docker.</span><span class="sxs-lookup"><span data-stu-id="04155-129">You can add Docker support when creating the project in the previous step, or later, if the need arises after starting the project.</span></span> <span data-ttu-id="04155-130">После создания проекта можно добавить поддержку Docker, щелкните правой кнопкой мыши файл проекта в **обозревателе решений** и выберите **добавить** > **поддержку Docker** на контекстное меню.</span><span class="sxs-lookup"><span data-stu-id="04155-130">To add the Docker support after the project creation, right-click on the project file in the **Solution Explorer** and select **Add** > **Docker support** on the context menu.</span></span>

![Контекстного меню для добавления поддержки Docker в существующий проект: Щелкнуть правой кнопкой мыши (проект) > Добавить > поддержка Docker.](media/add-docker-support-to-project.png)

<span data-ttu-id="04155-132">**Рис. 4-38**.</span><span class="sxs-lookup"><span data-stu-id="04155-132">**Figure 4-38**.</span></span> <span data-ttu-id="04155-133">Добавление поддержки Docker в существующий проект</span><span class="sxs-lookup"><span data-stu-id="04155-133">Adding Docker support to existing project</span></span>

<span data-ttu-id="04155-134">Чтобы завершить добавление поддержки Docker, вы можете выбрать Windows или Linux.</span><span class="sxs-lookup"><span data-stu-id="04155-134">To complete adding Docker support, you have the choice of Windows or Linux.</span></span> <span data-ttu-id="04155-135">В этом случае выберите **Linux**, потому что AKS не поддерживает контейнеры Windows (как позднего 2018 г.).</span><span class="sxs-lookup"><span data-stu-id="04155-135">In this case, select **Linux**, because AKS doesn’t support Windows Containers (as of late 2018).</span></span>

![Параметр диалоговое окно для выбора Целевая операционная система для Dockerfile.](media/select-linux-docker-support.png)

<span data-ttu-id="04155-137">**Рис. 4-39**.</span><span class="sxs-lookup"><span data-stu-id="04155-137">**Figure 4-39**.</span></span> <span data-ttu-id="04155-138">Выбор контейнеров Linux.</span><span class="sxs-lookup"><span data-stu-id="04155-138">Selecting Linux containers.</span></span>

<span data-ttu-id="04155-139">С помощью этих простых шагов вы получите приложение ASP.NET Core 2.1, выполняющееся в контейнере Linux.</span><span class="sxs-lookup"><span data-stu-id="04155-139">With these simple steps, you will have your ASP.NET Core 2.1 application running on a Linux container.</span></span>

<span data-ttu-id="04155-140">Как вы видите, интеграцию между Visual Studio 2017 и Docker, полностью ориентирован для повышения производительности разработчика.</span><span class="sxs-lookup"><span data-stu-id="04155-140">As you can see, the integration between Visual Studio 2017 and Docker is totally oriented to the developer’s productivity.</span></span>

<span data-ttu-id="04155-141">Теперь можно нажать клавишу **F5** для сборки и запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="04155-141">Now you can press **F5** to build and run your application.</span></span>

<span data-ttu-id="04155-142">После запуска проекта, вы можете получить список образов, с помощью `docker images` команды.</span><span class="sxs-lookup"><span data-stu-id="04155-142">After running the project, you can list the images using the `docker images` command.</span></span> <span data-ttu-id="04155-143">Вы должны увидеть `mssampleapplication` образ, созданный с помощью автоматического развертывания проектов в Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="04155-143">You should see the `mssampleapplication` image created with the automatic deploy of our project with Visual Studio 2017.</span></span>

```console
docker images
```

![Выходные данные команды образы docker, отображает список с консоли: Репозиторий, тег, идентификатор образа, Created (date) и размер.](media/docker-images-command.png)

<span data-ttu-id="04155-145">**Рис. 4-40**.</span><span class="sxs-lookup"><span data-stu-id="04155-145">**Figure 4-40**.</span></span> <span data-ttu-id="04155-146">Просмотр образов Docker</span><span class="sxs-lookup"><span data-stu-id="04155-146">View of Docker images</span></span>

## <a name="register-the-solution-in-the-azure-container-registry"></a><span data-ttu-id="04155-147">Зарегистрируйте решение в реестре контейнеров Azure</span><span class="sxs-lookup"><span data-stu-id="04155-147">Register the Solution in the Azure Container Registry</span></span>

<span data-ttu-id="04155-148">Передача образа в реестре Docker, например [реестр контейнеров Azure (ACR)](https://azure.microsoft.com/services/container-registry/) или Docker Hub, чтобы можно было развернуть в кластере AKS образы из реестра.</span><span class="sxs-lookup"><span data-stu-id="04155-148">Upload the image to any Docker registry, like [Azure Container Registry (ACR)](https://azure.microsoft.com/services/container-registry/) or Docker Hub so the images can be deployed to the AKS cluster from that registry.</span></span> <span data-ttu-id="04155-149">В этом случае мы отправляете образ в реестр контейнеров Azure.</span><span class="sxs-lookup"><span data-stu-id="04155-149">In this case, we’re uploading the image to Azure Container Registry.</span></span>

### <a name="create-the-image-in-release-mode"></a><span data-ttu-id="04155-150">Создать образ в режиме выпуска</span><span class="sxs-lookup"><span data-stu-id="04155-150">Create the image in Release mode</span></span>

<span data-ttu-id="04155-151">Создание образа в **выпуска** режим (готова к выпуску) изменение до выпуска, как показано ниже и нажмите клавишу F5, чтобы запустить приложение еще раз.</span><span class="sxs-lookup"><span data-stu-id="04155-151">Create the image in **Release** Mode (ready for production) changing to Release as shown here and press F5 to run the application again.</span></span>

![Параметр панели инструментов в Visual STUDIO для построения в режиме выпуска.](media/select-release-mode.png)

<span data-ttu-id="04155-153">**Рис. 4-41**.</span><span class="sxs-lookup"><span data-stu-id="04155-153">**Figure 4-41**.</span></span> <span data-ttu-id="04155-154">Выбор режима выпуска</span><span class="sxs-lookup"><span data-stu-id="04155-154">Selecting Release Mode</span></span>

<span data-ttu-id="04155-155">При выполнении `docker image` команды, вы увидите оба образы, созданные.</span><span class="sxs-lookup"><span data-stu-id="04155-155">If you execute the `docker image` command, you'll see both images created.</span></span> <span data-ttu-id="04155-156">Один для `debug` , а другой для `release` режим.</span><span class="sxs-lookup"><span data-stu-id="04155-156">One for `debug` and the other for `release` mode.</span></span>

### <a name="create-a-new-tag-for-the-image"></a><span data-ttu-id="04155-157">Создать тег для образа</span><span class="sxs-lookup"><span data-stu-id="04155-157">Create a new Tag for the Image</span></span>

<span data-ttu-id="04155-158">Каждый образ контейнера должен следует пометить как `loginServer` имя реестра.</span><span class="sxs-lookup"><span data-stu-id="04155-158">Each container image needs to be tagged with the `loginServer` name of the registry.</span></span> <span data-ttu-id="04155-159">Данный тег используется для маршрутизации при отправке образов контейнеров в реестр образов.</span><span class="sxs-lookup"><span data-stu-id="04155-159">This tag is used for routing when pushing container images to an image registry.</span></span>

<span data-ttu-id="04155-160">Можно просмотреть `loginServer` имя на портале Azure, используя сведения из реестра контейнеров Azure</span><span class="sxs-lookup"><span data-stu-id="04155-160">You can view the `loginServer` name from the Azure portal, taking the information from the Azure Container Registry</span></span>

![Представление браузера имени реестра контейнеров Azure, в правом верхнем углу.](media/loginServer-name.png)

<span data-ttu-id="04155-162">**Рис. 4-42**.</span><span class="sxs-lookup"><span data-stu-id="04155-162">**Figure 4-42**.</span></span> <span data-ttu-id="04155-163">Просмотр имени реестра</span><span class="sxs-lookup"><span data-stu-id="04155-163">View of the name of the Registry</span></span>

<span data-ttu-id="04155-164">Или с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="04155-164">Or by running the following command:</span></span>

```console
az acr list --resource-group MSSampleResourceGroup --query "[].{acrLoginServer:loginServer}" --output table
```

![Выходные данные этой команды консоли.](media/az-cli-loginServer-name.png)

<span data-ttu-id="04155-166">**Рис. 4-43**.</span><span class="sxs-lookup"><span data-stu-id="04155-166">**Figure 4-43**.</span></span> <span data-ttu-id="04155-167">Получите имя реестра, с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="04155-167">Get the name of the registry using PowerShell</span></span>

<span data-ttu-id="04155-168">В обоих случаях будет получить имя.</span><span class="sxs-lookup"><span data-stu-id="04155-168">In both cases, you'll obtain the name.</span></span> <span data-ttu-id="04155-169">В нашем примере `mssampleacr.azurecr.io`.</span><span class="sxs-lookup"><span data-stu-id="04155-169">In our example, `mssampleacr.azurecr.io`.</span></span>

<span data-ttu-id="04155-170">Теперь вы можете пометить изображения, используя последний образ (выпуск образа), с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="04155-170">Now you can tag the image, taking the latest image (Release image), with the following command:</span></span>

```console
docker tag mssampleaksapplication:latest mssampleacr.azurecr.io/mssampleaksapplication:v1
```

<span data-ttu-id="04155-171">После выполнения команды `docker tag` команды, список образов с `docker images` команды.</span><span class="sxs-lookup"><span data-stu-id="04155-171">After running the `docker tag` command, list the images with the `docker images` command.</span></span> <span data-ttu-id="04155-172">Вы должны увидеть изображение с новым тегом.</span><span class="sxs-lookup"><span data-stu-id="04155-172">You should see the image with the new tag.</span></span>

![Выходные данные консоли из команды образы docker.](media/tagged-docker-images-list.png)

<span data-ttu-id="04155-174">**Рис. 4-44**.</span><span class="sxs-lookup"><span data-stu-id="04155-174">**Figure 4-44**.</span></span> <span data-ttu-id="04155-175">Представление, заключенные в теги образов</span><span class="sxs-lookup"><span data-stu-id="04155-175">View of tagged images</span></span>

### <a name="push-the-image-into-the-azure-acr"></a><span data-ttu-id="04155-176">Отправка образа в Azure ACR</span><span class="sxs-lookup"><span data-stu-id="04155-176">Push the image into the Azure ACR</span></span>

<span data-ttu-id="04155-177">Отправьте образ в Azure ACR, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="04155-177">Push the image into the Azure ACR, using the following command:</span></span>

```console
docker push mssampleacr.azurecr.io/mssampleaksapplication:v1
```

<span data-ttu-id="04155-178">Эта команда может занять некоторое время передачи изображений, но предоставляет отзывы в процесс.</span><span class="sxs-lookup"><span data-stu-id="04155-178">This command takes a while uploading the images but gives you feedback in the process.</span></span>

![Консоли выходных данных команды docker Push-уведомлений: отображает символьно ориентированную индикатор выполнения для каждого слоя.](media/uploading-image-to-acr.png)

<span data-ttu-id="04155-180">**Рис. 4-45**.</span><span class="sxs-lookup"><span data-stu-id="04155-180">**Figure 4-45**.</span></span> <span data-ttu-id="04155-181">Отправка образа в ACR.</span><span class="sxs-lookup"><span data-stu-id="04155-181">Uploading the image to the ACR</span></span>

<span data-ttu-id="04155-182">Ниже вы видите результат, вы должны получить после завершения процесса:</span><span class="sxs-lookup"><span data-stu-id="04155-182">You can see below the result you should get when the process completes:</span></span>

![Выходные данные из команды docker Push-уведомлений, завершения работы, показывающий все слои или узлов консоли.](media/uploading-docker-images-complete.png)

<span data-ttu-id="04155-184">**Рис. 4-46**.</span><span class="sxs-lookup"><span data-stu-id="04155-184">**Figure 4-46**.</span></span> <span data-ttu-id="04155-185">Представление узлов</span><span class="sxs-lookup"><span data-stu-id="04155-185">View of nodes</span></span>

<span data-ttu-id="04155-186">Следующим шагом является развертывание контейнера в кластере Kubernetes в AKS.</span><span class="sxs-lookup"><span data-stu-id="04155-186">The next step is to deploy your container into your AKS Kubernetes cluster.</span></span> <span data-ttu-id="04155-187">Для этого требуется файл (**.yml развертывание файла**), таким образом, содержащий:</span><span class="sxs-lookup"><span data-stu-id="04155-187">For that you need a file (**.yml deploy file**) that, in this case, contains:</span></span>

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
> <span data-ttu-id="04155-188">Дополнительные сведения о развертывании с помощью Kubernetes см. в разделе: <https://kubernetes.io/docs/reference/kubectl/cheatsheet/></span><span class="sxs-lookup"><span data-stu-id="04155-188">For more information on deployment with Kubernetes see: <https://kubernetes.io/docs/reference/kubectl/cheatsheet/></span></span>

<span data-ttu-id="04155-189">Теперь почти все готово для развертывания с помощью **Kubectl**, но сначала необходимо получить учетные данные для кластера AKS с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="04155-189">Now you're almost ready to deploy using **Kubectl**, but first you must get the credentials to the AKS Cluster with this command:</span></span>

```console
az aks get-credentials --resource-group MSSampleResourceGroupAKS --name mssampleclusterk801
```

![Выходные данные этой команды консоли: Объединенные MSSampleK8Cluster «как текущий контекст в /root/.kube/config](media/getting-aks-credentials.png)

<span data-ttu-id="04155-191">**Рис. 4-47**.</span><span class="sxs-lookup"><span data-stu-id="04155-191">**Figure 4-47**.</span></span> <span data-ttu-id="04155-192">Получение учетных данных</span><span class="sxs-lookup"><span data-stu-id="04155-192">getting credentials</span></span>

<span data-ttu-id="04155-193">Затем с помощью `kubectl create` команда для запуска развертывания.</span><span class="sxs-lookup"><span data-stu-id="04155-193">Then, use the `kubectl create` command to launch the deployment.</span></span>

```console
kubectl create -f mssample-deploy.yml
```

![Выходных данных этой команды консоли: развертывание «mssamplesbook» создан.](media/kubectl-create-command.png)

<span data-ttu-id="04155-196">**Рис. 4-48**.</span><span class="sxs-lookup"><span data-stu-id="04155-196">**Figure 4-48**.</span></span> <span data-ttu-id="04155-197">Развертывание в Kubernetes</span><span class="sxs-lookup"><span data-stu-id="04155-197">Deploy to Kubernetes</span></span>

<span data-ttu-id="04155-198">После завершения развертывания, можно получить доступ к консоли Kubernetes с локального прокси-сервера, можно временно получить доступ с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="04155-198">When the deployment completes, you can access the Kubernetes console with a local proxy that you can temporally access with this command:</span></span>

```console
az aks browse --resource-group MSSampleResourceGroupAKS --name mssampleclusterk801
```

<span data-ttu-id="04155-199">И доступ к URL-адрес `http://127.0.0.1:8001`.</span><span class="sxs-lookup"><span data-stu-id="04155-199">And accessing the url `http://127.0.0.1:8001`.</span></span>

![Представление панели мониторинга Kubernetes, показывающий развертываний, модулей, наборов реплик и служб в браузере.](media/kubernetes-cluster-information.png)

<span data-ttu-id="04155-201">**Рис. 4-49**.</span><span class="sxs-lookup"><span data-stu-id="04155-201">**Figure 4-49**.</span></span> <span data-ttu-id="04155-202">Просмотреть сведения о кластере Kubernetes</span><span class="sxs-lookup"><span data-stu-id="04155-202">View Kubernetes cluster information</span></span>

<span data-ttu-id="04155-203">Теперь у вас есть приложение, развернутое в Azure с использованием контейнера Linux и кластер Kubernetes службы контейнеров AZURE.</span><span class="sxs-lookup"><span data-stu-id="04155-203">Now you have your application deployed on Azure, using a Linux Container, and an AKS Kubernetes Cluster.</span></span> <span data-ttu-id="04155-204">Вы сможете обращаться к приложению, перейдя к общедоступным IP-адресом службы, которую можно получить на портале Azure.</span><span class="sxs-lookup"><span data-stu-id="04155-204">You can access your app browsing to the public IP of your service, which you can get from the Azure portal.</span></span>

> [!NOTE]
> <span data-ttu-id="04155-205">Можно узнать, как создать кластер AKS для этого примера в разделе [ **развертывание для службы Azure Kubernetes (AKS)** ](deploy-azure-kubernetes-service.md) в этом руководстве.</span><span class="sxs-lookup"><span data-stu-id="04155-205">You can see how to create the AKS Cluster for this sample in section [**Deploy to Azure Kubernetes Service (AKS)**](deploy-azure-kubernetes-service.md) on this guide.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="04155-206">[Назад](set-up-windows-containers-with-powershell.md)
>[Вперед](../docker-devops-workflow/index.md)</span><span class="sxs-lookup"><span data-stu-id="04155-206">[Previous](set-up-windows-containers-with-powershell.md)
[Next](../docker-devops-workflow/index.md)</span></span>
