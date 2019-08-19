---
title: Развертывание .NET для Apache Spark приложения в модулях
description: Узнайте, как развернуть .NET для приложения Apache Spark в модулях.
ms.date: 05/17/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: ca9e93a413622c84325ca9fc8bac17268b990c5a
ms.sourcegitcommit: 127343afce8422bfa944c8b0c4ecc8f79f653255
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/25/2019
ms.locfileid: "69576971"
---
# <a name="deploy-a-net-for-apache-spark-application-to-databricks"></a><span data-ttu-id="319d8-103">Развертывание .NET для Apache Spark приложения в модулях</span><span class="sxs-lookup"><span data-stu-id="319d8-103">Deploy a .NET for Apache Spark application to Databricks</span></span>

<span data-ttu-id="319d8-104">В этом учебнике описывается развертывание приложения .NET для Apache Spark в модулях.</span><span class="sxs-lookup"><span data-stu-id="319d8-104">This tutorial teaches how to deploy a .NET for Apache Spark application to Databricks.</span></span>

<span data-ttu-id="319d8-105">В этом руководстве вы узнаете, как:</span><span class="sxs-lookup"><span data-stu-id="319d8-105">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="319d8-106">Подготовка Microsoft. Spark. Worker</span><span class="sxs-lookup"><span data-stu-id="319d8-106">Prepare Microsoft.Spark.Worker</span></span>
> * <span data-ttu-id="319d8-107">Публикация приложения Spark .NET</span><span class="sxs-lookup"><span data-stu-id="319d8-107">Publish your Spark .NET app</span></span>
> * <span data-ttu-id="319d8-108">Развертывание приложения в модулях</span><span class="sxs-lookup"><span data-stu-id="319d8-108">Deploy your app to Databricks</span></span>
> * <span data-ttu-id="319d8-109">Запуск приложения</span><span class="sxs-lookup"><span data-stu-id="319d8-109">Run your app</span></span>

## <a name="prerequisites"></a><span data-ttu-id="319d8-110">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="319d8-110">Prerequisites</span></span>

<span data-ttu-id="319d8-111">Прежде чем начать, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="319d8-111">Before you start, do the following:</span></span>

* <span data-ttu-id="319d8-112">Скачайте интерфейс [командной строки для модуля](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html).</span><span class="sxs-lookup"><span data-stu-id="319d8-112">Download the [Databricks CLI](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html).</span></span>
* <span data-ttu-id="319d8-113">Скачайте [Install-Worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) на локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="319d8-113">Download [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) to your local machine.</span></span> <span data-ttu-id="319d8-114">Это вспомогательный скрипт, который используется позже для копирования .NET для Apache Spark зависимых файлов в рабочие узлы кластера Spark.</span><span class="sxs-lookup"><span data-stu-id="319d8-114">This is a helper script that you use later to copy .NET for Apache Spark dependent files into your Spark cluster's worker nodes.</span></span>

## <a name="prepare-worker-dependencies"></a><span data-ttu-id="319d8-115">Подготовка зависимостей рабочей роли</span><span class="sxs-lookup"><span data-stu-id="319d8-115">Prepare worker dependencies</span></span>

<span data-ttu-id="319d8-116">**Microsoft. Spark. Worker** — это компонент серверной части, который находится на отдельных рабочих узлах кластера Spark.</span><span class="sxs-lookup"><span data-stu-id="319d8-116">**Microsoft.Spark.Worker** is a back-end component that lives on the individual worker nodes of your Spark cluster.</span></span> <span data-ttu-id="319d8-117">Если вы хотите выполнить определяемую C# пользователем функцию (UDF), Spark необходимо понять, как запустить среду CLR .NET для выполнения пользовательской функции.</span><span class="sxs-lookup"><span data-stu-id="319d8-117">When you want to execute a C# UDF (user-defined function), Spark needs to understand how to launch the .NET CLR to execute the UDF.</span></span> <span data-ttu-id="319d8-118">**Microsoft. Spark. Worker** предоставляет коллекцию классов для Spark, которые обеспечивают эту функциональность.</span><span class="sxs-lookup"><span data-stu-id="319d8-118">**Microsoft.Spark.Worker** provides a collection of classes to Spark that enable this functionality.</span></span>

