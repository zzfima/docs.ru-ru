---
title: Отладка приложения .NET для Apache Spark в Windows
description: Узнайте, как отлаживать приложения .NET для Apache Spark в Windows.
ms.date: 08/15/2019
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: 098c7519fe99ef04773c5e4b81685ca0f06f1272
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2019
ms.locfileid: "74281532"
---
# <a name="debug-a-net-for-apache-spark-application"></a><span data-ttu-id="cee60-103">Отладка приложения .NET для Apache Spark</span><span class="sxs-lookup"><span data-stu-id="cee60-103">Debug a .NET for Apache Spark application</span></span>

<span data-ttu-id="cee60-104">В этом практическом руководстве приведены команды, которые необходимы для отладки приложения .NET для Apache Spark и кода Scala в Windows.</span><span class="sxs-lookup"><span data-stu-id="cee60-104">This how-to provides the commands you need to run to debug your .NET for Apache Spark application and Scala code on Windows.</span></span>

## <a name="debug-your-application"></a><span data-ttu-id="cee60-105">Отладка приложения</span><span class="sxs-lookup"><span data-stu-id="cee60-105">Debug your application</span></span>

<span data-ttu-id="cee60-106">Откройте новое окно командной строки и выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="cee60-106">Open a new command prompt window, run the following:</span></span>

```shell
spark-submit \
  --class org.apache.spark.deploy.dotnet.DotnetRunner \
  --master local \
  <path-to-microsoft-spark-jar> \
  debug
```

<span data-ttu-id="cee60-107">При выполнении команды выводятся следующие выходные данные:</span><span class="sxs-lookup"><span data-stu-id="cee60-107">When you run the command, you see the following output:</span></span>

```console
***********************************************************************
* .NET Backend running debug mode. Press enter to exit *
***********************************************************************
```

<span data-ttu-id="cee60-108">В этом режиме отладки `DotnetRunner` не запускает приложение .NET, но ожидает его подключения.</span><span class="sxs-lookup"><span data-stu-id="cee60-108">In this debug mode, `DotnetRunner` does not launch the .NET application, but it waits for it to connect.</span></span> <span data-ttu-id="cee60-109">Не закрывайте окно командной строки.</span><span class="sxs-lookup"><span data-stu-id="cee60-109">Leave this command prompt window open.</span></span>

<span data-ttu-id="cee60-110">Теперь можно запустить приложение .NET с любым отладчиком.</span><span class="sxs-lookup"><span data-stu-id="cee60-110">Now you can run your .NET application with any debugger to debug your application.</span></span>

## <a name="debug-scala-code"></a><span data-ttu-id="cee60-111">Отладка кода Scala</span><span class="sxs-lookup"><span data-stu-id="cee60-111">Debug Scala code</span></span>

<span data-ttu-id="cee60-112">Если необходимо выполнить отладку кода на стороне Scala, например `DotnetRunner` или `DotnetBackendHandler`, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="cee60-112">If you need to debug the Scala side code, such as `DotnetRunner` or `DotnetBackendHandler`, run the following command:</span></span>

```shell
spark-submit \
  --driver-java-options -agentlib:jdwp=transport=dt_socket,server=y,suspend=n,address=5005 \
  --class org.apache.spark.deploy.dotnet.DotnetRunner \
  --master local \
  <path-to-microsoft-spark-jar> \
  <path-to-your-app-exe> <argument(s)-to-your-app>
```

<span data-ttu-id="cee60-113">После выполнения команды подключите отладчик к выполняющемуся процессу с помощью [Intellij](https://www.jetbrains.com/help/idea/attaching-to-local-process.html).</span><span class="sxs-lookup"><span data-stu-id="cee60-113">After you run the command, attach a debugger to the running process using [Intellij](https://www.jetbrains.com/help/idea/attaching-to-local-process.html).</span></span>

## <a name="next-steps"></a><span data-ttu-id="cee60-114">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="cee60-114">Next steps</span></span>

* [<span data-ttu-id="cee60-115">Начало работы с .NET для Apache Spark</span><span class="sxs-lookup"><span data-stu-id="cee60-115">Get started with .NET for Apache Spark</span></span>](../tutorials/get-started.md)
* [<span data-ttu-id="cee60-116">Развертывание приложения .NET для Apache Spark в Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="cee60-116">Deploy a .NET for Apache Spark application to Azure HDInsight</span></span>](../tutorials/hdinsight-deployment.md)
* [<span data-ttu-id="cee60-117">Развертывание приложения .NET для Apache Spark в Databricks</span><span class="sxs-lookup"><span data-stu-id="cee60-117">Deploy a .NET for Apache Spark application to Databricks</span></span>](../tutorials/databricks-deployment.md)
* [<span data-ttu-id="cee60-118">Развертывание приложения .NET для Apache Spark в Amazon EMR Spark</span><span class="sxs-lookup"><span data-stu-id="cee60-118">Deploy a .NET for Apache Spark application to Amazon EMR Spark</span></span>](../tutorials/amazon-emr-spark-deployment.md)
