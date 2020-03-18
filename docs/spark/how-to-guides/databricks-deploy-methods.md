---
title: Отправка задания .NET для Apache Spark в Databricks
description: Узнайте, как отправить задание .NET для Apache Spark в Databricks с помощью spark-submit и действия "Указание файла JAR".
ms.date: 12/05/2019
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: 65976f9095ecef66e0538c398492033c612c1430
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "79187611"
---
# <a name="submit-a-net-for-apache-spark-job-to-databricks"></a><span data-ttu-id="56408-103">Отправка задания .NET для Apache Spark в Databricks</span><span class="sxs-lookup"><span data-stu-id="56408-103">Submit a .NET for Apache Spark job to Databricks</span></span>

<span data-ttu-id="56408-104">Есть два способа развертывания задания .NET для Apache Spark в Databricks: с помощью команды `spark-submit` и действия "Указание файла JAR".</span><span class="sxs-lookup"><span data-stu-id="56408-104">There are two ways to deploy your .NET for Apache Spark job to Databricks: `spark-submit` and Set Jar.</span></span>

## <a name="deploy-using-spark-submit"></a><span data-ttu-id="56408-105">Развертывание с помощью spark-submit</span><span class="sxs-lookup"><span data-stu-id="56408-105">Deploy using spark-submit</span></span>

<span data-ttu-id="56408-106">Для отправки заданий .NET для Apache Spark в Databricks можно использовать команду [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html).</span><span class="sxs-lookup"><span data-stu-id="56408-106">You can use the [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) command to submit .NET for Apache Spark jobs to Databricks.</span></span> <span data-ttu-id="56408-107">`spark-submit` разрешает отправку только в кластер, который создается по требованию.</span><span class="sxs-lookup"><span data-stu-id="56408-107">`spark-submit` allows submission only to a cluster that gets created on-demand.</span></span>

1. <span data-ttu-id="56408-108">Перейдите в рабочую область Databricks и создайте задание.</span><span class="sxs-lookup"><span data-stu-id="56408-108">Navigate to your Databricks Workspace and create a job.</span></span> <span data-ttu-id="56408-109">Выберите название задания, а затем нажмите **Настройка spark-submit**.</span><span class="sxs-lookup"><span data-stu-id="56408-109">Choose a title for your job, and then select **Configure spark-submit**.</span></span> <span data-ttu-id="56408-110">Вставьте следующие параметры в конфигурацию задания и щелкните **Подтвердить**.</span><span class="sxs-lookup"><span data-stu-id="56408-110">Paste the following parameters in the job configuration, then select **Confirm**.</span></span>

    ```
    ["--files","/dbfs/<path-to>/<app assembly/file to deploy to worker>","--class","org.apache.spark.deploy.dotnet.DotnetRunner","/dbfs/<path-to>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar","/dbfs/<path-to>/<app name>.zip","<app bin name>","app arg1","app arg2"]
    ```

    > [!NOTE]
    > <span data-ttu-id="56408-111">Обновите содержимое указанного выше параметра с учетом конкретных файлов и конфигурации.</span><span class="sxs-lookup"><span data-stu-id="56408-111">Update the contents of the above parameter based on your specific files and configuration.</span></span> <span data-ttu-id="56408-112">Например, укажите версию файла JAR Microsoft.Spark, который вы отправили в DBFS, и используйте соответствующее имя приложения и ZIP-файла опубликованного приложения.</span><span class="sxs-lookup"><span data-stu-id="56408-112">For instance, reference the version of the Microsoft.Spark jar file that you uploaded to DBFS, and use the appropriate name of your app and published app zip file.</span></span>

2. <span data-ttu-id="56408-113">Перейдите к своему заданию и выберите **Изменить**, чтобы настроить кластер задания.</span><span class="sxs-lookup"><span data-stu-id="56408-113">Navigate to your job and select **Edit** to configure your job's cluster.</span></span> <span data-ttu-id="56408-114">Задайте версию Databricks Runtime в зависимости от версии Apache Spark, которую вы хотите использовать в развертывании.</span><span class="sxs-lookup"><span data-stu-id="56408-114">Set the Databricks Runtime Version based on the version of Apache Spark you wish to use in your deployment.</span></span> <span data-ttu-id="56408-115">Затем щелкните **Дополнительные параметры > Скрипты инициализации** и задайте значение `dbfs:/spark-dotnet/db-init.sh` для параметра пути к скрипту инициализации.</span><span class="sxs-lookup"><span data-stu-id="56408-115">Then select **Advanced Options > Init Scripts**, and set Init Script Path as `dbfs:/spark-dotnet/db-init.sh`.</span></span> <span data-ttu-id="56408-116">Выберите **Подтвердить**, чтобы подтвердить параметры кластера.</span><span class="sxs-lookup"><span data-stu-id="56408-116">Select **Confirm** to confirm your cluster settings.</span></span>

