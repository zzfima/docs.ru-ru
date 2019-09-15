---
title: Начало работы с .NET для Apache Spark
description: Узнайте, как запустить приложение .NET для Apache Spark с помощью .NET Core в Windows.
ms.date: 06/27/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 004256a2fe369b026b15151dfc72ae379da0be8e
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70928487"
---
# <a name="tutorial-get-started-with-net-for-apache-spark"></a><span data-ttu-id="bd3b6-103">Учебник. Начало работы с .NET для Apache Spark</span><span class="sxs-lookup"><span data-stu-id="bd3b6-103">Tutorial: Get started with .NET for Apache Spark</span></span>

<span data-ttu-id="bd3b6-104">В этом руководстве описывается, как запустить приложение .NET для Apache Spark с помощью .NET Core в Windows.</span><span class="sxs-lookup"><span data-stu-id="bd3b6-104">This tutorial teaches you how to run a .NET for Apache Spark app using .NET Core on Windows.</span></span>

<span data-ttu-id="bd3b6-105">В этом руководстве вы узнаете, как:</span><span class="sxs-lookup"><span data-stu-id="bd3b6-105">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="bd3b6-106">Подготовка среды Windows для .NET для Apache Spark</span><span class="sxs-lookup"><span data-stu-id="bd3b6-106">Prepare your Windows environment for .NET for Apache Spark</span></span>
> * <span data-ttu-id="bd3b6-107">Скачивание **Microsoft.Spark.Worker**</span><span class="sxs-lookup"><span data-stu-id="bd3b6-107">Download the **Microsoft.Spark.Worker**</span></span>
> * <span data-ttu-id="bd3b6-108">Сборка и запуск простого приложения .NET для Apache Spark</span><span class="sxs-lookup"><span data-stu-id="bd3b6-108">Build and run a simple .NET for Apache Spark application</span></span>

## <a name="prepare-your-environment"></a><span data-ttu-id="bd3b6-109">Подготовка среды</span><span class="sxs-lookup"><span data-stu-id="bd3b6-109">Prepare your environment</span></span>

<span data-ttu-id="bd3b6-110">Перед началом работы убедитесь в том, что вы можете выполнять команды `dotnet`, `java`, `mvn` и `spark-shell` из командной строки.</span><span class="sxs-lookup"><span data-stu-id="bd3b6-110">Before you begin, make sure you can run `dotnet`, `java`, `mvn`, `spark-shell` from your command line.</span></span> <span data-ttu-id="bd3b6-111">Если среда уже подготовлена, можно перейти к следующему разделу.</span><span class="sxs-lookup"><span data-stu-id="bd3b6-111">If your environment is already prepared, you can skip to the next section.</span></span> <span data-ttu-id="bd3b6-112">Если какие-либо из этих команд или все они не выполняются, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="bd3b6-112">If you cannot run any or all of the commands, follow the steps below.</span></span>

