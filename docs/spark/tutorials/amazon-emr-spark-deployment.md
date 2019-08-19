---
title: Развертывание приложения .NET для Apache Spark в Amazon EMR Spark
description: Узнайте, как развернуть приложение .NET для Apache Spark в Amazon EMR Spark.
ms.date: 05/17/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 5414bc20de3bb90a5d2144bd006d1b859e184a39
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2019
ms.locfileid: "69576931"
---
# <a name="deploy-a-net-for-apache-spark-application-to-amazon-emr-spark"></a><span data-ttu-id="412d9-103">Развертывание приложения .NET для Apache Spark в Amazon EMR Spark</span><span class="sxs-lookup"><span data-stu-id="412d9-103">Deploy a .NET for Apache Spark application to Amazon EMR Spark</span></span>

<span data-ttu-id="412d9-104">В этом учебнике описывается развертывание приложения .NET для Apache Spark в Amazon EMR Spark.</span><span class="sxs-lookup"><span data-stu-id="412d9-104">This tutorial teaches how to deploy a .NET for Apache Spark application to Amazon EMR Spark.</span></span>

<span data-ttu-id="412d9-105">В этом руководстве вы узнаете, как:</span><span class="sxs-lookup"><span data-stu-id="412d9-105">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="412d9-106">Подготовка Microsoft. Spark. Worker</span><span class="sxs-lookup"><span data-stu-id="412d9-106">Prepare Microsoft.Spark.Worker</span></span>
> * <span data-ttu-id="412d9-107">Публикация приложения Spark .NET</span><span class="sxs-lookup"><span data-stu-id="412d9-107">Publish your Spark .NET app</span></span>
> * <span data-ttu-id="412d9-108">Развертывание приложения в Amazon EMR Spark</span><span class="sxs-lookup"><span data-stu-id="412d9-108">Deploy your app to Amazon EMR Spark</span></span>
> * <span data-ttu-id="412d9-109">Запуск приложения</span><span class="sxs-lookup"><span data-stu-id="412d9-109">Run your app</span></span>

## <a name="prerequisites"></a><span data-ttu-id="412d9-110">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="412d9-110">Prerequisites</span></span>

<span data-ttu-id="412d9-111">Прежде чем начать, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="412d9-111">Before you start, do the following:</span></span>