3. <span data-ttu-id="56408-117">Перейдите к своему заданию и выберите **Запустить сейчас**, чтобы запустить задание в только что настроенном кластере Spark.</span><span class="sxs-lookup"><span data-stu-id="56408-117">Navigate to your job and select **Run Now** to run your job on your newly configured Spark cluster.</span></span> <span data-ttu-id="56408-118">Создание кластера для задания может занять несколько минут.</span><span class="sxs-lookup"><span data-stu-id="56408-118">It takes a few minutes for the job's cluster to be created.</span></span> <span data-ttu-id="56408-119">После этого в кластер будет отправлено задание.</span><span class="sxs-lookup"><span data-stu-id="56408-119">Once it is created, your job will be submitted.</span></span> <span data-ttu-id="56408-120">Чтобы просмотреть выходные данные, выберите **Кластеры** в меню слева в рабочей области Databricks, а затем щелкните **Журналы драйверов**.</span><span class="sxs-lookup"><span data-stu-id="56408-120">You can view the output by selecting **Clusters** from the left menu of your Databricks workspace, then select **Driver Logs**.</span></span>

## <a name="deploy-using-set-jar"></a><span data-ttu-id="56408-121">Развертывание с помощью действия "Указание файла JAR"</span><span class="sxs-lookup"><span data-stu-id="56408-121">Deploy using Set Jar</span></span>

