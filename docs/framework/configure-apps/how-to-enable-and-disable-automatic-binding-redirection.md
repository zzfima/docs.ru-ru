---
title: Практическое руководство. Включение и отключение автоматического перенаправления привязки
ms.date: 09/12/2018
helpviewer_keywords:
- side-by-side execution, assembly binding redirection
- assemblies [.NET Framework], binding redirection
ms.assetid: 5fca42f3-bdce-4b81-a704-61e42c89d3ba
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 9b9c9cbdb89ccf67942dcccee37ea410c6fa39a5
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47079547"
---
# <a name="how-to-enable-and-disable-automatic-binding-redirection"></a><span data-ttu-id="c9a1f-102">Практическое руководство. Включение и отключение автоматического перенаправления привязки</span><span class="sxs-lookup"><span data-stu-id="c9a1f-102">How to: Enable and Disable Automatic Binding Redirection</span></span>

<span data-ttu-id="c9a1f-103">При компиляции приложения в Visual Studio, предназначенных [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] и более поздних версиях перенаправление привязки могут быть автоматически добавлены в файл конфигурации приложения для переопределения унификации сборок.</span><span class="sxs-lookup"><span data-stu-id="c9a1f-103">When you compile apps in Visual Studio that target the [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] and later versions, binding redirects may be automatically added to the app configuration file to override assembly unification.</span></span> <span data-ttu-id="c9a1f-104">Переадресации привязок добавляются, если приложение или его компоненты ссылаются на несколько версий одной сборки, даже если вручную указать переадресации привязок в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="c9a1f-104">Binding redirects are added if your app or its components reference more than one version of the same assembly, even if you manually specify binding redirects in the configuration file for your app.</span></span> <span data-ttu-id="c9a1f-105">Возможность автоматической переадресации привязки затрагивает Классические приложения и веб-приложения, предназначенные [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] или более поздней версии, несмотря на то, что поведение несколько отличается для веб-приложения.</span><span class="sxs-lookup"><span data-stu-id="c9a1f-105">The automatic binding redirection feature affects traditional desktop apps and web apps that target the [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] or a later version, although the behavior is slightly different for a web app.</span></span> <span data-ttu-id="c9a1f-106">Автоматическую переадресацию привязки можно включить при наличии существующих приложений, нацеленных на предыдущие версии .NET Framework; также можно отключить эту возможность, если требуется сохранить созданные вручную переадресации привязок.</span><span class="sxs-lookup"><span data-stu-id="c9a1f-106">You can enable automatic binding redirection if you have existing apps that target previous versions of the .NET Framework, or you can disable this feature if you want to keep manually authored binding redirects.</span></span>

## <a name="disable-automatic-binding-redirects-in-desktop-apps"></a><span data-ttu-id="c9a1f-107">Отключить автоматические переадресации привязок в классических приложениях</span><span class="sxs-lookup"><span data-stu-id="c9a1f-107">Disable automatic binding redirects in desktop apps</span></span>

<span data-ttu-id="c9a1f-108">Автоматические переадресации привязки включены по умолчанию для классических приложений, нацеленных на [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] и более позних версий.</span><span class="sxs-lookup"><span data-stu-id="c9a1f-108">Automatic binding redirects are enabled by default for traditional desktop apps that target the [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] and later versions.</span></span> <span data-ttu-id="c9a1f-109">Переадресации привязок добавляются в выходной файл конфигурации (app.config), когда приложение компилируется и переопределяет унификацию сборок, которая может произойти в противном случае.</span><span class="sxs-lookup"><span data-stu-id="c9a1f-109">The binding redirects are added to the output configuration (app.config) file when the app is compiled and overrides the assembly unification that might otherwise take place.</span></span> <span data-ttu-id="c9a1f-110">Исходный файл app.config не изменяется.</span><span class="sxs-lookup"><span data-stu-id="c9a1f-110">The source app.config file is not modified.</span></span> <span data-ttu-id="c9a1f-111">Для отключения этой возможности необходимо внести изменения в файл проекта для приложения.</span><span class="sxs-lookup"><span data-stu-id="c9a1f-111">You can disable this feature by modifying the project file for the app.</span></span>

1. <span data-ttu-id="c9a1f-112">Откройте файл проекта для редактирования с помощью одного из следующих методов:</span><span class="sxs-lookup"><span data-stu-id="c9a1f-112">Open the project file for editing using one of the following methods:</span></span>

   - <span data-ttu-id="c9a1f-113">В Visual Studio выберите проект в **обозревателе решений**, а затем выберите **открыть папку в проводнике** в контекстном меню.</span><span class="sxs-lookup"><span data-stu-id="c9a1f-113">In Visual Studio, select the project in **Solution Explorer**, and then choose **Open Folder in File Explorer** from the shortcut menu.</span></span> <span data-ttu-id="c9a1f-114">В проводнике найдите файл проекта (CSPROJ или VBPROJ) и откройте его в блокноте.</span><span class="sxs-lookup"><span data-stu-id="c9a1f-114">In File Explorer, find the project (.csproj or .vbproj) file and open it in Notepad.</span></span>
   - <span data-ttu-id="c9a1f-115">В Visual Studio в **обозревателе решений**, щелкните правой кнопкой мыши проект и выберите пункт **выгрузить проект**.</span><span class="sxs-lookup"><span data-stu-id="c9a1f-115">In Visual Studio, in **Solution Explorer**, right-click the project and choose **Unload Project**.</span></span> <span data-ttu-id="c9a1f-116">Щелкните правой кнопкой мыши выгруженного проекта, а затем выберите **изменить [projectname.csproj]**.</span><span class="sxs-lookup"><span data-stu-id="c9a1f-116">Right-click the unloaded project again, and then choose **Edit [projectname.csproj]**.</span></span>

