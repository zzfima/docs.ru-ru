---
title: Развертывание приложения .NET для Apache Spark в Azure HDInsight
description: Узнайте, как развернуть приложение .NET для Apache Spark в HDInsight.
ms.date: 05/17/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 81d1af1fd4e3329c4a289eea388edf8af57d7c4e
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70243949"
---
# <a name="deploy-a-net-for-apache-spark-application-to-azure-hdinsight"></a><span data-ttu-id="797ef-103">Развертывание приложения .NET для Apache Spark в Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="797ef-103">Deploy a .NET for Apache Spark application to Azure HDInsight</span></span>

<span data-ttu-id="797ef-104">В этом руководстве рассматривается развертывание приложения .NET для Apache Spark в Azure HDInsight.</span><span class="sxs-lookup"><span data-stu-id="797ef-104">This tutorial teaches how to deploy a .NET for Apache Spark application to Azure HDInsight.</span></span>

<span data-ttu-id="797ef-105">В этом руководстве вы узнаете, как:</span><span class="sxs-lookup"><span data-stu-id="797ef-105">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="797ef-106">Подготовка Microsoft.Spark.Worker</span><span class="sxs-lookup"><span data-stu-id="797ef-106">Prepare Microsoft.Spark.Worker</span></span>
> * <span data-ttu-id="797ef-107">Публикация приложения Spark .NET</span><span class="sxs-lookup"><span data-stu-id="797ef-107">Publish your Spark .NET app</span></span>
> * <span data-ttu-id="797ef-108">Развертывание приложения в Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="797ef-108">Deploy your app to Azure HDInsight</span></span>
> * <span data-ttu-id="797ef-109">Запуск приложения</span><span class="sxs-lookup"><span data-stu-id="797ef-109">Run your app</span></span>

## <a name="prerequisites"></a><span data-ttu-id="797ef-110">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="797ef-110">Prerequisites</span></span>

<span data-ttu-id="797ef-111">Прежде чем начать, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="797ef-111">Before you start, do the following:</span></span>

