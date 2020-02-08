---
title: Отладка приложения .NET для Apache Spark в Windows
description: Узнайте, как отлаживать приложения .NET для Apache Spark в Windows.
ms.date: 01/29/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: 25f5291c47dc1cdf2668cb077fae7439e330cc1c
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/01/2020
ms.locfileid: "76919928"
---
# <a name="debug-a-net-for-apache-spark-application"></a><span data-ttu-id="4cebb-103">Отладка приложения .NET для Apache Spark</span><span class="sxs-lookup"><span data-stu-id="4cebb-103">Debug a .NET for Apache Spark application</span></span>

<span data-ttu-id="4cebb-104">Это практическое руководство содержит сведения о том, как отлаживать приложения .NET для Apache Spark в Windows.</span><span class="sxs-lookup"><span data-stu-id="4cebb-104">This how-to provides the steps to debug your .NET for Apache Spark application on Windows.</span></span>

## <a name="debug-your-application"></a><span data-ttu-id="4cebb-105">Отладка приложения</span><span class="sxs-lookup"><span data-stu-id="4cebb-105">Debug your application</span></span>

<span data-ttu-id="4cebb-106">Откройте новое окно командной строки и выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="4cebb-106">Open a new command prompt window and run the following command:</span></span>

```shell
spark-submit \
  --class org.apache.spark.deploy.dotnet.DotnetRunner \
  --master local \
  <path-to-microsoft-spark-jar> \
  debug
```

<span data-ttu-id="4cebb-107">При выполнении команды выводятся следующие выходные данные:</span><span class="sxs-lookup"><span data-stu-id="4cebb-107">When you run the command, you see the following output:</span></span>

```console
***********************************************************************
* .NET Backend running debug mode. Press enter to exit *
***********************************************************************
```

<span data-ttu-id="4cebb-108">В режиме отладки DotnetRunner не запускает приложение .NET, а ожидает, пока вы запустите это приложение вручную.</span><span class="sxs-lookup"><span data-stu-id="4cebb-108">In debug mode, DotnetRunner does not launch the .NET application, but instead waits for you to start the .NET app.</span></span> <span data-ttu-id="4cebb-109">Оставьте окно командной строки открытым и запустите приложение .NET через отладчик C#, чтобы выполнить отладку приложения.</span><span class="sxs-lookup"><span data-stu-id="4cebb-109">Leave this command prompt window open and start your .NET application through C# debugger to debug your application.</span></span> <span data-ttu-id="4cebb-110">Запустите приложение .NET через отладчик C# ([отладчик Visual Studio для Windows/macOS](https://visualstudio.microsoft.com/vs/) или [расширения отладчика C# для Visual Studio Code](https://code.visualstudio.com/Docs/editor/debugging)), чтобы выполнить отладку приложения.</span><span class="sxs-lookup"><span data-stu-id="4cebb-110">Start your .NET application with a C# debugger ([Visual Studio Debugger for Windows/macOS](https://visualstudio.microsoft.com/vs/) or [C# Debugger Extension in Visual Studio Code](https://code.visualstudio.com/Docs/editor/debugging)) to debug your application.</span></span>

## <a name="debug-a-user-defined-function-udf"></a><span data-ttu-id="4cebb-111">Отладка определяемой пользователем функции (UDF)</span><span class="sxs-lookup"><span data-stu-id="4cebb-111">Debug a user-defined function (UDF)</span></span>

> [!NOTE]
> <span data-ttu-id="4cebb-112">Определяемые пользователем функции поддерживаются только в Windows с отладчиком Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="4cebb-112">User-defined functions are supported only on Windows with Visual Studio Debugger.</span></span>

<span data-ttu-id="4cebb-113">Перед запуском `spark-submit` установите следующее значение переменной среды:</span><span class="sxs-lookup"><span data-stu-id="4cebb-113">Before running `spark-submit`, set the following environment variable:</span></span>

```bat
set DOTNET_WORKER_DEBUG=1
```

<span data-ttu-id="4cebb-114">При запуске приложения Spark появится окно `Choose Just-In-Time Debugger`.</span><span class="sxs-lookup"><span data-stu-id="4cebb-114">When you run your Spark application, a `Choose Just-In-Time Debugger` window will pop up.</span></span> <span data-ttu-id="4cebb-115">Выберите здесь отладчик Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="4cebb-115">Choose a Visual Studio debugger.</span></span>

