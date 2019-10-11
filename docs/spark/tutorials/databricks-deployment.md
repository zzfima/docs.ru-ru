---
title: Развертывание приложения .NET для Apache Spark в Databricks
description: Узнайте, как развернуть приложение .NET для Apache Spark в Databricks.
ms.date: 05/17/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 035a3c36337413153ee0370aec154d48b84a4711
ms.sourcegitcommit: 7bfe1682d9368cf88d43e895d1e80ba2d88c3a99
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2019
ms.locfileid: "71957251"
---
# <a name="deploy-a-net-for-apache-spark-application-to-databricks"></a><span data-ttu-id="10b0e-103">Развертывание приложения .NET для Apache Spark в Databricks</span><span class="sxs-lookup"><span data-stu-id="10b0e-103">Deploy a .NET for Apache Spark application to Databricks</span></span>

<span data-ttu-id="10b0e-104">В этом руководстве рассматривается развертывание приложения .NET для Apache Spark в Databricks.</span><span class="sxs-lookup"><span data-stu-id="10b0e-104">This tutorial teaches how to deploy a .NET for Apache Spark application to Databricks.</span></span>

<span data-ttu-id="10b0e-105">В этом руководстве вы узнаете, как:</span><span class="sxs-lookup"><span data-stu-id="10b0e-105">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="10b0e-106">Подготовка Microsoft.Spark.Worker</span><span class="sxs-lookup"><span data-stu-id="10b0e-106">Prepare Microsoft.Spark.Worker</span></span>
> - <span data-ttu-id="10b0e-107">Публикация приложения Spark .NET</span><span class="sxs-lookup"><span data-stu-id="10b0e-107">Publish your Spark .NET app</span></span>
> - <span data-ttu-id="10b0e-108">Развертывание приложения в Databricks</span><span class="sxs-lookup"><span data-stu-id="10b0e-108">Deploy your app to Databricks</span></span>
> - <span data-ttu-id="10b0e-109">Запуск приложения</span><span class="sxs-lookup"><span data-stu-id="10b0e-109">Run your app</span></span>

## <a name="prerequisites"></a><span data-ttu-id="10b0e-110">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="10b0e-110">Prerequisites</span></span>

<span data-ttu-id="10b0e-111">Прежде чем начать, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="10b0e-111">Before you start, do the following:</span></span>

- <span data-ttu-id="10b0e-112">Скачайте [интерфейс командной строки Databricks](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html).</span><span class="sxs-lookup"><span data-stu-id="10b0e-112">Download the [Databricks CLI](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html).</span></span>
- <span data-ttu-id="10b0e-113">Скачайте файл [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) на локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="10b0e-113">Download [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) to your local machine.</span></span> <span data-ttu-id="10b0e-114">Это вспомогательный скрипт, который будет использоваться позже для копирования зависимых файлов .NET для Apache Spark в рабочие узлы кластера Spark.</span><span class="sxs-lookup"><span data-stu-id="10b0e-114">This is a helper script that you use later to copy .NET for Apache Spark dependent files into your Spark cluster's worker nodes.</span></span>

## <a name="prepare-worker-dependencies"></a><span data-ttu-id="10b0e-115">Подготовка зависимостей рабочей роли</span><span class="sxs-lookup"><span data-stu-id="10b0e-115">Prepare worker dependencies</span></span>

<span data-ttu-id="10b0e-116">**Microsoft.Spark.Worker** — это серверный компонент, который размещается в отдельных рабочих узлах кластера Spark.</span><span class="sxs-lookup"><span data-stu-id="10b0e-116">**Microsoft.Spark.Worker** is a back-end component that lives on the individual worker nodes of your Spark cluster.</span></span> <span data-ttu-id="10b0e-117">Если вам нужно выполнить определяемую пользователем функцию C#, Spark необходимо знать, как запустить среду CLR .NET для выполнения этой функции.</span><span class="sxs-lookup"><span data-stu-id="10b0e-117">When you want to execute a C# UDF (user-defined function), Spark needs to understand how to launch the .NET CLR to execute the UDF.</span></span> <span data-ttu-id="10b0e-118">**Microsoft.Spark.Worker** предоставляет Spark коллекцию классов, которые обеспечивают такую возможность.</span><span class="sxs-lookup"><span data-stu-id="10b0e-118">**Microsoft.Spark.Worker** provides a collection of classes to Spark that enable this functionality.</span></span>

