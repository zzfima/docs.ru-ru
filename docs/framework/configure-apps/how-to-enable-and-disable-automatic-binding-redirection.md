---
title: Включение или отключение автоматически создаваемых перенаправлений привязок
ms.date: 10/30/2018
helpviewer_keywords:
- side-by-side execution, assembly binding redirection
- assemblies [.NET Framework], binding redirection
ms.assetid: 5fca42f3-bdce-4b81-a704-61e42c89d3ba
ms.openlocfilehash: 178d5070dd7018bbc0fce474cdd0b31ba3d17f77
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2019
ms.locfileid: "69913035"
---
# <a name="how-to-enable-and-disable-automatic-binding-redirection"></a><span data-ttu-id="1c542-102">Практическое руководство. Включение и отключение автоматического перенаправления привязки</span><span class="sxs-lookup"><span data-stu-id="1c542-102">How to: Enable and Disable Automatic Binding Redirection</span></span>

<span data-ttu-id="1c542-103">При компиляции приложений в Visual Studio, предназначенных для .NET Framework 4.5.1 и более поздних версий, перенаправления привязок могут быть автоматически добавлены в файл конфигурации приложения для переопределения унификации сборок.</span><span class="sxs-lookup"><span data-stu-id="1c542-103">When you compile apps in Visual Studio that target the .NET Framework 4.5.1 and later versions, binding redirects may be automatically added to the app configuration file to override assembly unification.</span></span> <span data-ttu-id="1c542-104">Переадресации привязок добавляются, если приложение или его компоненты ссылаются на несколько версий одной сборки, даже если вручную указать переадресации привязок в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="1c542-104">Binding redirects are added if your app or its components reference more than one version of the same assembly, even if you manually specify binding redirects in the configuration file for your app.</span></span> <span data-ttu-id="1c542-105">Функция автоматического перенаправления привязок влияет на классические приложения и веб-приложения, предназначенные для .NET Framework 4.5.1 или более поздней версии, хотя поведение немного отличается для веб-приложения.</span><span class="sxs-lookup"><span data-stu-id="1c542-105">The automatic binding redirection feature affects desktop apps and web apps that target the .NET Framework 4.5.1 or a later version, although the behavior is slightly different for a web app.</span></span> <span data-ttu-id="1c542-106">Можно включить автоматическое перенаправление привязки, если у вас есть приложения, предназначенные для предыдущих версий .NET Framework, или отключить эту функцию, если необходимо вручную создать перенаправления привязок.</span><span class="sxs-lookup"><span data-stu-id="1c542-106">You can enable automatic binding redirection if you have existing apps that target previous versions of the .NET Framework, or you can disable this feature if you want to manually author binding redirects.</span></span>

## <a name="disable-automatic-binding-redirects-in-desktop-apps"></a><span data-ttu-id="1c542-107">Отключение автоматического перенаправления привязок в классических приложениях</span><span class="sxs-lookup"><span data-stu-id="1c542-107">Disable automatic binding redirects in desktop apps</span></span>

<span data-ttu-id="1c542-108">Автоматические перенаправления привязок включены по умолчанию для классических приложений Windows, предназначенных для .NET Framework 4.5.1 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="1c542-108">Automatic binding redirects are enabled by default for Windows desktop apps that target the .NET Framework 4.5.1 and later versions.</span></span> <span data-ttu-id="1c542-109">Перенаправления привязки добавляются в файл конфигурации вывода (**app. config**) при компиляции приложения и переопределяют унификацию сборок, которая в противном случае может быть выполнена.</span><span class="sxs-lookup"><span data-stu-id="1c542-109">The binding redirects are added to the output configuration (**app.config**) file when the app is compiled and override the assembly unification that might otherwise take place.</span></span> <span data-ttu-id="1c542-110">Исходный файл **app. config** не изменяется.</span><span class="sxs-lookup"><span data-stu-id="1c542-110">The source **app.config** file is not modified.</span></span> <span data-ttu-id="1c542-111">Эту функцию можно отключить, изменив файл проекта для приложения или сняв флажок в свойствах проекта в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="1c542-111">You can disable this feature by modifying the project file for the app or by deselecting a checkbox in the project's properties in Visual Studio.</span></span>