* <span data-ttu-id="412d9-112">Скачайте интерфейс [командной строки AWS](https://aws.amazon.com/cli/).</span><span class="sxs-lookup"><span data-stu-id="412d9-112">Download the [AWS CLI](https://aws.amazon.com/cli/).</span></span>
* <span data-ttu-id="412d9-113">Скачайте [Install-Worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) на локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="412d9-113">Download [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) to your local machine.</span></span> <span data-ttu-id="412d9-114">Это вспомогательный скрипт, который используется позже для копирования .NET для Apache Spark зависимых файлов в рабочие узлы кластера Spark.</span><span class="sxs-lookup"><span data-stu-id="412d9-114">This is a helper script that you use later to copy .NET for Apache Spark dependent files into your Spark cluster's worker nodes.</span></span>

## <a name="prepare-worker-dependencies"></a><span data-ttu-id="412d9-115">Подготовка зависимостей рабочей роли</span><span class="sxs-lookup"><span data-stu-id="412d9-115">Prepare worker dependencies</span></span>

<span data-ttu-id="412d9-116">**Microsoft. Spark. Worker** — это серверный компонент, который находится на отдельных рабочих узлах кластера Spark.</span><span class="sxs-lookup"><span data-stu-id="412d9-116">**Microsoft.Spark.Worker** is a backend component that lives on the individual worker nodes of your Spark cluster.</span></span> <span data-ttu-id="412d9-117">Если вы хотите выполнить определяемую C# пользователем функцию (UDF), Spark необходимо понять, как запустить среду CLR .NET для выполнения пользовательской функции.</span><span class="sxs-lookup"><span data-stu-id="412d9-117">When you want to execute a C# UDF (user-defined function), Spark needs to understand how to launch the .NET CLR to execute the UDF.</span></span> <span data-ttu-id="412d9-118">**Microsoft. Spark. Worker** предоставляет коллекцию классов для Spark, которые обеспечивают эту функциональность.</span><span class="sxs-lookup"><span data-stu-id="412d9-118">**Microsoft.Spark.Worker** provides a collection of classes to Spark that enable this functionality.</span></span>

1. <span data-ttu-id="412d9-119">Выберите выпуск [Microsoft. Spark. Worker](https://github.com/dotnet/spark/releases) Linux netcoreapp, который будет развернут в кластере.</span><span class="sxs-lookup"><span data-stu-id="412d9-119">Select a [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) Linux netcoreapp release to be deployed on your cluster.</span></span>

   <span data-ttu-id="412d9-120">Например, если вы хотите `.NET for Apache Spark v0.1.0` использовать `netcoreapp2.1`, скачайте [Microsoft. Spark. Worker. netcoreapp 2.1. Linux-x64-0.1.0. tar. gz](https://github.com/dotnet/spark/releases/download/v0.1.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz).</span><span class="sxs-lookup"><span data-stu-id="412d9-120">For example, if you want `.NET for Apache Spark v0.1.0` using `netcoreapp2.1`, you'd download [Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz](https://github.com/dotnet/spark/releases/download/v0.1.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz).</span></span>

2. <span data-ttu-id="412d9-121">Отправляйте `Microsoft.Spark.Worker.<release>.tar.gz` и [Install-Worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) в распределенную файловую систему (например, S3), к которой имеет доступ кластер.</span><span class="sxs-lookup"><span data-stu-id="412d9-121">Upload `Microsoft.Spark.Worker.<release>.tar.gz` and [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) to a distributed file system (e.g., S3) that your cluster has access to.</span></span>

## <a name="prepare-your-net-for-apache-spark-app"></a><span data-ttu-id="412d9-122">Подготовка .NET для приложения Apache Spark</span><span class="sxs-lookup"><span data-stu-id="412d9-122">Prepare your .NET for Apache Spark app</span></span>

1. <span data-ttu-id="412d9-123">Выполните инструкции из руководства по [началу работы](get-started.md) , чтобы создать приложение.</span><span class="sxs-lookup"><span data-stu-id="412d9-123">Follow the [Get Started](get-started.md) tutorial to build your app.</span></span>

2. <span data-ttu-id="412d9-124">Опубликуйте свое приложение Spark .NET как автономное.</span><span class="sxs-lookup"><span data-stu-id="412d9-124">Publish your Spark .NET app as self-contained.</span></span>

   <span data-ttu-id="412d9-125">Выполните следующую команду в Linux.</span><span class="sxs-lookup"><span data-stu-id="412d9-125">Run the following command on Linux.</span></span>

   ```bash
   dotnet publish -c Release -f netcoreapp2.1 -r ubuntu.16.04-x64
   ```

3. <span data-ttu-id="412d9-126">Создание `<your app>.zip` для опубликованных файлов.</span><span class="sxs-lookup"><span data-stu-id="412d9-126">Produce `<your app>.zip` for the published files.</span></span>

   <span data-ttu-id="412d9-127">Выполните следующую команду в Linux с помощью `zip`.</span><span class="sxs-lookup"><span data-stu-id="412d9-127">Run the following command on Linux using `zip`.</span></span>

   ```bash
   zip -r <your app>.zip .
   ```

4. <span data-ttu-id="412d9-128">Отправьте следующие элементы в распределенную файловую систему (например, S3), к которой имеет доступ ваш кластер:</span><span class="sxs-lookup"><span data-stu-id="412d9-128">Upload the following items to a distributed file system (e.g., S3) that your cluster has access to:</span></span>

   * <span data-ttu-id="412d9-129">`microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar`: Этот JAR-файл входит в состав пакета NuGet [Microsoft. Spark](https://www.nuget.org/packages/Microsoft.Spark/) и размещается в выходном каталоге сборки приложения.</span><span class="sxs-lookup"><span data-stu-id="412d9-129">`microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar`: This jar is included as part of the [Microsoft.Spark](https://www.nuget.org/packages/Microsoft.Spark/) NuGet package and is colocated in your app's build output directory.</span></span>
   * `<your app>.zip`
   * <span data-ttu-id="412d9-130">Файлы (например, файлы зависимостей или общие данные, доступные каждому рабочему процессу) или сборки (например, библиотеки DLL, содержащие определяемые пользователем функции или библиотеки, от которых зависит ваше приложение) должны размещаться в рабочем каталоге каждого исполнителя.</span><span class="sxs-lookup"><span data-stu-id="412d9-130">Files (like dependency files or common data accessible to every worker) or assemblies (like DLLs that contain your user-defined functions or libraries that your app depends on) to be placed in the working directory of each executor.</span></span>

## <a name="deploy-to-amazon-emr-spark"></a><span data-ttu-id="412d9-131">Развертывание в Amazon EMR Spark</span><span class="sxs-lookup"><span data-stu-id="412d9-131">Deploy to Amazon EMR Spark</span></span>

<span data-ttu-id="412d9-132">[Amazon EMR](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-what-is-emr.html) — это управляемая кластерная платформа, которая упрощает запуск платформ больших данных на AWS.</span><span class="sxs-lookup"><span data-stu-id="412d9-132">[Amazon EMR](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-what-is-emr.html) is a managed cluster platform that simplifies running big data frameworks on AWS.</span></span>

> [!NOTE] 
> <span data-ttu-id="412d9-133">Amazon EMR Spark — на основе Linux.</span><span class="sxs-lookup"><span data-stu-id="412d9-133">Amazon EMR Spark is Linux-based.</span></span> <span data-ttu-id="412d9-134">Поэтому, если вы заинтересованы в развертывании приложения в Amazon EMR Spark, убедитесь, что приложение совместимо .NET Standard и вы используете [компилятор .NET Core](https://dotnet.microsoft.com/download) для компиляции приложения.</span><span class="sxs-lookup"><span data-stu-id="412d9-134">Therefore, if you are interested in deploying your app to Amazon EMR Spark, make sure your app is .NET Standard compatible and that you use the [.NET Core compiler](https://dotnet.microsoft.com/download) to compile your app.</span></span>

### <a name="deploy-microsoftsparkworker"></a><span data-ttu-id="412d9-135">Развертывание Microsoft. Spark. Worker</span><span class="sxs-lookup"><span data-stu-id="412d9-135">Deploy Microsoft.Spark.Worker</span></span>

<span data-ttu-id="412d9-136">Этот шаг требуется только при создании кластера.</span><span class="sxs-lookup"><span data-stu-id="412d9-136">This step is only required at cluster creation.</span></span>

<span data-ttu-id="412d9-137">Выполнение `install-worker.sh` во время создания кластера с помощью [действий начальной загрузки](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-plan-bootstrap.html).</span><span class="sxs-lookup"><span data-stu-id="412d9-137">Run `install-worker.sh` during cluster creation using [Bootstrap Actions](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-plan-bootstrap.html).</span></span>

<span data-ttu-id="412d9-138">Выполните следующую команду в Linux с помощью AWS CLI.</span><span class="sxs-lookup"><span data-stu-id="412d9-138">Run the following command on Linux using AWS CLI.</span></span>

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

## <a name="run-your-app"></a><span data-ttu-id="412d9-139">Запуск приложения</span><span class="sxs-lookup"><span data-stu-id="412d9-139">Run your app</span></span>

<span data-ttu-id="412d9-140">Существует два способа запуска приложения в Amazon EMR Spark: Spark-Submit и Amazon EMR.</span><span class="sxs-lookup"><span data-stu-id="412d9-140">There are two ways to run your app in Amazon EMR Spark: spark-submit and Amazon EMR Steps.</span></span>

### <a name="use-spark-submit"></a><span data-ttu-id="412d9-141">Использование Spark-Submit</span><span class="sxs-lookup"><span data-stu-id="412d9-141">Use spark-submit</span></span>

<span data-ttu-id="412d9-142">Команду [Spark-Submit](https://spark.apache.org/docs/latest/submitting-applications.html) можно использовать для отправки заданий .net для Apache Spark в Amazon EMR Spark.</span><span class="sxs-lookup"><span data-stu-id="412d9-142">You can use the [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) command to submit .NET for Apache Spark jobs to Amazon EMR Spark.</span></span>

1. <span data-ttu-id="412d9-143">`ssh`в один из узлов в кластере.</span><span class="sxs-lookup"><span data-stu-id="412d9-143">`ssh` into one of the nodes in the cluster.</span></span>

2. <span data-ttu-id="412d9-144">Запустите `spark-submit`.</span><span class="sxs-lookup"><span data-stu-id="412d9-144">Run `spark-submit`.</span></span>

   ```bash
   spark-submit \
   --master yarn \
   --class org.apache.spark.deploy.DotnetRunner \
   --files <comma-separated list of assemblies that contain UDF definitions, if any> \
   s3://mybucket/<some dir>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar \
   s3://mybucket/<some dir>/<your app>.zip <your app> <app args>
   ```

### <a name="use-amazon-emr-steps"></a><span data-ttu-id="412d9-145">Использование действий Amazon EMR</span><span class="sxs-lookup"><span data-stu-id="412d9-145">Use Amazon EMR Steps</span></span>

<span data-ttu-id="412d9-146">[Действия Amazon EMR](https://docs.aws.amazon.com/emr/latest/ReleaseGuide/emr-spark-submit-step.html) можно использовать для отправки заданий в платформу Spark, установленную в кластере EMR.</span><span class="sxs-lookup"><span data-stu-id="412d9-146">[Amazon EMR Steps](https://docs.aws.amazon.com/emr/latest/ReleaseGuide/emr-spark-submit-step.html) can be used to submit jobs to the Spark framework installed on the EMR cluster.</span></span>

<span data-ttu-id="412d9-147">Выполните следующую команду в Linux с помощью AWS CLI.</span><span class="sxs-lookup"><span data-stu-id="412d9-147">Run the following command on Linux using AWS CLI.</span></span>

```bash
aws emr add-steps \
--cluster-id j-xxxxxxxxxxxxx \
--steps Type=spark,Name="Spark Program",Args=[--master,yarn,--files,s3://mybucket/<some dir>/<udf assembly>,--class,org.apache.spark.deploy.DotnetRunner,s3://mybucket/<some dir>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar,s3://mybucket/<some dir>/<your app>.zip,<your app>,<app arg 1>,<app arg 2>,...,<app arg n>],ActionOnFailure=CONTINUE
```

## <a name="next-steps"></a><span data-ttu-id="412d9-148">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="412d9-148">Next steps</span></span>

<span data-ttu-id="412d9-149">В этом руководстве вы развернули приложение .NET для Apache Sparkного приложения в Amazon EMR Spark.</span><span class="sxs-lookup"><span data-stu-id="412d9-149">In this tutorial, you deployed your .NET for Apache Spark application to Amazon EMR Spark.</span></span> <span data-ttu-id="412d9-150">Для .NET для Apache Spark примеров проектов перейдите на сайт GitHub.</span><span class="sxs-lookup"><span data-stu-id="412d9-150">For .NET for Apache Spark example projects, continue to GitHub.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="412d9-151">Примеры .NET для Apache Spark</span><span class="sxs-lookup"><span data-stu-id="412d9-151">.NET for Apache Spark samples</span></span>](https://github.com/dotnet/spark/tree/master/examples)