1. <span data-ttu-id="319d8-119">Выберите выпуск [Microsoft. Spark. Worker](https://github.com/dotnet/spark/releases) Linux netcoreapp, который будет развернут в кластере.</span><span class="sxs-lookup"><span data-stu-id="319d8-119">Select a [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) Linux netcoreapp release to be deployed on your cluster.</span></span>

   <span data-ttu-id="319d8-120">Например, если вы хотите `.NET for Apache Spark v0.1.0` использовать `netcoreapp2.1`, скачайте [Microsoft. Spark. Worker. netcoreapp 2.1. Linux-x64-0.1.0. tar. gz](https://github.com/dotnet/spark/releases/download/v0.1.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz).</span><span class="sxs-lookup"><span data-stu-id="319d8-120">For example, if you want `.NET for Apache Spark v0.1.0` using `netcoreapp2.1`, you'd download [Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz](https://github.com/dotnet/spark/releases/download/v0.1.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz).</span></span>

2. <span data-ttu-id="319d8-121">Отправляйте `Microsoft.Spark.Worker.<release>.tar.gz` и [Install-Worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) в распределенную файловую систему (например, DBFS), к которой имеет доступ кластер.</span><span class="sxs-lookup"><span data-stu-id="319d8-121">Upload `Microsoft.Spark.Worker.<release>.tar.gz` and [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) to a distributed file system (for example, DBFS) that your cluster has access to.</span></span>

## <a name="prepare-your-net-for-apache-spark-app"></a><span data-ttu-id="319d8-122">Подготовка .NET для приложения Apache Spark</span><span class="sxs-lookup"><span data-stu-id="319d8-122">Prepare your .NET for Apache Spark app</span></span>

1. <span data-ttu-id="319d8-123">Выполните инструкции из руководства по [началу работы](get-started.md) , чтобы создать приложение.</span><span class="sxs-lookup"><span data-stu-id="319d8-123">Follow the [Get Started](get-started.md) tutorial to build your app.</span></span>

2. <span data-ttu-id="319d8-124">Опубликуйте свое приложение Spark .NET как автономное.</span><span class="sxs-lookup"><span data-stu-id="319d8-124">Publish your Spark .NET app as self-contained.</span></span>

   <span data-ttu-id="319d8-125">В Linux можно выполнить следующую команду.</span><span class="sxs-lookup"><span data-stu-id="319d8-125">You can run the following command on Linux.</span></span>

   ```bash
   dotnet publish -c Release -f netcoreapp2.1 -r ubuntu.16.04-x64
   ```

3. <span data-ttu-id="319d8-126">Создание `<your app>.zip` для опубликованных файлов.</span><span class="sxs-lookup"><span data-stu-id="319d8-126">Produce `<your app>.zip` for the published files.</span></span>

   <span data-ttu-id="319d8-127">Вы можете выполнить следующую команду в Linux с помощью `zip`команды.</span><span class="sxs-lookup"><span data-stu-id="319d8-127">You can run the following command on Linux using `zip`.</span></span>

   ```bash
   zip -r <your app>.zip .
   ```

4. <span data-ttu-id="319d8-128">Отправьте следующее в распределенную файловую систему (например, DBFS), к которой имеет доступ кластер:</span><span class="sxs-lookup"><span data-stu-id="319d8-128">Upload the following to a distributed file system (for example, DBFS) that your cluster has access to:</span></span>

   * <span data-ttu-id="319d8-129">`microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar`: Этот JAR-файл входит в состав пакета NuGet [Microsoft. Spark](https://www.nuget.org/packages/Microsoft.Spark/) и размещается в выходном каталоге сборки приложения.</span><span class="sxs-lookup"><span data-stu-id="319d8-129">`microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar`: This jar is included as part of the [Microsoft.Spark](https://www.nuget.org/packages/Microsoft.Spark/) NuGet package and is colocated in your app's build output directory.</span></span>
   * `<your app>.zip`
   * <span data-ttu-id="319d8-130">Файлы (например, файлы зависимостей или общие данные, доступные каждому рабочему процессу) или сборки (например, библиотеки DLL, содержащие определяемые пользователем функции или библиотеки, от которых зависит ваше приложение) должны размещаться в рабочем каталоге каждого исполнителя.</span><span class="sxs-lookup"><span data-stu-id="319d8-130">Files (like dependency files or common data accessible to every worker) or assemblies (like DLLs that contain your user-defined functions or libraries that your app depends on) to be placed in the working directory of each executor.</span></span>

## <a name="deploy-to-databricks"></a><span data-ttu-id="319d8-131">Развертывание в Databricks</span><span class="sxs-lookup"><span data-stu-id="319d8-131">Deploy to Databricks</span></span>

<span data-ttu-id="319d8-132">[Модуль](https://databricks.com) обработки данных — это платформа, которая предоставляет облачные данные, основанные на больших объемах, с помощью Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="319d8-132">[Databricks](https://databricks.com) is a platform that provides cloud-based big data processing using Apache Spark.</span></span>

> [!Note] 
> <span data-ttu-id="319d8-133">Модуль данных [Azure Databricks](https://azure.microsoft.com/services/databricks/) и [AWS](https://databricks.com/aws) основаны на Linux.</span><span class="sxs-lookup"><span data-stu-id="319d8-133">[Azure Databricks](https://azure.microsoft.com/services/databricks/) and [AWS Databricks](https://databricks.com/aws) are Linux-based.</span></span> <span data-ttu-id="319d8-134">Поэтому, если вы заинтересованы в развертывании приложения в модулях, убедитесь, что приложение совместимо .NET Standard и вы используете [компилятор .NET Core](https://dotnet.microsoft.com/download) для компиляции приложения.</span><span class="sxs-lookup"><span data-stu-id="319d8-134">Therefore, if you are interested in deploying your app to Databricks, make sure your app is .NET Standard compatible and that you use [.NET Core compiler](https://dotnet.microsoft.com/download) to compile your app.</span></span>

<span data-ttu-id="319d8-135">Кирпичы позволяют отправлять .NET для Apache Spark приложений в существующий активный кластер или создавать новый кластер при каждом запуске задания.</span><span class="sxs-lookup"><span data-stu-id="319d8-135">Databricks allows you to submit .NET for Apache Spark apps to an existing active cluster or create a new cluster every time you launch a job.</span></span> <span data-ttu-id="319d8-136">Для этого требуется установить **Microsoft. Spark. Worker** перед отправкой приложения .net для Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="319d8-136">This requires the **Microsoft.Spark.Worker** to be installed before you submit a .NET for Apache Spark app.</span></span>

### <a name="deploy-microsoftsparkworker"></a><span data-ttu-id="319d8-137">Развертывание Microsoft. Spark. Worker</span><span class="sxs-lookup"><span data-stu-id="319d8-137">Deploy Microsoft.Spark.Worker</span></span>

<span data-ttu-id="319d8-138">Этот шаг требуется только один раз для кластера.</span><span class="sxs-lookup"><span data-stu-id="319d8-138">This step is only required once for a cluster.</span></span>

1. <span data-ttu-id="319d8-139">Скачайте [DB-init.sh](https://github.com/dotnet/spark/blob/master/deployment/db-init.sh) и [Install-Worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh
) на локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="319d8-139">Download [db-init.sh](https://github.com/dotnet/spark/blob/master/deployment/db-init.sh) and [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh
) onto your local machine.</span></span>

2. <span data-ttu-id="319d8-140">Измените **DB-init.sh** , чтобы он указывал на выпуск **Microsoft. Spark. Worker** , который вы хотите скачать и установить в кластере.</span><span class="sxs-lookup"><span data-stu-id="319d8-140">Modify **db-init.sh** to point to the **Microsoft.Spark.Worker** release you want to download and install on your cluster.</span></span>

3. <span data-ttu-id="319d8-141">Установите интерфейс [командной строки для модуля](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html)установки.</span><span class="sxs-lookup"><span data-stu-id="319d8-141">Install the [Databricks CLI](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html).</span></span>

4. <span data-ttu-id="319d8-142">[Настройте](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html#set-up-authentication) сведения о проверке подлинности для интерфейса командной строки для модуля данных.</span><span class="sxs-lookup"><span data-stu-id="319d8-142">[Setup authentication](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html#set-up-authentication) details for the Databricks CLI.</span></span>

5. <span data-ttu-id="319d8-143">Отправьте файлы в кластер "кирпичы" с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="319d8-143">Upload the files to your Databricks cluster using the following command:</span></span>

   ```bash
   cd <path-to-db-init-and-install-worker>
   databricks fs cp db-init.sh dbfs:/spark-dotnet/db-init.sh
   databricks fs cp install-worker.sh dbfs:/spark-dotnet/install-worker.sh
   ```

6. <span data-ttu-id="319d8-144">Перейдите в рабочую область "кирпичы".</span><span class="sxs-lookup"><span data-stu-id="319d8-144">Go to your Databricks workspace.</span></span> <span data-ttu-id="319d8-145">Выберите **кластеры** в меню слева, а затем выберите **создать кластер**.</span><span class="sxs-lookup"><span data-stu-id="319d8-145">Select **Clusters** from the left-side menu, and then select **Create Cluster**.</span></span>

7. <span data-ttu-id="319d8-146">После надлежащего конфигурирования кластера задайте **Скрипт init** и создайте кластер.</span><span class="sxs-lookup"><span data-stu-id="319d8-146">After configuring the cluster appropriately, set the **Init Script** and create the cluster.</span></span>

   ![Изображение действия сценария](./media/databricks-deployment/deployment-databricks-init-script.png)

## <a name="run-your-app"></a><span data-ttu-id="319d8-148">Запуск приложения</span><span class="sxs-lookup"><span data-stu-id="319d8-148">Run your app</span></span> 

<span data-ttu-id="319d8-149">Вы можете использовать `set JAR` или `spark-submit` для отправки задания в кирпичы.</span><span class="sxs-lookup"><span data-stu-id="319d8-149">You can use `set JAR` or `spark-submit` to submit your job to Databricks.</span></span>

### <a name="use-set-jar"></a><span data-ttu-id="319d8-150">Использование Set JAR</span><span class="sxs-lookup"><span data-stu-id="319d8-150">Use Set JAR</span></span>

<span data-ttu-id="319d8-151">[Set JAR](https://docs.databricks.com/user-guide/jobs.html#create-a-job) позволяет отправить задание в существующий активный кластер.</span><span class="sxs-lookup"><span data-stu-id="319d8-151">[Set JAR](https://docs.databricks.com/user-guide/jobs.html#create-a-job) allows you to submit a job to an existing active cluster.</span></span>

#### <a name="one-time-setup"></a><span data-ttu-id="319d8-152">Однократная настройка</span><span class="sxs-lookup"><span data-stu-id="319d8-152">One-time setup</span></span>

1. <span data-ttu-id="319d8-153">Перейдите к кластеру кирпичов и выберите **задания** в меню слева.</span><span class="sxs-lookup"><span data-stu-id="319d8-153">Go to your Databricks cluster and select **Jobs** from the left-side menu.</span></span> <span data-ttu-id="319d8-154">Затем выберите **задать JAR**.</span><span class="sxs-lookup"><span data-stu-id="319d8-154">Then select **Set JAR**.</span></span>

2. <span data-ttu-id="319d8-155">Отправьте соответствующий `microsoft-spark-<spark-version>-<spark-dotnet-version>.jar` файл.</span><span class="sxs-lookup"><span data-stu-id="319d8-155">Upload the appropriate `microsoft-spark-<spark-version>-<spark-dotnet-version>.jar` file.</span></span>

3. <span data-ttu-id="319d8-156">Задайте соответствующие параметры.</span><span class="sxs-lookup"><span data-stu-id="319d8-156">Set the parameters appropriately.</span></span>

   ```
   Main Class: org.apache.spark.deploy.DotnetRunner
   Arguments /dbfs/apps/<your-app-name>.zip <your-app-main-class>
   ```
 
4. <span data-ttu-id="319d8-157">Настройте **кластер** так, чтобы он указывал на существующий кластер, для которого был создан **Скрипт init** , в предыдущем разделе.</span><span class="sxs-lookup"><span data-stu-id="319d8-157">Configure the **Cluster** to point to the existing cluster you created the **Init Script** for in the previous section.</span></span>

#### <a name="publish-and-run-your-app"></a><span data-ttu-id="319d8-158">Публикация и запуск приложения</span><span class="sxs-lookup"><span data-stu-id="319d8-158">Publish and run your app</span></span>

1. <span data-ttu-id="319d8-159">Используйте интерфейс [командной строки](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html) для передачи приложения в кластер кирпичей.</span><span class="sxs-lookup"><span data-stu-id="319d8-159">Use the [Databricks CLI](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html) to upload your application to your Databricks cluster.</span></span>

      ```bash
      cd <path-to-your-app-publish-directory>
      databricks fs cp <your-app-name>.zip dbfs:/apps/<your-app-name>.zip
      ```

2. <span data-ttu-id="319d8-160">Этот шаг необходим только в том случае, если сборки приложения (например, библиотеки DLL, содержащие определяемые пользователем функции вместе с их зависимостями) должны быть помещены в рабочий каталог каждого **Microsoft. Spark. Worker**.</span><span class="sxs-lookup"><span data-stu-id="319d8-160">This step is only required if your app assemblies (for example, DLLs that contain user-defined functions along with their dependencies) need to be placed in the working directory of each **Microsoft.Spark.Worker**.</span></span>

   - <span data-ttu-id="319d8-161">Передача сборок приложения в кластер кирпичов</span><span class="sxs-lookup"><span data-stu-id="319d8-161">Upload your application assemblies to your Databricks cluster</span></span>
      
      ```bash
      cd <path-to-your-app-publish-directory>
      databricks fs cp <assembly>.dll dbfs:/apps/dependencies
      ```

   - <span data-ttu-id="319d8-162">Раскомментируйте и измените раздел зависимостей приложений в [DB-init.sh](https://github.com/dotnet/spark/blob/master/deployment/db-init.sh) , чтобы указать путь зависимостей приложения и передать его в кластер кирпичей.</span><span class="sxs-lookup"><span data-stu-id="319d8-162">Uncomment and modify the app dependencies section in [db-init.sh](https://github.com/dotnet/spark/blob/master/deployment/db-init.sh) to point to your app dependencies path and upload to your Databricks cluster.</span></span>
   
      ```bash
      cd <path-to-db-init-and-install-worker>
      databricks fs cp db-init.sh dbfs:/spark-dotnet/db-init.sh
      ```
   
   - <span data-ttu-id="319d8-163">Перезапустите кластер.</span><span class="sxs-lookup"><span data-stu-id="319d8-163">Restart your cluster.</span></span>

3. <span data-ttu-id="319d8-164">Перейдите к кластеру "кирпичы" в рабочей области "кирпичы".</span><span class="sxs-lookup"><span data-stu-id="319d8-164">Go to your Databricks cluster in your Databricks workspace.</span></span> <span data-ttu-id="319d8-165">В разделе **задания**выберите задание, а затем щелкните **Запустить сейчас** , чтобы выполнить задание.</span><span class="sxs-lookup"><span data-stu-id="319d8-165">Under **Jobs**, select your job and then select **Run Now** to run your job.</span></span>

### <a name="use-spark-submit"></a><span data-ttu-id="319d8-166">Использование Spark-Submit</span><span class="sxs-lookup"><span data-stu-id="319d8-166">Use spark-submit</span></span>

<span data-ttu-id="319d8-167">Команда [Spark-Submit](https://spark.apache.org/docs/latest/submitting-applications.html) позволяет отправить задание в новый кластер.</span><span class="sxs-lookup"><span data-stu-id="319d8-167">The [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) command allows you to submit a job to a new cluster.</span></span>

1. <span data-ttu-id="319d8-168">[Создайте задание](https://docs.databricks.com/user-guide/jobs.html) и выберите **Настройка Spark-Submit**.</span><span class="sxs-lookup"><span data-stu-id="319d8-168">[Create a Job](https://docs.databricks.com/user-guide/jobs.html) and select **Configure spark-submit**.</span></span>

2. <span data-ttu-id="319d8-169">Настройте `spark-submit` со следующими параметрами:</span><span class="sxs-lookup"><span data-stu-id="319d8-169">Configure `spark-submit` with the following parameters:</span></span>

      ```bash
      ["--files","/dbfs/<path-to>/<app assembly/file to deploy to worker>","--class","org.apache.spark.deploy.DotnetRunner","/dbfs/<path-to>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar","/dbfs/<path-to>/<app name>.zip","<app bin name>","app arg1","app arg2"]
      ```

3. <span data-ttu-id="319d8-170">Перейдите к кластеру "кирпичы" в рабочей области "кирпичы".</span><span class="sxs-lookup"><span data-stu-id="319d8-170">Go to your Databricks cluster in your Databricks workspace.</span></span> <span data-ttu-id="319d8-171">В разделе **задания**выберите задание, а затем щелкните **Запустить сейчас** , чтобы выполнить задание.</span><span class="sxs-lookup"><span data-stu-id="319d8-171">Under **Jobs**, select your job and then select **Run Now** to run your job.</span></span>

## <a name="next-steps"></a><span data-ttu-id="319d8-172">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="319d8-172">Next steps</span></span>

<span data-ttu-id="319d8-173">В этом руководстве вы развернули .NET для Apache Spark приложения в модулях.</span><span class="sxs-lookup"><span data-stu-id="319d8-173">In this tutorial, you deployed your .NET for Apache Spark application to Databricks.</span></span> <span data-ttu-id="319d8-174">Чтобы узнать больше о модулях, перейдите к документации по Azure Databricks.</span><span class="sxs-lookup"><span data-stu-id="319d8-174">To learn more about Databricks, continue to the Azure Databricks Documentation.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="319d8-175">Документация по Azure Databricks</span><span class="sxs-lookup"><span data-stu-id="319d8-175">Azure Databricks Documentation</span></span>](https://docs.microsoft.com/azure/azure-databricks/)