1. <span data-ttu-id="10b0e-119">Выберите выпуск netcoreapp компонента [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) для Linux, который будет развернут в кластере.</span><span class="sxs-lookup"><span data-stu-id="10b0e-119">Select a [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) Linux netcoreapp release to be deployed on your cluster.</span></span>

   <span data-ttu-id="10b0e-120">Например, чтобы использовать `.NET for Apache Spark v0.1.0` с `netcoreapp2.1`, скачайте выпуск [Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz](https://github.com/dotnet/spark/releases/download/v0.1.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz).</span><span class="sxs-lookup"><span data-stu-id="10b0e-120">For example, if you want `.NET for Apache Spark v0.1.0` using `netcoreapp2.1`, you'd download [Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz](https://github.com/dotnet/spark/releases/download/v0.1.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz).</span></span>

2. <span data-ttu-id="10b0e-121">Передайте файлы `Microsoft.Spark.Worker.<release>.tar.gz` и [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) в распределенную файловую систему (например, DBFS), к которой есть доступ у кластера.</span><span class="sxs-lookup"><span data-stu-id="10b0e-121">Upload `Microsoft.Spark.Worker.<release>.tar.gz` and [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) to a distributed file system (for example, DBFS) that your cluster has access to.</span></span>

## <a name="prepare-your-net-for-apache-spark-app"></a><span data-ttu-id="10b0e-122">Подготовка приложения .NET для Apache Spark</span><span class="sxs-lookup"><span data-stu-id="10b0e-122">Prepare your .NET for Apache Spark app</span></span>

1. <span data-ttu-id="10b0e-123">Выполните сборку приложения согласно инструкциям из [руководства по началу работы](get-started.md).</span><span class="sxs-lookup"><span data-stu-id="10b0e-123">Follow the [Get Started](get-started.md) tutorial to build your app.</span></span>

2. <span data-ttu-id="10b0e-124">Опубликуйте приложение .NET для Spark как автономное.</span><span class="sxs-lookup"><span data-stu-id="10b0e-124">Publish your Spark .NET app as self-contained.</span></span>

   <span data-ttu-id="10b0e-125">В Linux можно выполнить приведенную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="10b0e-125">You can run the following command on Linux.</span></span>

   ```dotnetcli
   dotnet publish -c Release -f netcoreapp2.1 -r ubuntu.16.04-x64
   ```

3. <span data-ttu-id="10b0e-126">Создайте `<your app>.zip` для опубликованных файлов.</span><span class="sxs-lookup"><span data-stu-id="10b0e-126">Produce `<your app>.zip` for the published files.</span></span>

   <span data-ttu-id="10b0e-127">В Linux можно выполнить приведенную ниже команду с помощью `zip`.</span><span class="sxs-lookup"><span data-stu-id="10b0e-127">You can run the following command on Linux using `zip`.</span></span>

   ```bash
   zip -r <your app>.zip .
   ```

4. <span data-ttu-id="10b0e-128">Передайте в распределенную файловую систему (например, DBFS), к которой есть доступ у кластера, следующие файлы:</span><span class="sxs-lookup"><span data-stu-id="10b0e-128">Upload the following to a distributed file system (for example, DBFS) that your cluster has access to:</span></span>

   - <span data-ttu-id="10b0e-129">`microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar`. Этот JAR-файл входит в состав пакета NuGet [Microsoft.Spark](https://www.nuget.org/packages/Microsoft.Spark/) и размещается в выходном каталоге сборки приложения.</span><span class="sxs-lookup"><span data-stu-id="10b0e-129">`microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar`: This jar is included as part of the [Microsoft.Spark](https://www.nuget.org/packages/Microsoft.Spark/) NuGet package and is colocated in your app's build output directory.</span></span>
   - `<your app>.zip`
   - <span data-ttu-id="10b0e-130">Файлы (например, файлы зависимостей или общие данные, доступные каждой рабочей роли) или сборки (например, библиотеки DLL, содержащие определяемые пользователем функции, или библиотеки, от которых зависит приложение), которые необходимо поместить в рабочий каталог каждого исполнителя.</span><span class="sxs-lookup"><span data-stu-id="10b0e-130">Files (like dependency files or common data accessible to every worker) or assemblies (like DLLs that contain your user-defined functions or libraries that your app depends on) to be placed in the working directory of each executor.</span></span>

## <a name="deploy-to-databricks"></a><span data-ttu-id="10b0e-131">Развертывание в Databricks</span><span class="sxs-lookup"><span data-stu-id="10b0e-131">Deploy to Databricks</span></span>

<span data-ttu-id="10b0e-132">[Databricks](https://databricks.com) — это платформа, которая обеспечивает обработку больших данных в облаке с помощью Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="10b0e-132">[Databricks](https://databricks.com) is a platform that provides cloud-based big data processing using Apache Spark.</span></span>

> [!Note] 
> <span data-ttu-id="10b0e-133">[Azure Databricks](https://azure.microsoft.com/services/databricks/) и [AWS Databricks](https://databricks.com/aws) работают под управлением Linux.</span><span class="sxs-lookup"><span data-stu-id="10b0e-133">[Azure Databricks](https://azure.microsoft.com/services/databricks/) and [AWS Databricks](https://databricks.com/aws) are Linux-based.</span></span> <span data-ttu-id="10b0e-134">Поэтому если вы хотите развернуть приложение в Databricks, оно должно быть совместимо с .NET Standard, а для его компиляции необходимо использовать [компилятор .NET Core](https://dotnet.microsoft.com/download).</span><span class="sxs-lookup"><span data-stu-id="10b0e-134">Therefore, if you are interested in deploying your app to Databricks, make sure your app is .NET Standard compatible and that you use [.NET Core compiler](https://dotnet.microsoft.com/download) to compile your app.</span></span>

<span data-ttu-id="10b0e-135">Databricks позволяет отправлять приложения .NET для Apache Spark в существующий активный кластер или создавать новый кластер при каждом запуске задания.</span><span class="sxs-lookup"><span data-stu-id="10b0e-135">Databricks allows you to submit .NET for Apache Spark apps to an existing active cluster or create a new cluster every time you launch a job.</span></span> <span data-ttu-id="10b0e-136">Перед отправкой приложения .NET для Apache Spark требуется установить **Microsoft.Spark.Worker**.</span><span class="sxs-lookup"><span data-stu-id="10b0e-136">This requires the **Microsoft.Spark.Worker** to be installed before you submit a .NET for Apache Spark app.</span></span>

### <a name="deploy-microsoftsparkworker"></a><span data-ttu-id="10b0e-137">Развертывание Microsoft.Spark.Worker</span><span class="sxs-lookup"><span data-stu-id="10b0e-137">Deploy Microsoft.Spark.Worker</span></span>

<span data-ttu-id="10b0e-138">Этот шаг необходимо выполнить для кластера только один раз.</span><span class="sxs-lookup"><span data-stu-id="10b0e-138">This step is only required once for a cluster.</span></span>

1. <span data-ttu-id="10b0e-139">Скачайте файлы [db-init.sh](https://github.com/dotnet/spark/blob/master/deployment/db-init.sh) и [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh
) на локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="10b0e-139">Download [db-init.sh](https://github.com/dotnet/spark/blob/master/deployment/db-init.sh) and [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh
) onto your local machine.</span></span>

2. <span data-ttu-id="10b0e-140">Измените файл **db-init.sh** так, чтобы он указывал на выпуск **Microsoft.Spark.Worker**, который вы хотите скачать и установить в кластере.</span><span class="sxs-lookup"><span data-stu-id="10b0e-140">Modify **db-init.sh** to point to the **Microsoft.Spark.Worker** release you want to download and install on your cluster.</span></span>

3. <span data-ttu-id="10b0e-141">Установите [интерфейс командной строки Databricks](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html).</span><span class="sxs-lookup"><span data-stu-id="10b0e-141">Install the [Databricks CLI](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html).</span></span>

4. <span data-ttu-id="10b0e-142">[Настройте сведения о проверке подлинности](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html#set-up-authentication) для интерфейса командной строки Databricks.</span><span class="sxs-lookup"><span data-stu-id="10b0e-142">[Setup authentication](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html#set-up-authentication) details for the Databricks CLI.</span></span>

5. <span data-ttu-id="10b0e-143">Отправьте файлы в кластер Databricks с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="10b0e-143">Upload the files to your Databricks cluster using the following command:</span></span>

   ```bash
   cd <path-to-db-init-and-install-worker>
   databricks fs cp db-init.sh dbfs:/spark-dotnet/db-init.sh
   databricks fs cp install-worker.sh dbfs:/spark-dotnet/install-worker.sh
   ```

6. <span data-ttu-id="10b0e-144">Перейдите к рабочей области Databricks.</span><span class="sxs-lookup"><span data-stu-id="10b0e-144">Go to your Databricks workspace.</span></span> <span data-ttu-id="10b0e-145">В меню слева выберите **Кластеры**, а затем выберите **Создать кластер**.</span><span class="sxs-lookup"><span data-stu-id="10b0e-145">Select **Clusters** from the left-side menu, and then select **Create Cluster**.</span></span>

7. <span data-ttu-id="10b0e-146">Настроив кластер нужным образом, укажите **скрипт инициализации** и создайте кластер.</span><span class="sxs-lookup"><span data-stu-id="10b0e-146">After configuring the cluster appropriately, set the **Init Script** and create the cluster.</span></span>

   ![Изображение действия скрипта](./media/databricks-deployment/deployment-databricks-init-script.png)

## <a name="run-your-app"></a><span data-ttu-id="10b0e-148">Запуск приложения</span><span class="sxs-lookup"><span data-stu-id="10b0e-148">Run your app</span></span> 

<span data-ttu-id="10b0e-149">Для отправки задания в Databricks можно использовать `set JAR` или `spark-submit`.</span><span class="sxs-lookup"><span data-stu-id="10b0e-149">You can use `set JAR` or `spark-submit` to submit your job to Databricks.</span></span>

### <a name="use-set-jar"></a><span data-ttu-id="10b0e-150">Использование действия "Указание файла JAR"</span><span class="sxs-lookup"><span data-stu-id="10b0e-150">Use Set JAR</span></span>

<span data-ttu-id="10b0e-151">Действие [Указание файла JAR](https://docs.databricks.com/user-guide/jobs.html#create-a-job) позволяет отправить задание в существующий активный кластер.</span><span class="sxs-lookup"><span data-stu-id="10b0e-151">[Set JAR](https://docs.databricks.com/user-guide/jobs.html#create-a-job) allows you to submit a job to an existing active cluster.</span></span>

#### <a name="one-time-setup"></a><span data-ttu-id="10b0e-152">Однократная настройка</span><span class="sxs-lookup"><span data-stu-id="10b0e-152">One-time setup</span></span>

1. <span data-ttu-id="10b0e-153">Перейдите в кластер Databricks и в меню слева выберите **Задания**.</span><span class="sxs-lookup"><span data-stu-id="10b0e-153">Go to your Databricks cluster and select **Jobs** from the left-side menu.</span></span> <span data-ttu-id="10b0e-154">Затем выберите действие **Указание файла JAR**.</span><span class="sxs-lookup"><span data-stu-id="10b0e-154">Then select **Set JAR**.</span></span>

2. <span data-ttu-id="10b0e-155">Отправьте соответствующий файл `microsoft-spark-<spark-version>-<spark-dotnet-version>.jar`.</span><span class="sxs-lookup"><span data-stu-id="10b0e-155">Upload the appropriate `microsoft-spark-<spark-version>-<spark-dotnet-version>.jar` file.</span></span>

3. <span data-ttu-id="10b0e-156">Задайте необходимые параметры.</span><span class="sxs-lookup"><span data-stu-id="10b0e-156">Set the parameters appropriately.</span></span>

   | <span data-ttu-id="10b0e-157">Параметр</span><span class="sxs-lookup"><span data-stu-id="10b0e-157">Parameter</span></span>   | <span data-ttu-id="10b0e-158">Значение</span><span class="sxs-lookup"><span data-stu-id="10b0e-158">Value</span></span>                                                |
   |-------------|------------------------------------------------------|
   | <span data-ttu-id="10b0e-159">Основной класс</span><span class="sxs-lookup"><span data-stu-id="10b0e-159">Main Class</span></span>  | <span data-ttu-id="10b0e-160">org.apache.spark.deploy.dotnet.DotnetRunner</span><span class="sxs-lookup"><span data-stu-id="10b0e-160">org.apache.spark.deploy.dotnet.DotnetRunner</span></span>          |
   | <span data-ttu-id="10b0e-161">Аргументы</span><span class="sxs-lookup"><span data-stu-id="10b0e-161">Arguments</span></span>   | <span data-ttu-id="10b0e-162">/dbfs/apps/<your-app-name>.zip <your-app-main-class></span><span class="sxs-lookup"><span data-stu-id="10b0e-162">/dbfs/apps/<your-app-name>.zip <your-app-main-class></span></span> |

4. <span data-ttu-id="10b0e-163">Настройте параметр **Кластер** так, чтобы он указывал на существующий кластер, для которого в предыдущем разделе был создан **скрипт инициализации**.</span><span class="sxs-lookup"><span data-stu-id="10b0e-163">Configure the **Cluster** to point to the existing cluster you created the **Init Script** for in the previous section.</span></span>

#### <a name="publish-and-run-your-app"></a><span data-ttu-id="10b0e-164">Публикация и запуск приложения</span><span class="sxs-lookup"><span data-stu-id="10b0e-164">Publish and run your app</span></span>

1. <span data-ttu-id="10b0e-165">Чтобы передать приложение в кластер Databricks, используйте [интерфейс командной строки Databricks](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html).</span><span class="sxs-lookup"><span data-stu-id="10b0e-165">Use the [Databricks CLI](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html) to upload your application to your Databricks cluster.</span></span>

      ```bash
      cd <path-to-your-app-publish-directory>
      databricks fs cp <your-app-name>.zip dbfs:/apps/<your-app-name>.zip
      ```

2. <span data-ttu-id="10b0e-166">Этот шаг требуется, только если сборки приложения (например, библиотеки DLL, содержащие определяемые пользователем функции, и их зависимости) необходимо поместить в рабочий каталог каждой роли **Microsoft.Spark.Worker**.</span><span class="sxs-lookup"><span data-stu-id="10b0e-166">This step is only required if your app assemblies (for example, DLLs that contain user-defined functions along with their dependencies) need to be placed in the working directory of each **Microsoft.Spark.Worker**.</span></span>

   - <span data-ttu-id="10b0e-167">Передача сборок приложения в кластер Databricks</span><span class="sxs-lookup"><span data-stu-id="10b0e-167">Upload your application assemblies to your Databricks cluster</span></span>
      
      ```bash
      cd <path-to-your-app-publish-directory>
      databricks fs cp <assembly>.dll dbfs:/apps/dependencies
      ```

   - <span data-ttu-id="10b0e-168">Раскомментируйте и измените раздел зависимостей приложения в файле [db-init.sh](https://github.com/dotnet/spark/blob/master/deployment/db-init.sh), указав путь к зависимостям приложения, а затем передайте этот файл в кластер Databricks.</span><span class="sxs-lookup"><span data-stu-id="10b0e-168">Uncomment and modify the app dependencies section in [db-init.sh](https://github.com/dotnet/spark/blob/master/deployment/db-init.sh) to point to your app dependencies path and upload to your Databricks cluster.</span></span>
   
      ```bash
      cd <path-to-db-init-and-install-worker>
      databricks fs cp db-init.sh dbfs:/spark-dotnet/db-init.sh
      ```
   
   - <span data-ttu-id="10b0e-169">Перезапустите кластер.</span><span class="sxs-lookup"><span data-stu-id="10b0e-169">Restart your cluster.</span></span>

3. <span data-ttu-id="10b0e-170">Перейдите в кластер Databricks в рабочей области Databricks.</span><span class="sxs-lookup"><span data-stu-id="10b0e-170">Go to your Databricks cluster in your Databricks workspace.</span></span> <span data-ttu-id="10b0e-171">В разделе **Задания** выберите задание, а затем щелкните **Запустить сейчас**, чтобы выполнить его.</span><span class="sxs-lookup"><span data-stu-id="10b0e-171">Under **Jobs**, select your job and then select **Run Now** to run your job.</span></span>

### <a name="use-spark-submit"></a><span data-ttu-id="10b0e-172">Использование команды spark-submit</span><span class="sxs-lookup"><span data-stu-id="10b0e-172">Use spark-submit</span></span>

<span data-ttu-id="10b0e-173">Команда [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) позволяет отправить задание в новый кластер.</span><span class="sxs-lookup"><span data-stu-id="10b0e-173">The [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) command allows you to submit a job to a new cluster.</span></span>

1. <span data-ttu-id="10b0e-174">[Создайте задание](https://docs.databricks.com/user-guide/jobs.html) и выберите **Настройка spark-submit**.</span><span class="sxs-lookup"><span data-stu-id="10b0e-174">[Create a Job](https://docs.databricks.com/user-guide/jobs.html) and select **Configure spark-submit**.</span></span>

2. <span data-ttu-id="10b0e-175">Настройте команду `spark-submit` со следующими параметрами:</span><span class="sxs-lookup"><span data-stu-id="10b0e-175">Configure `spark-submit` with the following parameters:</span></span>

      ```bash
      ["--files","/dbfs/<path-to>/<app assembly/file to deploy to worker>","--class","org.apache.spark.deploy.dotnet.DotnetRunner","/dbfs/<path-to>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar","/dbfs/<path-to>/<app name>.zip","<app bin name>","app arg1","app arg2"]
      ```

3. <span data-ttu-id="10b0e-176">Перейдите в кластер Databricks в рабочей области Databricks.</span><span class="sxs-lookup"><span data-stu-id="10b0e-176">Go to your Databricks cluster in your Databricks workspace.</span></span> <span data-ttu-id="10b0e-177">В разделе **Задания** выберите задание, а затем щелкните **Запустить сейчас**, чтобы выполнить его.</span><span class="sxs-lookup"><span data-stu-id="10b0e-177">Under **Jobs**, select your job and then select **Run Now** to run your job.</span></span>

## <a name="next-steps"></a><span data-ttu-id="10b0e-178">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="10b0e-178">Next steps</span></span>

<span data-ttu-id="10b0e-179">В этом руководстве вы развернули приложение .NET для Apache Spark в Databricks.</span><span class="sxs-lookup"><span data-stu-id="10b0e-179">In this tutorial, you deployed your .NET for Apache Spark application to Databricks.</span></span> <span data-ttu-id="10b0e-180">Дополнительные сведения о Databricks см. в документации по Azure Databricks.</span><span class="sxs-lookup"><span data-stu-id="10b0e-180">To learn more about Databricks, continue to the Azure Databricks Documentation.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="10b0e-181">Документация по Azure Databricks</span><span class="sxs-lookup"><span data-stu-id="10b0e-181">Azure Databricks Documentation</span></span>](https://docs.microsoft.com/azure/azure-databricks/)