### <a name="disable-through-project-properties"></a><span data-ttu-id="1c542-112">Отключить через свойства проекта</span><span class="sxs-lookup"><span data-stu-id="1c542-112">Disable through project properties</span></span>

<span data-ttu-id="1c542-113">При наличии Visual Studio 2017 версии 15,7 или более поздней можно легко отключить автоматически создаваемые перенаправления привязок на страницах свойств проекта.</span><span class="sxs-lookup"><span data-stu-id="1c542-113">If you have Visual Studio 2017 version 15.7 or later, you can easily disable autogenerated binding redirects in the project's property pages.</span></span>

1. <span data-ttu-id="1c542-114">В **обозревателе решений** щелкните проект правой кнопкой мыши и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="1c542-114">Right-click the project in **Solution Explorer** and select **Properties**.</span></span>

2. <span data-ttu-id="1c542-115">На странице **приложение** снимите флажок **Автоматическое создание перенаправлений привязки** .</span><span class="sxs-lookup"><span data-stu-id="1c542-115">On the **Application** page, uncheck the **Auto-generate binding redirects** option.</span></span>

3. <span data-ttu-id="1c542-116">Нажмите клавиши **CTRL**+**S** , чтобы сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="1c542-116">Press **Ctrl**+**S** to save the change.</span></span>

### <a name="disable-manually-in-the-project-file"></a><span data-ttu-id="1c542-117">Отключение вручную в файле проекта</span><span class="sxs-lookup"><span data-stu-id="1c542-117">Disable manually in the project file</span></span>

1. <span data-ttu-id="1c542-118">Откройте файл проекта для редактирования с помощью одного из следующих методов:</span><span class="sxs-lookup"><span data-stu-id="1c542-118">Open the project file for editing using one of the following methods:</span></span>

   - <span data-ttu-id="1c542-119">В Visual Studio выберите проект в **Обозреватель решений**, а затем в контекстном меню выберите **Открыть папку в проводнике** .</span><span class="sxs-lookup"><span data-stu-id="1c542-119">In Visual Studio, select the project in **Solution Explorer**, and then choose **Open Folder in File Explorer** from the shortcut menu.</span></span> <span data-ttu-id="1c542-120">В проводнике найдите файл проекта (с расширением CSPROJ или VBPROJ) и откройте его в блокноте.</span><span class="sxs-lookup"><span data-stu-id="1c542-120">In File Explorer, find the project (.csproj or .vbproj) file and open it in Notepad.</span></span>
   - <span data-ttu-id="1c542-121">В **Обозреватель решений**щелкните правой кнопкой мыши проект в Visual Studio и выберите команду **Выгрузить проект**.</span><span class="sxs-lookup"><span data-stu-id="1c542-121">In Visual Studio, in **Solution Explorer**, right-click the project and choose **Unload Project**.</span></span> <span data-ttu-id="1c542-122">Снова щелкните правой кнопкой мыши выгруженный проект и выберите пункт **изменить [имя_проекта. csproj]** .</span><span class="sxs-lookup"><span data-stu-id="1c542-122">Right-click the unloaded project again, and then choose **Edit [projectname.csproj]**.</span></span>

2. <span data-ttu-id="1c542-123">Найдите в файле проекта следующую запись свойства:</span><span class="sxs-lookup"><span data-stu-id="1c542-123">In the project file, find the following property entry:</span></span>

   ```xml
   <AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>
   ```

3. <span data-ttu-id="1c542-124">Измените `true` на `false`:</span><span class="sxs-lookup"><span data-stu-id="1c542-124">Change `true` to `false`:</span></span>

   ```xml
   <AutoGenerateBindingRedirects>false</AutoGenerateBindingRedirects>
   ```

## <a name="enable-automatic-binding-redirects-manually"></a><span data-ttu-id="1c542-125">Включение автоматического перенаправления привязок вручную</span><span class="sxs-lookup"><span data-stu-id="1c542-125">Enable automatic binding redirects manually</span></span>

