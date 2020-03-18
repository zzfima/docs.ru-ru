---
title: Отправка задания .NET для Apache Spark в Azure HDInsight
description: Узнайте, как отправить задание .NET для Apache Spark в Azure HDInsight с помощью spark-submit и Apache Livy.
ms.date: 11/19/2019
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: 83359f7f613b500a4ce121ce1612cda0ad1191ab
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "79185795"
---
# <a name="submit-a-net-for-apache-spark-job-to-azure-hdinsight"></a><span data-ttu-id="1c8b1-103">Отправка задания .NET для Apache Spark в Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="1c8b1-103">Submit a .NET for Apache Spark job to Azure HDInsight</span></span>

<span data-ttu-id="1c8b1-104">Существует два способа развертывания задания .NET для Apache Spark в HDInsight: команда `spark-submit` и Apache Livy.</span><span class="sxs-lookup"><span data-stu-id="1c8b1-104">There are two ways to deploy your .NET for Apache Spark job to HDInsight: `spark-submit` and Apache Livy.</span></span>

## <a name="deploy-using-spark-submit"></a><span data-ttu-id="1c8b1-105">Развертывание с помощью spark-submit</span><span class="sxs-lookup"><span data-stu-id="1c8b1-105">Deploy using spark-submit</span></span>

<span data-ttu-id="1c8b1-106">Для отправки заданий .NET для Apache Spark в Azure HDInsight можно использовать команду [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html).</span><span class="sxs-lookup"><span data-stu-id="1c8b1-106">You can use the [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) command to submit .NET for Apache Spark jobs to Azure HDInsight.</span></span>

1. <span data-ttu-id="1c8b1-107">Перейдите к кластеру HDInsight Spark на портале Azure и выберите **SSH и вход в кластер**.</span><span class="sxs-lookup"><span data-stu-id="1c8b1-107">Navigate to your HDInsight Spark cluster in Azure portal, and then select **SSH + Cluster login**.</span></span>

2. <span data-ttu-id="1c8b1-108">Скопируйте данные для входа по протоколу SSH и вставьте имя для входа в терминал.</span><span class="sxs-lookup"><span data-stu-id="1c8b1-108">Copy the ssh login information and paste the login into a terminal.</span></span> <span data-ttu-id="1c8b1-109">Войдите в кластер, используя пароль, заданный во время создания кластера.</span><span class="sxs-lookup"><span data-stu-id="1c8b1-109">Sign in to your cluster using the password you set during cluster creation.</span></span> <span data-ttu-id="1c8b1-110">Вы должны увидеть сообщение с приветствием в Ubuntu и Spark.</span><span class="sxs-lookup"><span data-stu-id="1c8b1-110">You should see messages welcoming you to Ubuntu and Spark.</span></span>

3. <span data-ttu-id="1c8b1-111">Используйте команду **spark-submit**, чтобы запустить приложение в кластере HDInsight.</span><span class="sxs-lookup"><span data-stu-id="1c8b1-111">Use the **spark-submit** command to run your app on your HDInsight cluster.</span></span> <span data-ttu-id="1c8b1-112">Не забудьте заменить **mycontainer** и **mystorageaccount** в примере скрипта, указав фактические имена контейнера больших двоичных объектов и учетной записи хранения.</span><span class="sxs-lookup"><span data-stu-id="1c8b1-112">Remember to replace **mycontainer** and **mystorageaccount** in the example script with the actual names of your blob container and storage account.</span></span> <span data-ttu-id="1c8b1-113">Кроме того, обязательно замените `microsoft-spark-2.3.x-0.6.0.jar` соответствующим JAR-файлом, используемым для развертывания.</span><span class="sxs-lookup"><span data-stu-id="1c8b1-113">Also, be sure to replace `microsoft-spark-2.3.x-0.6.0.jar` with the appropriate jar file you're using for deployment.</span></span> <span data-ttu-id="1c8b1-114">`2.3.x` представляет версию Apache Spark, а `0.6.0` представляет версию [рабочего процесса .NET для Apache Spark](https://github.com/dotnet/spark/releases).</span><span class="sxs-lookup"><span data-stu-id="1c8b1-114">`2.3.x` represents the version of Apache Spark, and `0.6.0` represents the version of the [.NET for Apache Spark worker](https://github.com/dotnet/spark/releases).</span></span>

   ```bash
   $SPARK_HOME/bin/spark-submit \
   --master yarn \
   --class org.apache.spark.deploy.dotnet.DotnetRunner \
   wasbs://mycontainer@mystorageaccount.blob.core.windows.net/microsoft-spark-2.3.x-0.6.0.jar \
   wasbs://mycontainer@mystorageaccount.blob.core.windows.net/publish.zip mySparkApp
   ```

## <a name="deploy-using-apache-livy"></a><span data-ttu-id="1c8b1-115">Развертывание с помощью Apache Livy</span><span class="sxs-lookup"><span data-stu-id="1c8b1-115">Deploy using Apache Livy</span></span>

<span data-ttu-id="1c8b1-116">Для отправки заданий .NET для Apache Spark в кластер Azure HDInsight Spark можно использовать [Apache Livy](https://livy.incubator.apache.org/), интерфейс REST API для Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="1c8b1-116">You can use [Apache Livy](https://livy.incubator.apache.org/), the Apache Spark REST API, to submit .NET for Apache Spark jobs to an Azure HDInsight Spark cluster.</span></span> <span data-ttu-id="1c8b1-117">Дополнительные сведения см. в статье [Работа с удаленными заданиями с помощью Apache Livy](https://docs.microsoft.com/azure/hdinsight/spark/apache-spark-livy-rest-interface).</span><span class="sxs-lookup"><span data-stu-id="1c8b1-117">For more information, see [Remote jobs with Apache Livy](https://docs.microsoft.com/azure/hdinsight/spark/apache-spark-livy-rest-interface).</span></span>

<span data-ttu-id="1c8b1-118">В Linux можно выполнить следующую команду с помощью `curl`:</span><span class="sxs-lookup"><span data-stu-id="1c8b1-118">You can run the following command on Linux using `curl`:</span></span>

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

## <a name="next-steps"></a><span data-ttu-id="1c8b1-119">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="1c8b1-119">Next steps</span></span>

* [<span data-ttu-id="1c8b1-120">Начало работы с .NET для Apache Spark</span><span class="sxs-lookup"><span data-stu-id="1c8b1-120">Get started with .NET for Apache Spark</span></span>](../tutorials/get-started.md)
* [<span data-ttu-id="1c8b1-121">Развертывание приложения .NET для Apache Spark в Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="1c8b1-121">Deploy a .NET for Apache Spark application to Azure HDInsight</span></span>](../tutorials/hdinsight-deployment.md)
* [<span data-ttu-id="1c8b1-122">Документация по HDInsight</span><span class="sxs-lookup"><span data-stu-id="1c8b1-122">HDInsight Documentation</span></span>](https://docs.microsoft.com/azure/hdinsight/)
