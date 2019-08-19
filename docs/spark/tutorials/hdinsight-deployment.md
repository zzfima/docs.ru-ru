---
title: Развертывание приложения .NET для Apache Spark в Azure HDInsight
description: Узнайте, как развернуть приложение .NET для Apache Spark приложения в HDInsight.
ms.date: 05/17/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 4769c194520790ce217d46d1d3197b20742d4f1a
ms.sourcegitcommit: ffd7dd79468a81bbb0d6449f6d65513e050c04c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/21/2019
ms.locfileid: "69576951"
---
# <a name="deploy-a-net-for-apache-spark-application-to-azure-hdinsight"></a>Развертывание приложения .NET для Apache Spark в Azure HDInsight

В этом учебнике описывается развертывание приложения .NET для Apache Spark в Azure HDInsight.

В этом руководстве вы узнаете, как:

> [!div class="checklist"]
> * Подготовка Microsoft. Spark. Worker
> * Публикация приложения Spark .NET
> * Развертывание приложения в Azure HDInsight
> * Запуск приложения

## <a name="prerequisites"></a>Предварительные требования

Прежде чем начать, выполните следующие действия.

* Скачайте [Обозреватель службы хранилища Azure](https://azure.microsoft.com/features/storage-explorer/).
* Скачайте [Install-Worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) на локальный компьютер. Это вспомогательный скрипт, который используется позже для копирования .NET для Apache Spark зависимых файлов в рабочие узлы кластера Spark.

## <a name="prepare-worker-dependencies"></a>Подготовка зависимостей рабочей роли

**Microsoft. Spark. Worker** — это серверный компонент, который находится на отдельных рабочих узлах кластера Spark. Если вы хотите выполнить определяемую C# пользователем функцию (UDF), Spark необходимо понять, как запустить среду CLR .NET для выполнения пользовательской функции. **Microsoft. Spark. Worker** предоставляет коллекцию классов для Spark, которые обеспечивают эту функциональность.

1. Выберите выпуск [Microsoft. Spark. Worker](https://github.com/dotnet/spark/releases) Linux netcoreapp, который будет развернут в кластере.

   Например, если вы хотите `.NET for Apache Spark v0.1.0` использовать `netcoreapp2.1`, скачайте [Microsoft. Spark. Worker. netcoreapp 2.1. Linux-x64-0.1.0. tar. gz](https://github.com/dotnet/spark/releases/download/v0.1.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz).

2. Отправляйте `Microsoft.Spark.Worker.<release>.tar.gz` и [Install-Worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) в распределенную файловую систему (например, HDFS, WASB, ADLS), к которой имеет доступ ваш кластер.

## <a name="prepare-your-net-for-apache-spark-app"></a>Подготовка .NET для приложения Apache Spark

1. Выполните инструкции из руководства по [началу работы](get-started.md) , чтобы создать приложение.

2. Опубликуйте свое приложение Spark .NET как автономное.

   В Linux можно выполнить следующую команду.

   ```bash
   dotnet publish -c Release -f netcoreapp2.1 -r ubuntu.16.04-x64
   ```

3. Создание `<your app>.zip` для опубликованных файлов.

   Вы можете выполнить следующую команду в Linux с помощью `zip`команды.

   ```bash
   zip -r <your app>.zip .
   ```

4. Отправьте следующее в распределенную файловую систему (например, HDFS, WASB, ADLS), к которой имеет доступ кластер.

   * `microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar`: Этот JAR-файл входит в состав пакета NuGet [Microsoft. Spark](https://www.nuget.org/packages/Microsoft.Spark/) и размещается в выходном каталоге сборки приложения.
   * `<your app>.zip`
   * Файлы (например, файлы зависимостей или общие данные, доступные для каждого рабочего процесса) или сборки (например, библиотеки DLL, содержащие определяемые пользователем функции `app` или библиотеки, от которых зависит) будут помещены в рабочий каталог каждого исполнителя.

## <a name="deploy-to-azure-hdinsight-spark"></a>Развертывание в Azure HDInsight Spark

[Azure HDInsight Spark](https://docs.microsoft.com/azure/hdinsight/spark/apache-spark-overview) — это реализация Майкрософт Apache Spark в облаке, которая позволяет пользователям запускать и настраивать кластеры Spark в Azure. Кластеры HDInsight Spark можно использовать для обработки данных, хранящихся в [службе хранилища Azure](https://azure.microsoft.com/services/storage/) или в [Azure Data Lake Storage](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-use-data-lake-storage-gen2).

> [!NOTE]
> Azure HDInsight Spark работает под управлением Linux. Если вы заинтересованы в развертывании приложения на Azure HDInsight Spark, убедитесь, что приложение совместимо .NET Standard и вы используете [компилятор .NET Core](https://dotnet.microsoft.com/download) для компиляции приложения.

### <a name="deploy-microsoftsparkworker"></a>Развертывание Microsoft. Spark. Worker

Этот шаг требуется только один раз для кластера.

Запустите `install-worker.sh` в кластере с помощью [действий сценария HDInsight](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-customize-cluster-linux).

|Параметр|Значение|
|-------|-----|
|Тип скрипта|Настраиваемый|
|name|Установка Microsoft. Spark. Worker|
|URI Bash Script|URI, в который был отправлен `install-worker.sh`. Например: `abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/install-worker.sh`|
|Типы узлов|Работников|
|Параметры|Для `install-worker.sh`параметров. Например, если вы передавали `install-worker.sh` в Azure Data Lake Gen 2, это `azure abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/Microsoft.Spark.Worker.<release>.tar.gz /usr/local/bin`будет.|

![Изображение действия сценария](./media/hdinsight-deployment/deployment-hdi-action-script.png)

## <a name="run-your-app"></a>Запуск приложения

Вы можете отправить задание в Azure HDInsight с помощью `spark-submit` или Apache Livy.

### <a name="use-spark-submit"></a>Использование Spark-Submit

Вы можете использовать команду [Spark-Submit](https://spark.apache.org/docs/latest/submitting-applications.html) , чтобы отправить задания .net для Apache Spark в Azure HDInsight.
 
1. `ssh`в один из головных узлов кластера.

1. Выполните `spark-submit`команду:

   ```bash
   spark-submit \
   --master yarn \
   --class org.apache.spark.deploy.DotnetRunner \
   --files <comma-separated list of assemblies that contain UDF definitions, if any> \
   abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar \
   abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/<your app>.zip <your app> <app arg 1> <app arg 2> ... <app arg n>
   ```

### <a name="use-apache-livy"></a>Использование Apache Livy

Для отправки заданий .NET для Apache Spark в кластер Azure HDInsight Spark можно использовать [Apache Livy](https://livy.incubator.apache.org/), REST API Apache Spark. Дополнительные сведения см. [в разделе Удаленные задания с помощью Apache Livy](https://docs.microsoft.com/azure/hdinsight/spark/apache-spark-livy-rest-interface).

В Linux можно выполнить следующую команду с помощью `curl`:

```bash
curl -k -v -X POST "https://<your spark cluster>.azurehdinsight.net/livy/batches" \
-u "<hdinsight username>:<hdinsight password>" \
-H "Content-Type: application/json" \
-H "X-Requested-By: <hdinsight username>" \
-d @- << EOF
{
    "file":"abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar",
    "className":"org.apache.spark.deploy.DotnetRunner",
    "files":["abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/<udf assembly>", "abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/<file>"],
    "args":["abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/<your app>.zip","<your app>","<app arg 1>","<app arg 2>,"...","<app arg n>"]
}
EOF
```

## <a name="next-steps"></a>Следующие шаги

В этом руководстве вы развернули приложение .NET для Apache Sparkного приложения в Azure HDInsight. Чтобы узнать больше о HDInsight, перейдите к документации по Azure HDInsight.

> [!div class="nextstepaction"]
> [Документация по Azure HDInsight](https://docs.microsoft.com/azure/hdinsight/)