* <span data-ttu-id="797ef-112">Скачайте [Обозреватель службы хранилища Azure](https://azure.microsoft.com/features/storage-explorer/).</span><span class="sxs-lookup"><span data-stu-id="797ef-112">Download [Azure Storage Explorer](https://azure.microsoft.com/features/storage-explorer/).</span></span>
* <span data-ttu-id="797ef-113">Скачайте файл [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) на локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="797ef-113">Download [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) to your local machine.</span></span> <span data-ttu-id="797ef-114">Это вспомогательный скрипт, который будет использоваться позже для копирования зависимых файлов .NET для Apache Spark в рабочие узлы кластера Spark.</span><span class="sxs-lookup"><span data-stu-id="797ef-114">This is a helper script that you use later to copy .NET for Apache Spark dependent files into your Spark cluster's worker nodes.</span></span>

## <a name="prepare-worker-dependencies"></a><span data-ttu-id="797ef-115">Подготовка зависимостей рабочей роли</span><span class="sxs-lookup"><span data-stu-id="797ef-115">Prepare worker dependencies</span></span>

<span data-ttu-id="797ef-116">**Microsoft.Spark.Worker** — это серверный компонент, который размещается в отдельных рабочих узлах кластера Spark.</span><span class="sxs-lookup"><span data-stu-id="797ef-116">**Microsoft.Spark.Worker** is a backend component that lives on the individual worker nodes of your Spark cluster.</span></span> <span data-ttu-id="797ef-117">Если вам нужно выполнить определяемую пользователем функцию C#, Spark необходимо знать, как запустить среду CLR .NET для выполнения этой функции.</span><span class="sxs-lookup"><span data-stu-id="797ef-117">When you want to execute a C# UDF (user-defined function), Spark needs to understand how to launch the .NET CLR to execute the UDF.</span></span> <span data-ttu-id="797ef-118">**Microsoft.Spark.Worker** предоставляет Spark коллекцию классов, которые обеспечивают такую возможность.</span><span class="sxs-lookup"><span data-stu-id="797ef-118">**Microsoft.Spark.Worker** provides a collection of classes to Spark that enable this functionality.</span></span>

1. <span data-ttu-id="797ef-119">Выберите выпуск netcoreapp компонента [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) для Linux, который будет развернут в кластере.</span><span class="sxs-lookup"><span data-stu-id="797ef-119">Select a [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) Linux netcoreapp release to be deployed on your cluster.</span></span>

   <span data-ttu-id="797ef-120">Например, чтобы использовать `.NET for Apache Spark v0.1.0` с `netcoreapp2.1`, скачайте выпуск [Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz](https://github.com/dotnet/spark/releases/download/v0.1.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz).</span><span class="sxs-lookup"><span data-stu-id="797ef-120">For example, if you want `.NET for Apache Spark v0.1.0` using `netcoreapp2.1`, you'd download [Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz](https://github.com/dotnet/spark/releases/download/v0.1.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz).</span></span>

2. <span data-ttu-id="797ef-121">Передайте файлы `Microsoft.Spark.Worker.<release>.tar.gz` и [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) в распределенную файловую систему (например, HDFS, WASB или ADLS), к которой есть доступ у кластера.</span><span class="sxs-lookup"><span data-stu-id="797ef-121">Upload `Microsoft.Spark.Worker.<release>.tar.gz` and [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) to a distributed file system (e.g., HDFS, WASB, ADLS) that your cluster has access to.</span></span>

## <a name="prepare-your-net-for-apache-spark-app"></a><span data-ttu-id="797ef-122">Подготовка приложения .NET для Apache Spark</span><span class="sxs-lookup"><span data-stu-id="797ef-122">Prepare your .NET for Apache Spark app</span></span>

1. <span data-ttu-id="797ef-123">Выполните сборку приложения согласно инструкциям из [руководства по началу работы](get-started.md).</span><span class="sxs-lookup"><span data-stu-id="797ef-123">Follow the [Get Started](get-started.md) tutorial to build your app.</span></span>

2. <span data-ttu-id="797ef-124">Опубликуйте приложение .NET для Spark как автономное.</span><span class="sxs-lookup"><span data-stu-id="797ef-124">Publish your Spark .NET app as self-contained.</span></span>

   <span data-ttu-id="797ef-125">В Linux можно выполнить приведенную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="797ef-125">You can run the following command on Linux.</span></span>

   ```bash
   dotnet publish -c Release -f netcoreapp2.1 -r ubuntu.16.04-x64
   ```

3. <span data-ttu-id="797ef-126">Создайте `<your app>.zip` для опубликованных файлов.</span><span class="sxs-lookup"><span data-stu-id="797ef-126">Produce `<your app>.zip` for the published files.</span></span>

   <span data-ttu-id="797ef-127">В Linux можно выполнить приведенную ниже команду с помощью `zip`.</span><span class="sxs-lookup"><span data-stu-id="797ef-127">You can run the following command on Linux using `zip`.</span></span>

   ```bash
   zip -r <your app>.zip .
   ```

4. <span data-ttu-id="797ef-128">Передайте в распределенную файловую систему (например, HDFS, WASB или ADLS), к которой есть доступ у кластера, следующие файлы:</span><span class="sxs-lookup"><span data-stu-id="797ef-128">Upload the following to a distributed file system (e.g., HDFS, WASB, ADLS) that your cluster has access to:</span></span>

   * <span data-ttu-id="797ef-129">`microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar`: Этот JAR-файл входит в состав пакета NuGet [Microsoft.Spark](https://www.nuget.org/packages/Microsoft.Spark/) и размещается в выходном каталоге сборки приложения.</span><span class="sxs-lookup"><span data-stu-id="797ef-129">`microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar`: This jar is included as part of the [Microsoft.Spark](https://www.nuget.org/packages/Microsoft.Spark/) NuGet package and is colocated in your app's build output directory.</span></span>
   * `<your app>.zip`
   * <span data-ttu-id="797ef-130">Файлы (например, файлы зависимостей или общие данные, доступные каждой рабочей роли) или сборки (например, библиотеки DLL, содержащие определяемые пользователем функции, или библиотеки, от которых зависит `app`), которые необходимо поместить в рабочий каталог каждого исполнителя.</span><span class="sxs-lookup"><span data-stu-id="797ef-130">Files (like dependency files or common data accessible to every worker) or Assemblies (like DLLs that contain your user-defined functions or libraries that your `app` depends on) to be placed in the working directory of each executor.</span></span>

## <a name="deploy-to-azure-hdinsight-spark"></a><span data-ttu-id="797ef-131">Развертывание в Azure HDInsight Spark</span><span class="sxs-lookup"><span data-stu-id="797ef-131">Deploy to Azure HDInsight Spark</span></span>

<span data-ttu-id="797ef-132">[Azure HDInsight Spark](https://docs.microsoft.com/azure/hdinsight/spark/apache-spark-overview) — это предоставляемая корпорацией Майкрософт реализация Apache Spark в облаке, которая позволяет пользователям запускать и настраивать кластеры Spark в Azure.</span><span class="sxs-lookup"><span data-stu-id="797ef-132">[Azure HDInsight Spark](https://docs.microsoft.com/azure/hdinsight/spark/apache-spark-overview) is the Microsoft implementation of Apache Spark in the cloud that allows users to launch and configure Spark clusters in Azure.</span></span> <span data-ttu-id="797ef-133">Кластеры HDInsight Spark можно использовать для обработки данных, хранящихся в [службе хранилища Azure](https://azure.microsoft.com/services/storage/) или [Azure Data Lake Storage](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-use-data-lake-storage-gen2).</span><span class="sxs-lookup"><span data-stu-id="797ef-133">You can use HDInsight Spark clusters to process your data stored in [Azure Storage](https://azure.microsoft.com/services/storage/) or [Azure Data Lake Storage](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-use-data-lake-storage-gen2).</span></span>

> [!NOTE]
> <span data-ttu-id="797ef-134">Azure HDInsight Spark работает под управлением Linux.</span><span class="sxs-lookup"><span data-stu-id="797ef-134">Azure HDInsight Spark is Linux-based.</span></span> <span data-ttu-id="797ef-135">Если вы хотите развернуть приложение в Azure HDInsight Spark, оно должно быть совместимо с .NET Standard, а для его компиляции необходимо использовать [компилятор .NET Core](https://dotnet.microsoft.com/download).</span><span class="sxs-lookup"><span data-stu-id="797ef-135">If you are interested in deploying your app to Azure HDInsight Spark, make sure your app is .NET Standard compatible and that you use the [.NET Core compiler](https://dotnet.microsoft.com/download) to compile your app.</span></span>

### <a name="deploy-microsoftsparkworker"></a><span data-ttu-id="797ef-136">Развертывание Microsoft.Spark.Worker</span><span class="sxs-lookup"><span data-stu-id="797ef-136">Deploy Microsoft.Spark.Worker</span></span>

<span data-ttu-id="797ef-137">Этот шаг необходимо выполнить для кластера только один раз.</span><span class="sxs-lookup"><span data-stu-id="797ef-137">This step is only required once for your cluster.</span></span>

<span data-ttu-id="797ef-138">Выполните скрипт `install-worker.sh` в кластере с помощью [действий скриптов HDInsight](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-customize-cluster-linux).</span><span class="sxs-lookup"><span data-stu-id="797ef-138">Run `install-worker.sh` on the cluster using [HDInsight Script Actions](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-customize-cluster-linux).</span></span>

|<span data-ttu-id="797ef-139">Параметр</span><span class="sxs-lookup"><span data-stu-id="797ef-139">Setting</span></span>|<span data-ttu-id="797ef-140">Значение</span><span class="sxs-lookup"><span data-stu-id="797ef-140">Value</span></span>|
|-------|-----|
|<span data-ttu-id="797ef-141">Тип скрипта</span><span class="sxs-lookup"><span data-stu-id="797ef-141">Script type</span></span>|<span data-ttu-id="797ef-142">Другой</span><span class="sxs-lookup"><span data-stu-id="797ef-142">Custom</span></span>|
|<span data-ttu-id="797ef-143">name</span><span class="sxs-lookup"><span data-stu-id="797ef-143">Name</span></span>|<span data-ttu-id="797ef-144">Установка Microsoft.Spark.Worker</span><span class="sxs-lookup"><span data-stu-id="797ef-144">Install Microsoft.Spark.Worker</span></span>|
|<span data-ttu-id="797ef-145">URI bash-скрипта</span><span class="sxs-lookup"><span data-stu-id="797ef-145">Bash script URI</span></span>|<span data-ttu-id="797ef-146">Универсальный код ресурса (URI), по которому был отправлен файл `install-worker.sh`.</span><span class="sxs-lookup"><span data-stu-id="797ef-146">The URI to which you uploaded `install-worker.sh`.</span></span> <span data-ttu-id="797ef-147">Например `abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/install-worker.sh`.</span><span class="sxs-lookup"><span data-stu-id="797ef-147">For example, `abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/install-worker.sh`</span></span>|
|<span data-ttu-id="797ef-148">Типы узлов</span><span class="sxs-lookup"><span data-stu-id="797ef-148">Node type(s)</span></span>|<span data-ttu-id="797ef-149">Рабочий узел</span><span class="sxs-lookup"><span data-stu-id="797ef-149">Worker</span></span>|
|<span data-ttu-id="797ef-150">Параметры</span><span class="sxs-lookup"><span data-stu-id="797ef-150">Parameters</span></span>|<span data-ttu-id="797ef-151">Параметры скрипта `install-worker.sh`.</span><span class="sxs-lookup"><span data-stu-id="797ef-151">Parameters to `install-worker.sh`.</span></span> <span data-ttu-id="797ef-152">Например, если файл `install-worker.sh` был отправлен в Azure Data Lake 2-го поколения, параметры будут следующими: `azure abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/Microsoft.Spark.Worker.<release>.tar.gz /usr/local/bin`.</span><span class="sxs-lookup"><span data-stu-id="797ef-152">For example, if you uploaded `install-worker.sh` to Azure Data Lake Gen 2 then it would be `azure abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/Microsoft.Spark.Worker.<release>.tar.gz /usr/local/bin`.</span></span>|

![Изображение действия скрипта](./media/hdinsight-deployment/deployment-hdi-action-script.png)

## <a name="run-your-app"></a><span data-ttu-id="797ef-154">Запуск приложения</span><span class="sxs-lookup"><span data-stu-id="797ef-154">Run your app</span></span>

<span data-ttu-id="797ef-155">Задание можно отправить в Azure HDInsight с помощью `spark-submit` или Apache Livy.</span><span class="sxs-lookup"><span data-stu-id="797ef-155">You can submit your job to Azure HDInsight using `spark-submit` or Apache Livy.</span></span>

### <a name="use-spark-submit"></a><span data-ttu-id="797ef-156">Использование команды spark-submit</span><span class="sxs-lookup"><span data-stu-id="797ef-156">Use spark-submit</span></span>

<span data-ttu-id="797ef-157">Для отправки заданий .NET для Apache Spark в Azure HDInsight можно использовать команду [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html).</span><span class="sxs-lookup"><span data-stu-id="797ef-157">You can use the [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) command to submit .NET for Apache Spark jobs to Azure HDInsight.</span></span>
 
1. <span data-ttu-id="797ef-158">Подключитесь к одному из головных узлов кластера с помощью команды `ssh`.</span><span class="sxs-lookup"><span data-stu-id="797ef-158">`ssh` into one of the head nodes in your cluster.</span></span>

1. <span data-ttu-id="797ef-159">Выполните команду `spark-submit`:</span><span class="sxs-lookup"><span data-stu-id="797ef-159">Run `spark-submit`:</span></span>

   ```bash
   spark-submit \
   --master yarn \
   --class org.apache.spark.deploy.dotnet.DotnetRunner \
   --files <comma-separated list of assemblies that contain UDF definitions, if any> \
   abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar \
   abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/<your app>.zip <your app> <app arg 1> <app arg 2> ... <app arg n>
   ```

### <a name="use-apache-livy"></a><span data-ttu-id="797ef-160">Использование Apache Livy</span><span class="sxs-lookup"><span data-stu-id="797ef-160">Use Apache Livy</span></span>

<span data-ttu-id="797ef-161">Для отправки заданий .NET для Apache Spark в кластер Azure HDInsight Spark можно использовать [Apache Livy](https://livy.incubator.apache.org/), интерфейс REST API для Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="797ef-161">You can use [Apache Livy](https://livy.incubator.apache.org/), the Apache Spark REST API, to submit .NET for Apache Spark jobs to an Azure HDInsight Spark cluster.</span></span> <span data-ttu-id="797ef-162">Дополнительные сведения см. в статье [Работа с удаленными заданиями с помощью Apache Livy](https://docs.microsoft.com/azure/hdinsight/spark/apache-spark-livy-rest-interface).</span><span class="sxs-lookup"><span data-stu-id="797ef-162">For more information, see [Remote jobs with Apache Livy](https://docs.microsoft.com/azure/hdinsight/spark/apache-spark-livy-rest-interface).</span></span>

<span data-ttu-id="797ef-163">В Linux можно выполнить следующую команду с помощью `curl`:</span><span class="sxs-lookup"><span data-stu-id="797ef-163">You can run the following command on Linux using `curl`:</span></span>

```bash
curl -k -v -X POST "https://<your spark cluster>.azurehdinsight.net/livy/batches" \
-u "<hdinsight username>:<hdinsight password>" \
-H "Content-Type: application/json" \
-H "X-Requested-By: <hdinsight username>" \
-d @- << EOF
{
    "file":"abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar",
    "className":"org.apache.spark.deploy.dotnet.DotnetRunner",
    "files":["abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/<udf assembly>", "abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/<file>"],
    "args":["abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/<your app>.zip","<your app>","<app arg 1>","<app arg 2>,"...","<app arg n>"]
}
EOF
```

## <a name="next-steps"></a><span data-ttu-id="797ef-164">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="797ef-164">Next steps</span></span>

<span data-ttu-id="797ef-165">В этом руководстве вы развернули приложение .NET для Apache Spark в Azure HDInsight.</span><span class="sxs-lookup"><span data-stu-id="797ef-165">In this tutorial, you deployed your .NET for Apache Spark application to Azure HDInsight.</span></span> <span data-ttu-id="797ef-166">Дополнительные сведения об HDInsight см. в документации по Azure HDInsight.</span><span class="sxs-lookup"><span data-stu-id="797ef-166">To learn more about HDInsight, continue to the Azure HDInsight Documentation.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="797ef-167">Документация по Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="797ef-167">Azure HDInsight Documentation</span></span>](https://docs.microsoft.com/azure/hdinsight/)