<span data-ttu-id="1c542-126">Можно включить автоматическое перенаправление привязок в существующих приложениях, предназначенных для более ранних версий .NET Framework, или в случаях, когда не будет автоматически предложено добавить перенаправление.</span><span class="sxs-lookup"><span data-stu-id="1c542-126">You can enable automatic binding redirects in existing apps that target older versions of the .NET Framework, or in cases where you're not automatically prompted to add a redirect.</span></span> <span data-ttu-id="1c542-127">Если вы нацелены на более новую версию платформы, но не получаете автоматически запрос на Добавление перенаправления, скорее всего, будут получены выходные данные сборки, предлагающие повторное сопоставление сборок.</span><span class="sxs-lookup"><span data-stu-id="1c542-127">If you're targeting a newer version of the framework but do not get automatically prompted to add a redirect, you'll likely get build output that suggests you remap assemblies.</span></span>

1. <span data-ttu-id="1c542-128">Откройте файл проекта для редактирования с помощью одного из следующих методов:</span><span class="sxs-lookup"><span data-stu-id="1c542-128">Open the project file for editing using one of the following methods:</span></span>

   - <span data-ttu-id="1c542-129">В Visual Studio выберите проект в **Обозреватель решений**, а затем в контекстном меню выберите **Открыть папку в проводнике** .</span><span class="sxs-lookup"><span data-stu-id="1c542-129">In Visual Studio, select the project in **Solution Explorer**, and then choose **Open Folder in File Explorer** from the shortcut menu.</span></span> <span data-ttu-id="1c542-130">В проводнике найдите файл проекта (с расширением CSPROJ или VBPROJ) и откройте его в блокноте.</span><span class="sxs-lookup"><span data-stu-id="1c542-130">In File Explorer, find the project (.csproj or .vbproj) file and open it in Notepad.</span></span>
   - <span data-ttu-id="1c542-131">В **Обозреватель решений**щелкните правой кнопкой мыши проект в Visual Studio и выберите команду **Выгрузить проект**.</span><span class="sxs-lookup"><span data-stu-id="1c542-131">In Visual Studio, in **Solution Explorer**, right-click the project and choose **Unload Project**.</span></span> <span data-ttu-id="1c542-132">Снова щелкните правой кнопкой мыши выгруженный проект и выберите пункт **изменить [имя_проекта. csproj]** .</span><span class="sxs-lookup"><span data-stu-id="1c542-132">Right-click the unloaded project again, and then choose **Edit [projectname.csproj]**.</span></span>

2. <span data-ttu-id="1c542-133">Добавьте следующий элемент в первую группу свойств конфигурации (в \<теге PropertyGroup > тег):</span><span class="sxs-lookup"><span data-stu-id="1c542-133">Add the following element to the first configuration property group (under the \<PropertyGroup> tag):</span></span>

   ```xml
   <AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>
   ```

   <span data-ttu-id="1c542-134">Ниже приведен пример файла проекта с вставленным элементом:</span><span class="sxs-lookup"><span data-stu-id="1c542-134">The following shows an example project file with the element inserted:</span></span>

   ```xml
   <?xml version="1.0" encoding="utf-8"?>
   <Project ToolsVersion="12.0" DefaultTargets="Build" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
     <Import Project="$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props" Condition="Exists('$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props')" />
     <PropertyGroup>
       <Configuration Condition=" '$(Configuration)' == '' ">Debug</Configuration>
       <Platform Condition=" '$(Platform)' == '' ">AnyCPU</Platform>
       <ProjectGuid>{123334}</ProjectGuid>
       ...
       <AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>
     </PropertyGroup>
     ...
   </Project>
   ```

3. <span data-ttu-id="1c542-135">Скомпилируйте приложение.</span><span class="sxs-lookup"><span data-stu-id="1c542-135">Compile your app.</span></span>

## <a name="enable-automatic-binding-redirects-in-web-apps"></a><span data-ttu-id="1c542-136">Включение автоматического перенаправления привязок в веб-приложениях</span><span class="sxs-lookup"><span data-stu-id="1c542-136">Enable automatic binding redirects in web apps</span></span>

