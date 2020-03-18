---
title: Развертывание приложения .NET для Apache Spark в Amazon EMR Spark
description: Узнайте, как развернуть приложение .NET для Apache Spark в Amazon EMR Spark.
ms.date: 05/17/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: a1ff1ba4d5e855e0ac36b99b0c9d63adfaaaac1e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "73454933"
---
# <a name="deploy-a-net-for-apache-spark-application-to-amazon-emr-spark"></a><span data-ttu-id="072de-103">Развертывание приложения .NET для Apache Spark в Amazon EMR Spark</span><span class="sxs-lookup"><span data-stu-id="072de-103">Deploy a .NET for Apache Spark application to Amazon EMR Spark</span></span>

<span data-ttu-id="072de-104">В этом руководстве рассматривается развертывание приложения .NET для Apache Spark в Amazon EMR Spark.</span><span class="sxs-lookup"><span data-stu-id="072de-104">This tutorial teaches how to deploy a .NET for Apache Spark application to Amazon EMR Spark.</span></span>

<span data-ttu-id="072de-105">В этом руководстве вы узнаете, как:</span><span class="sxs-lookup"><span data-stu-id="072de-105">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="072de-106">Подготовка Microsoft.Spark.Worker</span><span class="sxs-lookup"><span data-stu-id="072de-106">Prepare Microsoft.Spark.Worker</span></span>
> * <span data-ttu-id="072de-107">Публикация приложения Spark .NET</span><span class="sxs-lookup"><span data-stu-id="072de-107">Publish your Spark .NET app</span></span>
> * <span data-ttu-id="072de-108">Развертывание приложения в Amazon EMR Spark</span><span class="sxs-lookup"><span data-stu-id="072de-108">Deploy your app to Amazon EMR Spark</span></span>
> * <span data-ttu-id="072de-109">Запуск приложения</span><span class="sxs-lookup"><span data-stu-id="072de-109">Run your app</span></span>

## <a name="prerequisites"></a><span data-ttu-id="072de-110">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="072de-110">Prerequisites</span></span>

<span data-ttu-id="072de-111">Прежде чем начать, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="072de-111">Before you start, do the following:</span></span>