2. <span data-ttu-id="c9a1f-117">Найдите в файле проекта следующую запись свойства:</span><span class="sxs-lookup"><span data-stu-id="c9a1f-117">In the project file, find the following property entry:</span></span>

   ```xml
   <AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>
   ```

3. <span data-ttu-id="c9a1f-118">Измените `true` на `false`:</span><span class="sxs-lookup"><span data-stu-id="c9a1f-118">Change `true` to `false`:</span></span>

   ```xml
   <AutoGenerateBindingRedirects>false</AutoGenerateBindingRedirects>
   ```

## <a name="enable-automatic-binding-redirects-manually"></a><span data-ttu-id="c9a1f-119">Вручную включить автоматические переадресации привязок</span><span class="sxs-lookup"><span data-stu-id="c9a1f-119">Enable automatic binding redirects manually</span></span>

<span data-ttu-id="c9a1f-120">Вы можете включить автоматические переадресации привязок в существующих приложениях, целевой объект более старые версии платформы .NET Framework, а также в случаях, где вам будет предложено автоматически Добавление переадресации.</span><span class="sxs-lookup"><span data-stu-id="c9a1f-120">You can enable automatic binding redirects in existing apps that target older versions of the .NET Framework, or in cases where you're not automatically prompted to add a redirect.</span></span> <span data-ttu-id="c9a1f-121">Если целевой платформой является более новой версии платформы, но не получаю автоматически запрос на добавление переадресации, скорее всего появится выходные данные сборки, пересопоставить сборки.</span><span class="sxs-lookup"><span data-stu-id="c9a1f-121">If you're targeting a newer version of the framework but do not get automatically prompted to add a redirect, you'll likely get build output that suggests you remap assemblies.</span></span>

1. <span data-ttu-id="c9a1f-122">Откройте файл проекта для редактирования с помощью одного из следующих методов:</span><span class="sxs-lookup"><span data-stu-id="c9a1f-122">Open the project file for editing using one of the following methods:</span></span>

   - <span data-ttu-id="c9a1f-123">В Visual Studio выберите проект в **обозревателе решений**, а затем выберите **открыть папку в проводнике** в контекстном меню.</span><span class="sxs-lookup"><span data-stu-id="c9a1f-123">In Visual Studio, select the project in **Solution Explorer**, and then choose **Open Folder in File Explorer** from the shortcut menu.</span></span> <span data-ttu-id="c9a1f-124">В проводнике найдите файл проекта (CSPROJ или VBPROJ) и откройте его в блокноте.</span><span class="sxs-lookup"><span data-stu-id="c9a1f-124">In File Explorer, find the project (.csproj or .vbproj) file and open it in Notepad.</span></span>
   - <span data-ttu-id="c9a1f-125">В Visual Studio в **обозревателе решений**, щелкните правой кнопкой мыши проект и выберите пункт **выгрузить проект**.</span><span class="sxs-lookup"><span data-stu-id="c9a1f-125">In Visual Studio, in **Solution Explorer**, right-click the project and choose **Unload Project**.</span></span> <span data-ttu-id="c9a1f-126">Щелкните правой кнопкой мыши выгруженного проекта, а затем выберите **изменить [projectname.csproj]**.</span><span class="sxs-lookup"><span data-stu-id="c9a1f-126">Right-click the unloaded project again, and then choose **Edit [projectname.csproj]**.</span></span>

2. <span data-ttu-id="c9a1f-127">Добавьте следующий элемент в первую группу свойств конфигурации (в разделе \<PropertyGroup > тег):</span><span class="sxs-lookup"><span data-stu-id="c9a1f-127">Add the following element to the first configuration property group (under the \<PropertyGroup> tag):</span></span>

   ```xml
   <AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>
   ```

   <span data-ttu-id="c9a1f-128">Ниже показан пример файла проекта со вставленным элементом:</span><span class="sxs-lookup"><span data-stu-id="c9a1f-128">The following shows an example project file with the element inserted:</span></span>

   ```xml
   <?xml version="1.0" encoding="utf-8"?>
   <Project ToolsVersion="12.0" DefaultTargets="Build" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
     <Import Project="$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props" Condition="Exists('$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props')" />
       <PropertyGroup>
         <Configuration Condition=" '$(Configuration)' == ''     ">Debug</Configuration>
         <Platform Condition=" '$(Platform)' == '' ">AnyCPU</Platform>
         <ProjectGuid>{123334}</ProjectGuid>
         ...
         <AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>
       </PropertyGroup>
     ...
   </Project>
   ```

