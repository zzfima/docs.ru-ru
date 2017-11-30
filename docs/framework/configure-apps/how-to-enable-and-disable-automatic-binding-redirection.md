---
title: "Практическое руководство. Включение и отключение автоматического перенаправления привязки"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- side-by-side execution, assembly binding redirection
- assemblies [.NET Framework], binding redirection
ms.assetid: 5fca42f3-bdce-4b81-a704-61e42c89d3ba
caps.latest.revision: "17"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 83b004934c303c95bdc4e6edb6031a86e2b1a6ad
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-enable-and-disable-automatic-binding-redirection"></a><span data-ttu-id="38cf6-102">Практическое руководство. Включение и отключение автоматического перенаправления привязки</span><span class="sxs-lookup"><span data-stu-id="38cf6-102">How to: Enable and Disable Automatic Binding Redirection</span></span>
<span data-ttu-id="38cf6-103">Начиная с [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)] при компиляции приложений, нацеленных на [!INCLUDE[net_v451](../../../includes/net-v451-md.md)], в файл конфигурации приложения могут автоматически быть добавлены переадресации привязок для переопределения унификации сборок.</span><span class="sxs-lookup"><span data-stu-id="38cf6-103">Starting with [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)], when you compile apps that target the [!INCLUDE[net_v451](../../../includes/net-v451-md.md)], binding redirects may be automatically added to the app configuration file to override assembly unification.</span></span> <span data-ttu-id="38cf6-104">Переадресации привязок добавляются, если приложение или его компоненты ссылаются на несколько версий одной сборки, даже если вручную указать переадресации привязок в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="38cf6-104">Binding redirects are added if your app or its components reference more than one version of the same assembly, even if you manually specify binding redirects in the configuration file for your app.</span></span> <span data-ttu-id="38cf6-105">Функция автоматической переадресации привязки затрагивает классические приложения и веб-приложения, нацеленные на [!INCLUDE[net_v451](../../../includes/net-v451-md.md)], хотя в случае веб-приложений она ведет себя несколько иначе.</span><span class="sxs-lookup"><span data-stu-id="38cf6-105">The automatic binding redirection feature affects traditional desktop apps and web apps that target the [!INCLUDE[net_v451](../../../includes/net-v451-md.md)], although the behavior is slightly different for a web app.</span></span> <span data-ttu-id="38cf6-106">Автоматическую переадресацию привязки можно включить при наличии существующих приложений, нацеленных на предыдущие версии .NET Framework; также можно отключить эту функцию, если требуется сохранить созданные вручную переадресации привязок.</span><span class="sxs-lookup"><span data-stu-id="38cf6-106">You can enable automatic binding redirection if you have existing apps that target previous versions of the .NET Framework, or you can disable this feature if you want to keep manually authored binding redirects.</span></span>  
  
## <a name="disabling-automatic-binding-redirects-in-desktop-apps"></a><span data-ttu-id="38cf6-107">Отключение автоматической переадресации привязок в классических приложениях</span><span class="sxs-lookup"><span data-stu-id="38cf6-107">Disabling automatic binding redirects in desktop apps</span></span>  
 <span data-ttu-id="38cf6-108">Автоматические переадресации привязки включены по умолчанию для классических приложений, нацеленных на [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] и более позних версий.</span><span class="sxs-lookup"><span data-stu-id="38cf6-108">Automatic binding redirects are enabled by default for traditional desktop apps that target the [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] and later versions.</span></span> <span data-ttu-id="38cf6-109">Переадресации привязок добавляются в выходной файл конфигурации (app.config), когда приложение компилируется и переопределяет унификацию сборок, которая может произойти в противном случае.</span><span class="sxs-lookup"><span data-stu-id="38cf6-109">The binding redirects are added to the output configuration (app.config) file when the app is compiled and overrides the assembly unification that might otherwise take place.</span></span> <span data-ttu-id="38cf6-110">Исходный файл app.config не изменяется.</span><span class="sxs-lookup"><span data-stu-id="38cf6-110">The source app.config file is not modified.</span></span> <span data-ttu-id="38cf6-111">Для отключения этой функции необходимо внести изменения в файл проекта для приложения.</span><span class="sxs-lookup"><span data-stu-id="38cf6-111">You can disable this feature by modifying the project file for the app.</span></span>  
  
#### <a name="to-disable-automatic-binding-redirects"></a><span data-ttu-id="38cf6-112">Отключение автоматических переадресаций привязки</span><span class="sxs-lookup"><span data-stu-id="38cf6-112">To disable automatic binding redirects</span></span>  
  