* <span data-ttu-id="072de-112">Скачайте [интерфейс командной строки AWS](https://aws.amazon.com/cli/).</span><span class="sxs-lookup"><span data-stu-id="072de-112">Download the [AWS CLI](https://aws.amazon.com/cli/).</span></span>
* <span data-ttu-id="072de-113">Скачайте файл [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) на локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="072de-113">Download [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) to your local machine.</span></span> <span data-ttu-id="072de-114">Это вспомогательный скрипт, который будет использоваться позже для копирования зависимых файлов .NET для Apache Spark в рабочие узлы кластера Spark.</span><span class="sxs-lookup"><span data-stu-id="072de-114">This is a helper script that you use later to copy .NET for Apache Spark dependent files into your Spark cluster's worker nodes.</span></span>

## <a name="prepare-worker-dependencies"></a><span data-ttu-id="072de-115">Подготовка зависимостей рабочей роли</span><span class="sxs-lookup"><span data-stu-id="072de-115">Prepare worker dependencies</span></span>

<span data-ttu-id="072de-116">**Microsoft.Spark.Worker** — это серверный компонент, который размещается в отдельных рабочих узлах кластера Spark.</span><span class="sxs-lookup"><span data-stu-id="072de-116">**Microsoft.Spark.Worker** is a backend component that lives on the individual worker nodes of your Spark cluster.</span></span> <span data-ttu-id="072de-117">Если вам нужно выполнить определяемую пользователем функцию C#, Spark необходимо знать, как запустить среду CLR .NET для выполнения этой функции.</span><span class="sxs-lookup"><span data-stu-id="072de-117">When you want to execute a C# UDF (user-defined function), Spark needs to understand how to launch the .NET CLR to execute the UDF.</span></span> <span data-ttu-id="072de-118">**Microsoft.Spark.Worker** предоставляет Spark коллекцию классов, которые обеспечивают такую возможность.</span><span class="sxs-lookup"><span data-stu-id="072de-118">**Microsoft.Spark.Worker** provides a collection of classes to Spark that enable this functionality.</span></span>

1. <span data-ttu-id="072de-119">Выберите выпуск netcoreapp компонента [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) для Linux, который будет развернут в кластере.</span><span class="sxs-lookup"><span data-stu-id="072de-119">Select a [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) Linux netcoreapp release to be deployed on your cluster.</span></span>

   <span data-ttu-id="072de-120">Например, чтобы использовать `.NET for Apache Spark v0.1.0` с `netcoreapp2.1`, скачайте выпуск [Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz](https://github.com/dotnet/spark/releases/download/v0.1.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz).</span><span class="sxs-lookup"><span data-stu-id="072de-120">For example, if you want `.NET for Apache Spark v0.1.0` using `netcoreapp2.1`, you'd download [Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz](https://github.com/dotnet/spark/releases/download/v0.1.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz).</span></span>

2. <span data-ttu-id="072de-121">Передайте файлы `Microsoft.Spark.Worker.<release>.tar.gz` и [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) в распределенную файловую систему (например, S3), к которой есть доступ у кластера.</span><span class="sxs-lookup"><span data-stu-id="072de-121">Upload `Microsoft.Spark.Worker.<release>.tar.gz` and [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) to a distributed file system (e.g., S3) that your cluster has access to.</span></span>

## <a name="prepare-your-net-for-apache-spark-app"></a><span data-ttu-id="072de-122">Подготовка приложения .NET для Apache Spark</span><span class="sxs-lookup"><span data-stu-id="072de-122">Prepare your .NET for Apache Spark app</span></span>

1. <span data-ttu-id="072de-123">Выполните сборку приложения согласно инструкциям из [руководства по началу работы](get-started.md).</span><span class="sxs-lookup"><span data-stu-id="072de-123">Follow the [Get Started](get-started.md) tutorial to build your app.</span></span>

2. <span data-ttu-id="072de-124">Опубликуйте приложение .NET для Spark как автономное.</span><span class="sxs-lookup"><span data-stu-id="072de-124">Publish your Spark .NET app as self-contained.</span></span>

   <span data-ttu-id="072de-125">Выполните приведенную ниже команду в Linux.</span><span class="sxs-lookup"><span data-stu-id="072de-125">Run the following command on Linux.</span></span>

   ```dotnetcli
   dotnet publish -c Release -f netcoreapp2.1 -r ubuntu.16.04-x64
   ```

3. <span data-ttu-id="072de-126">Создайте `<your app>.zip` для опубликованных файлов.</span><span class="sxs-lookup"><span data-stu-id="072de-126">Produce `<your app>.zip` for the published files.</span></span>

   <span data-ttu-id="072de-127">Выполните приведенную ниже команду в Linux с помощью `zip`.</span><span class="sxs-lookup"><span data-stu-id="072de-127">Run the following command on Linux using `zip`.</span></span>

   ```bash
   zip -r <your app>.zip .
   ```

4. <span data-ttu-id="072de-128">Передайте в распределенную файловую систему (например, S3), к которой есть доступ у кластера, следующие объекты:</span><span class="sxs-lookup"><span data-stu-id="072de-128">Upload the following items to a distributed file system (e.g., S3) that your cluster has access to:</span></span>

   * <span data-ttu-id="072de-129">`microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar`. Этот JAR-файл входит в состав пакета NuGet [Microsoft.Spark](https://www.nuget.org/packages/Microsoft.Spark/) и размещается в выходном каталоге сборки приложения.</span><span class="sxs-lookup"><span data-stu-id="072de-129">`microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar`: This jar is included as part of the [Microsoft.Spark](https://www.nuget.org/packages/Microsoft.Spark/) NuGet package and is colocated in your app's build output directory.</span></span>
   * `<your app>.zip`
   * <span data-ttu-id="072de-130">Файлы (например, файлы зависимостей или общие данные, доступные каждой рабочей роли) или сборки (например, библиотеки DLL, содержащие определяемые пользователем функции, или библиотеки, от которых зависит приложение), которые необходимо поместить в рабочий каталог каждого исполнителя.</span><span class="sxs-lookup"><span data-stu-id="072de-130">Files (like dependency files or common data accessible to every worker) or assemblies (like DLLs that contain your user-defined functions or libraries that your app depends on) to be placed in the working directory of each executor.</span></span>

## <a name="deploy-to-amazon-emr-spark"></a><span data-ttu-id="072de-131">Развертывание в Amazon EMR Spark</span><span class="sxs-lookup"><span data-stu-id="072de-131">Deploy to Amazon EMR Spark</span></span>

<span data-ttu-id="072de-132">[Amazon EMR](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-what-is-emr.html) — это управляемая кластерная платформа, которая упрощает выполнение систем больших данных в AWS.</span><span class="sxs-lookup"><span data-stu-id="072de-132">[Amazon EMR](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-what-is-emr.html) is a managed cluster platform that simplifies running big data frameworks on AWS.</span></span>

> [!NOTE]
> <span data-ttu-id="072de-133">Amazon EMR Spark работает под управлением Linux.</span><span class="sxs-lookup"><span data-stu-id="072de-133">Amazon EMR Spark is Linux-based.</span></span> <span data-ttu-id="072de-134">Поэтому если вы хотите развернуть приложение в Amazon EMR Spark, оно должно быть совместимо с .NET Standard, а для его компиляции необходимо использовать [компилятор .NET Core](https://dotnet.microsoft.com/download).</span><span class="sxs-lookup"><span data-stu-id="072de-134">Therefore, if you are interested in deploying your app to Amazon EMR Spark, make sure your app is .NET Standard compatible and that you use the [.NET Core compiler](https://dotnet.microsoft.com/download) to compile your app.</span></span>

### <a name="deploy-microsoftsparkworker"></a><span data-ttu-id="072de-135">Развертывание Microsoft.Spark.Worker</span><span class="sxs-lookup"><span data-stu-id="072de-135">Deploy Microsoft.Spark.Worker</span></span>

<span data-ttu-id="072de-136">Этот шаг необходимо выполнить только при создании кластера.</span><span class="sxs-lookup"><span data-stu-id="072de-136">This step is only required at cluster creation.</span></span>

<span data-ttu-id="072de-137">Выполните скрипт `install-worker.sh` во время создания кластера с помощью [действий начальной загрузки](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-plan-bootstrap.html).</span><span class="sxs-lookup"><span data-stu-id="072de-137">Run `install-worker.sh` during cluster creation using [Bootstrap Actions](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-plan-bootstrap.html).</span></span>

<span data-ttu-id="072de-138">Выполните приведенную ниже команду в Linux с помощью интерфейса командной строки AWS.</span><span class="sxs-lookup"><span data-stu-id="072de-138">Run the following command on Linux using AWS CLI.</span></span>

```bash
aws emr create-cluster \
--name "Test cluster" \
--release-label emr-5.23.0 \
--use-default-roles \
--ec2-attributes KeyName=myKey \
--applications Name=Spark \
--instance-count 3 \
--instance-type m1.medium \
--bootstrap-actions Path=s3://mybucket/<some dir>/install-worker.sh,Name="Install Microsoft.Spark.Worker",Args=["aws","s3://mybucket/<some dir>/Microsoft.Spark.Worker.<release>.tar.gz","/usr/local/bin"]
```

## <a name="run-your-app"></a><span data-ttu-id="072de-139">Запуск приложения</span><span class="sxs-lookup"><span data-stu-id="072de-139">Run your app</span></span>

<span data-ttu-id="072de-140">Приложение можно запускать в Amazon EMR Spark двумя способами: с помощью команды spark-submit или с помощью шагов Amazon EMR.</span><span class="sxs-lookup"><span data-stu-id="072de-140">There are two ways to run your app in Amazon EMR Spark: spark-submit and Amazon EMR Steps.</span></span>

### <a name="use-spark-submit"></a><span data-ttu-id="072de-141">Использование команды spark-submit</span><span class="sxs-lookup"><span data-stu-id="072de-141">Use spark-submit</span></span>

<span data-ttu-id="072de-142">Для отправки заданий .NET для Apache Spark в Amazon EMR Spark можно использовать команду [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html).</span><span class="sxs-lookup"><span data-stu-id="072de-142">You can use the [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) command to submit .NET for Apache Spark jobs to Amazon EMR Spark.</span></span>

1. <span data-ttu-id="072de-143">Подключитесь к одному из узлов кластера с помощью команды `ssh`.</span><span class="sxs-lookup"><span data-stu-id="072de-143">`ssh` into one of the nodes in the cluster.</span></span>

2. <span data-ttu-id="072de-144">Запустите `spark-submit`.</span><span class="sxs-lookup"><span data-stu-id="072de-144">Run `spark-submit`.</span></span>

   ```bash
   spark-submit \
   --master yarn \
   --class org.apache.spark.deploy.dotnet.DotnetRunner \
   --files <comma-separated list of assemblies that contain UDF definitions, if any> \
   s3://mybucket/<some dir>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar \
   s3://mybucket/<some dir>/<your app>.zip <your app> <app args>
   ```

### <a name="use-amazon-emr-steps"></a><span data-ttu-id="072de-145">Использование шагов Amazon EMR</span><span class="sxs-lookup"><span data-stu-id="072de-145">Use Amazon EMR Steps</span></span>

<span data-ttu-id="072de-146">[Шаги Amazon EMR](https://docs.aws.amazon.com/emr/latest/ReleaseGuide/emr-spark-submit-step.html) можно использовать для отправки заданий в платформу Spark, установленную в кластере EMR.</span><span class="sxs-lookup"><span data-stu-id="072de-146">[Amazon EMR Steps](https://docs.aws.amazon.com/emr/latest/ReleaseGuide/emr-spark-submit-step.html) can be used to submit jobs to the Spark framework installed on the EMR cluster.</span></span>

<span data-ttu-id="072de-147">Выполните приведенную ниже команду в Linux с помощью интерфейса командной строки AWS.</span><span class="sxs-lookup"><span data-stu-id="072de-147">Run the following command on Linux using AWS CLI.</span></span>

```bash
aws emr add-steps \
--cluster-id j-xxxxxxxxxxxxx \
--steps Type=spark,Name="Spark Program",Args=[--master,yarn,--files,s3://mybucket/<some dir>/<udf assembly>,--class,org.apache.spark.deploy.dotnet.DotnetRunner,s3://mybucket/<some dir>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar,s3://mybucket/<some dir>/<your app>.zip,<your app>,<app arg 1>,<app arg 2>,...,<app arg n>],ActionOnFailure=CONTINUE
```

## <a name="next-steps"></a><span data-ttu-id="072de-148">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="072de-148">Next steps</span></span>

<span data-ttu-id="072de-149">В этом руководстве вы развернули приложение .NET для Apache Spark в Amazon EMR Spark.</span><span class="sxs-lookup"><span data-stu-id="072de-149">In this tutorial, you deployed your .NET for Apache Spark application to Amazon EMR Spark.</span></span> <span data-ttu-id="072de-150">Примеры проектов .NET для Apache Spark можно найти в GitHub.</span><span class="sxs-lookup"><span data-stu-id="072de-150">For .NET for Apache Spark example projects, continue to GitHub.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="072de-151">Примеры .NET для Apache Spark</span><span class="sxs-lookup"><span data-stu-id="072de-151">.NET for Apache Spark samples</span></span>](https://github.com/dotnet/spark/tree/master/examples)
