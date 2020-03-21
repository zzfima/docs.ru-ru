---
title: Практическое руководство. Локализация приложения
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- localization [WPF], applications
- LocBaml tool [WPF]
- applications [WPF], localizing
ms.assetid: 5001227e-9326-48a4-9dcd-ba1b89ee6653
ms.openlocfilehash: f2e7e5e8879e89806cfd457a1af80f51b91871cb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174216"
---
# <a name="how-to-localize-an-application"></a><span data-ttu-id="40a3d-102">Практическое руководство. Локализация приложения</span><span class="sxs-lookup"><span data-stu-id="40a3d-102">How to: Localize an Application</span></span>
<span data-ttu-id="40a3d-103">В этом учебнике рассматривается создание локализованного приложения с помощью средства LocBaml.</span><span class="sxs-lookup"><span data-stu-id="40a3d-103">This tutorial explains how to create a localized application by using the LocBaml tool.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="40a3d-104">Средство LocBaml не является готовым приложением.</span><span class="sxs-lookup"><span data-stu-id="40a3d-104">The LocBaml tool is not a production-ready application.</span></span> <span data-ttu-id="40a3d-105">Оно представлено в качестве примера, в котором используются некоторые API локализации и показывается, как можно написать средство локализации.</span><span class="sxs-lookup"><span data-stu-id="40a3d-105">It is presented as a sample that uses some of the localization APIs and illustrates how you might write a localization tool.</span></span>  
  
<a name="Introduction"></a>
## <a name="overview"></a><span data-ttu-id="40a3d-106">Обзор</span><span class="sxs-lookup"><span data-stu-id="40a3d-106">Overview</span></span>  
 <span data-ttu-id="40a3d-107">В этом обзоре предоставляется поэтапный подход к локализации приложений.</span><span class="sxs-lookup"><span data-stu-id="40a3d-107">This discussion gives you a step-by-step approach to localizing an application.</span></span> <span data-ttu-id="40a3d-108">Сначала необходимо подготовить приложение так, чтобы можно было извлечь текст, который будет переведен.</span><span class="sxs-lookup"><span data-stu-id="40a3d-108">First, you will prepare your application so that the text that will be translated can be extracted.</span></span> <span data-ttu-id="40a3d-109">После перевода текста требуется влить переведенный текст в новую копию исходного приложения.</span><span class="sxs-lookup"><span data-stu-id="40a3d-109">After the text is translated, you will merge the translated text into a new copy of the original application.</span></span>  
  
<a name="Requirements"></a>
## <a name="requirements"></a><span data-ttu-id="40a3d-110">Требования</span><span class="sxs-lookup"><span data-stu-id="40a3d-110">Requirements</span></span>  
 <span data-ttu-id="40a3d-111">В ходе обсуждения вы будете использовать движок сборки Microsoft (MSBuild), который представляет собой компилятор, который работает от командной строки.</span><span class="sxs-lookup"><span data-stu-id="40a3d-111">Over the course of this discussion, you will use Microsoft build engine (MSBuild), which is a compiler that runs from the command line.</span></span>  
  
 <span data-ttu-id="40a3d-112">Кроме того, будет рекомендовано использовать файл проекта.</span><span class="sxs-lookup"><span data-stu-id="40a3d-112">Also, you will be instructed to use a project file.</span></span> <span data-ttu-id="40a3d-113">Для получения инструкций по использованию файлов MSBuild и проектов [см.](../app-development/building-and-deploying-wpf-applications.md)</span><span class="sxs-lookup"><span data-stu-id="40a3d-113">For instructions on how to use MSBuild and project files, see [Build and Deploy](../app-development/building-and-deploying-wpf-applications.md).</span></span>  
  
 <span data-ttu-id="40a3d-114">Во всех примерах в этом разделе в качестве языка и региональных параметров используется en-US (английский (США)).</span><span class="sxs-lookup"><span data-stu-id="40a3d-114">All the examples in this discussion use en-US (English-US) as the culture.</span></span> <span data-ttu-id="40a3d-115">Это позволяет проходить по шагам примеров без установки другого языка.</span><span class="sxs-lookup"><span data-stu-id="40a3d-115">This enables you to work through the steps of the examples without installing a different language.</span></span>  
  