1.  <span data-ttu-id="38cf6-113">В Visual Studio выберите проект в **обозревателе решений**, а затем выберите **открыть папку в проводнике** в контекстном меню.</span><span class="sxs-lookup"><span data-stu-id="38cf6-113">In Visual Studio, select the project in **Solution Explorer**, and then choose **Open Folder in File Explorer** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="38cf6-114">В проводнике найдите файл проекта (с расширением .csproj или .vbproj) и откройте его в Блокноте.</span><span class="sxs-lookup"><span data-stu-id="38cf6-114">In File Explorer, find the project (.csproj or .vbproj) file, and open it in Notepad.</span></span>  
  
3.  <span data-ttu-id="38cf6-115">Найдите в файле проекта следующую запись свойства:</span><span class="sxs-lookup"><span data-stu-id="38cf6-115">In the project file, find the following property entry:</span></span>  
  
     `<AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>`  
  
4.  <span data-ttu-id="38cf6-116">Измените `true` на `false`:</span><span class="sxs-lookup"><span data-stu-id="38cf6-116">Change `true` to `false`:</span></span>  
  
     `<AutoGenerateBindingRedirects>false</AutoGenerateBindingRedirects>`  
  
## <a name="enabling-automatic-binding-redirects-manually"></a><span data-ttu-id="38cf6-117">Ручное включение автоматической переадресации привязок</span><span class="sxs-lookup"><span data-stu-id="38cf6-117">Enabling automatic binding redirects manually</span></span>  
 <span data-ttu-id="38cf6-118">Можно включить автоматические переадресации привязок в существующих приложениях, нацеленных на более старые версии .NET Framework, либо в случаях, когда не появляется автоматический запрос на добавление переадресации.</span><span class="sxs-lookup"><span data-stu-id="38cf6-118">You can enable automatic binding redirects in existing apps that target older versions of the .NET Framework, or in cases where you are not automatically prompted to add a redirect.</span></span> <span data-ttu-id="38cf6-119">Если вы ориентируетесь на более новую версию платформы, но не получаете автоматический запрос на добавление переадресации, скорее всего, в полученных выходных данных сборки вам будет предложено пересопоставить сборки.</span><span class="sxs-lookup"><span data-stu-id="38cf6-119">If you are targeting a newer version of the framework but do not get automatically prompted to add a redirect, you will likely get   build output that suggests you remap assemblies.</span></span>  
  
#### <a name="to-manually-add-an-automatic-binding-redirect-property"></a><span data-ttu-id="38cf6-120">Ручное добавление свойства автоматической переадресации привязки</span><span class="sxs-lookup"><span data-stu-id="38cf6-120">To manually add an automatic binding redirect property</span></span>  
  
1.  <span data-ttu-id="38cf6-121">В Visual Studio выберите проект в **обозревателе решений**, а затем выберите **открыть папку в проводнике** в контекстном меню.</span><span class="sxs-lookup"><span data-stu-id="38cf6-121">In Visual Studio, select the project in **Solution Explorer**, and then choose **Open Folder in File Explorer** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="38cf6-122">В проводнике найдите файл проекта (с расширением .csproj или .vbproj) и откройте его в Блокноте.</span><span class="sxs-lookup"><span data-stu-id="38cf6-122">In File Explorer, find the project (.csproj or .vbproj) file, and open it in Notepad.</span></span>  
  
3.  <span data-ttu-id="38cf6-123">Добавьте следующий элемент в первую группу свойств конфигурации (в разделе \<PropertyGroup > тег):</span><span class="sxs-lookup"><span data-stu-id="38cf6-123">Add the following element to the first configuration property group (under the \<PropertyGroup> tag):</span></span>  
  
     `<AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>`  
  
     <span data-ttu-id="38cf6-124">Ниже показан пример файла проекта со вставленным элементом.</span><span class="sxs-lookup"><span data-stu-id="38cf6-124">The following shows an example project file with the element inserted.</span></span>  
  
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
  
4.  <span data-ttu-id="38cf6-125">Скомпилируйте приложение.</span><span class="sxs-lookup"><span data-stu-id="38cf6-125">Compile your app.</span></span>  
  
