---
title: Начало работы с .NET для Apache Spark
description: Узнайте, как запустить приложение .NET для Apache Spark, используя .NET Core на Windows, macOS и Ubuntu.
ms.date: 01/31/2020
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 018c21804bf942233e07039281d7ec22a6bef763
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2020
ms.locfileid: "77092321"
---
# <a name="tutorial-get-started-with-net-for-apache-spark"></a><span data-ttu-id="5d7ed-103">Учебник. Начало работы с .NET для Apache Spark</span><span class="sxs-lookup"><span data-stu-id="5d7ed-103">Tutorial: Get started with .NET for Apache Spark</span></span>

<span data-ttu-id="5d7ed-104">В этом руководстве описывается, как запустить приложение .NET для Apache Spark, используя .NET Core на Windows, macOS и Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="5d7ed-104">This tutorial teaches you how to run a .NET for Apache Spark app using .NET Core on Windows, MacOS, and Ubuntu.</span></span>

<span data-ttu-id="5d7ed-105">В этом руководстве вы узнаете, как:</span><span class="sxs-lookup"><span data-stu-id="5d7ed-105">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="5d7ed-106">подготовить среду под .NET для Apache Spark;</span><span class="sxs-lookup"><span data-stu-id="5d7ed-106">Prepare your environment for .NET for Apache Spark</span></span>
> * <span data-ttu-id="5d7ed-107">написать свое первое приложение .NET для Apache Spark;</span><span class="sxs-lookup"><span data-stu-id="5d7ed-107">Write your first .NET for Apache Spark application</span></span>
> * <span data-ttu-id="5d7ed-108">скомпилировать и запустить простое приложение .NET для Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="5d7ed-108">Build and run your simple .NET for Apache Spark application</span></span>

## <a name="prepare-your-environment"></a><span data-ttu-id="5d7ed-109">Подготовка среды</span><span class="sxs-lookup"><span data-stu-id="5d7ed-109">Prepare your environment</span></span>

<span data-ttu-id="5d7ed-110">Прежде чем приступить к написанию приложения, нужно настроить некоторые необходимые зависимости.</span><span class="sxs-lookup"><span data-stu-id="5d7ed-110">Before you begin writing your app, you need to set up some prerequisite dependencies.</span></span> <span data-ttu-id="5d7ed-111">Если вы можете выполнить `dotnet`, `java`, `mvn`, `spark-shell` из среды командной строки, то ваша среда уже подготовлена, и вы можете перейти к следующему разделу.</span><span class="sxs-lookup"><span data-stu-id="5d7ed-111">If you can run `dotnet`, `java`, `mvn`, `spark-shell` from your command line environment, then your environment is already prepared and you can skip to the next section.</span></span> <span data-ttu-id="5d7ed-112">Если эти команды или хотя бы одну из них выполнить не получается, сделайте следующее.</span><span class="sxs-lookup"><span data-stu-id="5d7ed-112">If you cannot run any or all of the commands, do the following steps.</span></span>

### <a name="1-install-net"></a><span data-ttu-id="5d7ed-113">1. Установка .NET</span><span class="sxs-lookup"><span data-stu-id="5d7ed-113">1. Install .NET</span></span>

<span data-ttu-id="5d7ed-114">Чтобы приступить к созданию приложений .NET, необходимо загрузить и установить пакет средств разработки программного обеспечения (SDK) для .NET.</span><span class="sxs-lookup"><span data-stu-id="5d7ed-114">To start building .NET apps, you need to download and install the .NET SDK (Software Development Kit).</span></span>