<span data-ttu-id="56408-122">Кроме того, для отправки заданий .NET для Apache Spark в Databricks можно использовать действия [Указание файла JAR](https://docs.microsoft.com/azure/databricks/jobs#--create-a-job) в рабочей области Databricks.</span><span class="sxs-lookup"><span data-stu-id="56408-122">Alternatively, you can use [Set Jar](https://docs.microsoft.com/azure/databricks/jobs#--create-a-job) in your Databricks workspace to submit .NET for Apache Spark jobs to Databricks.</span></span> <span data-ttu-id="56408-123">Действие *Указание файла JAR* позволяет отправить задание в существующий активный кластер.</span><span class="sxs-lookup"><span data-stu-id="56408-123">*Set Jar* allows job submission to an existing active cluster.</span></span>

### <a name="one-time-setup"></a><span data-ttu-id="56408-124">Однократная настройка</span><span class="sxs-lookup"><span data-stu-id="56408-124">One-time setup</span></span>

1. <span data-ttu-id="56408-125">Перейдите в кластер Databricks и в меню слева выберите **Задания**, а затем **Указание файла JAR**.</span><span class="sxs-lookup"><span data-stu-id="56408-125">Navigate to your Databricks cluster and select **Jobs** from the left-side menu, followed by **Set JAR**.</span></span>

2. <span data-ttu-id="56408-126">Отправьте соответствующий файл `microsoft-spark-<spark-version>-<spark-dotnet-version>.jar`.</span><span class="sxs-lookup"><span data-stu-id="56408-126">Upload the appropriate `microsoft-spark-<spark-version>-<spark-dotnet-version>.jar`.</span></span>

3. <span data-ttu-id="56408-127">Измените следующие параметры, чтобы вместо `<your-app-name>` указать правильное имя опубликованного исполняемого файла.</span><span class="sxs-lookup"><span data-stu-id="56408-127">Modify the following parameters to include the correct name for the executable that you published in place of `<your-app-name>`:</span></span>

    ```
    Main Class: org.apache.spark.deploy.dotnet.DotnetRunner
    Arguments /dbfs/apps/<your-app-name>.zip <your-app-name>
    ```

4. <span data-ttu-id="56408-128">Настройте для кластера ссылку на существующий кластер, для которого вы уже настроили скрипт инициализации.</span><span class="sxs-lookup"><span data-stu-id="56408-128">Configure the cluster to point to an existing cluster for which you have already set the init script.</span></span>

### <a name="publish-and-run-your-app"></a><span data-ttu-id="56408-129">Публикация и запуск приложения</span><span class="sxs-lookup"><span data-stu-id="56408-129">Publish and run your app</span></span>

1. <span data-ttu-id="56408-130">Убедитесь, что приложение опубликовано, а код приложения не использует `SparkSession.Stop()`.</span><span class="sxs-lookup"><span data-stu-id="56408-130">Ensure you have published your app, and that your application code does not use `SparkSession.Stop()`.</span></span>

2. <span data-ttu-id="56408-131">Чтобы передать приложение в кластер Databricks, используйте [Databricks CLI](https://docs.microsoft.com/azure/databricks/dev-tools/databricks-cli).</span><span class="sxs-lookup"><span data-stu-id="56408-131">Use [Databricks CLI](https://docs.microsoft.com/azure/databricks/dev-tools/databricks-cli) to upload your application to your Databricks cluster.</span></span> <span data-ttu-id="56408-132">Например, следующая команда отправляет опубликованное приложение в ваш кластер.</span><span class="sxs-lookup"><span data-stu-id="56408-132">For example, use the following command to upload your published app to your cluster:</span></span>

    ```console
    cd <path-to-your-app-publish-directory>
    databricks fs cp <your-app-name>.zip dbfs:/apps/<your-app-name>.zip
    ```

3. <span data-ttu-id="56408-133">Если в приложении есть определяемые пользователем функции, сборки приложения (например, библиотеки DLL, содержащие определяемые пользователем функции и их зависимости) необходимо поместить в рабочий каталог каждой роли *Microsoft.Spark.Worker*.</span><span class="sxs-lookup"><span data-stu-id="56408-133">If you have any user-defined functions in your app, the app assemblies, such as DLLs that contain user-defined functions along with their dependencies, need to be placed in the working directory of each *Microsoft.Spark.Worker*.</span></span>

    <span data-ttu-id="56408-134">Отправка сборок приложения в кластер Databricks.</span><span class="sxs-lookup"><span data-stu-id="56408-134">Upload your application assemblies to your Databricks cluster:</span></span>

    ```console
    cd <path-to-your-app-publish-directory>
    databricks fs cp <assembly>.dll dbfs:/apps/dependencies
    ```

    <span data-ttu-id="56408-135">Раскомментируйте и измените раздел зависимостей приложения в файле [db-init.sh](https://github.com/dotnet/spark/blob/master/deployment/db-init.sh), указав путь к зависимостям приложения.</span><span class="sxs-lookup"><span data-stu-id="56408-135">Uncomment and modify the app dependencies section in [db-init.sh](https://github.com/dotnet/spark/blob/master/deployment/db-init.sh) to point to your app dependencies path.</span></span> <span data-ttu-id="56408-136">После этого отправьте обновленный файл *db-init.sh* в кластер:</span><span class="sxs-lookup"><span data-stu-id="56408-136">Then, upload the updated *db-init.sh* to your cluster:</span></span>

    ```console
    cd <path-to-db-init-and-install-worker>
    databricks fs cp db-init.sh dbfs:/spark-dotnet/db-init.sh
    ```

4. <span data-ttu-id="56408-137">Чтобы запустить задание, последовательно выберите **Кластер Databricks > Задания > [имя_задания] > Запустить сейчас**.</span><span class="sxs-lookup"><span data-stu-id="56408-137">Navigate to **Databricks cluster > Jobs > [Job-name] > Run Now** to run your job.</span></span>

## <a name="next-steps"></a><span data-ttu-id="56408-138">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="56408-138">Next steps</span></span>

* [<span data-ttu-id="56408-139">Начало работы с .NET для Apache Spark</span><span class="sxs-lookup"><span data-stu-id="56408-139">Get started with .NET for Apache Spark</span></span>](../tutorials/get-started.md)
* [<span data-ttu-id="56408-140">Развертывание приложения .NET для Apache Spark в Databricks</span><span class="sxs-lookup"><span data-stu-id="56408-140">Deploy a .NET for Apache Spark application to Databricks</span></span>](../tutorials/databricks-deployment.md)
* [<span data-ttu-id="56408-141">Документация по Azure Databricks</span><span class="sxs-lookup"><span data-stu-id="56408-141">Azure Databricks Documentation</span></span>](https://docs.microsoft.com/azure/azure-databricks/)