## <a name="enabling-automatic-binding-redirects-in-web-apps"></a><span data-ttu-id="38cf6-126">Включение автоматической переадресации привязок в веб-приложениях</span><span class="sxs-lookup"><span data-stu-id="38cf6-126">Enabling automatic binding redirects in web apps</span></span>  
 <span data-ttu-id="38cf6-127">Для веб-приложений автоматические переадресации привязок реализованы иным образом.</span><span class="sxs-lookup"><span data-stu-id="38cf6-127">Automatic binding redirects are implemented differently for web apps.</span></span> <span data-ttu-id="38cf6-128">Поскольку в исходный файл конфигурации (web.config) для веб-приложений должны вноситься изменения, переадресации привязки не добавляются в файл конфигурации автоматически.</span><span class="sxs-lookup"><span data-stu-id="38cf6-128">Because the source configuration (web.config) file must be modified for web apps, binding redirects are not automatically added to the configuration file.</span></span> <span data-ttu-id="38cf6-129">Однако Visual Studio уведомляет вас о конфликтах привязки, и вы можете добавлять переадресации привязок для разрешения конфликтов.</span><span class="sxs-lookup"><span data-stu-id="38cf6-129">However, Visual Studio notifies you of binding conflicts, and you can add binding redirects to resolve the conflicts.</span></span> <span data-ttu-id="38cf6-130">Поскольку на добавление переадресации привязок всегда выводятся запросы, нет необходимости явно отключать эту функцию для веб-приложения.</span><span class="sxs-lookup"><span data-stu-id="38cf6-130">Because you are always prompted to add binding redirects, you do not need to explicitly disable this feature for a web app.</span></span>  
  
#### <a name="to-add-binding-redirects-to-a-webconfig-file"></a><span data-ttu-id="38cf6-131">Добавление переадресаций привязок в файл web.config</span><span class="sxs-lookup"><span data-stu-id="38cf6-131">To add binding redirects to a web.config file</span></span>  
  
1.  <span data-ttu-id="38cf6-132">В Visual Studio скомпилируйте приложение и проверьте его на наличие предупреждений сборки.</span><span class="sxs-lookup"><span data-stu-id="38cf6-132">In Visual Studio, compile the app, and check for build warnings.</span></span>  
  
     <span data-ttu-id="38cf6-133">![Предупреждение сборки для конфликтов ссылок сборок](../../../docs/framework/configure-apps/media/clr-assemblyrefwarning.png "CLR_AssemblyRefWarning")</span><span class="sxs-lookup"><span data-stu-id="38cf6-133">![Build warning for assembly reference conflicts](../../../docs/framework/configure-apps/media/clr-assemblyrefwarning.png "CLR_AssemblyRefWarning")</span></span>  
  
2.  <span data-ttu-id="38cf6-134">При наличии конфликтов привязки сборок выводится предупреждение.</span><span class="sxs-lookup"><span data-stu-id="38cf6-134">If there are assembly binding conflicts, a warning appears.</span></span> <span data-ttu-id="38cf6-135">Дважды щелкните предупреждение.</span><span class="sxs-lookup"><span data-stu-id="38cf6-135">Double-click the warning.</span></span> <span data-ttu-id="38cf6-136">(Клавиатура: выберите предупреждение и нажмите клавишу **ввод**.)</span><span class="sxs-lookup"><span data-stu-id="38cf6-136">(Keyboard: Select the warning and press **Enter**.)</span></span>  
  
     <span data-ttu-id="38cf6-137">Откроется диалоговое окно, которое позволяет автоматически добавить необходимые переадресации привязки в исходный файл web.config.</span><span class="sxs-lookup"><span data-stu-id="38cf6-137">A dialog box that enables you to automatically add the necessary binding redirects to the source web.config file appears.</span></span>  
  
     <span data-ttu-id="38cf6-138">![Диалоговое окно разрешений перенаправления привязки](../../../docs/framework/configure-apps/media/clr-addbindingredirect.png "CLR_AddBindingRedirect")</span><span class="sxs-lookup"><span data-stu-id="38cf6-138">![Binding redirect permission dialog](../../../docs/framework/configure-apps/media/clr-addbindingredirect.png "CLR_AddBindingRedirect")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38cf6-139">См. также</span><span class="sxs-lookup"><span data-stu-id="38cf6-139">See Also</span></span>  
 [<span data-ttu-id="38cf6-140">\<bindingRedirect > элемент</span><span class="sxs-lookup"><span data-stu-id="38cf6-140">\<bindingRedirect> Element</span></span>](../../../docs/framework/configure-apps/file-schema/runtime/bindingredirect-element.md)  
 [<span data-ttu-id="38cf6-141">Перенаправление версий сборки</span><span class="sxs-lookup"><span data-stu-id="38cf6-141">Redirecting Assembly Versions</span></span>](../../../docs/framework/configure-apps/redirect-assembly-versions.md)
