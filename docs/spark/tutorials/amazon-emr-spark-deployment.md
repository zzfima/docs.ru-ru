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
# <a name="deploy-a-net-for-apache-spark-application-to-amazon-emr-spark"></a>Развертывание приложения .NET для Apache Spark в Amazon EMR Spark

В этом учебнике описывается развертывание приложения .NET для Apache Spark в Amazon EMR Spark.

В этом руководстве вы узнаете, как:

> [!div class="checklist"]
> * Подготовка Microsoft. Spark. Worker
> * Публикация приложения Spark .NET
> * Развертывание приложения в Amazon EMR Spark
> * Запуск приложения

## <a name="prerequisites"></a>Предварительные требования

Прежде чем начать, выполните следующие действия.

* Скачайте интерфейс [командной строки AWS](https://aws.amazon.com/cli/).
* Скачайте [Install-Worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) на локальный компьютер. Это вспомогательный скрипт, который используется позже для копирования .NET для Apache Spark зависимых файлов в рабочие узлы кластера Spark.

## <a name="prepare-worker-dependencies"></a>Подготовка зависимостей рабочей роли

**Microsoft. Spark. Worker** — это серверный компонент, который находится на отдельных рабочих узлах кластера Spark. Если вы хотите выполнить определяемую C# пользователем функцию (UDF), Spark необходимо понять, как запустить среду CLR .NET для выполнения пользовательской функции. **Microsoft. Spark. Worker** предоставляет коллекцию классов для Spark, которые обеспечивают эту функциональность.

1. Выберите выпуск [Microsoft. Spark. Worker](https://github.com/dotnet/spark/releases) Linux netcoreapp, который будет развернут в кластере.

   Например, если вы хотите `.NET for Apache Spark v0.1.0` использовать `netcoreapp2.1`, скачайте [Microsoft. Spark. Worker. netcoreapp 2.1. Linux-x64-0.1.0. tar. gz](https://github.com/dotnet/spark/releases/download/v0.1.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz).

2. Отправляйте `Microsoft.Spark.Worker.<release>.tar.gz` и [Install-Worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) в распределенную файловую систему (например, S3), к которой имеет доступ кластер.

## <a name="prepare-your-net-for-apache-spark-app"></a>Подготовка .NET для приложения Apache Spark

1. Выполните инструкции из руководства по [началу работы](get-started.md) , чтобы создать приложение.

2. Опубликуйте свое приложение Spark .NET как автономное.

   Выполните следующую команду в Linux.

   ```bash
   dotnet publish -c Release -f netcoreapp2.1 -r ubuntu.16.04-x64
   ```

3. Создание `<your app>.zip` для опубликованных файлов.

   Выполните следующую команду в Linux с помощью `zip`.

   ```bash
   zip -r <your app>.zip .
   ```

4. Отправьте следующие элементы в распределенную файловую систему (например, S3), к которой имеет доступ ваш кластер:

   * `microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar`: Этот JAR-файл входит в состав пакета NuGet [Microsoft. Spark](https://www.nuget.org/packages/Microsoft.Spark/) и размещается в выходном каталоге сборки приложения.
   * `<your app>.zip`
   * Файлы (например, файлы зависимостей или общие данные, доступные каждому рабочему процессу) или сборки (например, библиотеки DLL, содержащие определяемые пользователем функции или библиотеки, от которых зависит ваше приложение) должны размещаться в рабочем каталоге каждого исполнителя.

## <a name="deploy-to-amazon-emr-spark"></a>Развертывание в Amazon EMR Spark

[Amazon EMR](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-what-is-emr.html) — это управляемая кластерная платформа, которая упрощает запуск платформ больших данных на AWS.

> [!NOTE] 
> Amazon EMR Spark — на основе Linux. Поэтому, если вы заинтересованы в развертывании приложения в Amazon EMR Spark, убедитесь, что приложение совместимо .NET Standard и вы используете [компилятор .NET Core](https://dotnet.microsoft.com/download) для компиляции приложения.

### <a name="deploy-microsoftsparkworker"></a>Развертывание Microsoft. Spark. Worker

Этот шаг требуется только при создании кластера.

Выполнение `install-worker.sh` во время создания кластера с помощью [действий начальной загрузки](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-plan-bootstrap.html).

Выполните следующую команду в Linux с помощью AWS CLI.

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

## <a name="run-your-app"></a>Запуск приложения

Существует два способа запуска приложения в Amazon EMR Spark: Spark-Submit и Amazon EMR.

### <a name="use-spark-submit"></a>Использование Spark-Submit

Команду [Spark-Submit](https://spark.apache.org/docs/latest/submitting-applications.html) можно использовать для отправки заданий .net для Apache Spark в Amazon EMR Spark.

1. `ssh`в один из узлов в кластере.

2. Запустите `spark-submit`.

   ```bash
   spark-submit \
   --master yarn \
   --class org.apache.spark.deploy.DotnetRunner \
   --files <comma-separated list of assemblies that contain UDF definitions, if any> \
   s3://mybucket/<some dir>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar \
   s3://mybucket/<some dir>/<your app>.zip <your app> <app args>
   ```

### <a name="use-amazon-emr-steps"></a>Использование действий Amazon EMR

[Действия Amazon EMR](https://docs.aws.amazon.com/emr/latest/ReleaseGuide/emr-spark-submit-step.html) можно использовать для отправки заданий в платформу Spark, установленную в кластере EMR.

Выполните следующую команду в Linux с помощью AWS CLI.

```bash
aws emr add-steps \
--cluster-id j-xxxxxxxxxxxxx \
--steps Type=spark,Name="Spark Program",Args=[--master,yarn,--files,s3://mybucket/<some dir>/<udf assembly>,--class,org.apache.spark.deploy.DotnetRunner,s3://mybucket/<some dir>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar,s3://mybucket/<some dir>/<your app>.zip,<your app>,<app arg 1>,<app arg 2>,...,<app arg n>],ActionOnFailure=CONTINUE
```

## <a name="next-steps"></a>Следующие шаги

В этом руководстве вы развернули приложение .NET для Apache Sparkного приложения в Amazon EMR Spark. Для .NET для Apache Spark примеров проектов перейдите на сайт GitHub.

> [!div class="nextstepaction"]
> [Примеры .NET для Apache Spark](https://github.com/dotnet/spark/tree/master/examples)
