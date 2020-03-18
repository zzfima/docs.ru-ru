---
title: Отладка приложения .NET для Apache Spark в Windows
description: Узнайте, как отлаживать приложения .NET для Apache Spark в Windows.
ms.date: 01/29/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: dac6aed1f7faba7f07b722a6dac0da930ab9ec66
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "79185811"
---
# <a name="debug-a-net-for-apache-spark-application"></a>Отладка приложения .NET для Apache Spark

Это практическое руководство содержит сведения о том, как отлаживать приложения .NET для Apache Spark в Windows.

## <a name="debug-your-application"></a>Отладка приложения

Откройте новое окно командной строки и выполните следующую команду:

```shell
spark-submit \
  --class org.apache.spark.deploy.dotnet.DotnetRunner \
  --master local \
  <path-to-microsoft-spark-jar> \
  debug
```

При выполнении команды выводятся следующие выходные данные:

```console
***********************************************************************
* .NET Backend running debug mode. Press enter to exit *
***********************************************************************
```

В режиме отладки DotnetRunner не запускает приложение .NET, а ожидает, пока вы запустите это приложение вручную. Оставьте окно командной строки открытым и запустите приложение .NET через отладчик C#, чтобы выполнить отладку приложения. Запустите приложение .NET через отладчик C# ([отладчик Visual Studio для Windows/macOS](https://visualstudio.microsoft.com/vs/) или [расширения отладчика C# для Visual Studio Code](https://code.visualstudio.com/Docs/editor/debugging)), чтобы выполнить отладку приложения.

## <a name="debug-a-user-defined-function-udf"></a>Отладка определяемой пользователем функции (UDF)

> [!NOTE]
> Определяемые пользователем функции поддерживаются только в Windows с отладчиком Visual Studio.

Перед запуском `spark-submit` установите следующее значение переменной среды:

```bat
set DOTNET_WORKER_DEBUG=1
```

При запуске приложения Spark появится окно `Choose Just-In-Time Debugger`. Выберите здесь отладчик Visual Studio.

Отладчик остановит выполнение программы в следующей строке файла [TaskRunner.cs](https://github.com/dotnet/spark/blob/5e9c08b430b4bc56b5f42252c4b73437377afaed/src/csharp/Microsoft.Spark.Worker/TaskRunner.cs#L52):

```csharp
if (EnvironmentUtils.GetEnvironmentVariableAsBool("DOTNET_WORKER_DEBUG"))
{
    Debugger.Launch(); // <-- The debugger will break here.
}
```

Перейдите к файлу *.cs*, который содержит определяемую пользователем функцию, которую вам нужно отладить, и [установите точку останова](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints?view=vs-2019). От точки останова поступит сообщение `The breakpoint will not currently be hit`, так как рабочая роль еще не загрузила сборку с нужной функцией UDF.

Нажмите `F5`, чтобы продолжить работу приложения до момента, когда будет достигнута эта точка останова.

> [!NOTE]
> Для каждой задачи откроется окно выбора JIT-отладчика. Чтобы всплывающих окон не было слишком много, настройте небольшое число исполнителей. Например, параметр **--master local [1]** для команды spark-submit позволяет задать для числа задач значение 1. Это означает, что запускается только один экземпляр отладчика.

## <a name="debug-scala-code"></a>Отладка кода Scala

Если вам нужно выполнить отладку кода на стороне Scala (`DotnetRunner`, `DotnetBackendHandler` и т. д.), можно использовать следующую команду и подключить отладчик к выполняющемуся процессу с помощью [IntelliJ](https://www.jetbrains.com/help/idea/attaching-to-local-process.html):

```shell
spark-submit \
  --driver-java-options -agentlib:jdwp=transport=dt_socket,server=y,suspend=n,address=5005 \
  --class org.apache.spark.deploy.dotnet.DotnetRunner \
  --master local \
  <path-to-microsoft-spark-jar> \
  <path-to-your-app-exe> <argument(s)-to-your-app>
```

После выполнения команды подключите отладчик к выполняющемуся процессу с помощью [Intellij](https://www.jetbrains.com/help/idea/attaching-to-local-process.html).

## <a name="next-steps"></a>Дальнейшие действия

* [Начало работы с .NET для Apache Spark](../tutorials/get-started.md)
* [Развертывание приложения .NET для Apache Spark в Azure HDInsight](../tutorials/hdinsight-deployment.md)
* [Развертывание приложения .NET для Apache Spark в Databricks](../tutorials/databricks-deployment.md)
* [Развертывание приложения .NET для Apache Spark в Amazon EMR Spark](../tutorials/amazon-emr-spark-deployment.md)