3. <span data-ttu-id="c9a1f-129">Скомпилируйте приложение.</span><span class="sxs-lookup"><span data-stu-id="c9a1f-129">Compile your app.</span></span>

## <a name="enable-automatic-binding-redirects-in-web-apps"></a><span data-ttu-id="c9a1f-130">Включить автоматические переадресации привязок в веб-приложениях</span><span class="sxs-lookup"><span data-stu-id="c9a1f-130">Enable automatic binding redirects in web apps</span></span>

<span data-ttu-id="c9a1f-131">Для веб-приложений автоматические переадресации привязок реализованы иным образом.</span><span class="sxs-lookup"><span data-stu-id="c9a1f-131">Automatic binding redirects are implemented differently for web apps.</span></span> <span data-ttu-id="c9a1f-132">Поскольку в исходный файл конфигурации (web.config) для веб-приложений должны вноситься изменения, переадресации привязки не добавляются в файл конфигурации автоматически.</span><span class="sxs-lookup"><span data-stu-id="c9a1f-132">Because the source configuration (web.config) file must be modified for web apps, binding redirects are not automatically added to the configuration file.</span></span> <span data-ttu-id="c9a1f-133">Однако Visual Studio уведомляет вас о конфликтах привязки, и вы можете добавлять переадресации привязок для разрешения конфликтов.</span><span class="sxs-lookup"><span data-stu-id="c9a1f-133">However, Visual Studio notifies you of binding conflicts, and you can add binding redirects to resolve the conflicts.</span></span> <span data-ttu-id="c9a1f-134">Так как всегда, будет предложено добавить переадресации привязок, не нужно явно отключить эту функцию для веб-приложения.</span><span class="sxs-lookup"><span data-stu-id="c9a1f-134">Because you're always prompted to add binding redirects, you don't need to explicitly disable this feature for a web app.</span></span>

<span data-ttu-id="c9a1f-135">Добавление переадресаций привязок в файл web.config:</span><span class="sxs-lookup"><span data-stu-id="c9a1f-135">To add binding redirects to a web.config file:</span></span>

1. <span data-ttu-id="c9a1f-136">В Visual Studio скомпилируйте приложение и проверьте его на наличие предупреждений сборки.</span><span class="sxs-lookup"><span data-stu-id="c9a1f-136">In Visual Studio, compile the app, and check for build warnings.</span></span>

   <span data-ttu-id="c9a1f-137">![Предупреждение сборки для конфликтов ссылок сборок](../../../docs/framework/configure-apps/media/clr-assemblyrefwarning.png "CLR_AssemblyRefWarning")</span><span class="sxs-lookup"><span data-stu-id="c9a1f-137">![Build warning for assembly reference conflicts](../../../docs/framework/configure-apps/media/clr-assemblyrefwarning.png "CLR_AssemblyRefWarning")</span></span>

2. <span data-ttu-id="c9a1f-138">При наличии конфликтов привязки сборок выводится предупреждение.</span><span class="sxs-lookup"><span data-stu-id="c9a1f-138">If there are assembly binding conflicts, a warning appears.</span></span> <span data-ttu-id="c9a1f-139">Дважды щелкните предупреждение, или выберите предупреждение и нажмите клавишу **ввод**.</span><span class="sxs-lookup"><span data-stu-id="c9a1f-139">Double-click the warning, or select the warning and press **Enter**.</span></span>

   <span data-ttu-id="c9a1f-140">Откроется диалоговое окно, которое позволяет автоматически добавить необходимые переадресации привязки в исходный файл web.config.</span><span class="sxs-lookup"><span data-stu-id="c9a1f-140">A dialog box that enables you to automatically add the necessary binding redirects to the source web.config file appears.</span></span>

   <span data-ttu-id="c9a1f-141">![Диалоговое окно разрешений для перенаправления привязки](../../../docs/framework/configure-apps/media/clr-addbindingredirect.png "CLR_AddBindingRedirect")</span><span class="sxs-lookup"><span data-stu-id="c9a1f-141">![Binding redirect permission dialog](../../../docs/framework/configure-apps/media/clr-addbindingredirect.png "CLR_AddBindingRedirect")</span></span>

## <a name="see-also"></a><span data-ttu-id="c9a1f-142">См. также</span><span class="sxs-lookup"><span data-stu-id="c9a1f-142">See also</span></span>

- [<span data-ttu-id="c9a1f-143">\<bindingRedirect > элемент</span><span class="sxs-lookup"><span data-stu-id="c9a1f-143">\<bindingRedirect> Element</span></span>](../../../docs/framework/configure-apps/file-schema/runtime/bindingredirect-element.md)
- [<span data-ttu-id="c9a1f-144">Перенаправление версий сборки</span><span class="sxs-lookup"><span data-stu-id="c9a1f-144">Redirecting Assembly Versions</span></span>](../../../docs/framework/configure-apps/redirect-assembly-versions.md)
