---
title: Начало работы с .NET для Apache Spark
description: Узнайте, как запустить приложение .NET для Apache Spark с помощью .NET Core в Windows.
ms.date: 11/04/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 679ee7660e96504768a781e1e384acab80362736
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743204"
---
# <a name="tutorial-get-started-with-net-for-apache-spark"></a><span data-ttu-id="50b73-103">Учебник. Начало работы с .NET для Apache Spark</span><span class="sxs-lookup"><span data-stu-id="50b73-103">Tutorial: Get started with .NET for Apache Spark</span></span>

<span data-ttu-id="50b73-104">В этом руководстве описывается, как запустить приложение .NET для Apache Spark с помощью .NET Core в Windows.</span><span class="sxs-lookup"><span data-stu-id="50b73-104">This tutorial teaches you how to run a .NET for Apache Spark app using .NET Core on Windows.</span></span>

<span data-ttu-id="50b73-105">В этом руководстве вы узнаете, как:</span><span class="sxs-lookup"><span data-stu-id="50b73-105">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="50b73-106">Подготовка среды Windows для .NET для Apache Spark</span><span class="sxs-lookup"><span data-stu-id="50b73-106">Prepare your Windows environment for .NET for Apache Spark</span></span>
> * <span data-ttu-id="50b73-107">написать свое первое приложение .NET для Apache Spark;</span><span class="sxs-lookup"><span data-stu-id="50b73-107">Write your first .NET for Apache Spark application</span></span>
> * <span data-ttu-id="50b73-108">скомпилировать и запустить простое приложение .NET для Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="50b73-108">Build and run your simple .NET for Apache Spark application</span></span>

## <a name="prepare-your-environment"></a><span data-ttu-id="50b73-109">Подготовка среды</span><span class="sxs-lookup"><span data-stu-id="50b73-109">Prepare your environment</span></span>

<span data-ttu-id="50b73-110">Прежде чем приступить к написанию приложения, нужно настроить некоторые необходимые зависимости.</span><span class="sxs-lookup"><span data-stu-id="50b73-110">Before you begin writing your app, you need to set up some prerequisite dependencies.</span></span> <span data-ttu-id="50b73-111">Если вы можете выполнить `dotnet`, `java`, `mvn`, `spark-shell` из среды командной строки, то ваша среда уже подготовлена, и вы можете перейти к следующему разделу.</span><span class="sxs-lookup"><span data-stu-id="50b73-111">If you can run `dotnet`, `java`, `mvn`, `spark-shell` from your command line environment, then your environment is already prepared and you can skip to the next section.</span></span> <span data-ttu-id="50b73-112">Если эти команды или хотя бы одну из них выполнить не получается, сделайте следующее.</span><span class="sxs-lookup"><span data-stu-id="50b73-112">If you cannot run any or all of the commands, do the following steps.</span></span>

### <a name="1-install-net"></a><span data-ttu-id="50b73-113">1. Установка .NET</span><span class="sxs-lookup"><span data-stu-id="50b73-113">1. Install .NET</span></span>

<span data-ttu-id="50b73-114">Чтобы приступить к созданию приложений .NET, необходимо загрузить и установить пакет средств разработки программного обеспечения (SDK) для .NET.</span><span class="sxs-lookup"><span data-stu-id="50b73-114">To start building .NET apps, you need to download and install the .NET SDK (Software Development Kit).</span></span>