1. <span data-ttu-id="bd3b6-113">Скачайте и установите [пакет SDK для .NET Core 2.1x](https://dotnet.microsoft.com/download/dotnet-core/2.1).</span><span class="sxs-lookup"><span data-stu-id="bd3b6-113">Download and install the [.NET Core 2.1x SDK](https://dotnet.microsoft.com/download/dotnet-core/2.1).</span></span> <span data-ttu-id="bd3b6-114">При установке пакета SDK в переменную PATH добавляется цепочка инструментов `dotnet`.</span><span class="sxs-lookup"><span data-stu-id="bd3b6-114">Installing the SDK adds the `dotnet` toolchain to your PATH.</span></span> <span data-ttu-id="bd3b6-115">Выполните команду PowerShell `dotnet --version`, чтобы проверить установку.</span><span class="sxs-lookup"><span data-stu-id="bd3b6-115">Use the PowerShell command `dotnet --version` to verify the installation.</span></span>

2. <span data-ttu-id="bd3b6-116">Установите [Visual Studio 2017](https://www.visualstudio.com/downloads/) или [Visual Studio 2019](https://visualstudio.microsoft.com/vs/preview/) с последними обновлениями.</span><span class="sxs-lookup"><span data-stu-id="bd3b6-116">Install [Visual Studio 2017](https://www.visualstudio.com/downloads/) or [Visual Studio 2019](https://visualstudio.microsoft.com/vs/preview/) with the latest updates.</span></span> <span data-ttu-id="bd3b6-117">Можно использовать выпуск Community, Professional или Enterprise.</span><span class="sxs-lookup"><span data-stu-id="bd3b6-117">You can use Community, Professional, or Enterprise.</span></span> <span data-ttu-id="bd3b6-118">Версия Community бесплатна.</span><span class="sxs-lookup"><span data-stu-id="bd3b6-118">The Community version is free.</span></span>

   <span data-ttu-id="bd3b6-119">Во время установки выберите следующие рабочие нагрузки:</span><span class="sxs-lookup"><span data-stu-id="bd3b6-119">Choose the following workloads during installation:</span></span>
      * <span data-ttu-id="bd3b6-120">Разработка классических приложений .NET</span><span class="sxs-lookup"><span data-stu-id="bd3b6-120">.NET desktop development</span></span>
          * <span data-ttu-id="bd3b6-121">Все необходимые компоненты</span><span class="sxs-lookup"><span data-stu-id="bd3b6-121">All required components</span></span>
          * <span data-ttu-id="bd3b6-122">Средства разработки для .NET Framework 4.6.1</span><span class="sxs-lookup"><span data-stu-id="bd3b6-122">.NET Framework 4.6.1 Development Tools</span></span>
      * <span data-ttu-id="bd3b6-123">Кроссплатформенная разработка .NET Core</span><span class="sxs-lookup"><span data-stu-id="bd3b6-123">.NET Core cross-platform development</span></span>
          * <span data-ttu-id="bd3b6-124">Все необходимые компоненты</span><span class="sxs-lookup"><span data-stu-id="bd3b6-124">All required components</span></span>

3. <span data-ttu-id="bd3b6-125">Установите [Java 1.8](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html).</span><span class="sxs-lookup"><span data-stu-id="bd3b6-125">Install [Java 1.8](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html).</span></span>

    * <span data-ttu-id="bd3b6-126">Выберите соответствующую версию для вашей операционной системы.</span><span class="sxs-lookup"><span data-stu-id="bd3b6-126">Select the appropriate version for your operating system.</span></span> <span data-ttu-id="bd3b6-127">Например, для компьютера с 64-разрядной версией Windows выберите **jdk-8u201-windows-x64.exe**.</span><span class="sxs-lookup"><span data-stu-id="bd3b6-127">For example, select **jdk-8u201-windows-x64.exe** for a Windows x64 machine.</span></span>
    * <span data-ttu-id="bd3b6-128">Выполните команду PowerShell `java -version`, чтобы проверить установку.</span><span class="sxs-lookup"><span data-stu-id="bd3b6-128">Use the PowerShell command `java -version` to verify the installation.</span></span>

4. <span data-ttu-id="bd3b6-129">Установите [Apache Maven 3.6.0 или более поздней версии](https://maven.apache.org/download.cgi).</span><span class="sxs-lookup"><span data-stu-id="bd3b6-129">Install [Apache Maven 3.6.0+](https://maven.apache.org/download.cgi).</span></span>
    * <span data-ttu-id="bd3b6-130">Скачайте [Apache Maven 3.6.0](http://mirror.metrocast.net/apache/maven/maven-3/3.6.0/binaries/apache-maven-3.6.0-bin.zip).</span><span class="sxs-lookup"><span data-stu-id="bd3b6-130">Download [Apache Maven 3.6.0](http://mirror.metrocast.net/apache/maven/maven-3/3.6.0/binaries/apache-maven-3.6.0-bin.zip).</span></span>
    * <span data-ttu-id="bd3b6-131">Извлеките содержимое в локальный каталог.</span><span class="sxs-lookup"><span data-stu-id="bd3b6-131">Extract to a local directory.</span></span> <span data-ttu-id="bd3b6-132">Например, `c:\bin\apache-maven-3.6.0\`.</span><span class="sxs-lookup"><span data-stu-id="bd3b6-132">For example, `c:\bin\apache-maven-3.6.0\`.</span></span>
    * <span data-ttu-id="bd3b6-133">Добавьте Apache Maven в [переменную среды PATH](https://www.java.com/en/download/help/path.xml).</span><span class="sxs-lookup"><span data-stu-id="bd3b6-133">Add Apache Maven to your [PATH environment variable](https://www.java.com/en/download/help/path.xml).</span></span> <span data-ttu-id="bd3b6-134">Если содержимое было извлечено в `c:\bin\apache-maven-3.6.0\`, в переменную PATH следует добавить `c:\bin\apache-maven-3.6.0\bin`.</span><span class="sxs-lookup"><span data-stu-id="bd3b6-134">If you extracted to `c:\bin\apache-maven-3.6.0\`, you would add `c:\bin\apache-maven-3.6.0\bin` to your PATH.</span></span>
    * <span data-ttu-id="bd3b6-135">Выполните команду PowerShell `mvn -version`, чтобы проверить установку.</span><span class="sxs-lookup"><span data-stu-id="bd3b6-135">Use the PowerShell command `mvn -version` to verify the installation.</span></span>

5. <span data-ttu-id="bd3b6-136">Установите [Apache Spark 2.3 или более поздней версии](https://spark.apache.org/downloads.html).</span><span class="sxs-lookup"><span data-stu-id="bd3b6-136">Install [Apache Spark 2.3+](https://spark.apache.org/downloads.html).</span></span> <span data-ttu-id="bd3b6-137">Apache Spark 2.4 и более поздние версии не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="bd3b6-137">Apache Spark 2.4+ isn't supported.</span></span>
    * <span data-ttu-id="bd3b6-138">Скачайте [Apache Spark 2.3 или более поздней версии](https://spark.apache.org/downloads.html) и извлеките содержимое в локальную папку с помощью такого средства, как [7-zip](https://www.7-zip.org/) или [WinZip](https://www.winzip.com/).</span><span class="sxs-lookup"><span data-stu-id="bd3b6-138">Download [Apache Spark 2.3+](https://spark.apache.org/downloads.html) and extract it into a local folder using a tool like [7-zip](https://www.7-zip.org/) or [WinZip](https://www.winzip.com/).</span></span> <span data-ttu-id="bd3b6-139">Например, можно извлечь его в папку `c:\bin\spark-2.3.2-bin-hadoop2.7\`.</span><span class="sxs-lookup"><span data-stu-id="bd3b6-139">For example, you might extract it to `c:\bin\spark-2.3.2-bin-hadoop2.7\`.</span></span>
    * <span data-ttu-id="bd3b6-140">Добавьте Apache Spark в [переменную среды PATH](https://www.java.com/en/download/help/path.xml).</span><span class="sxs-lookup"><span data-stu-id="bd3b6-140">Add Apache Spark to your [PATH environment variable](https://www.java.com/en/download/help/path.xml).</span></span> <span data-ttu-id="bd3b6-141">Если содержимое было извлечено в `c:\bin\spark-2.3.2-bin-hadoop2.7\`, в переменную PATH следует добавить `c:\bin\spark-2.3.2-bin-hadoop2.7\bin`.</span><span class="sxs-lookup"><span data-stu-id="bd3b6-141">If you extracted to `c:\bin\spark-2.3.2-bin-hadoop2.7\`, you would add `c:\bin\spark-2.3.2-bin-hadoop2.7\bin` to your PATH.</span></span>
    * <span data-ttu-id="bd3b6-142">Добавьте [новую переменную среды](https://www.java.com/en/download/help/path.xml) с именем `SPARK_HOME`.</span><span class="sxs-lookup"><span data-stu-id="bd3b6-142">Add a [new environment variable](https://www.java.com/en/download/help/path.xml) called `SPARK_HOME`.</span></span> <span data-ttu-id="bd3b6-143">Если содержимое было извлечено в `C:\bin\spark-2.3.2-bin-hadoop2.7\`, используйте `C:\bin\spark-2.3.2-bin-hadoop2.7\` в качестве **значения переменной**.</span><span class="sxs-lookup"><span data-stu-id="bd3b6-143">If you extracted to `C:\bin\spark-2.3.2-bin-hadoop2.7\`, use  `C:\bin\spark-2.3.2-bin-hadoop2.7\` for the **Variable value**.</span></span>
    * <span data-ttu-id="bd3b6-144">Убедитесь в том, что вы можете выполнить команду `spark-shell` в командной строке.</span><span class="sxs-lookup"><span data-stu-id="bd3b6-144">Verify you are able to run `spark-shell` from your command line.</span></span>

6. <span data-ttu-id="bd3b6-145">Настройте [WinUtils](https://github.com/steveloughran/winutils).</span><span class="sxs-lookup"><span data-stu-id="bd3b6-145">Set up [WinUtils](https://github.com/steveloughran/winutils).</span></span>
    * <span data-ttu-id="bd3b6-146">Скачайте двоичный файл **winutils.exe** из [репозитория WinUtils](https://github.com/steveloughran/winutils).</span><span class="sxs-lookup"><span data-stu-id="bd3b6-146">Download the **winutils.exe** binary from [WinUtils repository](https://github.com/steveloughran/winutils).</span></span> <span data-ttu-id="bd3b6-147">Выберите версию Hadoop, с использованием которой был скомпилирован дистрибутив Spark.</span><span class="sxs-lookup"><span data-stu-id="bd3b6-147">Select the version of Hadoop the Spark distribution was compiled with.</span></span> <span data-ttu-id="bd3b6-148">Например, для **Spark 2.3.2** используйте **hadoop-2.7.1**.</span><span class="sxs-lookup"><span data-stu-id="bd3b6-148">For example, you use **hadoop-2.7.1** for **Spark 2.3.2**.</span></span> <span data-ttu-id="bd3b6-149">Версия Hadoop указывается в конце имени папки установки Spark.</span><span class="sxs-lookup"><span data-stu-id="bd3b6-149">The Hadoop version is annotated at the end of your Spark install folder name.</span></span>
    * <span data-ttu-id="bd3b6-150">Сохраните двоичный файл **winutils.exe** в любом каталоге на ваш выбор.</span><span class="sxs-lookup"><span data-stu-id="bd3b6-150">Save the **winutils.exe** binary to a directory of your choice.</span></span> <span data-ttu-id="bd3b6-151">Например, `c:\hadoop\bin`.</span><span class="sxs-lookup"><span data-stu-id="bd3b6-151">For example, `c:\hadoop\bin`.</span></span>
    * <span data-ttu-id="bd3b6-152">Присвойте переменной `HADOOP_HOME` путь к каталогу с файлом **winutils.exe** без `bin`.</span><span class="sxs-lookup"><span data-stu-id="bd3b6-152">Set `HADOOP_HOME` to reflect the directory with **winutils.exe** without `bin`.</span></span> <span data-ttu-id="bd3b6-153">Например, `c:\hadoop`.</span><span class="sxs-lookup"><span data-stu-id="bd3b6-153">For example, `c:\hadoop`.</span></span>
    * <span data-ttu-id="bd3b6-154">Включите в переменную среды PATH значение `%HADOOP_HOME%\bin`.</span><span class="sxs-lookup"><span data-stu-id="bd3b6-154">Set the PATH environment variable to include `%HADOOP_HOME%\bin`.</span></span>

<span data-ttu-id="bd3b6-155">Перед переходом к следующему разделу еще раз проверьте, можно ли выполнять команды `dotnet`, `java`, `mvn` и `spark-shell` из командной строки.</span><span class="sxs-lookup"><span data-stu-id="bd3b6-155">Double check that you can run `dotnet`, `java`, `mvn`, `spark-shell` from your command line before you move to the next section.</span></span>

## <a name="download-the-microsoftsparkworker-release"></a><span data-ttu-id="bd3b6-156">Скачивание выпуска Microsoft.Spark.Worker</span><span class="sxs-lookup"><span data-stu-id="bd3b6-156">Download the Microsoft.Spark.Worker release</span></span>

1. <span data-ttu-id="bd3b6-157">Скачайте выпуск [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) на локальный компьютер со страницы выпусков .NET для Apache Spark в GitHub.</span><span class="sxs-lookup"><span data-stu-id="bd3b6-157">Download the [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) release from the .NET for Apache Spark GitHub Releases page to your local machine.</span></span> <span data-ttu-id="bd3b6-158">Например, его можно скачать по пути `c:\bin\Microsoft.Spark.Worker\`.</span><span class="sxs-lookup"><span data-stu-id="bd3b6-158">For example, you might download it to the path, `c:\bin\Microsoft.Spark.Worker\`.</span></span>

2. <span data-ttu-id="bd3b6-159">Создайте [переменную среды](https://www.java.com/en/download/help/path.xml) с именем `DotnetWorkerPath` и присвойте ей путь к каталогу, в который вы скачали и извлекли выпуск **Microsoft.Spark.Worker**.</span><span class="sxs-lookup"><span data-stu-id="bd3b6-159">Create a [new environment variable](https://www.java.com/en/download/help/path.xml) called `DotnetWorkerPath` and set it to the directory where you downloaded and extracted the **Microsoft.Spark.Worker**.</span></span> <span data-ttu-id="bd3b6-160">Например, `c:\bin\Microsoft.Spark.Worker`.</span><span class="sxs-lookup"><span data-stu-id="bd3b6-160">For example, `c:\bin\Microsoft.Spark.Worker`.</span></span>

## <a name="clone-the-net-for-apache-spark-github-repo"></a><span data-ttu-id="bd3b6-161">Клонирование репозитория .NET для Apache Spark в GitHub</span><span class="sxs-lookup"><span data-stu-id="bd3b6-161">Clone the .NET for Apache Spark GitHub repo</span></span>

<span data-ttu-id="bd3b6-162">Используйте приведенную ниже команду [GitBash](https://gitforwindows.org/), чтобы клонировать репозиторий .NET для Apache Spark на компьютер.</span><span class="sxs-lookup"><span data-stu-id="bd3b6-162">Use the following [GitBash](https://gitforwindows.org/) command to clone the .NET for Apache Spark repo to your machine.</span></span>

```bash
git clone https://github.com/dotnet/spark.git c:\github\dotnet-spark
```

## <a name="write-a-net-for-apache-spark-app"></a><span data-ttu-id="bd3b6-163">Написание приложения .NET для Apache Spark</span><span class="sxs-lookup"><span data-stu-id="bd3b6-163">Write a .NET for Apache Spark app</span></span>

1. <span data-ttu-id="bd3b6-164">Откройте **Visual Studio** и последовательно выберите **Файл > Создать новый проект > Консольное приложение (.NET Core)** .</span><span class="sxs-lookup"><span data-stu-id="bd3b6-164">Open **Visual Studio** and navigate to **File > Create New Project > Console App (.NET Core)**.</span></span> <span data-ttu-id="bd3b6-165">Назовите приложение **HelloSpark**.</span><span class="sxs-lookup"><span data-stu-id="bd3b6-165">Name the application **HelloSpark**.</span></span>

2. <span data-ttu-id="bd3b6-166">Установите [пакет NuGet Microsoft.Spark](https://www.nuget.org/profiles/spark).</span><span class="sxs-lookup"><span data-stu-id="bd3b6-166">Install the [Microsoft.Spark NuGet package](https://www.nuget.org/profiles/spark).</span></span> <span data-ttu-id="bd3b6-167">Дополнительные сведения об установке пакетов NuGet см. в статье [Способы установки пакетов NuGet](https://docs.microsoft.com/nuget/consume-packages/ways-to-install-a-package).</span><span class="sxs-lookup"><span data-stu-id="bd3b6-167">For more information on installing NuGet packages, see [Different ways to install a NuGet Package](https://docs.microsoft.com/nuget/consume-packages/ways-to-install-a-package).</span></span>

3. <span data-ttu-id="bd3b6-168">В **обозревателе решений** откройте файл **Program.cs** и добавьте следующий код C#:</span><span class="sxs-lookup"><span data-stu-id="bd3b6-168">In **Solution Explorer**, open **Program.cs** and write the following C# code:</span></span>

   ```csharp
     var spark = SparkSession.Builder().GetOrCreate();
     var df = spark.Read().Json("people.json");
     df.Show();
   ```

4. <span data-ttu-id="bd3b6-169">Постройте решение.</span><span class="sxs-lookup"><span data-stu-id="bd3b6-169">Build the solution.</span></span>

## <a name="run-your-net-for-apache-spark-app"></a><span data-ttu-id="bd3b6-170">Запуск приложения .NET для Apache Spark</span><span class="sxs-lookup"><span data-stu-id="bd3b6-170">Run your .NET for Apache Spark app</span></span>

1. <span data-ttu-id="bd3b6-171">Откройте **PowerShell** и перейдите в папку, в которой хранится приложение.</span><span class="sxs-lookup"><span data-stu-id="bd3b6-171">Open **PowerShell** and change the directory to the folder where your app is stored.</span></span>

   ```powershell
   cd <your-app-output-directory>
   ```

2. <span data-ttu-id="bd3b6-172">Создайте файл **people.json** со следующим содержимым:</span><span class="sxs-lookup"><span data-stu-id="bd3b6-172">Create a file called **people.json** with the following content:</span></span>

   ```json
   {"name":"Michael"}
   {"name":"Andy", "age":30}
   {"name":"Justin", "age":19}
   ```

3. <span data-ttu-id="bd3b6-173">Запустите приложение с помощью следующей команды PowerShell:</span><span class="sxs-lookup"><span data-stu-id="bd3b6-173">Use the following PowerShell command to run your app:</span></span>

   ```powershell
    spark-submit `
    --class org.apache.spark.deploy.dotnet.DotnetRunner `
    --master local `
    microsoft-spark-2.4.x-<version>.jar `
    dotnet HelloSpark.dll
    ```

<span data-ttu-id="bd3b6-174">Поздравляем!</span><span class="sxs-lookup"><span data-stu-id="bd3b6-174">Congratulations!</span></span> <span data-ttu-id="bd3b6-175">Вы успешно создали и запустили приложение .NET для Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="bd3b6-175">You successfully authored and ran a .NET for Apache Spark app.</span></span>

## <a name="next-steps"></a><span data-ttu-id="bd3b6-176">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="bd3b6-176">Next steps</span></span>

<span data-ttu-id="bd3b6-177">В этом руководстве вы узнали, как:</span><span class="sxs-lookup"><span data-stu-id="bd3b6-177">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="bd3b6-178">Подготовка среды Windows для .NET для Apache Spark</span><span class="sxs-lookup"><span data-stu-id="bd3b6-178">Prepare your Windows environment for .NET for Apache Spark</span></span>
> * <span data-ttu-id="bd3b6-179">Скачивание **Microsoft.Spark.Worker**</span><span class="sxs-lookup"><span data-stu-id="bd3b6-179">Download the **Microsoft.Spark.Worker**</span></span>
> * <span data-ttu-id="bd3b6-180">Сборка и запуск простого приложения .NET для Apache Spark</span><span class="sxs-lookup"><span data-stu-id="bd3b6-180">Build and run a simple .NET for Apache Spark application</span></span>

<span data-ttu-id="bd3b6-181">Дополнительные сведения см. на странице ресурсов.</span><span class="sxs-lookup"><span data-stu-id="bd3b6-181">Check out the resources page to learn more.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="bd3b6-182">Ресурсы по .NET для Apache Spark</span><span class="sxs-lookup"><span data-stu-id="bd3b6-182">.NET for Apache Spark Resources</span></span>](../resources/index.md)
