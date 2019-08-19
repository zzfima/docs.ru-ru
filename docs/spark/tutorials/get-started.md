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
# <a name="tutorial-get-started-with-net-for-apache-spark"></a><span data-ttu-id="9500e-103">Учебник. Начало работы с .NET для Apache Spark</span><span class="sxs-lookup"><span data-stu-id="9500e-103">Tutorial: Get started with .NET for Apache Spark</span></span>

<span data-ttu-id="9500e-104">В этом учебнике описывается, как запустить .NET для Apache Spark приложения с помощью .NET Core в Windows.</span><span class="sxs-lookup"><span data-stu-id="9500e-104">This tutorial teaches you how to run a .NET for Apache Spark app using .NET Core on Windows.</span></span>

<span data-ttu-id="9500e-105">В этом руководстве вы узнаете, как:</span><span class="sxs-lookup"><span data-stu-id="9500e-105">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="9500e-106">Подготовка среды Windows для .NET для Apache Spark</span><span class="sxs-lookup"><span data-stu-id="9500e-106">Prepare your Windows environment for .NET for Apache Spark</span></span>
> * <span data-ttu-id="9500e-107">Скачайте **Microsoft. Spark. Worker**</span><span class="sxs-lookup"><span data-stu-id="9500e-107">Download the **Microsoft.Spark.Worker**</span></span>
> * <span data-ttu-id="9500e-108">Создание и запуск простого .NET для Apache Spark приложения</span><span class="sxs-lookup"><span data-stu-id="9500e-108">Build and run a simple .NET for Apache Spark application</span></span>

## <a name="prepare-your-environment"></a><span data-ttu-id="9500e-109">Подготовка среды</span><span class="sxs-lookup"><span data-stu-id="9500e-109">Prepare your environment</span></span>

<span data-ttu-id="9500e-110">Перед началом работы убедитесь, что вы можете запустить `dotnet` `mvn`, `java`,, `spark-shell` из командной строки.</span><span class="sxs-lookup"><span data-stu-id="9500e-110">Before you begin, make sure you can run `dotnet`, `java`, `mvn`, `spark-shell` from your command line.</span></span> <span data-ttu-id="9500e-111">Если ваша среда уже подготовлена, можно перейти к следующему разделу.</span><span class="sxs-lookup"><span data-stu-id="9500e-111">If your environment is already prepared, you can skip to the next section.</span></span> <span data-ttu-id="9500e-112">Если вы не можете выполнить какие либо команды, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="9500e-112">If you cannot run any or all of the commands, follow the steps below.</span></span>