<span data-ttu-id="4cebb-116">Отладчик остановит выполнение программы в следующей строке файла [TaskRunner.cs](https://github.com/dotnet/spark/blob/5e9c08b430b4bc56b5f42252c4b73437377afaed/src/csharp/Microsoft.Spark.Worker/TaskRunner.cs#L52):</span><span class="sxs-lookup"><span data-stu-id="4cebb-116">The debugger will break at the following location in [TaskRunner.cs](https://github.com/dotnet/spark/blob/5e9c08b430b4bc56b5f42252c4b73437377afaed/src/csharp/Microsoft.Spark.Worker/TaskRunner.cs#L52):</span></span>

```csharp
if (EnvironmentUtils.GetEnvironmentVariableAsBool("DOTNET_WORKER_DEBUG"))
{
    Debugger.Launch(); // <-- The debugger will break here.
}
```

<span data-ttu-id="4cebb-117">Перейдите к файлу *.cs*, который содержит определяемую пользователем функцию, которую вам нужно отладить, и [установите точку останова](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints?view=vs-2019).</span><span class="sxs-lookup"><span data-stu-id="4cebb-117">Navigate to the *.cs* file that contains the UDF that you plan to debug, and [set a breakpoint](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints?view=vs-2019).</span></span> <span data-ttu-id="4cebb-118">От точки останова поступит сообщение `The breakpoint will not currently be hit`, так как рабочая роль еще не загрузила сборку с нужной функцией UDF.</span><span class="sxs-lookup"><span data-stu-id="4cebb-118">The breakpoint will say `The breakpoint will not currently be hit` because the worker hasn't loaded the assembly that contains UDF yet.</span></span>

<span data-ttu-id="4cebb-119">Нажмите `F5`, чтобы продолжить работу приложения до момента, когда будет достигнута эта точка останова.</span><span class="sxs-lookup"><span data-stu-id="4cebb-119">Hit `F5` to continue your application and the breakpoint will eventually be hit.</span></span>

> [!NOTE] 
> <span data-ttu-id="4cebb-120">Для каждой задачи откроется окно выбора JIT-отладчика.</span><span class="sxs-lookup"><span data-stu-id="4cebb-120">The Choose Just-In-Time Debugger window pops up for each task.</span></span> <span data-ttu-id="4cebb-121">Чтобы всплывающих окон не было слишком много, настройте небольшое число исполнителей.</span><span class="sxs-lookup"><span data-stu-id="4cebb-121">To avoid excessive pop-ups, set the number of executors to a low number.</span></span> <span data-ttu-id="4cebb-122">Например, параметр **--master local [1]** для команды spark-submit позволяет задать для числа задач значение 1. Это означает, что запускается только один экземпляр отладчика.</span><span class="sxs-lookup"><span data-stu-id="4cebb-122">For example, you can use the **--master local[1]** option for spark-submit to set the number of tasks to 1, which launches a single debugger instance.</span></span>

## <a name="debug-scala-code"></a><span data-ttu-id="4cebb-123">Отладка кода Scala</span><span class="sxs-lookup"><span data-stu-id="4cebb-123">Debug Scala code</span></span>

<span data-ttu-id="4cebb-124">Если вам нужно выполнить отладку кода на стороне Scala (`DotnetRunner`, `DotnetBackendHandler` и т. д.), можно использовать следующую команду и подключить отладчик к выполняющемуся процессу с помощью [IntelliJ](https://www.jetbrains.com/help/idea/attaching-to-local-process.html):</span><span class="sxs-lookup"><span data-stu-id="4cebb-124">If you need to debug the Scala-side code (`DotnetRunner`, `DotnetBackendHandler`, etc.), you can use the following command and attach a debugger to the running process using [IntelliJ](https://www.jetbrains.com/help/idea/attaching-to-local-process.html):</span></span>

```shell
spark-submit \
  --driver-java-options -agentlib:jdwp=transport=dt_socket,server=y,suspend=n,address=5005 \
  --class org.apache.spark.deploy.dotnet.DotnetRunner \
  --master local \
  <path-to-microsoft-spark-jar> \
  <path-to-your-app-exe> <argument(s)-to-your-app>
```

<span data-ttu-id="4cebb-125">После выполнения команды подключите отладчик к выполняющемуся процессу с помощью [Intellij](https://www.jetbrains.com/help/idea/attaching-to-local-process.html).</span><span class="sxs-lookup"><span data-stu-id="4cebb-125">After you run the command, attach a debugger to the running process using [Intellij](https://www.jetbrains.com/help/idea/attaching-to-local-process.html).</span></span>

## <a name="next-steps"></a><span data-ttu-id="4cebb-126">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="4cebb-126">Next steps</span></span>

* [<span data-ttu-id="4cebb-127">Начало работы с .NET для Apache Spark</span><span class="sxs-lookup"><span data-stu-id="4cebb-127">Get started with .NET for Apache Spark</span></span>](../tutorials/get-started.md)
* [<span data-ttu-id="4cebb-128">Развертывание приложения .NET для Apache Spark в Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="4cebb-128">Deploy a .NET for Apache Spark application to Azure HDInsight</span></span>](../tutorials/hdinsight-deployment.md)
* [<span data-ttu-id="4cebb-129">Развертывание приложения .NET для Apache Spark в Databricks</span><span class="sxs-lookup"><span data-stu-id="4cebb-129">Deploy a .NET for Apache Spark application to Databricks</span></span>](../tutorials/databricks-deployment.md)
* [<span data-ttu-id="4cebb-130">Развертывание приложения .NET для Apache Spark в Amazon EMR Spark</span><span class="sxs-lookup"><span data-stu-id="4cebb-130">Deploy a .NET for Apache Spark application to Amazon EMR Spark</span></span>](../tutorials/amazon-emr-spark-deployment.md)