<span data-ttu-id="1c542-137">Для веб-приложений автоматические переадресации привязок реализованы иным образом.</span><span class="sxs-lookup"><span data-stu-id="1c542-137">Automatic binding redirects are implemented differently for web apps.</span></span> <span data-ttu-id="1c542-138">Поскольку файл конфигурации источника (**Web. config**) необходимо изменить для веб-приложений, перенаправления привязки не добавляются автоматически в файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="1c542-138">Because the source configuration (**web.config**) file must be modified for web apps, binding redirects are not automatically added to the configuration file.</span></span> <span data-ttu-id="1c542-139">Однако Visual Studio уведомляет вас о конфликтах привязки, и вы можете добавлять переадресации привязок для разрешения конфликтов.</span><span class="sxs-lookup"><span data-stu-id="1c542-139">However, Visual Studio notifies you of binding conflicts, and you can add binding redirects to resolve the conflicts.</span></span> <span data-ttu-id="1c542-140">Поскольку вам всегда предлагается добавить перенаправления привязок, вам не нужно явно отключать эту функцию для веб-приложения.</span><span class="sxs-lookup"><span data-stu-id="1c542-140">Because you're always prompted to add binding redirects, you don't need to explicitly disable this feature for a web app.</span></span>

<span data-ttu-id="1c542-141">Добавление перенаправлений привязок в файл **Web. config** :</span><span class="sxs-lookup"><span data-stu-id="1c542-141">To add binding redirects to a **web.config** file:</span></span>

1. <span data-ttu-id="1c542-142">В Visual Studio скомпилируйте приложение и проверьте его на наличие предупреждений сборки.</span><span class="sxs-lookup"><span data-stu-id="1c542-142">In Visual Studio, compile the app, and check for build warnings.</span></span>

   <span data-ttu-id="1c542-143">![Предупреждение сборки для конфликтов ссылок на сборки](./media/clr-assemblyrefwarning.png "CLR_AssemblyRefWarning")</span><span class="sxs-lookup"><span data-stu-id="1c542-143">![Build warning for assembly reference conflicts](./media/clr-assemblyrefwarning.png "CLR_AssemblyRefWarning")</span></span>

2. <span data-ttu-id="1c542-144">При наличии конфликтов привязки сборок выводится предупреждение.</span><span class="sxs-lookup"><span data-stu-id="1c542-144">If there are assembly binding conflicts, a warning appears.</span></span> <span data-ttu-id="1c542-145">Дважды щелкните предупреждение или выберите предупреждение и нажмите клавишу **Ввод**.</span><span class="sxs-lookup"><span data-stu-id="1c542-145">Double-click the warning, or select the warning and press **Enter**.</span></span>

   <span data-ttu-id="1c542-146">Откроется диалоговое окно, которое позволяет автоматически добавлять необходимые перенаправления привязок в исходный файл **Web. config** .</span><span class="sxs-lookup"><span data-stu-id="1c542-146">A dialog box that enables you to automatically add the necessary binding redirects to the source **web.config** file appears.</span></span>

   <span data-ttu-id="1c542-147">![Диалоговое окно разрешения перенаправления привязки](./media/clr-addbindingredirect.png "CLR_AddBindingRedirect")</span><span class="sxs-lookup"><span data-stu-id="1c542-147">![Binding redirect permission dialog](./media/clr-addbindingredirect.png "CLR_AddBindingRedirect")</span></span>

## <a name="see-also"></a><span data-ttu-id="1c542-148">См. также</span><span class="sxs-lookup"><span data-stu-id="1c542-148">See also</span></span>

- [<span data-ttu-id="1c542-149">\<Элемент bindingRedirect ></span><span class="sxs-lookup"><span data-stu-id="1c542-149">\<bindingRedirect> Element</span></span>](./file-schema/runtime/bindingredirect-element.md)
- [<span data-ttu-id="1c542-150">Перенаправление версий сборки</span><span class="sxs-lookup"><span data-stu-id="1c542-150">Redirecting Assembly Versions</span></span>](redirect-assembly-versions.md)