1. <span data-ttu-id="9500e-113">Скачайте и установите [пакет SDK для .NET Core 2.1 x](https://dotnet.microsoft.com/download/dotnet-core/2.1).</span><span class="sxs-lookup"><span data-stu-id="9500e-113">Download and install the [.NET Core 2.1x SDK](https://dotnet.microsoft.com/download/dotnet-core/2.1).</span></span> <span data-ttu-id="9500e-114">При установке пакета SDK в `dotnet` путь добавляется цепочки инструментов.</span><span class="sxs-lookup"><span data-stu-id="9500e-114">Installing the SDK adds the `dotnet` toolchain to your PATH.</span></span> <span data-ttu-id="9500e-115">Используйте команду `dotnet --version` PowerShell для проверки установки.</span><span class="sxs-lookup"><span data-stu-id="9500e-115">Use the PowerShell command `dotnet --version` to verify the installation.</span></span>

2. <span data-ttu-id="9500e-116">Установите [Visual studio 2017](https://www.visualstudio.com/downloads/) или [Visual Studio 2019](https://visualstudio.microsoft.com/vs/preview/) с последними обновлениями.</span><span class="sxs-lookup"><span data-stu-id="9500e-116">Install [Visual Studio 2017](https://www.visualstudio.com/downloads/) or [Visual Studio 2019](https://visualstudio.microsoft.com/vs/preview/) with the latest updates.</span></span> <span data-ttu-id="9500e-117">Вы можете использовать сообщество, профессиональный выпуск или Enterprise.</span><span class="sxs-lookup"><span data-stu-id="9500e-117">You can use Community, Professional, or Enterprise.</span></span> <span data-ttu-id="9500e-118">Версия сообщества бесплатная.</span><span class="sxs-lookup"><span data-stu-id="9500e-118">The Community version is free.</span></span>

   <span data-ttu-id="9500e-119">Во время установки выберите следующие рабочие нагрузки:</span><span class="sxs-lookup"><span data-stu-id="9500e-119">Choose the following workloads during installation:</span></span>
      * <span data-ttu-id="9500e-120">Разработка классических приложений .NET</span><span class="sxs-lookup"><span data-stu-id="9500e-120">.NET desktop development</span></span>
          * <span data-ttu-id="9500e-121">Все необходимые компоненты</span><span class="sxs-lookup"><span data-stu-id="9500e-121">All required components</span></span>
          * <span data-ttu-id="9500e-122">Средства разработки .NET Framework 4.6.1</span><span class="sxs-lookup"><span data-stu-id="9500e-122">.NET Framework 4.6.1 Development Tools</span></span>
      * <span data-ttu-id="9500e-123">Кроссплатформенная разработка .NET Core</span><span class="sxs-lookup"><span data-stu-id="9500e-123">.NET Core cross-platform development</span></span>
          * <span data-ttu-id="9500e-124">Все необходимые компоненты</span><span class="sxs-lookup"><span data-stu-id="9500e-124">All required components</span></span>

3. <span data-ttu-id="9500e-125">Установите [Java 1,8](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html).</span><span class="sxs-lookup"><span data-stu-id="9500e-125">Install [Java 1.8](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html).</span></span>

    * <span data-ttu-id="9500e-126">Выберите соответствующую версию для вашей операционной системы.</span><span class="sxs-lookup"><span data-stu-id="9500e-126">Select the appropriate version for your operating system.</span></span> <span data-ttu-id="9500e-127">Например, выберите **JDK-8u201-Windows-x64. exe** для компьютера под Windows x64.</span><span class="sxs-lookup"><span data-stu-id="9500e-127">For example, select **jdk-8u201-windows-x64.exe** for a Windows x64 machine.</span></span>
    * <span data-ttu-id="9500e-128">Используйте команду `java -version` PowerShell для проверки установки.</span><span class="sxs-lookup"><span data-stu-id="9500e-128">Use the PowerShell command `java -version` to verify the installation.</span></span>

4. <span data-ttu-id="9500e-129">Установите [Apache Maven 3.6.0 +](https://maven.apache.org/download.cgi).</span><span class="sxs-lookup"><span data-stu-id="9500e-129">Install [Apache Maven 3.6.0+](https://maven.apache.org/download.cgi).</span></span>
    * <span data-ttu-id="9500e-130">Скачайте [Apache Maven 3.6.0](http://mirror.metrocast.net/apache/maven/maven-3/3.6.0/binaries/apache-maven-3.6.0-bin.zip).</span><span class="sxs-lookup"><span data-stu-id="9500e-130">Download [Apache Maven 3.6.0](http://mirror.metrocast.net/apache/maven/maven-3/3.6.0/binaries/apache-maven-3.6.0-bin.zip).</span></span>
    * <span data-ttu-id="9500e-131">Извлеките в локальный каталог.</span><span class="sxs-lookup"><span data-stu-id="9500e-131">Extract to a local directory.</span></span> <span data-ttu-id="9500e-132">Например, `c:\bin\apache-maven-3.6.0\`.</span><span class="sxs-lookup"><span data-stu-id="9500e-132">For example, `c:\bin\apache-maven-3.6.0\`.</span></span>
    * <span data-ttu-id="9500e-133">Добавьте Apache Maven в [переменную среды PATH](https://www.java.com/en/download/help/path.xml).</span><span class="sxs-lookup"><span data-stu-id="9500e-133">Add Apache Maven to your [PATH environment variable](https://www.java.com/en/download/help/path.xml).</span></span> <span data-ttu-id="9500e-134">При извлечении в `c:\bin\apache-maven-3.6.0\`необходимо добавить `c:\bin\apache-maven-3.6.0\bin` в путь.</span><span class="sxs-lookup"><span data-stu-id="9500e-134">If you extracted to `c:\bin\apache-maven-3.6.0\`, you would add `c:\bin\apache-maven-3.6.0\bin` to your PATH.</span></span>
    * <span data-ttu-id="9500e-135">Используйте команду `mvn -version` PowerShell для проверки установки.</span><span class="sxs-lookup"><span data-stu-id="9500e-135">Use the PowerShell command `mvn -version` to verify the installation.</span></span>

5. <span data-ttu-id="9500e-136">Установите [Apache Spark 2.3 +](https://spark.apache.org/downloads.html).</span><span class="sxs-lookup"><span data-stu-id="9500e-136">Install [Apache Spark 2.3+](https://spark.apache.org/downloads.html).</span></span> <span data-ttu-id="9500e-137">Apache Spark 2.4 + не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="9500e-137">Apache Spark 2.4+ isn't supported.</span></span>
    * <span data-ttu-id="9500e-138">Скачайте [Apache Spark 2.3](https://spark.apache.org/downloads.html) и извлеките его в локальную папку с помощью такого средства, как [7-Zip](https://www.7-zip.org/) или [WinZip](https://www.winzip.com/).</span><span class="sxs-lookup"><span data-stu-id="9500e-138">Download [Apache Spark 2.3+](https://spark.apache.org/downloads.html) and extract it into a local folder using a tool like [7-zip](https://www.7-zip.org/) or [WinZip](https://www.winzip.com/).</span></span> <span data-ttu-id="9500e-139">Например, вы можете извлечь его в `c:\bin\spark-2.3.2-bin-hadoop2.7\`.</span><span class="sxs-lookup"><span data-stu-id="9500e-139">For example, you might extract it to `c:\bin\spark-2.3.2-bin-hadoop2.7\`.</span></span>
    * <span data-ttu-id="9500e-140">Добавьте Apache Spark в [переменную среды PATH](https://www.java.com/en/download/help/path.xml).</span><span class="sxs-lookup"><span data-stu-id="9500e-140">Add Apache Spark to your [PATH environment variable](https://www.java.com/en/download/help/path.xml).</span></span> <span data-ttu-id="9500e-141">При извлечении в `c:\bin\spark-2.3.2-bin-hadoop2.7\`необходимо добавить `c:\bin\spark-2.3.2-bin-hadoop2.7\bin` в путь.</span><span class="sxs-lookup"><span data-stu-id="9500e-141">If you extracted to `c:\bin\spark-2.3.2-bin-hadoop2.7\`, you would add `c:\bin\spark-2.3.2-bin-hadoop2.7\bin` to your PATH.</span></span>
    * <span data-ttu-id="9500e-142">Добавьте [новую переменную среды](https://www.java.com/en/download/help/path.xml) с `SPARK_HOME`именем.</span><span class="sxs-lookup"><span data-stu-id="9500e-142">Add a [new environment variable](https://www.java.com/en/download/help/path.xml) called `SPARK_HOME`.</span></span> <span data-ttu-id="9500e-143">Если вы извлекли `C:\bin\spark-2.3.2-bin-hadoop2.7\`в, `C:\bin\spark-2.3.2-bin-hadoop2.7\` используйте для **значения переменной**.</span><span class="sxs-lookup"><span data-stu-id="9500e-143">If you extracted to `C:\bin\spark-2.3.2-bin-hadoop2.7\`, use  `C:\bin\spark-2.3.2-bin-hadoop2.7\` for the **Variable value**.</span></span>
    * <span data-ttu-id="9500e-144">Убедитесь, что вы можете запустить `spark-shell` из командной строки.</span><span class="sxs-lookup"><span data-stu-id="9500e-144">Verify you are able to run `spark-shell` from your command line.</span></span>

6. <span data-ttu-id="9500e-145">Настройте [WinUtils](https://github.com/steveloughran/winutils).</span><span class="sxs-lookup"><span data-stu-id="9500e-145">Set up [WinUtils](https://github.com/steveloughran/winutils).</span></span>
    * <span data-ttu-id="9500e-146">Скачайте двоичный файл **winutils. exe** из [репозитория winutils](https://github.com/steveloughran/winutils).</span><span class="sxs-lookup"><span data-stu-id="9500e-146">Download the **winutils.exe** binary from [WinUtils repository](https://github.com/steveloughran/winutils).</span></span> <span data-ttu-id="9500e-147">Выберите версию Hadoop, с которой было скомпилировано распространение Spark.</span><span class="sxs-lookup"><span data-stu-id="9500e-147">Select the version of Hadoop the Spark distribution was compiled with.</span></span> <span data-ttu-id="9500e-148">Например, вы используете **Hadoop-2.7.1** для **Spark 2.3.2**.</span><span class="sxs-lookup"><span data-stu-id="9500e-148">For example, you use **hadoop-2.7.1** for **Spark 2.3.2**.</span></span> <span data-ttu-id="9500e-149">Версия Hadoop помечается в конце имени папки установки Spark.</span><span class="sxs-lookup"><span data-stu-id="9500e-149">The Hadoop version is annotated at the end of your Spark install folder name.</span></span>
    * <span data-ttu-id="9500e-150">Сохраните двоичный файл **winutils. exe** в каталоге по своему усмотрению.</span><span class="sxs-lookup"><span data-stu-id="9500e-150">Save the **winutils.exe** binary to a directory of your choice.</span></span> <span data-ttu-id="9500e-151">Например, `c:\hadoop\bin`.</span><span class="sxs-lookup"><span data-stu-id="9500e-151">For example, `c:\hadoop\bin`.</span></span>
    * <span data-ttu-id="9500e-152">Установите `HADOOP_HOME` для отражения каталога с **winutils. exe** без `bin`.</span><span class="sxs-lookup"><span data-stu-id="9500e-152">Set `HADOOP_HOME` to reflect the directory with **winutils.exe** without `bin`.</span></span> <span data-ttu-id="9500e-153">Например, `c:\hadoop`.</span><span class="sxs-lookup"><span data-stu-id="9500e-153">For example, `c:\hadoop`.</span></span>
    * <span data-ttu-id="9500e-154">Задайте переменную среды PATH для включения `%HADOOP_HOME%\bin`.</span><span class="sxs-lookup"><span data-stu-id="9500e-154">Set the PATH environment variable to include `%HADOOP_HOME%\bin`.</span></span>

<span data-ttu-id="9500e-155">Перед переходом к следующему разделу `java`проверьте, `spark-shell` можно ли выполнить `dotnet`команду,, `mvn`, в командной строке.</span><span class="sxs-lookup"><span data-stu-id="9500e-155">Double check that you can run `dotnet`, `java`, `mvn`, `spark-shell` from your command line before you move to the next section.</span></span>

## <a name="download-the-microsoftsparkworker-release"></a><span data-ttu-id="9500e-156">Скачайте выпуск Microsoft. Spark. Worker</span><span class="sxs-lookup"><span data-stu-id="9500e-156">Download the Microsoft.Spark.Worker release</span></span>

1. <span data-ttu-id="9500e-157">Скачайте выпуск [Microsoft. Spark. Worker](https://github.com/dotnet/spark/releases) со страницы .net для Apache Spark GitHub releases на локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="9500e-157">Download the [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) release from the .NET for Apache Spark GitHub Releases page to your local machine.</span></span> <span data-ttu-id="9500e-158">Например, вы можете скачать его по пути, `c:\bin\Microsoft.Spark.Worker\`.</span><span class="sxs-lookup"><span data-stu-id="9500e-158">For example, you might download it to the path, `c:\bin\Microsoft.Spark.Worker\`.</span></span>

2. <span data-ttu-id="9500e-159">Создайте [новую переменную среды](https://www.java.com/en/download/help/path.xml) с `DotnetWorkerPath` именем и установите ее в каталог, в который вы скачали и извлекли файл **Microsoft. Spark. Worker**.</span><span class="sxs-lookup"><span data-stu-id="9500e-159">Create a [new environment variable](https://www.java.com/en/download/help/path.xml) called `DotnetWorkerPath` and set it to the directory where you downloaded and extracted the **Microsoft.Spark.Worker**.</span></span> <span data-ttu-id="9500e-160">Например, `c:\bin\Microsoft.Spark.Worker`.</span><span class="sxs-lookup"><span data-stu-id="9500e-160">For example, `c:\bin\Microsoft.Spark.Worker`.</span></span>

## <a name="clone-the-net-for-apache-spark-github-repo"></a><span data-ttu-id="9500e-161">Клонирование .NET для Apache Spark репозитория GitHub</span><span class="sxs-lookup"><span data-stu-id="9500e-161">Clone the .NET for Apache Spark GitHub repo</span></span>

<span data-ttu-id="9500e-162">Используйте следующую команду [GitBash](https://gitforwindows.org/) , чтобы клонировать репозиторий .net для Apache Spark на компьютер.</span><span class="sxs-lookup"><span data-stu-id="9500e-162">Use the following [GitBash](https://gitforwindows.org/) command to clone the .NET for Apache Spark repo to your machine.</span></span>

```bash
git clone https://github.com/dotnet/spark.git c:\github\dotnet-spark
```

## <a name="write-a-net-for-apache-spark-app"></a><span data-ttu-id="9500e-163">Написание .NET для приложения Apache Spark</span><span class="sxs-lookup"><span data-stu-id="9500e-163">Write a .NET for Apache Spark app</span></span>

1. <span data-ttu-id="9500e-164">Откройте **Visual Studio** и выберите **файл > создать новый проект > консольное приложение (.NET Core)** .</span><span class="sxs-lookup"><span data-stu-id="9500e-164">Open **Visual Studio** and navigate to **File > Create New Project > Console App (.NET Core)**.</span></span> <span data-ttu-id="9500e-165">Назовите приложение **хеллоспарк**.</span><span class="sxs-lookup"><span data-stu-id="9500e-165">Name the application **HelloSpark**.</span></span>

2. <span data-ttu-id="9500e-166">Установите [пакет NuGet Microsoft. Spark](https://www.nuget.org/profiles/spark).</span><span class="sxs-lookup"><span data-stu-id="9500e-166">Install the [Microsoft.Spark NuGet package](https://www.nuget.org/profiles/spark).</span></span> <span data-ttu-id="9500e-167">Дополнительные сведения об установке пакетов NuGet см. в разделе [различные способы установки пакета NuGet](https://docs.microsoft.com/nuget/consume-packages/ways-to-install-a-package).</span><span class="sxs-lookup"><span data-stu-id="9500e-167">For more information on installing NuGet packages, see [Different ways to install a NuGet Package](https://docs.microsoft.com/nuget/consume-packages/ways-to-install-a-package).</span></span>

3. <span data-ttu-id="9500e-168">В **Обозреватель решений**откройте **Program.CS** и напишите следующий C# код:</span><span class="sxs-lookup"><span data-stu-id="9500e-168">In **Solution Explorer**, open **Program.cs** and write the following C# code:</span></span>

   ```csharp
     var spark = SparkSession.Builder().GetOrCreate();
     var df = spark.Read().Json("people.json");
     df.Show();
   ```

4. <span data-ttu-id="9500e-169">Постройте решение.</span><span class="sxs-lookup"><span data-stu-id="9500e-169">Build the solution.</span></span>

## <a name="run-your-net-for-apache-spark-app"></a><span data-ttu-id="9500e-170">Запуск .NET для приложения Apache Spark</span><span class="sxs-lookup"><span data-stu-id="9500e-170">Run your .NET for Apache Spark app</span></span>

1. <span data-ttu-id="9500e-171">Откройте **PowerShell** и измените каталог на папку, в которой хранится ваше приложение.</span><span class="sxs-lookup"><span data-stu-id="9500e-171">Open **PowerShell** and change the directory to the folder where your app is stored.</span></span>

   ```powershell
   cd <your-app-output-directory>
   ```

2. <span data-ttu-id="9500e-172">Создайте файл с именем **People. JSON** со следующим содержимым:</span><span class="sxs-lookup"><span data-stu-id="9500e-172">Create a file called **people.json** with the following content:</span></span>

   ```json
   {"name":"Michael"}
   {"name":"Andy", "age":30}
   {"name":"Justin", "age":19}
   ```

3. <span data-ttu-id="9500e-173">Используйте следующую команду PowerShell для запуска приложения:</span><span class="sxs-lookup"><span data-stu-id="9500e-173">Use the following PowerShell command to run your app:</span></span>

   ```powershell
    spark-submit `
    --class org.apache.spark.deploy.dotnet.DotnetRunner `
    --master local `
    microsoft-spark-2.4.x-<version>.jar `
    dotnet HelloSpark.dll
    ```

<span data-ttu-id="9500e-174">Поздравляем!</span><span class="sxs-lookup"><span data-stu-id="9500e-174">Congratulations!</span></span> <span data-ttu-id="9500e-175">Вы успешно создали и запустили .NET для Apache Sparkного приложения.</span><span class="sxs-lookup"><span data-stu-id="9500e-175">You successfully authored and ran a .NET for Apache Spark app.</span></span>

## <a name="next-steps"></a><span data-ttu-id="9500e-176">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="9500e-176">Next steps</span></span>

<span data-ttu-id="9500e-177">В этом руководстве вы узнали, как:</span><span class="sxs-lookup"><span data-stu-id="9500e-177">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="9500e-178">Подготовка среды Windows для .NET для Apache Spark</span><span class="sxs-lookup"><span data-stu-id="9500e-178">Prepare your Windows environment for .NET for Apache Spark</span></span>
> * <span data-ttu-id="9500e-179">Скачайте **Microsoft. Spark. Worker**</span><span class="sxs-lookup"><span data-stu-id="9500e-179">Download the **Microsoft.Spark.Worker**</span></span>
> * <span data-ttu-id="9500e-180">Создание и запуск простого .NET для Apache Spark приложения</span><span class="sxs-lookup"><span data-stu-id="9500e-180">Build and run a simple .NET for Apache Spark application</span></span>

<span data-ttu-id="9500e-181">Дополнительные сведения см. на странице ресурсов.</span><span class="sxs-lookup"><span data-stu-id="9500e-181">Check out the resources page to learn more.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="9500e-182">Ресурсы .NET для Apache Spark</span><span class="sxs-lookup"><span data-stu-id="9500e-182">.NET for Apache Spark Resources</span></span>](../resources/index.md)