<span data-ttu-id="50b73-115">Скачайте и установите [пакет SDK для .NET Core](https://dotnet.microsoft.com/download/dotnet-core/3.0).</span><span class="sxs-lookup"><span data-stu-id="50b73-115">Download and install the [.NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core/3.0).</span></span> <span data-ttu-id="50b73-116">При установке пакета SDK в переменную PATH добавляется цепочка инструментов `dotnet`.</span><span class="sxs-lookup"><span data-stu-id="50b73-116">Installing the SDK adds the `dotnet` toolchain to your PATH.</span></span>

<span data-ttu-id="50b73-117">После установки пакета SDK для .NET Core, откройте новую командную строку и выполните команду `dotnet`.</span><span class="sxs-lookup"><span data-stu-id="50b73-117">Once you've installed the .NET Core SDK, open a new command prompt and run `dotnet`.</span></span>

<span data-ttu-id="50b73-118">Если команда выполняется и выводит сведения об использовании dotnet, можно перейти к следующему шагу.</span><span class="sxs-lookup"><span data-stu-id="50b73-118">If the command runs and prints out information about how to use dotnet, can move to the next step.</span></span> <span data-ttu-id="50b73-119">При возникновении ошибки `'dotnet' is not recognized as an internal or external command` убедитесь, что вы открыли **новую** командную строку перед выполнением команды.</span><span class="sxs-lookup"><span data-stu-id="50b73-119">If you receive a `'dotnet' is not recognized as an internal or external command` error, make sure you opened a **new** command prompt before running the command.</span></span>

### <a name="2-install-java"></a><span data-ttu-id="50b73-120">2. Установка Java</span><span class="sxs-lookup"><span data-stu-id="50b73-120">2. Install Java</span></span>

<span data-ttu-id="50b73-121">Установите [Java 8.1](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html).</span><span class="sxs-lookup"><span data-stu-id="50b73-121">Install [Java 8.1](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html).</span></span>

<span data-ttu-id="50b73-122">Выберите соответствующую версию для вашей операционной системы.</span><span class="sxs-lookup"><span data-stu-id="50b73-122">Select the appropriate version for your operating system.</span></span> <span data-ttu-id="50b73-123">Например, для компьютера с 64-разрядной версией Windows выберите **jdk-8u201-windows-x64.exe**.</span><span class="sxs-lookup"><span data-stu-id="50b73-123">For example, select **jdk-8u201-windows-x64.exe** for a Windows x64 machine.</span></span> <span data-ttu-id="50b73-124">Затем используйте команду `java`, чтобы проверить установку.</span><span class="sxs-lookup"><span data-stu-id="50b73-124">Then, use the command `java` to verify the installation.</span></span>

![Скачать Java](https://dotnet.microsoft.com/static/images/java-jdk-downloads-windows.png?v=6BbJHoNyDO-PyYVciImr5wzh2AW_YHNcyb3p093AwPA)

### <a name="3-install-7-zip"></a><span data-ttu-id="50b73-126">3. Установка 7-Zip</span><span class="sxs-lookup"><span data-stu-id="50b73-126">3. Install 7-zip</span></span>

<span data-ttu-id="50b73-127">Apache Spark загружается как сжатый файл TGZ.</span><span class="sxs-lookup"><span data-stu-id="50b73-127">Apache Spark is downloaded as a compressed .tgz file.</span></span> <span data-ttu-id="50b73-128">Чтобы извлечь файл, используйте программу-архиватор, например 7-Zip.</span><span class="sxs-lookup"><span data-stu-id="50b73-128">Use an extraction program, like 7-zip, to extract the file.</span></span>

* <span data-ttu-id="50b73-129">Посетите [страницу загрузок 7-Zip](https://www.7-zip.org/).</span><span class="sxs-lookup"><span data-stu-id="50b73-129">Visit [7-Zip downloads](https://www.7-zip.org/).</span></span>
* <span data-ttu-id="50b73-130">В первой таблице на странице выберите загрузку 32-разрядной (x86) или 64-разрядной версии (x64) в зависимости от вашей операционной системы.</span><span class="sxs-lookup"><span data-stu-id="50b73-130">In the first table on the page, select the 32-bit x86 or 64-bit x64 download, depending on your operating system.</span></span>
* <span data-ttu-id="50b73-131">После завершения загрузки запустите установщик.</span><span class="sxs-lookup"><span data-stu-id="50b73-131">When the download completes, run the installer.</span></span>

![Скачать 7-Zip](https://dotnet.microsoft.com/static/images/7-zip-downloads.png?v=W6qWtFC1tTMKv3YGXz7lBa9F3M22uWyTvkMmunyroNk)

### <a name="4-install-apache-spark"></a><span data-ttu-id="50b73-133">4. Установка Apache Spark</span><span class="sxs-lookup"><span data-stu-id="50b73-133">4. Install Apache Spark</span></span>

<span data-ttu-id="50b73-134">[Скачайте и установите Apache Spark](https://spark.apache.org/downloads.html).</span><span class="sxs-lookup"><span data-stu-id="50b73-134">[Download and install Apache Spark](https://spark.apache.org/downloads.html).</span></span> <span data-ttu-id="50b73-135">Вам потребуется выбрать одну из следующих версий: 2.3.\* либо 2.4.0, 2.4.1, 2.4.3 или 2.4.4 (.NET для Apache Spark несовместима с другими версиями Apache Spark).</span><span class="sxs-lookup"><span data-stu-id="50b73-135">You'll need to select from version 2.3.\* or 2.4.0, 2.4.1, 2.4.3, or 2.4.4 (.NET for Apache Spark is not compatible with other versions of Apache Spark).</span></span>

<span data-ttu-id="50b73-136">Команды, используемые на следующих этапах, подразумевают, что [скачана и установлена версия Apache Spark 2.4.1](https://archive.apache.org/dist/spark/spark-2.4.1/spark-2.4.1-bin-hadoop2.7.tgz).</span><span class="sxs-lookup"><span data-stu-id="50b73-136">The commands used in the following steps assume you have [downloaded and installed Apache Spark 2.4.1](https://archive.apache.org/dist/spark/spark-2.4.1/spark-2.4.1-bin-hadoop2.7.tgz).</span></span> <span data-ttu-id="50b73-137">Если вы хотите использовать другую версию, замените **2.4.1** на соответствующий номер версии.</span><span class="sxs-lookup"><span data-stu-id="50b73-137">If you wish to use a different version, replace **2.4.1** with the appropriate version number.</span></span> <span data-ttu-id="50b73-138">Затем извлеките файл **TAR** и файлы Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="50b73-138">Then, extract the **.tar** file and the Apache Spark files.</span></span>

<span data-ttu-id="50b73-139">Чтобы извлечь вложенный файл **TAR**:</span><span class="sxs-lookup"><span data-stu-id="50b73-139">To extract the nested **.tar** file:</span></span>

* <span data-ttu-id="50b73-140">Найдите скачанный файл **spark-2.4.1-bin-hadoop2.7.tgz**.</span><span class="sxs-lookup"><span data-stu-id="50b73-140">Locate the **spark-2.4.1-bin-hadoop2.7.tgz** file that you downloaded.</span></span>
* <span data-ttu-id="50b73-141">Щелкните файл правой кнопкой мыши и выберите **7-Zip -> Извлечь сюда**.</span><span class="sxs-lookup"><span data-stu-id="50b73-141">Right click on the file and select **7-Zip -> Extract here**.</span></span>
* <span data-ttu-id="50b73-142">**spark-2.4.1-bin-hadoop2.7.tar** будет создан рядом со скачанным файлом **TGZ**.</span><span class="sxs-lookup"><span data-stu-id="50b73-142">**spark-2.4.1-bin-hadoop2.7.tar** is created alongside the **.tgz** file you downloaded.</span></span>

<span data-ttu-id="50b73-143">Чтобы извлечь файлы Apache Spark:</span><span class="sxs-lookup"><span data-stu-id="50b73-143">To extract the Apache Spark files:</span></span>

* <span data-ttu-id="50b73-144">Щелкните правой кнопкой мыши **spark-2.4.1-bin-hadoop2.7.tar** и выберите **7-Zip-> Извлечь файлы…**</span><span class="sxs-lookup"><span data-stu-id="50b73-144">Right click on **spark-2.4.1-bin-hadoop2.7.tar** and select **7-Zip -> Extract files...**</span></span>
* <span data-ttu-id="50b73-145">Введите **C:\bin** в поле **Извлечь в**.</span><span class="sxs-lookup"><span data-stu-id="50b73-145">Enter **C:\bin** in the **Extract to** field.</span></span>
* <span data-ttu-id="50b73-146">Снимите флажок под полем **Извлечь в**.</span><span class="sxs-lookup"><span data-stu-id="50b73-146">Uncheck the checkbox below the **Extract to** field.</span></span>
* <span data-ttu-id="50b73-147">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="50b73-147">Select **OK**.</span></span>
* <span data-ttu-id="50b73-148">Файлы Apache Spark будут извлечены в папку C:\bin\spark-2.4.1-bin-hadoop2.7</span><span class="sxs-lookup"><span data-stu-id="50b73-148">The Apache Spark files are extracted to C:\bin\spark-2.4.1-bin-hadoop2.7</span></span>\

![Установка Spark](https://dotnet.microsoft.com/static/images/spark-extract-with-7-zip.png?v=YvjUv54LIxI9FbALPC3h8zSQdyMtK2-NKbFOliG-f8M)

<span data-ttu-id="50b73-150">Выполните следующие команды, чтобы задать переменные среды, используемые для размещения Apache Spark:</span><span class="sxs-lookup"><span data-stu-id="50b73-150">Run the following commands to set the environment variables used to locate Apache Spark:</span></span>

```console
setx HADOOP_HOME C:\bin\spark-2.4.1-bin-hadoop2.7\
setx SPARK_HOME C:\bin\spark-2.4.1-bin-hadoop2.7\
```

<span data-ttu-id="50b73-151">После установки всего необходимого и настройки переменных среды, откройте **новую** командную строку и выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="50b73-151">Once you've installed everything and set your environment variables, open a **new** command prompt and run the following command:</span></span>

`%SPARK_HOME%\bin\spark-submit --version`

<span data-ttu-id="50b73-152">Если команда выполняется и выводит сведения о версии, можно перейти к следующему шагу.</span><span class="sxs-lookup"><span data-stu-id="50b73-152">If the command runs and prints version information, you can move to the next step.</span></span>

<span data-ttu-id="50b73-153">При возникновении ошибки `'spark-submit' is not recognized as an internal or external command` убедитесь, что вы открыли **новую** командную строку.</span><span class="sxs-lookup"><span data-stu-id="50b73-153">If you receive a `'spark-submit' is not recognized as an internal or external command` error, make sure you opened a **new** command prompt.</span></span>

### <a name="5-install-net-for-apache-spark"></a><span data-ttu-id="50b73-154">5. Установка .NET для Apache Spark</span><span class="sxs-lookup"><span data-stu-id="50b73-154">5. Install .NET for Apache Spark</span></span>

<span data-ttu-id="50b73-155">Загрузите выпуск [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) со страницы выпусков .NET для Apache Spark в GitHub.</span><span class="sxs-lookup"><span data-stu-id="50b73-155">Download the [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) release from the .NET for Apache Spark GitHub.</span></span> <span data-ttu-id="50b73-156">Например, если у вас компьютер Windows и вы планируете использовать .NET Core, [загрузите выпуск netcoreapp 2.1 для Windows x64 ](https://github.com/dotnet/spark/releases/download/v0.6.0/Microsoft.Spark.Worker.netcoreapp2.1.win-x64-0.6.0.zip).</span><span class="sxs-lookup"><span data-stu-id="50b73-156">For example if you're on a Windows machine and plan to use .NET Core, [download the Windows x64 netcoreapp2.1 release](https://github.com/dotnet/spark/releases/download/v0.6.0/Microsoft.Spark.Worker.netcoreapp2.1.win-x64-0.6.0.zip).</span></span>

<span data-ttu-id="50b73-157">Для извлечения Microsoft.Spark.Worker:</span><span class="sxs-lookup"><span data-stu-id="50b73-157">To extract the Microsoft.Spark.Worker:</span></span>

* <span data-ttu-id="50b73-158">Найдите скачанный файл **Microsoft.Spark.Worker.netcoreapp2.1.win-x64-0.6.0.zip**.</span><span class="sxs-lookup"><span data-stu-id="50b73-158">Locate the **Microsoft.Spark.Worker.netcoreapp2.1.win-x64-0.6.0.zip** file that you downloaded.</span></span>
* <span data-ttu-id="50b73-159">Щелкните правой кнопкой мыши и выберите **7-Zip -> Извлечь файлы…** .</span><span class="sxs-lookup"><span data-stu-id="50b73-159">Right click and select **7-Zip -> Extract files...**.</span></span>
* <span data-ttu-id="50b73-160">Введите **C:\bin** в поле **Извлечь в**.</span><span class="sxs-lookup"><span data-stu-id="50b73-160">Enter **C:\bin** in the **Extract to** field.</span></span>
* <span data-ttu-id="50b73-161">Снимите флажок под полем **Извлечь в**.</span><span class="sxs-lookup"><span data-stu-id="50b73-161">Uncheck the checkbox below the **Extract to** field.</span></span>
* <span data-ttu-id="50b73-162">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="50b73-162">Select **OK**.</span></span>

![Установка .NET Spark](https://dotnet.microsoft.com/static/images/dotnet-for-spark-extract-with-7-zip.png?v=jwCyum9mL0mGIi4V5zC7yuvLfcj1_nL-QFFD8TClhZk)

### <a name="6-install-winutils"></a><span data-ttu-id="50b73-164">6.  Установка WinUtils</span><span class="sxs-lookup"><span data-stu-id="50b73-164">6. Install WinUtils</span></span>

<span data-ttu-id="50b73-165">.NET для Apache Spark требует установки WinUtils вместе с Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="50b73-165">.NET for Apache Spark requires WinUtils to be installed alongside Apache Spark.</span></span> <span data-ttu-id="50b73-166">[Скачайте winutils.exe](https://github.com/steveloughran/winutils/blob/master/hadoop-2.7.1/bin/winutils.exe).</span><span class="sxs-lookup"><span data-stu-id="50b73-166">[Download winutils.exe](https://github.com/steveloughran/winutils/blob/master/hadoop-2.7.1/bin/winutils.exe).</span></span> <span data-ttu-id="50b73-167">Затем скопируйте WinUtils в папку **C:\bin\spark-2.4.1-bin-hadoop2.7\bin**.</span><span class="sxs-lookup"><span data-stu-id="50b73-167">Then, copy WinUtils into **C:\bin\spark-2.4.1-bin-hadoop2.7\bin**.</span></span>

> [!NOTE]
> <span data-ttu-id="50b73-168">Если вы используете другую версию Hadoop, которая указывается в конце имени папки установки Spark, [выберите версию WinUtils](https://github.com/steveloughran/winutils), совместимую с вашей версией Hadoop.</span><span class="sxs-lookup"><span data-stu-id="50b73-168">If you are using a different version of Hadoop, which is annotated at the end of your Spark install folder name, [select the version of WinUtils](https://github.com/steveloughran/winutils) that's compatible with your version of Hadoop.</span></span>

### <a name="7-set-dotnet_worker_dir-and-check-dependencies"></a><span data-ttu-id="50b73-169">7. Установка DOTNET_WORKER_DIR и проверка зависимостей</span><span class="sxs-lookup"><span data-stu-id="50b73-169">7. Set DOTNET_WORKER_DIR and check dependencies</span></span>

<span data-ttu-id="50b73-170">Выполните следующую команду, чтобы задать переменную среды `DOTNET_WORKER_DIR`, которая используется приложениями .NET для обнаружения .NET для Apache Spark:</span><span class="sxs-lookup"><span data-stu-id="50b73-170">Run the following command to set the `DOTNET_WORKER_DIR` Environment Variable, which is used by .NET apps to locate .NET for Apache Spark:</span></span>

`setx DOTNET_WORKER_DIR "C:\bin\Microsoft.Spark.Worker-0.6.0"`

<span data-ttu-id="50b73-171">Наконец, перед переходом к следующему разделу еще раз проверьте, можно ли выполнять команды `dotnet`, `java`, `mvn` и `spark-shell` из командной строки.</span><span class="sxs-lookup"><span data-stu-id="50b73-171">Finally, double-check that you can run `dotnet`, `java`, `mvn`, `spark-shell` from your command line before you move to the next section.</span></span>

## <a name="write-a-net-for-apache-spark-app"></a><span data-ttu-id="50b73-172">Написание приложения .NET для Apache Spark</span><span class="sxs-lookup"><span data-stu-id="50b73-172">Write a .NET for Apache Spark app</span></span>

### <a name="1-create-a-console-app"></a><span data-ttu-id="50b73-173">1. Создание консольного приложения</span><span class="sxs-lookup"><span data-stu-id="50b73-173">1. Create a console app</span></span>

<span data-ttu-id="50b73-174">В командной строке выполните следующие команды, чтобы создать новое консольное приложение:</span><span class="sxs-lookup"><span data-stu-id="50b73-174">In your command prompt, run the following commands to create a new console application:</span></span>

```console
dotnet new console -o mySparkApp
cd mySparkApp
```

<span data-ttu-id="50b73-175">Команда `dotnet` создаст для вас приложение `new` типа `console`.</span><span class="sxs-lookup"><span data-stu-id="50b73-175">The `dotnet` command creates a `new` application of type `console` for you.</span></span> <span data-ttu-id="50b73-176">Параметр `-o` создаст каталог с именем *mySparkApp*, в котором хранится приложение и используемые им файлы.</span><span class="sxs-lookup"><span data-stu-id="50b73-176">The `-o` parameter creates a directory named *mySparkApp* where your app is stored and populates it with the required files.</span></span> <span data-ttu-id="50b73-177">Команда `cd mySparkApp` изменит каталог на только что созданный каталог приложения.</span><span class="sxs-lookup"><span data-stu-id="50b73-177">The `cd mySparkApp` command changes the directory to the app directory you just created.</span></span>

### <a name="2-install-nuget-package"></a><span data-ttu-id="50b73-178">2. Установка пакета NuGet</span><span class="sxs-lookup"><span data-stu-id="50b73-178">2. Install NuGet package</span></span>

<span data-ttu-id="50b73-179">Чтобы использовать .NET для Apache Spark в приложении, установите пакет Microsoft.Spark.</span><span class="sxs-lookup"><span data-stu-id="50b73-179">To use .NET for Apache Spark in an app, install the Microsoft.Spark package.</span></span> <span data-ttu-id="50b73-180">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="50b73-180">In your command prompt, run the following command:</span></span>

`dotnet add package Microsoft.Spark --version 0.6.0`

### <a name="3-code-your-app"></a><span data-ttu-id="50b73-181">3. Написание кода приложения</span><span class="sxs-lookup"><span data-stu-id="50b73-181">3. Code your app</span></span>

<span data-ttu-id="50b73-182">Откройте *Program.cs* в Visual Studio Code или любом текстовом редакторе и замените весь код следующим:</span><span class="sxs-lookup"><span data-stu-id="50b73-182">Open *Program.cs* in Visual Studio Code, or any text editor, and replace all of the code with the following:</span></span>

```csharp
using Microsoft.Spark.Sql;

namespace MySparkApp
{
    class Program
    {
        static void Main(string[] args)
        {
            // Create a Spark session.
            var spark = SparkSession
                .Builder()
                .AppName("word_count_sample")
                .GetOrCreate();

            // Create initial DataFrame.
            DataFrame dataFrame = spark.Read().Text("input.txt");

            // Count words.
            var words = dataFrame
                .Select(Functions.Split(Functions.Col("value"), " ").Alias("words"))
                .Select(Functions.Explode(Functions.Col("words"))
                .Alias("word"))
                .GroupBy("word")
                .Count()
                .OrderBy(Functions.Col("count").Desc());

            // Show results.
            words.Show();

            // Stop Spark session.
            spark.Stop();
        }
    }
}
```

### <a name="4-add-data-file"></a><span data-ttu-id="50b73-183">4. Добавление файла данных</span><span class="sxs-lookup"><span data-stu-id="50b73-183">4. Add data file</span></span>

<span data-ttu-id="50b73-184">Ваше приложение обрабатывает файл, содержащий строки текста.</span><span class="sxs-lookup"><span data-stu-id="50b73-184">Your app processes a file containing lines of text.</span></span> <span data-ttu-id="50b73-185">Создайте файл *input.txt* в каталоге *mySparkApp*, содержащий следующий текст:</span><span class="sxs-lookup"><span data-stu-id="50b73-185">Create an *input.txt* file in your *mySparkApp* directory, containing the following text:</span></span>

```text
Hello World
This .NET app uses .NET for Apache Spark
This .NET app counts words with Apache Spark
```

## <a name="run-your-net-for-apache-spark-app"></a><span data-ttu-id="50b73-186">Запуск приложения .NET для Apache Spark</span><span class="sxs-lookup"><span data-stu-id="50b73-186">Run your .NET for Apache Spark app</span></span>

1. <span data-ttu-id="50b73-187">Запустите сборку приложения с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="50b73-187">Run the following command to build your application:</span></span>

   ```dotnetcli
   dotnet build
   ```

2. <span data-ttu-id="50b73-188">Отправьте приложение для запуска на Apache Spark с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="50b73-188">Run the following command to submit your application to run on Apache Spark:</span></span>

   ```powershell
   %SPARK_HOME%\bin\spark-submit --class org.apache.spark.deploy.dotnet.DotnetRunner --master local bin\Debug\netcoreapp3.0\microsoft-spark-2.4.x-0.6.0.jar dotnet bin\Debug\netcoreapp3.0\mySparkApp.dll
   ```

3. <span data-ttu-id="50b73-189">При запуске приложения данные подсчета слов из файла *input.txt* записываются в консоль.</span><span class="sxs-lookup"><span data-stu-id="50b73-189">When your app runs, the word count data of the *input.txt* file is written to the console.</span></span>

<span data-ttu-id="50b73-190">Поздравляем!</span><span class="sxs-lookup"><span data-stu-id="50b73-190">Congratulations!</span></span> <span data-ttu-id="50b73-191">Вы успешно создали и запустили приложение .NET для Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="50b73-191">You successfully authored and ran a .NET for Apache Spark app.</span></span>

## <a name="next-steps"></a><span data-ttu-id="50b73-192">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="50b73-192">Next steps</span></span>

<span data-ttu-id="50b73-193">В этом руководстве вы узнали, как:</span><span class="sxs-lookup"><span data-stu-id="50b73-193">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="50b73-194">Подготовка среды Windows для .NET для Apache Spark</span><span class="sxs-lookup"><span data-stu-id="50b73-194">Prepare your Windows environment for .NET for Apache Spark</span></span>
> * <span data-ttu-id="50b73-195">написать свое первое приложение .NET для Apache Spark;</span><span class="sxs-lookup"><span data-stu-id="50b73-195">Write your first .NET for Apache Spark application</span></span>
> * <span data-ttu-id="50b73-196">скомпилировать и запустить простое приложение .NET для Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="50b73-196">Build and run your simple .NET for Apache Spark application</span></span>

<span data-ttu-id="50b73-197">Видео, подробнее объясняющее приведенные выше шаги, можно найти в серии видео [.NET for Apache Spark 101](https://channel9.msdn.com/Series/NET-for-Apache-Spark-101/Run-Your-First-NET-for-Apache-Spark-App) (Введение в .NET для Apache Spark).</span><span class="sxs-lookup"><span data-stu-id="50b73-197">To see a video explaining the steps above, checkout the [.NET for Apache Spark 101 video series](https://channel9.msdn.com/Series/NET-for-Apache-Spark-101/Run-Your-First-NET-for-Apache-Spark-App).</span></span>

<span data-ttu-id="50b73-198">Дополнительные сведения см. на странице ресурсов.</span><span class="sxs-lookup"><span data-stu-id="50b73-198">Check out the resources page to learn more.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="50b73-199">Ресурсы по .NET для Apache Spark</span><span class="sxs-lookup"><span data-stu-id="50b73-199">.NET for Apache Spark Resources</span></span>](../resources/index.md)