<a name="create_sample_app"></a>
## <a name="create-a-sample-application"></a><span data-ttu-id="40a3d-116">Создание примера приложения</span><span class="sxs-lookup"><span data-stu-id="40a3d-116">Create a Sample Application</span></span>  
 <span data-ttu-id="40a3d-117">На этом шаге вы будете выполнять подготовку приложения к локализации.</span><span class="sxs-lookup"><span data-stu-id="40a3d-117">In this step, you will prepare your application for localization.</span></span> <span data-ttu-id="40a3d-118">В примерах [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] предоставляется приложение HelloApp, которое будет использоваться для примеров кода в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="40a3d-118">In the [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] samples, a HelloApp sample is supplied that will be used for the code examples in this discussion.</span></span> <span data-ttu-id="40a3d-119">Если вы хотите использовать этот пример, загрузите [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] файлы из [образца инструмента LocBaml.](https://github.com/microsoft/WPF-Samples/tree/master/Tools/LocBaml)</span><span class="sxs-lookup"><span data-stu-id="40a3d-119">If you would like to use this sample, download the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] files from the [LocBaml Tool Sample](https://github.com/microsoft/WPF-Samples/tree/master/Tools/LocBaml).</span></span>  
  
1. <span data-ttu-id="40a3d-120">Разработайте свое приложение до точки, в которой хотите начать локализацию.</span><span class="sxs-lookup"><span data-stu-id="40a3d-120">Develop your application to the point where you want to start localization.</span></span>  
  
2. <span data-ttu-id="40a3d-121">Укажите язык разработки в файле проекта, чтобы MSBuild генерировал основную сборку и спутниковую сборку (файл с расширением .resources.dll) для хранения нейтральных языковых ресурсов.</span><span class="sxs-lookup"><span data-stu-id="40a3d-121">Specify the development language in the project file so that MSBuild generates a main assembly and a satellite assembly (a file with the .resources.dll extension) to contain the neutral language resources.</span></span> <span data-ttu-id="40a3d-122">Файл проекта в примере HelloApp — HelloApp.csproj.</span><span class="sxs-lookup"><span data-stu-id="40a3d-122">The project file in the HelloApp sample is HelloApp.csproj.</span></span> <span data-ttu-id="40a3d-123">В этом файле можно найти язык разработки, заданный следующим образом:</span><span class="sxs-lookup"><span data-stu-id="40a3d-123">In that file, you will find the development language identified as follows:</span></span>  
  
     `<UICulture>en-US</UICulture>`  
  
3. <span data-ttu-id="40a3d-124">Добавьте ИД пользователей в свои файлы [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="40a3d-124">Add Uids to your [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] files.</span></span> <span data-ttu-id="40a3d-125">ИД пользователей используются для отслеживания изменений в файлах и для идентификации элементов, которые должны быть переведены.</span><span class="sxs-lookup"><span data-stu-id="40a3d-125">Uids are used to keep track of changes to files and to identify items that must be translated.</span></span> <span data-ttu-id="40a3d-126">Чтобы добавить Uids в файлы, запустите **обновление** в файле проекта:</span><span class="sxs-lookup"><span data-stu-id="40a3d-126">To add Uids to your files, run **updateuid** on your project file:</span></span>  
  
     <span data-ttu-id="40a3d-127">**msbuild -t:updateuid helloapp.csproj**</span><span class="sxs-lookup"><span data-stu-id="40a3d-127">**msbuild -t:updateuid helloapp.csproj**</span></span>  
  
     <span data-ttu-id="40a3d-128">Чтобы убедиться, что у вас нет пропавших без вести или дублировать Uids, запустите **checkuid:**</span><span class="sxs-lookup"><span data-stu-id="40a3d-128">To verify that you have no missing or duplicate Uids, run **checkuid**:</span></span>  
  
     <span data-ttu-id="40a3d-129">**msbuild -t:checkuid helloapp.csproj**</span><span class="sxs-lookup"><span data-stu-id="40a3d-129">**msbuild -t:checkuid helloapp.csproj**</span></span>  
  
     <span data-ttu-id="40a3d-130">После запуска **updateuid,** ваши файлы должны содержать Uids.</span><span class="sxs-lookup"><span data-stu-id="40a3d-130">After running **updateuid**, your files should contain Uids.</span></span> <span data-ttu-id="40a3d-131">Например, в файле Pane1.xaml приложения HelloApp вы должны найти следующее:</span><span class="sxs-lookup"><span data-stu-id="40a3d-131">For example, in the Pane1.xaml file of HelloApp, you should find the following:</span></span>  
  
     `<StackPanel x:Uid="StackPanel_1">`  
  
     `<TextBlock x:Uid="TextBlock_1">Hello World</TextBlock>`  
  
     `<TextBlock x:Uid="TextBlock_2">Goodbye World</TextBlock>`  
  
     `</StackPanel>`  
  
<a name="create_dll"></a>
## <a name="create-the-neutral-language-resources-satellite-assembly"></a><span data-ttu-id="40a3d-132">Создание вспомогательной сборки ресурсов нейтрального языка</span><span class="sxs-lookup"><span data-stu-id="40a3d-132">Create the Neutral Language Resources Satellite Assembly</span></span>  
 <span data-ttu-id="40a3d-133">После настройки приложения для создания вспомогательной сборки для ресурсов нейтрального языка можно построить приложение.</span><span class="sxs-lookup"><span data-stu-id="40a3d-133">After the application is configured to generate a neutral language resources satellite assembly, you build the application.</span></span> <span data-ttu-id="40a3d-134">При этом будет создана основная сборка приложения, а также вспомогательная сборка ресурсов нейтрального языка, которая требуется LocBaml для локализации.</span><span class="sxs-lookup"><span data-stu-id="40a3d-134">This generates the main application assembly, as well as the neutral language resources satellite assembly that is required by LocBaml for localization.</span></span> <span data-ttu-id="40a3d-135">Чтобы создать приложение:</span><span class="sxs-lookup"><span data-stu-id="40a3d-135">To build the application:</span></span>  
  
1. <span data-ttu-id="40a3d-136">Составить HelloApp для создания библиотеки динамических ссылк (DLL):</span><span class="sxs-lookup"><span data-stu-id="40a3d-136">Compile HelloApp to create a dynamic-link library (DLL):</span></span>  
  
     <span data-ttu-id="40a3d-137">**msbuild helloapp.csproj**</span><span class="sxs-lookup"><span data-stu-id="40a3d-137">**msbuild helloapp.csproj**</span></span>  
  
2. <span data-ttu-id="40a3d-138">Новая основная сборка приложения, HelloApp.exe, создается в следующей папке:</span><span class="sxs-lookup"><span data-stu-id="40a3d-138">The newly created main application assembly, HelloApp.exe, is created in the following folder:</span></span>  
  
     `C:\HelloApp\Bin\Debug\`  
  
3. <span data-ttu-id="40a3d-139">Новая вспомогательная сборка ресурсов нейтрального языка, HelloApp.resources.dll, создается в следующей папке:</span><span class="sxs-lookup"><span data-stu-id="40a3d-139">The newly created neutral language resources satellite assembly, HelloApp.resources.dll, is created in the following folder:</span></span>  
  
     `C:\HelloApp\Bin\Debug\en-US\`  
  
<a name="build_locbaml"></a>
## <a name="build-the-locbaml-tool"></a><span data-ttu-id="40a3d-140">Построение средства LocBaml</span><span class="sxs-lookup"><span data-stu-id="40a3d-140">Build the LocBaml Tool</span></span>  
  
1. <span data-ttu-id="40a3d-141">Все файлы, необходимые для построения LocBaml, находятся в примерах [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="40a3d-141">All the files necessary to build LocBaml are located in the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] samples.</span></span> <span data-ttu-id="40a3d-142">Загрузите файлы c's из [образца инструмента LocBaml.](https://github.com/microsoft/WPF-Samples/tree/master/Tools/LocBaml)</span><span class="sxs-lookup"><span data-stu-id="40a3d-142">Download the C# files from the [LocBaml Tool Sample](https://github.com/microsoft/WPF-Samples/tree/master/Tools/LocBaml).</span></span>  
  
2. <span data-ttu-id="40a3d-143">Из командной строки запустите файл проекта (locbaml.csproj), чтобы построить это средство:</span><span class="sxs-lookup"><span data-stu-id="40a3d-143">From the command line, run the project file (locbaml.csproj) to build the tool:</span></span>  
  
     <span data-ttu-id="40a3d-144">**msbuild locbaml.csproj**</span><span class="sxs-lookup"><span data-stu-id="40a3d-144">**msbuild locbaml.csproj**</span></span>  
  
3. <span data-ttu-id="40a3d-145">Перейдите в каталог Bin\Release, чтобы найти созданный исполняемый файл (locbaml.exe).</span><span class="sxs-lookup"><span data-stu-id="40a3d-145">Go to the Bin\Release directory to find the newly created executable file (locbaml.exe).</span></span> <span data-ttu-id="40a3d-146">Например: C:\LocBaml\Bin\Release\locbaml.exe.</span><span class="sxs-lookup"><span data-stu-id="40a3d-146">Example:C:\LocBaml\Bin\Release\locbaml.exe.</span></span>  
  
4. <span data-ttu-id="40a3d-147">При запуске LocBaml вы можете указать следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="40a3d-147">The options that you can specify when you run LocBaml are as follows:</span></span>  
  
    - <span data-ttu-id="40a3d-148">**разбор или** **p:** Parses Baml, ресурсы или DLL-файлы для создания файла .csv или .txt.</span><span class="sxs-lookup"><span data-stu-id="40a3d-148">**parse** or **-p:** Parses Baml, resources, or DLL files to generate a .csv or .txt file.</span></span>  
  
    - <span data-ttu-id="40a3d-149">**генерировать** или **-g:** генерирует локализованный двоичный файл с помощью переведенного файла.</span><span class="sxs-lookup"><span data-stu-id="40a3d-149">**generate** or **-g:** Generates a localized binary file by using a translated file.</span></span>  
  
    - <span data-ttu-id="40a3d-150">**вне** или **-o** *filedirectory* **:** имя файла выхода.</span><span class="sxs-lookup"><span data-stu-id="40a3d-150">**out** or **-o** {*filedirectory*] **:** Output file name.</span></span>  
  
    - <span data-ttu-id="40a3d-151">**культура** или **-куль** *культура* **:** Локаль сборок выхода.</span><span class="sxs-lookup"><span data-stu-id="40a3d-151">**culture** or **-cul** {*culture*] **:** Locale of output assemblies.</span></span>  
  
    - <span data-ttu-id="40a3d-152">**перевод** или **-транс** и*перевод.csv* **:** Перевод или локализованный файл.</span><span class="sxs-lookup"><span data-stu-id="40a3d-152">**translation** or **-trans** {*translation.csv*] **:** Translated or localized file.</span></span>  
  
    - <span data-ttu-id="40a3d-153">**asmpath** или **-asmpath:** *файлорежиссеризм:* Если ваш **:** [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] код содержит пользовательские элементы управления, вы должны предоставить **асмпат** на сборку пользовательского элемента управления.</span><span class="sxs-lookup"><span data-stu-id="40a3d-153">**asmpath** or **-asmpath:** {*filedirectory*] **:** If your [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] code contains custom controls, you must supply the **asmpath** to the custom control assembly.</span></span>  
  
    - <span data-ttu-id="40a3d-154">**nologo:** запрещает отображение логотипа или сведений об авторских правах.</span><span class="sxs-lookup"><span data-stu-id="40a3d-154">**nologo:** Displays no logo or copyright information.</span></span>  
  
    - <span data-ttu-id="40a3d-155">**verbose:** отображает сведения режима подробного протоколирования.</span><span class="sxs-lookup"><span data-stu-id="40a3d-155">**verbose:** Displays verbose mode information.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="40a3d-156">Если вам нужен список опций при запуске инструмента, введите **LocBaml.exe** и нажмите ENTER.</span><span class="sxs-lookup"><span data-stu-id="40a3d-156">If you need a list of the options when you are running the tool, type     **LocBaml.exe** and press ENTER.</span></span>  
  
<a name="parse_dll"></a>
## <a name="use-locbaml-to-parse-a-file"></a><span data-ttu-id="40a3d-157">Использование LocBaml для анализа файла</span><span class="sxs-lookup"><span data-stu-id="40a3d-157">Use LocBaml to Parse a File</span></span>  
 <span data-ttu-id="40a3d-158">Теперь, после создания средства LocBaml, вы можете выполнить анализ файла HelloApp.resources.dll, чтобы извлечь текстовое содержимое, которое будет локализовано.</span><span class="sxs-lookup"><span data-stu-id="40a3d-158">Now that you have created the LocBaml tool, you are ready to use it to parse HelloApp.resources.dll to extract the text content that will be localized.</span></span>  
  
1. <span data-ttu-id="40a3d-159">Скопируйте LocBaml.exe в папку приложения bin\debug, где была создана основная сборка приложения.</span><span class="sxs-lookup"><span data-stu-id="40a3d-159">Copy LocBaml.exe to your application's bin\debug folder, where the main application assembly was created.</span></span>  
  
2. <span data-ttu-id="40a3d-160">Чтобы выполнить анализ файла вспомогательной сборки и сохранить результат в виде CSV-файла, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="40a3d-160">To parse the satellite assembly file and store the output as a .csv file, use the following command:</span></span>  
  
     <span data-ttu-id="40a3d-161">**LocBaml.exe /parse HelloApp.resources.dll /out:Hello.csv**</span><span class="sxs-lookup"><span data-stu-id="40a3d-161">**LocBaml.exe /parse HelloApp.resources.dll /out:Hello.csv**</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="40a3d-162">Если входной файл HelloApp.resources.dll не находится в том же каталоге, что и LocBaml.exe, переместите один из файлов таким образом, чтобы оба файла были в одном каталоге.</span><span class="sxs-lookup"><span data-stu-id="40a3d-162">If the input file, HelloApp.resources.dll, is not in the same directory as LocBaml.exe move one of the files so that both files are in the same directory.</span></span>  
  
3. <span data-ttu-id="40a3d-163">При выполнении анализа файлов с помощью LocBaml выходные данные состоят из семи полей, разделенных запятыми (CSV-файлы) или знаками табуляции (TXT-файлы).</span><span class="sxs-lookup"><span data-stu-id="40a3d-163">When you run LocBaml to parse files, the output consists of seven fields delimited by commas (.csv files) or tabs (.txt files).</span></span> <span data-ttu-id="40a3d-164">Ниже показан проанализированный CSV-файл для HelloApp.resources.dll:</span><span class="sxs-lookup"><span data-stu-id="40a3d-164">The following shows the parsed .csv file for the HelloApp.resources.dll:</span></span>

   | |
   |-|
   |<span data-ttu-id="40a3d-165">HelloApp.g.en-US.resources:window1.baml,Stack1:System.Windows.Controls.StackPanel.$Content,Ignore,FALSE, FALSE,,#Text1;#Text2;</span><span class="sxs-lookup"><span data-stu-id="40a3d-165">HelloApp.g.en-US.resources:window1.baml,Stack1:System.Windows.Controls.StackPanel.$Content,Ignore,FALSE, FALSE,,#Text1;#Text2;</span></span>|
   |<span data-ttu-id="40a3d-166">HelloApp.g.en-US.resources:window1.baml,Stack1:System.Windows.Controls.StackPanel.$Content,Ignore,FALSE, FALSE,,#Text1;#Text2;</span><span class="sxs-lookup"><span data-stu-id="40a3d-166">HelloApp.g.en-US.resources:window1.baml,Text1:System.Windows.Controls.TextBlock.$Content,None,TRUE, TRUE,,Hello World</span></span>|
   |<span data-ttu-id="40a3d-167">HelloApp.g.en-US.resources:window1.baml,Stack1:System.Windows.Controls.StackPanel.$Content,Ignore,FALSE, FALSE,,#Text1;#Text2;</span><span class="sxs-lookup"><span data-stu-id="40a3d-167">HelloApp.g.en-US.resources:window1.baml,Text2:System.Windows.Controls.TextBlock.$Content,None,TRUE, TRUE,,Goodbye World</span></span>|

   <span data-ttu-id="40a3d-168">Это следующие семь полей.</span><span class="sxs-lookup"><span data-stu-id="40a3d-168">The seven fields are:</span></span>  
  
   1. <span data-ttu-id="40a3d-169">**НАЗВАНИЕ BAML**.</span><span class="sxs-lookup"><span data-stu-id="40a3d-169">**BAML Name**.</span></span> <span data-ttu-id="40a3d-170">Имя ресурса BAML по отношению к вспомогательной сборке исходного языка.</span><span class="sxs-lookup"><span data-stu-id="40a3d-170">The name of the BAML resource with respect to the source language satellite assembly.</span></span>  
  
   2. <span data-ttu-id="40a3d-171">**Ключ ресурса**.</span><span class="sxs-lookup"><span data-stu-id="40a3d-171">**Resource Key**.</span></span> <span data-ttu-id="40a3d-172">Идентификатор локализованного ресурса.</span><span class="sxs-lookup"><span data-stu-id="40a3d-172">The localized resource identifier.</span></span>  
  
   3. <span data-ttu-id="40a3d-173">**Категория**.</span><span class="sxs-lookup"><span data-stu-id="40a3d-173">**Category**.</span></span> <span data-ttu-id="40a3d-174">Тип значения.</span><span class="sxs-lookup"><span data-stu-id="40a3d-174">The value type.</span></span> <span data-ttu-id="40a3d-175">Смотрите [атрибуты и комментарии локализации](localization-attributes-and-comments.md).</span><span class="sxs-lookup"><span data-stu-id="40a3d-175">See [Localization Attributes and Comments](localization-attributes-and-comments.md).</span></span>  
  
   4. <span data-ttu-id="40a3d-176">**Удобочитаемость**.</span><span class="sxs-lookup"><span data-stu-id="40a3d-176">**Readability**.</span></span> <span data-ttu-id="40a3d-177">Может ли значение быть прочитано средством локализации.</span><span class="sxs-lookup"><span data-stu-id="40a3d-177">Whether the value can be read by a localizer.</span></span> <span data-ttu-id="40a3d-178">Смотрите [атрибуты и комментарии локализации](localization-attributes-and-comments.md).</span><span class="sxs-lookup"><span data-stu-id="40a3d-178">See [Localization Attributes and Comments](localization-attributes-and-comments.md).</span></span>  
  
   5. <span data-ttu-id="40a3d-179">**Изменяемость**.</span><span class="sxs-lookup"><span data-stu-id="40a3d-179">**Modifiability**.</span></span> <span data-ttu-id="40a3d-180">Может ли значение изменяться средством локализации.</span><span class="sxs-lookup"><span data-stu-id="40a3d-180">Whether the value can be modified by a localizer.</span></span> <span data-ttu-id="40a3d-181">Смотрите [атрибуты и комментарии локализации](localization-attributes-and-comments.md).</span><span class="sxs-lookup"><span data-stu-id="40a3d-181">See [Localization Attributes and Comments](localization-attributes-and-comments.md).</span></span>  
  
   6. <span data-ttu-id="40a3d-182">**Комментарии**.</span><span class="sxs-lookup"><span data-stu-id="40a3d-182">**Comments**.</span></span> <span data-ttu-id="40a3d-183">Дополнительное описание значения, помогающее определить способ локализации значения.</span><span class="sxs-lookup"><span data-stu-id="40a3d-183">Additional description of the value to help determine how a value is localized.</span></span> <span data-ttu-id="40a3d-184">Смотрите [атрибуты и комментарии локализации](localization-attributes-and-comments.md).</span><span class="sxs-lookup"><span data-stu-id="40a3d-184">See [Localization Attributes and Comments](localization-attributes-and-comments.md).</span></span>  
  
   7. <span data-ttu-id="40a3d-185">**Значение**.</span><span class="sxs-lookup"><span data-stu-id="40a3d-185">**Value**.</span></span> <span data-ttu-id="40a3d-186">Текстовое значение для перевода на нужный язык.</span><span class="sxs-lookup"><span data-stu-id="40a3d-186">The text value to translate to the desired culture.</span></span>  
  
   <span data-ttu-id="40a3d-187">В следующей таблице показывается, как эти поля соответствуют разделенным значениям CSV-файла.</span><span class="sxs-lookup"><span data-stu-id="40a3d-187">The following table shows how these fields map to the delimited values of the .csv file:</span></span>  
  
   |<span data-ttu-id="40a3d-188">Имя BAML</span><span class="sxs-lookup"><span data-stu-id="40a3d-188">BAML name</span></span>|<span data-ttu-id="40a3d-189">Ключ ресурса</span><span class="sxs-lookup"><span data-stu-id="40a3d-189">Resource key</span></span>|<span data-ttu-id="40a3d-190">Категория</span><span class="sxs-lookup"><span data-stu-id="40a3d-190">Category</span></span>|<span data-ttu-id="40a3d-191">Удобочитаемость</span><span class="sxs-lookup"><span data-stu-id="40a3d-191">Readability</span></span>|<span data-ttu-id="40a3d-192">Изменяемость</span><span class="sxs-lookup"><span data-stu-id="40a3d-192">Modifiability</span></span>|<span data-ttu-id="40a3d-193">Комментарии</span><span class="sxs-lookup"><span data-stu-id="40a3d-193">Comments</span></span>|<span data-ttu-id="40a3d-194">Значение</span><span class="sxs-lookup"><span data-stu-id="40a3d-194">Value</span></span>|  
   |---------------|------------------|--------------|-----------------|-------------------|--------------|-----------|
   |<span data-ttu-id="40a3d-195">HelloApp.g.en-US.resources:window1.baml</span><span class="sxs-lookup"><span data-stu-id="40a3d-195">HelloApp.g.en-US.resources:window1.baml</span></span>|<span data-ttu-id="40a3d-196">Stack1:System.Windows.Controls.StackPanel.$Content</span><span class="sxs-lookup"><span data-stu-id="40a3d-196">Stack1:System.Windows.Controls.StackPanel.$Content</span></span>|<span data-ttu-id="40a3d-197">Игнорировать</span><span class="sxs-lookup"><span data-stu-id="40a3d-197">Ignore</span></span>|<span data-ttu-id="40a3d-198">FALSE</span><span class="sxs-lookup"><span data-stu-id="40a3d-198">FALSE</span></span>|<span data-ttu-id="40a3d-199">FALSE</span><span class="sxs-lookup"><span data-stu-id="40a3d-199">FALSE</span></span>||<span data-ttu-id="40a3d-200">#Text1;#Text2</span><span class="sxs-lookup"><span data-stu-id="40a3d-200">#Text1;#Text2</span></span>|
   |<span data-ttu-id="40a3d-201">HelloApp.g.en-US.resources:window1.baml</span><span class="sxs-lookup"><span data-stu-id="40a3d-201">HelloApp.g.en-US.resources:window1.baml</span></span>|<span data-ttu-id="40a3d-202">Text1:System.Windows.Controls.TextBlock.$Content</span><span class="sxs-lookup"><span data-stu-id="40a3d-202">Text1:System.Windows.Controls.TextBlock.$Content</span></span>|<span data-ttu-id="40a3d-203">None</span><span class="sxs-lookup"><span data-stu-id="40a3d-203">None</span></span>|<span data-ttu-id="40a3d-204">TRUE</span><span class="sxs-lookup"><span data-stu-id="40a3d-204">TRUE</span></span>|<span data-ttu-id="40a3d-205">TRUE</span><span class="sxs-lookup"><span data-stu-id="40a3d-205">TRUE</span></span>||<span data-ttu-id="40a3d-206">Hello World</span><span class="sxs-lookup"><span data-stu-id="40a3d-206">Hello World</span></span>|
   |<span data-ttu-id="40a3d-207">HelloApp.g.en-US.resources:window1.baml</span><span class="sxs-lookup"><span data-stu-id="40a3d-207">HelloApp.g.en-US.resources:window1.baml</span></span>|<span data-ttu-id="40a3d-208">Text1:System.Windows.Controls.TextBlock.$Content</span><span class="sxs-lookup"><span data-stu-id="40a3d-208">Text2:System.Windows.Controls.TextBlock.$Content</span></span>|<span data-ttu-id="40a3d-209">None</span><span class="sxs-lookup"><span data-stu-id="40a3d-209">None</span></span>|<span data-ttu-id="40a3d-210">TRUE</span><span class="sxs-lookup"><span data-stu-id="40a3d-210">TRUE</span></span>|<span data-ttu-id="40a3d-211">TRUE</span><span class="sxs-lookup"><span data-stu-id="40a3d-211">TRUE</span></span>||<span data-ttu-id="40a3d-212">Goodbye World</span><span class="sxs-lookup"><span data-stu-id="40a3d-212">Goodbye World</span></span>|
  
   <span data-ttu-id="40a3d-213">Обратите внимание, что все значения для поля **Комментарии** не содержат значений; если поле не имеет значения, оно пусто.</span><span class="sxs-lookup"><span data-stu-id="40a3d-213">Notice that all the values for the **Comments** field contain no values; if a field doesn't have a value, it is empty.</span></span> <span data-ttu-id="40a3d-214">Также обратите внимание, что элемент в первом ряду не является ни читаемым, ни модифицируемым, и имеет "Игнорирование" в качестве значения **категории,** все из которых указывает на то, что значение не является локализованным.</span><span class="sxs-lookup"><span data-stu-id="40a3d-214">Also notice that the item in the first row is neither readable nor modifiable, and has "Ignore" as its **Category** value, all of which indicates that the value is not localizable.</span></span>  
  
4. <span data-ttu-id="40a3d-215">Для облегчения обнаружения локальных элементов в разобранах файлов, особенно в больших файлах, можно сортировать или фильтровать элементы по **категориям,** **читаемости**и **модификируемости.**</span><span class="sxs-lookup"><span data-stu-id="40a3d-215">To facilitate discovery of localizable items in parsed files, particularly in large files, you can sort or filter the items by **Category**, **Readability**, and **Modifiability**.</span></span> <span data-ttu-id="40a3d-216">Например можно отфильтровать нечитаемые и неизменяемые значения.</span><span class="sxs-lookup"><span data-stu-id="40a3d-216">For example, you can filter out unreadable and unmodifiable values.</span></span>  
  
<a name="translate_loc_content"></a>
## <a name="translate-the-localizable-content"></a><span data-ttu-id="40a3d-217">Перевод локализуемого содержимого</span><span class="sxs-lookup"><span data-stu-id="40a3d-217">Translate the Localizable Content</span></span>  
 <span data-ttu-id="40a3d-218">Используйте любое доступное средство для перевода извлеченного содержимого.</span><span class="sxs-lookup"><span data-stu-id="40a3d-218">Use any tool that you have available to translate the extracted content.</span></span> <span data-ttu-id="40a3d-219">Хороший способ сделать это — записать ресурсы в файл .csv и просмотреть их в Microsoft Excel, внося изменения в перевод последнего столбца (значение).</span><span class="sxs-lookup"><span data-stu-id="40a3d-219">A good way to do this is to write the resources to a .csv file and view them in Microsoft Excel, making translation changes to the last column (value).</span></span>  
  
<a name="merge_translations"></a>
## <a name="use-locbaml-to-generate-a-new-resourcesdll-file"></a><span data-ttu-id="40a3d-220">Использование LocBaml для создания нового файла .resources.dll</span><span class="sxs-lookup"><span data-stu-id="40a3d-220">Use LocBaml to Generate a New .resources.dll File</span></span>  
 <span data-ttu-id="40a3d-221">Содержимое, которое было идентифицировано при анализе файла HelloApp.resources.dll с помощью LocBaml, переведено, и его необходимо влить обратно в исходное приложение.</span><span class="sxs-lookup"><span data-stu-id="40a3d-221">The content that was identified by parsing HelloApp.resources.dll with LocBaml has been translated and must be merged back into the original application.</span></span> <span data-ttu-id="40a3d-222">Используйте опцию **generate** or **-g** для создания нового файла .resources.dll.</span><span class="sxs-lookup"><span data-stu-id="40a3d-222">Use the **generate** or **-g** option to generate a new .resources.dll file.</span></span>  
  
1. <span data-ttu-id="40a3d-223">Чтобы создать новый файл HelloApp.resources.dll, используйте следующий синтаксис.</span><span class="sxs-lookup"><span data-stu-id="40a3d-223">Use the following syntax to generate a new HelloApp.resources.dll file.</span></span> <span data-ttu-id="40a3d-224">Пометьте язык и региональные параметры как en-US (/cul:en-US).</span><span class="sxs-lookup"><span data-stu-id="40a3d-224">Mark the culture as en-US (/cul:en-US).</span></span>  
  
     <span data-ttu-id="40a3d-225">**LocBaml.exe /generate HelloApp.resources.dll /trans:Hello.csv /out:c:\ /cul:en-US**</span><span class="sxs-lookup"><span data-stu-id="40a3d-225">**LocBaml.exe /generate HelloApp.resources.dll /trans:Hello.csv /out:c:\ /cul:en-US**</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="40a3d-226">Если входной файл Hello.csv не находится в том же каталоге, что и исполняемый файл LocBaml.exe, переместите один из файлов таким образом, чтобы оба файла были в одном каталоге.</span><span class="sxs-lookup"><span data-stu-id="40a3d-226">If the input file, Hello.csv, is not in the same directory as the executable, LocBaml.exe, move one of the files so that both files are in the same directory.</span></span>  
  
2. <span data-ttu-id="40a3d-227">Замените старый файл HelloApp.resources.dll в каталоге C:\HelloApp\Bin\Debug\en-US\HelloApp.resources.dll на новый созданный файл HelloApp.resources.dll.</span><span class="sxs-lookup"><span data-stu-id="40a3d-227">Replace the old HelloApp.resources.dll file in the C:\HelloApp\Bin\Debug\en-US\HelloApp.resources.dll directory with your newly created HelloApp.resources.dll file.</span></span>  
  
3. <span data-ttu-id="40a3d-228">Теперь в вашем приложении фразы Hello World и Goodbye World должны быть переведены.</span><span class="sxs-lookup"><span data-stu-id="40a3d-228">"Hello World" and "Goodbye World" should now be translated in your application.</span></span>  
  
4. <span data-ttu-id="40a3d-229">Для перевода на другой язык используйте язык, на который вы переводите.</span><span class="sxs-lookup"><span data-stu-id="40a3d-229">To translate to a different culture, use the culture of the language that you are translating to.</span></span> <span data-ttu-id="40a3d-230">В следующем примере показано, как переводить на канадский французский.</span><span class="sxs-lookup"><span data-stu-id="40a3d-230">The following example shows how to translate to French-Canadian:</span></span>  
  
     <span data-ttu-id="40a3d-231">**LocBaml.exe /generate HelloApp.resources.dll /trans:Hellofr-CA.csv /out:c:\ /cul:fr-CA**</span><span class="sxs-lookup"><span data-stu-id="40a3d-231">**LocBaml.exe /generate HelloApp.resources.dll /trans:Hellofr-CA.csv /out:c:\ /cul:fr-CA**</span></span>  
  
5. <span data-ttu-id="40a3d-232">В той же основной сборке приложения создайте новую папку для выбранного языка и региональных параметров, в которой будет размещена новая вспомогательная сборка.</span><span class="sxs-lookup"><span data-stu-id="40a3d-232">In the same assembly as the main application assembly, create a new culture-specific folder to house the new satellite assembly.</span></span> <span data-ttu-id="40a3d-233">Для канадского французского папку можно назвать fr-CA.</span><span class="sxs-lookup"><span data-stu-id="40a3d-233">For French-Canadian, the folder would be fr-CA.</span></span>  
  
6. <span data-ttu-id="40a3d-234">Скопируйте созданную вспомогательную сборку в новую папку.</span><span class="sxs-lookup"><span data-stu-id="40a3d-234">Copy the generated satellite assembly to the new folder.</span></span>  
  
7. <span data-ttu-id="40a3d-235">Чтобы протестировать новую вспомогательную сборку, необходимо изменить язык и региональные параметры, с которыми будет выполняться приложение.</span><span class="sxs-lookup"><span data-stu-id="40a3d-235">To test the new satellite assembly, you need to change the culture under which your application will run.</span></span> <span data-ttu-id="40a3d-236">Это можно сделать одним из двух способов.</span><span class="sxs-lookup"><span data-stu-id="40a3d-236">You can do this in one of two ways:</span></span>  
  
    - <span data-ttu-id="40a3d-237">Измените региональные настройки операционной системы **(Группа** **управления** &#124; &#124; региональных **и языковых опций).**</span><span class="sxs-lookup"><span data-stu-id="40a3d-237">Change your operating system's regional settings (**Start** &#124; **Control Panel** &#124; **Regional and Language Options**).</span></span>  
  
    - <span data-ttu-id="40a3d-238">В своем приложении добавьте в файл App.xaml.cs следующий код:</span><span class="sxs-lookup"><span data-stu-id="40a3d-238">In your application, add the following code to App.xaml.cs:</span></span>  
  
   [!code-xaml[LocBamlChangeCultureSnippets#LocBamlChangeCultureMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/LocBamlChangeCultureSnippets/CSharp/App.xaml#locbamlchangeculturemarkup)]
   [!code-csharp[LocBamlChangeCultureSnippets#LocBamlChangeCultureCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/LocBamlChangeCultureSnippets/CSharp/App.xaml.cs#locbamlchangeculturecodebehind)]
   [!code-vb[LocBamlChangeCultureSnippets#LocBamlChangeCultureCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/LocBamlChangeCultureSnippets/VisualBasic/Application.xaml.vb#locbamlchangeculturecodebehind)]  
  
<a name="Some_Tips_for_Using_LocBaml"></a>
## <a name="some-tips-for-using-locbaml"></a><span data-ttu-id="40a3d-239">Советы по использованию LocBaml</span><span class="sxs-lookup"><span data-stu-id="40a3d-239">Some Tips for Using LocBaml</span></span>  
  
- <span data-ttu-id="40a3d-240">Все зависимые сборки, которые определяют пользовательские элементы управления, должны быть скопированы в локальный каталог LocBaml или установлены в глобальном кэше сборок.</span><span class="sxs-lookup"><span data-stu-id="40a3d-240">All dependent assemblies that define custom controls must be copied into the local directory of LocBaml or installed into the GAC.</span></span> <span data-ttu-id="40a3d-241">Это необходимо, поскольку API локализации должен иметь доступ к зависимым сборкам при чтении двоичного XAML (BAML).</span><span class="sxs-lookup"><span data-stu-id="40a3d-241">This is necessary because the localization API must have access to the dependent assemblies when it reads the binary XAML (BAML).</span></span>  
  
- <span data-ttu-id="40a3d-242">Если основная сборка имеет подпись, созданная библиотека DLL ресурсов также должна быть подписана для ее загрузки.</span><span class="sxs-lookup"><span data-stu-id="40a3d-242">If the main assembly is signed, the generated resource DLL must also be signed in order for it to be loaded.</span></span>  
  
- <span data-ttu-id="40a3d-243">Версия библиотеки DLL локализованных ресурсов должна быть синхронизирована с основной сборкой.</span><span class="sxs-lookup"><span data-stu-id="40a3d-243">The version of the localized resource DLL needs to be synchronized with the main assembly.</span></span>  
  
<a name="Whats_Next"></a>
## <a name="whats-next"></a><span data-ttu-id="40a3d-244">Что дальше?</span><span class="sxs-lookup"><span data-stu-id="40a3d-244">What's Next</span></span>  
 <span data-ttu-id="40a3d-245">Теперь у вас есть базовое представление о том, как использовать средство LocBaml.</span><span class="sxs-lookup"><span data-stu-id="40a3d-245">You should now have a basic understanding of how to use the LocBaml tool.</span></span>  <span data-ttu-id="40a3d-246">Вы можете создать файл, содержащий ИД пользователей.</span><span class="sxs-lookup"><span data-stu-id="40a3d-246">You should be able to make a file that contains Uids.</span></span> <span data-ttu-id="40a3d-247">С помощью средства LocBaml вы можете анализировать файл для извлечения локализуемого содержимого и после перевода этого содержимого можете создать файл .resources.dll, объединяющий переведенное содержимое.</span><span class="sxs-lookup"><span data-stu-id="40a3d-247">By using the LocBaml tool, you should be able to parse a file to extract the localizable content, and after the content is translated, you should be able to generate a .resources.dll file that merges the translated content.</span></span> <span data-ttu-id="40a3d-248">В этом разделе не рассматриваются все возможные детали, но теперь у вас есть знания, необходимые для использования LocBaml для локализации приложений.</span><span class="sxs-lookup"><span data-stu-id="40a3d-248">This topic does not include every possible detail, but you now have the knowledge necessary to use LocBaml for localizing your applications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40a3d-249">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="40a3d-249">See also</span></span>

- [<span data-ttu-id="40a3d-250">Глобализация для WPF</span><span class="sxs-lookup"><span data-stu-id="40a3d-250">Globalization for WPF</span></span>](globalization-for-wpf.md)
- [<span data-ttu-id="40a3d-251">Обзор использования автоматической разметки</span><span class="sxs-lookup"><span data-stu-id="40a3d-251">Use Automatic Layout Overview</span></span>](use-automatic-layout-overview.md)
