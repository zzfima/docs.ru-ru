---
title: Начало работы с .NET для Apache Spark
description: Узнайте, как запустить .NET для Apache Spark приложения с помощью .NET Core в Windows.
ms.date: 06/27/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 7ce7d7aec6c15385d3d797d5a548519eea33b764
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/13/2019
ms.locfileid: "69577011"
---
# <a name="tutorial-get-started-with-net-for-apache-spark"></a>Учебник. Начало работы с .NET для Apache Spark

В этом учебнике описывается, как запустить .NET для Apache Spark приложения с помощью .NET Core в Windows.

В этом руководстве вы узнаете, как:

> [!div class="checklist"]
> * Подготовка среды Windows для .NET для Apache Spark
> * Скачайте **Microsoft. Spark. Worker**
> * Создание и запуск простого .NET для Apache Spark приложения

## <a name="prepare-your-environment"></a>Подготовка среды

Перед началом работы убедитесь, что вы можете запустить `dotnet` `mvn`, `java`,, `spark-shell` из командной строки. Если ваша среда уже подготовлена, можно перейти к следующему разделу. Если вы не можете выполнить какие либо команды, выполните следующие действия.

1. Скачайте и установите [пакет SDK для .NET Core 2.1 x](https://dotnet.microsoft.com/download/dotnet-core/2.1). При установке пакета SDK в `dotnet` путь добавляется цепочки инструментов. Используйте команду `dotnet --version` PowerShell для проверки установки.

2. Установите [Visual studio 2017](https://www.visualstudio.com/downloads/) или [Visual Studio 2019](https://visualstudio.microsoft.com/vs/preview/) с последними обновлениями. Вы можете использовать сообщество, профессиональный выпуск или Enterprise. Версия сообщества бесплатная.

   Во время установки выберите следующие рабочие нагрузки:
      * Разработка классических приложений .NET
          * Все необходимые компоненты
          * Средства разработки .NET Framework 4.6.1
      * Кроссплатформенная разработка .NET Core
          * Все необходимые компоненты

3. Установите [Java 1,8](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html).

    * Выберите соответствующую версию для вашей операционной системы. Например, выберите **JDK-8u201-Windows-x64. exe** для компьютера под Windows x64.
    * Используйте команду `java -version` PowerShell для проверки установки.

4. Установите [Apache Maven 3.6.0 +](https://maven.apache.org/download.cgi).
    * Скачайте [Apache Maven 3.6.0](http://mirror.metrocast.net/apache/maven/maven-3/3.6.0/binaries/apache-maven-3.6.0-bin.zip).
    * Извлеките в локальный каталог. Например, `c:\bin\apache-maven-3.6.0\`.
    * Добавьте Apache Maven в [переменную среды PATH](https://www.java.com/en/download/help/path.xml). При извлечении в `c:\bin\apache-maven-3.6.0\`необходимо добавить `c:\bin\apache-maven-3.6.0\bin` в путь.
    * Используйте команду `mvn -version` PowerShell для проверки установки.

5. Установите [Apache Spark 2.3 +](https://spark.apache.org/downloads.html). Apache Spark 2.4 + не поддерживается.
    * Скачайте [Apache Spark 2.3](https://spark.apache.org/downloads.html) и извлеките его в локальную папку с помощью такого средства, как [7-Zip](https://www.7-zip.org/) или [WinZip](https://www.winzip.com/). Например, вы можете извлечь его в `c:\bin\spark-2.3.2-bin-hadoop2.7\`.
    * Добавьте Apache Spark в [переменную среды PATH](https://www.java.com/en/download/help/path.xml). При извлечении в `c:\bin\spark-2.3.2-bin-hadoop2.7\`необходимо добавить `c:\bin\spark-2.3.2-bin-hadoop2.7\bin` в путь.
    * Добавьте [новую переменную среды](https://www.java.com/en/download/help/path.xml) с `SPARK_HOME`именем. Если вы извлекли `C:\bin\spark-2.3.2-bin-hadoop2.7\`в, `C:\bin\spark-2.3.2-bin-hadoop2.7\` используйте для **значения переменной**.
    * Убедитесь, что вы можете запустить `spark-shell` из командной строки.

6. Настройте [WinUtils](https://github.com/steveloughran/winutils).
    * Скачайте двоичный файл **winutils. exe** из [репозитория winutils](https://github.com/steveloughran/winutils). Выберите версию Hadoop, с которой было скомпилировано распространение Spark. Например, вы используете **Hadoop-2.7.1** для **Spark 2.3.2**. Версия Hadoop помечается в конце имени папки установки Spark.
    * Сохраните двоичный файл **winutils. exe** в каталоге по своему усмотрению. Например, `c:\hadoop\bin`.
    * Установите `HADOOP_HOME` для отражения каталога с **winutils. exe** без `bin`. Например, `c:\hadoop`.
    * Задайте переменную среды PATH для включения `%HADOOP_HOME%\bin`.

Перед переходом к следующему разделу `java`проверьте, `spark-shell` можно ли выполнить `dotnet`команду,, `mvn`, в командной строке.

## <a name="download-the-microsoftsparkworker-release"></a>Скачайте выпуск Microsoft. Spark. Worker

1. Скачайте выпуск [Microsoft. Spark. Worker](https://github.com/dotnet/spark/releases) со страницы .net для Apache Spark GitHub releases на локальный компьютер. Например, вы можете скачать его по пути, `c:\bin\Microsoft.Spark.Worker\`.

2. Создайте [новую переменную среды](https://www.java.com/en/download/help/path.xml) с `DotnetWorkerPath` именем и установите ее в каталог, в который вы скачали и извлекли файл **Microsoft. Spark. Worker**. Например, `c:\bin\Microsoft.Spark.Worker`.

## <a name="clone-the-net-for-apache-spark-github-repo"></a>Клонирование .NET для Apache Spark репозитория GitHub

Используйте следующую команду [GitBash](https://gitforwindows.org/) , чтобы клонировать репозиторий .net для Apache Spark на компьютер.

```bash
git clone https://github.com/dotnet/spark.git c:\github\dotnet-spark
```

## <a name="write-a-net-for-apache-spark-app"></a>Написание .NET для приложения Apache Spark

1. Откройте **Visual Studio** и выберите **файл > создать новый проект > консольное приложение (.NET Core)** . Назовите приложение **хеллоспарк**.

2. Установите [пакет NuGet Microsoft. Spark](https://www.nuget.org/profiles/spark). Дополнительные сведения об установке пакетов NuGet см. в разделе [различные способы установки пакета NuGet](https://docs.microsoft.com/nuget/consume-packages/ways-to-install-a-package).

3. В **Обозреватель решений**откройте **Program.CS** и напишите следующий C# код:

   ```csharp
     var spark = SparkSession.Builder().GetOrCreate();
     var df = spark.Read().Json("people.json");
     df.Show();
   ```

4. Постройте решение.

## <a name="run-your-net-for-apache-spark-app"></a>Запуск .NET для приложения Apache Spark

1. Откройте **PowerShell** и измените каталог на папку, в которой хранится ваше приложение.

   ```powershell
   cd <your-app-output-directory>
   ```

2. Создайте файл с именем **People. JSON** со следующим содержимым:

   ```json
   {"name":"Michael"}
   {"name":"Andy", "age":30}
   {"name":"Justin", "age":19}
   ```

3. Используйте следующую команду PowerShell для запуска приложения:

   ```powershell
    spark-submit `
    --class org.apache.spark.deploy.dotnet.DotnetRunner `
    --master local `
    microsoft-spark-2.4.x-<version>.jar `
    dotnet HelloSpark.dll
    ```

Поздравляем! Вы успешно создали и запустили .NET для Apache Sparkного приложения.

## <a name="next-steps"></a>Следующие шаги

В этом руководстве вы узнали, как:
> [!div class="checklist"]
> * Подготовка среды Windows для .NET для Apache Spark
> * Скачайте **Microsoft. Spark. Worker**
> * Создание и запуск простого .NET для Apache Spark приложения

Дополнительные сведения см. на странице ресурсов.
> [!div class="nextstepaction"]
> [Ресурсы .NET для Apache Spark](../resources/index.md)
