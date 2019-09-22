---
title: Развертывание приложения .NET для Apache Spark в Azure HDInsight
description: Узнайте, как развернуть приложение .NET для Apache Spark в HDInsight.
ms.date: 05/17/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 2e8da5497035a83fde75bf91a7d21437d510b480
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117981"
---
# <a name="deploy-a-net-for-apache-spark-application-to-azure-hdinsight"></a>Развертывание приложения .NET для Apache Spark в Azure HDInsight

В этом руководстве рассматривается развертывание приложения .NET для Apache Spark в Azure HDInsight.

В этом руководстве вы узнаете, как:

> [!div class="checklist"]
>
> * Подготовка Microsoft.Spark.Worker
> * Публикация приложения Spark .NET
> * Развертывание приложения в Azure HDInsight
> * Запуск приложения

## <a name="prerequisites"></a>Предварительные требования

Прежде чем начать, сделайте следующее:

* Скачайте [Обозреватель службы хранилища Azure](https://azure.microsoft.com/features/storage-explorer/).
* Скачайте файл [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) на локальный компьютер. Это вспомогательный скрипт, который будет использоваться позже для копирования зависимых файлов .NET для Apache Spark в рабочие узлы кластера Spark.

## <a name="prepare-worker-dependencies"></a>Подготовка зависимостей рабочей роли

**Microsoft.Spark.Worker** — это серверный компонент, который размещается в отдельных рабочих узлах кластера Spark. Если вам нужно выполнить определяемую пользователем функцию C#, Spark необходимо знать, как запустить среду CLR .NET для выполнения этой функции. **Microsoft.Spark.Worker** предоставляет Spark коллекцию классов, которые обеспечивают такую возможность.

1. Выберите выпуск netcoreapp компонента [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) для Linux, который будет развернут в кластере.

   Например, чтобы использовать `.NET for Apache Spark v0.1.0` с `netcoreapp2.1`, скачайте выпуск [Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz](https://github.com/dotnet/spark/releases/download/v0.1.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz).

2. Передайте файлы `Microsoft.Spark.Worker.<release>.tar.gz` и [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) в распределенную файловую систему (например, HDFS, WASB или ADLS), к которой есть доступ у кластера.

## <a name="prepare-your-net-for-apache-spark-app"></a>Подготовка приложения .NET для Apache Spark

1. Выполните сборку приложения согласно инструкциям из [руководства по началу работы](get-started.md).

2. Опубликуйте приложение .NET для Spark как автономное.

   В Linux можно выполнить приведенную ниже команду.

   ```dotnetcli
   dotnet publish -c Release -f netcoreapp2.1 -r ubuntu.16.04-x64
   ```

3. Создайте `<your app>.zip` для опубликованных файлов.

   В Linux можно выполнить приведенную ниже команду с помощью `zip`.

   ```bash
   zip -r <your app>.zip .
   ```

4. Передайте в распределенную файловую систему (например, HDFS, WASB или ADLS), к которой есть доступ у кластера, следующие файлы:

   * `microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar`. Этот JAR-файл входит в состав пакета NuGet [Microsoft.Spark](https://www.nuget.org/packages/Microsoft.Spark/) и размещается в выходном каталоге сборки приложения.
   * `<your app>.zip`
   * Файлы (например, файлы зависимостей или общие данные, доступные каждой рабочей роли) или сборки (например, библиотеки DLL, содержащие определяемые пользователем функции, или библиотеки, от которых зависит `app`), которые необходимо поместить в рабочий каталог каждого исполнителя.

## <a name="deploy-to-azure-hdinsight-spark"></a>Развертывание в Azure HDInsight Spark

[Azure HDInsight Spark](https://docs.microsoft.com/azure/hdinsight/spark/apache-spark-overview) — это предоставляемая корпорацией Майкрософт реализация Apache Spark в облаке, которая позволяет пользователям запускать и настраивать кластеры Spark в Azure. Кластеры HDInsight Spark можно использовать для обработки данных, хранящихся в [службе хранилища Azure](https://azure.microsoft.com/services/storage/) или [Azure Data Lake Storage](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-use-data-lake-storage-gen2).

> [!NOTE]
> Azure HDInsight Spark работает под управлением Linux. Если вы хотите развернуть приложение в Azure HDInsight Spark, оно должно быть совместимо с .NET Standard, а для его компиляции необходимо использовать [компилятор .NET Core](https://dotnet.microsoft.com/download).

### <a name="deploy-microsoftsparkworker"></a>Развертывание Microsoft.Spark.Worker

Этот шаг необходимо выполнить для кластера только один раз.

Выполните скрипт `install-worker.sh` в кластере с помощью [действий скриптов HDInsight](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-customize-cluster-linux).

|Параметр|Значение|
|-------|-----|
|Тип скрипта|Другой|
|name|Установка Microsoft.Spark.Worker|
|URI bash-скрипта|Универсальный код ресурса (URI), по которому был отправлен файл `install-worker.sh`. Например: `abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/install-worker.sh`|
|Типы узлов|Рабочий узел|
|Параметры|Параметры скрипта `install-worker.sh`. Например, если файл `install-worker.sh` был отправлен в Azure Data Lake 2-го поколения, параметры будут следующими: `azure abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/Microsoft.Spark.Worker.<release>.tar.gz /usr/local/bin`.|

![Изображение действия скрипта](./media/hdinsight-deployment/deployment-hdi-action-script.png)

## <a name="run-your-app"></a>Запуск приложения

Задание можно отправить в Azure HDInsight с помощью `spark-submit` или Apache Livy.

### <a name="use-spark-submit"></a>Использование команды spark-submit

Для отправки заданий .NET для Apache Spark в Azure HDInsight можно использовать команду [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html).
 
1. Подключитесь к одному из головных узлов кластера с помощью команды `ssh`.

1. Выполните команду `spark-submit`:

   ```bash
   spark-submit \
   --master yarn \
   --class org.apache.spark.deploy.dotnet.DotnetRunner \
   --files <comma-separated list of assemblies that contain UDF definitions, if any> \
   abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar \
   abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/<your app>.zip <your app> <app arg 1> <app arg 2> ... <app arg n>
   ```

### <a name="use-apache-livy"></a>Использование Apache Livy

Для отправки заданий .NET для Apache Spark в кластер Azure HDInsight Spark можно использовать [Apache Livy](https://livy.incubator.apache.org/), интерфейс REST API для Apache Spark. Дополнительные сведения см. в статье [Работа с удаленными заданиями с помощью Apache Livy](https://docs.microsoft.com/azure/hdinsight/spark/apache-spark-livy-rest-interface).

В Linux можно выполнить следующую команду с помощью `curl`:

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

## <a name="next-steps"></a>Следующие шаги

В этом руководстве вы развернули приложение .NET для Apache Spark в Azure HDInsight. Дополнительные сведения об HDInsight см. в документации по Azure HDInsight.

> [!div class="nextstepaction"]
> [Документация по Azure HDInsight](https://docs.microsoft.com/azure/hdinsight/)