<span data-ttu-id="5d7ed-115">Скачайте и установите [пакет SDK для .NET Core](https://dotnet.microsoft.com/download/dotnet-core/3.1).</span><span class="sxs-lookup"><span data-stu-id="5d7ed-115">Download and install the [.NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core/3.1).</span></span> <span data-ttu-id="5d7ed-116">При установке пакета SDK в переменную PATH добавляется цепочка инструментов `dotnet`.</span><span class="sxs-lookup"><span data-stu-id="5d7ed-116">Installing the SDK adds the `dotnet` toolchain to your PATH.</span></span>

<span data-ttu-id="5d7ed-117">Установив пакет SDK для .NET Core, откройте новое окно командной строки или терминала и выполните команду `dotnet`.</span><span class="sxs-lookup"><span data-stu-id="5d7ed-117">Once you've installed the .NET Core SDK, open a new command prompt or terminal and run `dotnet`.</span></span>

<span data-ttu-id="5d7ed-118">Если команда выполняется и выводит сведения об использовании dotnet, можно перейти к следующему шагу.</span><span class="sxs-lookup"><span data-stu-id="5d7ed-118">If the command runs and prints out information about how to use dotnet, can move to the next step.</span></span> <span data-ttu-id="5d7ed-119">Если возникает ошибка `'dotnet' is not recognized as an internal or external command`, убедитесь, что команда выполняется в **новом** окне терминала или командной строки.</span><span class="sxs-lookup"><span data-stu-id="5d7ed-119">If you receive a `'dotnet' is not recognized as an internal or external command` error, make sure you opened a **new** command prompt or terminal before running the command.</span></span>

### <a name="2-install-java"></a><span data-ttu-id="5d7ed-120">2. Установка Java</span><span class="sxs-lookup"><span data-stu-id="5d7ed-120">2. Install Java</span></span>

<span data-ttu-id="5d7ed-121">Установите [Java 8.1](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html) для Windows и macOS или [OpenJDK 8](https://openjdk.java.net/install/) для Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="5d7ed-121">Install [Java 8.1](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html) for Windows and MacOS, or [OpenJDK 8](https://openjdk.java.net/install/) for Ubuntu.</span></span>

<span data-ttu-id="5d7ed-122">Выберите соответствующую версию для вашей операционной системы.</span><span class="sxs-lookup"><span data-stu-id="5d7ed-122">Select the appropriate version for your operating system.</span></span> <span data-ttu-id="5d7ed-123">Например, выберите **jdk-8u201-windows-x64.exe** для компьютера с 64-разрядной версией Windows (как показано ниже) или **jdk-8u231-macosx-x64.dmg** для macOS.</span><span class="sxs-lookup"><span data-stu-id="5d7ed-123">For example, select **jdk-8u201-windows-x64.exe** for a Windows x64 machine (as shown below) or **jdk-8u231-macosx-x64.dmg** for MacOS.</span></span> <span data-ttu-id="5d7ed-124">Затем используйте команду `java`, чтобы проверить установку.</span><span class="sxs-lookup"><span data-stu-id="5d7ed-124">Then, use the command `java` to verify the installation.</span></span>

![Скачать Java](https://dotnet.microsoft.com/static/images/java-jdk-downloads-windows.png?v=6BbJHoNyDO-PyYVciImr5wzh2AW_YHNcyb3p093AwPA)

### <a name="3-install-compression-software"></a><span data-ttu-id="5d7ed-126">3. Установка ПО для сжатия</span><span class="sxs-lookup"><span data-stu-id="5d7ed-126">3. Install compression software</span></span>

<span data-ttu-id="5d7ed-127">Apache Spark загружается как сжатый файл TGZ.</span><span class="sxs-lookup"><span data-stu-id="5d7ed-127">Apache Spark is downloaded as a compressed .tgz file.</span></span> <span data-ttu-id="5d7ed-128">Чтобы извлечь файл, используйте программу-архиватор, например [7-Zip](https://www.7-zip.org/) или [WinZip](https://www.winzip.com/).</span><span class="sxs-lookup"><span data-stu-id="5d7ed-128">Use an extraction program, like [7-Zip](https://www.7-zip.org/) or [WinZip](https://www.winzip.com/), to extract the file.</span></span>

### <a name="4-install-apache-spark"></a><span data-ttu-id="5d7ed-129">4. Установка Apache Spark</span><span class="sxs-lookup"><span data-stu-id="5d7ed-129">4. Install Apache Spark</span></span>

<span data-ttu-id="5d7ed-130">[Скачайте и установите Apache Spark](https://spark.apache.org/downloads.html).</span><span class="sxs-lookup"><span data-stu-id="5d7ed-130">[Download and install Apache Spark](https://spark.apache.org/downloads.html).</span></span> <span data-ttu-id="5d7ed-131">Вам потребуется выбрать одну из следующих версий: 2.3.\* либо 2.4.0, 2.4.1, 2.4.3 или 2.4.4 (.NET для Apache Spark несовместима с другими версиями Apache Spark).</span><span class="sxs-lookup"><span data-stu-id="5d7ed-131">You'll need to select from version 2.3.\* or 2.4.0, 2.4.1, 2.4.3, or 2.4.4 (.NET for Apache Spark is not compatible with other versions of Apache Spark).</span></span>

<span data-ttu-id="5d7ed-132">Команды, используемые на следующих этапах, подразумевают, что [скачана и установлена версия Apache Spark 2.4.1](https://archive.apache.org/dist/spark/spark-2.4.1/spark-2.4.1-bin-hadoop2.7.tgz).</span><span class="sxs-lookup"><span data-stu-id="5d7ed-132">The commands used in the following steps assume you have [downloaded and installed Apache Spark 2.4.1](https://archive.apache.org/dist/spark/spark-2.4.1/spark-2.4.1-bin-hadoop2.7.tgz).</span></span> <span data-ttu-id="5d7ed-133">Если вы хотите использовать другую версию, замените **2.4.1** на соответствующий номер версии.</span><span class="sxs-lookup"><span data-stu-id="5d7ed-133">If you wish to use a different version, replace **2.4.1** with the appropriate version number.</span></span> <span data-ttu-id="5d7ed-134">Затем извлеките файл **TAR** и файлы Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="5d7ed-134">Then, extract the **.tar** file and the Apache Spark files.</span></span>

<span data-ttu-id="5d7ed-135">Чтобы извлечь вложенный файл **TAR**:</span><span class="sxs-lookup"><span data-stu-id="5d7ed-135">To extract the nested **.tar** file:</span></span>

* <span data-ttu-id="5d7ed-136">Найдите скачанный файл **spark-2.4.1-bin-hadoop2.7.tgz**.</span><span class="sxs-lookup"><span data-stu-id="5d7ed-136">Locate the **spark-2.4.1-bin-hadoop2.7.tgz** file that you downloaded.</span></span>
* <span data-ttu-id="5d7ed-137">Щелкните файл правой кнопкой мыши и выберите **7-Zip -> Извлечь сюда**.</span><span class="sxs-lookup"><span data-stu-id="5d7ed-137">Right click on the file and select **7-Zip -> Extract here**.</span></span>
* <span data-ttu-id="5d7ed-138">**spark-2.4.1-bin-hadoop2.7.tar** будет создан рядом со скачанным файлом **TGZ**.</span><span class="sxs-lookup"><span data-stu-id="5d7ed-138">**spark-2.4.1-bin-hadoop2.7.tar** is created alongside the **.tgz** file you downloaded.</span></span>

<span data-ttu-id="5d7ed-139">Чтобы извлечь файлы Apache Spark:</span><span class="sxs-lookup"><span data-stu-id="5d7ed-139">To extract the Apache Spark files:</span></span>

* <span data-ttu-id="5d7ed-140">Щелкните правой кнопкой мыши **spark-2.4.1-bin-hadoop2.7.tar** и выберите **7-Zip-> Извлечь файлы…**</span><span class="sxs-lookup"><span data-stu-id="5d7ed-140">Right click on **spark-2.4.1-bin-hadoop2.7.tar** and select **7-Zip -> Extract files...**</span></span>
* <span data-ttu-id="5d7ed-141">Введите **C:\bin** в поле **Извлечь в**.</span><span class="sxs-lookup"><span data-stu-id="5d7ed-141">Enter **C:\bin** in the **Extract to** field.</span></span>
* <span data-ttu-id="5d7ed-142">Снимите флажок под полем **Извлечь в**.</span><span class="sxs-lookup"><span data-stu-id="5d7ed-142">Uncheck the checkbox below the **Extract to** field.</span></span>
* <span data-ttu-id="5d7ed-143">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="5d7ed-143">Select **OK**.</span></span>
* <span data-ttu-id="5d7ed-144">Файлы Apache Spark будут извлечены в папку C:\bin\spark-2.4.1-bin-hadoop2.7</span><span class="sxs-lookup"><span data-stu-id="5d7ed-144">The Apache Spark files are extracted to C:\bin\spark-2.4.1-bin-hadoop2.7</span></span>\

![Установка Spark](https://dotnet.microsoft.com/static/images/spark-extract-with-7-zip.png?v=YvjUv54LIxI9FbALPC3h8zSQdyMtK2-NKbFOliG-f8M)

<span data-ttu-id="5d7ed-146">Выполните следующие команды, чтобы задать переменные сред, используемые для обнаружения Apache Spark на **Windows**:</span><span class="sxs-lookup"><span data-stu-id="5d7ed-146">Run the following commands to set the environment variables used to locate Apache Spark on **Windows**:</span></span>

```console
setx HADOOP_HOME C:\bin\spark-2.4.1-bin-hadoop2.7\
setx SPARK_HOME C:\bin\spark-2.4.1-bin-hadoop2.7\
```

<span data-ttu-id="5d7ed-147">Выполните следующие команды, чтобы задать переменные сред, используемые для обнаружения Apache Spark на **macOS** и **Ubuntu**:</span><span class="sxs-lookup"><span data-stu-id="5d7ed-147">Run the following commands to set the environment variables used to locate Apache Spark on **MacOS** and **Ubuntu**:</span></span>

```bash
export SPARK_HOME=~/bin/spark-2.4.1-bin-hadoop2.7/
export PATH="$SPARK_HOME/bin:$PATH"
source ~/.bashrc
```

<span data-ttu-id="5d7ed-148">Установив все необходимое и задав переменные сред, откройте **новое** окно командной строки или терминала и выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="5d7ed-148">Once you've installed everything and set your environment variables, open a **new** command prompt or terminal and run the following command:</span></span>

`%SPARK_HOME%\bin\spark-submit --version`

<span data-ttu-id="5d7ed-149">Если команда выполняется и выводит сведения о версии, можно перейти к следующему шагу.</span><span class="sxs-lookup"><span data-stu-id="5d7ed-149">If the command runs and prints version information, you can move to the next step.</span></span>

<span data-ttu-id="5d7ed-150">При возникновении ошибки `'spark-submit' is not recognized as an internal or external command` убедитесь, что вы открыли **новую** командную строку.</span><span class="sxs-lookup"><span data-stu-id="5d7ed-150">If you receive a `'spark-submit' is not recognized as an internal or external command` error, make sure you opened a **new** command prompt.</span></span>

### <a name="5-install-net-for-apache-spark"></a><span data-ttu-id="5d7ed-151">5. Установка .NET для Apache Spark</span><span class="sxs-lookup"><span data-stu-id="5d7ed-151">5. Install .NET for Apache Spark</span></span>

<span data-ttu-id="5d7ed-152">Загрузите выпуск [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) со страницы выпусков .NET для Apache Spark в GitHub.</span><span class="sxs-lookup"><span data-stu-id="5d7ed-152">Download the [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) release from the .NET for Apache Spark GitHub.</span></span> <span data-ttu-id="5d7ed-153">Например, если вы планируете использовать .NET Core на компьютере под управлением Windows, [скачайте выпуск netcoreapp3.1 для Windows x64](https://github.com/dotnet/spark/releases/download/v0.8.0/Microsoft.Spark.Worker.netcoreapp3.1.win-x64-0.8.0.zip).</span><span class="sxs-lookup"><span data-stu-id="5d7ed-153">For example if you're on a Windows machine and plan to use .NET Core, [download the Windows x64 netcoreapp3.1 release](https://github.com/dotnet/spark/releases/download/v0.8.0/Microsoft.Spark.Worker.netcoreapp3.1.win-x64-0.8.0.zip).</span></span>

<span data-ttu-id="5d7ed-154">Для извлечения Microsoft.Spark.Worker:</span><span class="sxs-lookup"><span data-stu-id="5d7ed-154">To extract the Microsoft.Spark.Worker:</span></span>

* <span data-ttu-id="5d7ed-155">Найдите скачанный файл **Microsoft.Spark.Worker.netcoreapp3.1.win-x64-0.8.0.zip**.</span><span class="sxs-lookup"><span data-stu-id="5d7ed-155">Locate the **Microsoft.Spark.Worker.netcoreapp3.1.win-x64-0.8.0.zip** file that you downloaded.</span></span>
* <span data-ttu-id="5d7ed-156">Щелкните правой кнопкой мыши и выберите **7-Zip -> Извлечь файлы…** .</span><span class="sxs-lookup"><span data-stu-id="5d7ed-156">Right click and select **7-Zip -> Extract files...**.</span></span>
* <span data-ttu-id="5d7ed-157">Введите **C:\bin** в поле **Извлечь в**.</span><span class="sxs-lookup"><span data-stu-id="5d7ed-157">Enter **C:\bin** in the **Extract to** field.</span></span>
* <span data-ttu-id="5d7ed-158">Снимите флажок под полем **Извлечь в**.</span><span class="sxs-lookup"><span data-stu-id="5d7ed-158">Uncheck the checkbox below the **Extract to** field.</span></span>
* <span data-ttu-id="5d7ed-159">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="5d7ed-159">Select **OK**.</span></span>

![Установка .NET Spark](https://dotnet.microsoft.com/static/images/dotnet-for-spark-extract-with-7-zip.png?v=jwCyum9mL0mGIi4V5zC7yuvLfcj1_nL-QFFD8TClhZk)

### <a name="6-install-winutils-windows-only"></a><span data-ttu-id="5d7ed-161">6.  Установка WinUtils (только для Windows)</span><span class="sxs-lookup"><span data-stu-id="5d7ed-161">6. Install WinUtils (Windows only)</span></span>

<span data-ttu-id="5d7ed-162">.NET для Apache Spark требует установки WinUtils вместе с Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="5d7ed-162">.NET for Apache Spark requires WinUtils to be installed alongside Apache Spark.</span></span> <span data-ttu-id="5d7ed-163">[Скачайте winutils.exe](https://github.com/steveloughran/winutils/blob/master/hadoop-2.7.1/bin/winutils.exe).</span><span class="sxs-lookup"><span data-stu-id="5d7ed-163">[Download winutils.exe](https://github.com/steveloughran/winutils/blob/master/hadoop-2.7.1/bin/winutils.exe).</span></span> <span data-ttu-id="5d7ed-164">Затем скопируйте WinUtils в папку **C:\bin\spark-2.4.1-bin-hadoop2.7\bin**.</span><span class="sxs-lookup"><span data-stu-id="5d7ed-164">Then, copy WinUtils into **C:\bin\spark-2.4.1-bin-hadoop2.7\bin**.</span></span>

> [!NOTE]
> <span data-ttu-id="5d7ed-165">Если вы используете другую версию Hadoop, которая указывается в конце имени папки установки Spark, [выберите версию WinUtils](https://github.com/steveloughran/winutils), совместимую с вашей версией Hadoop.</span><span class="sxs-lookup"><span data-stu-id="5d7ed-165">If you are using a different version of Hadoop, which is annotated at the end of your Spark install folder name, [select the version of WinUtils](https://github.com/steveloughran/winutils) that's compatible with your version of Hadoop.</span></span>

### <a name="7-set-dotnet_worker_dir-and-check-dependencies"></a><span data-ttu-id="5d7ed-166">7. Установка DOTNET_WORKER_DIR и проверка зависимостей</span><span class="sxs-lookup"><span data-stu-id="5d7ed-166">7. Set DOTNET_WORKER_DIR and check dependencies</span></span>

<span data-ttu-id="5d7ed-167">Выполните одну из следующих команд, чтобы задать переменную среды `DOTNET_WORKER_DIR`, которая используется приложениями .NET для обнаружения .NET для Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="5d7ed-167">Run one of the following commands to set the `DOTNET_WORKER_DIR` Environment Variable, which is used by .NET apps to locate .NET for Apache Spark.</span></span>

<span data-ttu-id="5d7ed-168">В **Windows** создайте [переменную среды](https://www.java.com/en/download/help/path.xml) с именем `DOTNET_WORKER_DIR` и присвойте ей путь к каталогу, в который вы скачали и извлекли Microsoft.Spark.Worker (например, `C:\bin\Microsoft.Spark.Worker\`).</span><span class="sxs-lookup"><span data-stu-id="5d7ed-168">On **Windows**, create a [new environment variable](https://www.java.com/en/download/help/path.xml) `DOTNET_WORKER_DIR` and set it to the directory where you downloaded and extracted the Microsoft.Spark.Worker (for example, `C:\bin\Microsoft.Spark.Worker\`).</span></span>

<span data-ttu-id="5d7ed-169">В **macOS** создайте переменную среды с помощью `export DOTNET_WORKER_DIR <your_path>` и присвойте ей путь к каталогу, в который вы скачали и извлекли Microsoft.Spark.Worker (например, *~/bin/Microsoft.Spark.Worker/* ).</span><span class="sxs-lookup"><span data-stu-id="5d7ed-169">On **MacOS**, create a new environment variable using `export DOTNET_WORKER_DIR <your_path>` and set it to the directory where you downloaded and extracted the Microsoft.Spark.Worker (for example, *~/bin/Microsoft.Spark.Worker/*).</span></span> 

<span data-ttu-id="5d7ed-170">В **Ubuntu** создайте [переменную среды](https://help.ubuntu.com/community/EnvironmentVariables) с именем `DOTNET_WORKER_DIR` и присвойте ей путь к каталогу, в который вы скачали и извлекли Microsoft.Spark.Worker (например, *~/bin/Microsoft.Spark.Worker*).</span><span class="sxs-lookup"><span data-stu-id="5d7ed-170">On **Ubuntu**, create a [new environment variable](https://help.ubuntu.com/community/EnvironmentVariables) `DOTNET_WORKER_DIR` and set it to the directory where you downloaded and extracted the Microsoft.Spark.Worker (for example, *~/bin/Microsoft.Spark.Worker*).</span></span>

<span data-ttu-id="5d7ed-171">Наконец, перед переходом к следующему разделу еще раз проверьте, можно ли выполнять команды `dotnet`, `java`, `mvn` и `spark-shell` из командной строки.</span><span class="sxs-lookup"><span data-stu-id="5d7ed-171">Finally, double-check that you can run `dotnet`, `java`, `mvn`, `spark-shell` from your command line before you move to the next section.</span></span>

## <a name="write-a-net-for-apache-spark-app"></a><span data-ttu-id="5d7ed-172">Написание приложения .NET для Apache Spark</span><span class="sxs-lookup"><span data-stu-id="5d7ed-172">Write a .NET for Apache Spark app</span></span>

### <a name="1-create-a-console-app"></a><span data-ttu-id="5d7ed-173">1. Создание консольного приложения</span><span class="sxs-lookup"><span data-stu-id="5d7ed-173">1. Create a console app</span></span>

<span data-ttu-id="5d7ed-174">В командной строке или терминале выполните следующие команды, чтобы создать новое консольное приложение:</span><span class="sxs-lookup"><span data-stu-id="5d7ed-174">In your command prompt or terminal, run the following commands to create a new console application:</span></span>

```dotnetcli
dotnet new console -o mySparkApp
cd mySparkApp
```

<span data-ttu-id="5d7ed-175">Команда `dotnet` создаст для вас приложение `new` типа `console`.</span><span class="sxs-lookup"><span data-stu-id="5d7ed-175">The `dotnet` command creates a `new` application of type `console` for you.</span></span> <span data-ttu-id="5d7ed-176">Параметр `-o` создаст каталог с именем *mySparkApp*, в котором хранится приложение и используемые им файлы.</span><span class="sxs-lookup"><span data-stu-id="5d7ed-176">The `-o` parameter creates a directory named *mySparkApp* where your app is stored and populates it with the required files.</span></span> <span data-ttu-id="5d7ed-177">Команда `cd mySparkApp` изменит каталог на только что созданный каталог приложения.</span><span class="sxs-lookup"><span data-stu-id="5d7ed-177">The `cd mySparkApp` command changes the directory to the app directory you just created.</span></span>

### <a name="2-install-nuget-package"></a><span data-ttu-id="5d7ed-178">2. Установка пакета NuGet</span><span class="sxs-lookup"><span data-stu-id="5d7ed-178">2. Install NuGet package</span></span>

<span data-ttu-id="5d7ed-179">Чтобы использовать .NET для Apache Spark в приложении, установите пакет Microsoft.Spark.</span><span class="sxs-lookup"><span data-stu-id="5d7ed-179">To use .NET for Apache Spark in an app, install the Microsoft.Spark package.</span></span> <span data-ttu-id="5d7ed-180">В командной строке или терминале выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="5d7ed-180">In your command prompt or terminal, run the following command:</span></span>

`dotnet add package Microsoft.Spark --version 0.8.0`

### <a name="3-code-your-app"></a><span data-ttu-id="5d7ed-181">3. Написание кода приложения</span><span class="sxs-lookup"><span data-stu-id="5d7ed-181">3. Code your app</span></span>

<span data-ttu-id="5d7ed-182">Откройте *Program.cs* в Visual Studio Code или любом текстовом редакторе и замените весь код следующим:</span><span class="sxs-lookup"><span data-stu-id="5d7ed-182">Open *Program.cs* in Visual Studio Code, or any text editor, and replace all of the code with the following:</span></span>

```csharp
using Microsoft.Spark.Sql;

namespace MySparkApp
{
    class Program
    {
        static void Main(string[] args)
        {
            // Create a Spark session.
            SparkSession spark = SparkSession
                .Builder()
                .AppName("word_count_sample")
                .GetOrCreate();

            // Create initial DataFrame.
            DataFrame dataFrame = spark.Read().Text("input.txt");

            // Count words.
            DataFrame words = dataFrame
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

### <a name="4-create-and-add-a-data-file"></a><span data-ttu-id="5d7ed-183">4. Создание и добавление файла данных</span><span class="sxs-lookup"><span data-stu-id="5d7ed-183">4. Create and add a data file</span></span>

<span data-ttu-id="5d7ed-184">Откройте командную строку или терминал и перейдите в папку своего приложения.</span><span class="sxs-lookup"><span data-stu-id="5d7ed-184">Open your command prompt or terminal and navigate into your app folder.</span></span>

```bash
cd <your-app-output-directory>
```

<span data-ttu-id="5d7ed-185">Ваше приложение обрабатывает файл, содержащий строки текста.</span><span class="sxs-lookup"><span data-stu-id="5d7ed-185">Your app processes a file containing lines of text.</span></span> <span data-ttu-id="5d7ed-186">Создайте файл *input.txt* в каталоге *mySparkApp*, содержащий следующий текст:</span><span class="sxs-lookup"><span data-stu-id="5d7ed-186">Create an *input.txt* file in your *mySparkApp* directory, containing the following text:</span></span>

```text
Hello World
This .NET app uses .NET for Apache Spark
This .NET app counts words with Apache Spark
```

## <a name="run-your-net-for-apache-spark-app"></a><span data-ttu-id="5d7ed-187">Запуск приложения .NET для Apache Spark</span><span class="sxs-lookup"><span data-stu-id="5d7ed-187">Run your .NET for Apache Spark app</span></span>

1. <span data-ttu-id="5d7ed-188">Запустите сборку приложения с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="5d7ed-188">Run the following command to build your application:</span></span>

   ```dotnetcli
   dotnet build
   ```

2. <span data-ttu-id="5d7ed-189">Отправьте приложение для запуска на Apache Spark с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="5d7ed-189">Run the following command to submit your application to run on Apache Spark:</span></span>

   ```console
   spark-submit \
   --class org.apache.spark.deploy.dotnet.DotnetRunner \
   --master local \
   microsoft-spark-2.4.x-<version>.jar \
   dotnet HelloSpark.dll
   ```

   > [!NOTE]
   > <span data-ttu-id="5d7ed-190">При выполнении этой команды предполагается, что вы скачали Apache Spark и добавили это решение в переменную среды PATH, чтобы использовать `spark-submit`.</span><span class="sxs-lookup"><span data-stu-id="5d7ed-190">This command assumes you have downloaded Apache Spark and added it to your PATH environment variable to be able to use `spark-submit`.</span></span> <span data-ttu-id="5d7ed-191">В противном случае потребуется использовать полный путь (например, *C:\bin\apache-spark\bin\spark-submit* или *~/spark/bin/spark-submit*).</span><span class="sxs-lookup"><span data-stu-id="5d7ed-191">Otherwise, you'd have to use the full path (for example, *C:\bin\apache-spark\bin\spark-submit* or *~/spark/bin/spark-submit*).</span></span>

3. <span data-ttu-id="5d7ed-192">При запуске приложения данные подсчета слов из файла *input.txt* записываются в консоль.</span><span class="sxs-lookup"><span data-stu-id="5d7ed-192">When your app runs, the word count data of the *input.txt* file is written to the console.</span></span>

<span data-ttu-id="5d7ed-193">Поздравляем!</span><span class="sxs-lookup"><span data-stu-id="5d7ed-193">Congratulations!</span></span> <span data-ttu-id="5d7ed-194">Вы успешно создали и запустили приложение .NET для Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="5d7ed-194">You successfully authored and ran a .NET for Apache Spark app.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5d7ed-195">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="5d7ed-195">Next steps</span></span>

<span data-ttu-id="5d7ed-196">В этом руководстве вы узнали, как:</span><span class="sxs-lookup"><span data-stu-id="5d7ed-196">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="5d7ed-197">Подготовка среды Windows для .NET для Apache Spark</span><span class="sxs-lookup"><span data-stu-id="5d7ed-197">Prepare your Windows environment for .NET for Apache Spark</span></span>
> * <span data-ttu-id="5d7ed-198">написать свое первое приложение .NET для Apache Spark;</span><span class="sxs-lookup"><span data-stu-id="5d7ed-198">Write your first .NET for Apache Spark application</span></span>
> * <span data-ttu-id="5d7ed-199">скомпилировать и запустить простое приложение .NET для Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="5d7ed-199">Build and run your simple .NET for Apache Spark application</span></span>

<span data-ttu-id="5d7ed-200">Видео, подробнее объясняющее приведенные выше шаги, можно найти в серии видео [.NET for Apache Spark 101](https://channel9.msdn.com/Series/NET-for-Apache-Spark-101/Run-Your-First-NET-for-Apache-Spark-App) (Введение в .NET для Apache Spark).</span><span class="sxs-lookup"><span data-stu-id="5d7ed-200">To see a video explaining the steps above, checkout the [.NET for Apache Spark 101 video series](https://channel9.msdn.com/Series/NET-for-Apache-Spark-101/Run-Your-First-NET-for-Apache-Spark-App).</span></span>

<span data-ttu-id="5d7ed-201">Дополнительные сведения см. на странице ресурсов.</span><span class="sxs-lookup"><span data-stu-id="5d7ed-201">Check out the resources page to learn more.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="5d7ed-202">Ресурсы по .NET для Apache Spark</span><span class="sxs-lookup"><span data-stu-id="5d7ed-202">.NET for Apache Spark Resources</span></span>](../resources/index.md)
