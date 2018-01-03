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
ms.workload: dotnet
ms.openlocfilehash: b6887706aeef3855c1e02c8b1379856022cdac04
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-enable-and-disable-automatic-binding-redirection"></a><span data-ttu-id="bd114-102">Практическое руководство. Включение и отключение автоматического перенаправления привязки</span><span class="sxs-lookup"><span data-stu-id="bd114-102">How to: Enable and Disable Automatic Binding Redirection</span></span>
<span data-ttu-id="bd114-103">Начиная с [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)] при компиляции приложений, нацеленных на [!INCLUDE[net_v451](../../../includes/net-v451-md.md)], в файл конфигурации приложения могут автоматически быть добавлены переадресации привязок для переопределения унификации сборок.</span><span class="sxs-lookup"><span data-stu-id="bd114-103">Starting with [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)], when you compile apps that target the [!INCLUDE[net_v451](../../../includes/net-v451-md.md)], binding redirects may be automatically added to the app configuration file to override assembly unification.</span></span> <span data-ttu-id="bd114-104">Переадресации привязок добавляются, если приложение или его компоненты ссылаются на несколько версий одной сборки, даже если вручную указать переадресации привязок в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="bd114-104">Binding redirects are added if your app or its components reference more than one version of the same assembly, even if you manually specify binding redirects in the configuration file for your app.</span></span> <span data-ttu-id="bd114-105">Функция автоматической переадресации привязки затрагивает классические приложения и веб-приложения, нацеленные на [!INCLUDE[net_v451](../../../includes/net-v451-md.md)], хотя в случае веб-приложений она ведет себя несколько иначе.</span><span class="sxs-lookup"><span data-stu-id="bd114-105">The automatic binding redirection feature affects traditional desktop apps and web apps that target the [!INCLUDE[net_v451](../../../includes/net-v451-md.md)], although the behavior is slightly different for a web app.</span></span> <span data-ttu-id="bd114-106">Автоматическую переадресацию привязки можно включить при наличии существующих приложений, нацеленных на предыдущие версии .NET Framework; также можно отключить эту функцию, если требуется сохранить созданные вручную переадресации привязок.</span><span class="sxs-lookup"><span data-stu-id="bd114-106">You can enable automatic binding redirection if you have existing apps that target previous versions of the .NET Framework, or you can disable this feature if you want to keep manually authored binding redirects.</span></span>  
  
## <a name="disabling-automatic-binding-redirects-in-desktop-apps"></a><span data-ttu-id="bd114-107">Отключение автоматической переадресации привязок в классических приложениях</span><span class="sxs-lookup"><span data-stu-id="bd114-107">Disabling automatic binding redirects in desktop apps</span></span>  
 <span data-ttu-id="bd114-108">Автоматические переадресации привязки включены по умолчанию для классических приложений, нацеленных на [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] и более позних версий.</span><span class="sxs-lookup"><span data-stu-id="bd114-108">Automatic binding redirects are enabled by default for traditional desktop apps that target the [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] and later versions.</span></span> <span data-ttu-id="bd114-109">Переадресации привязок добавляются в выходной файл конфигурации (app.config), когда приложение компилируется и переопределяет унификацию сборок, которая может произойти в противном случае.</span><span class="sxs-lookup"><span data-stu-id="bd114-109">The binding redirects are added to the output configuration (app.config) file when the app is compiled and overrides the assembly unification that might otherwise take place.</span></span> <span data-ttu-id="bd114-110">Исходный файл app.config не изменяется.</span><span class="sxs-lookup"><span data-stu-id="bd114-110">The source app.config file is not modified.</span></span> <span data-ttu-id="bd114-111">Для отключения этой функции необходимо внести изменения в файл проекта для приложения.</span><span class="sxs-lookup"><span data-stu-id="bd114-111">You can disable this feature by modifying the project file for the app.</span></span>  
  
#### <a name="to-disable-automatic-binding-redirects"></a><span data-ttu-id="bd114-112">Отключение автоматических переадресаций привязки</span><span class="sxs-lookup"><span data-stu-id="bd114-112">To disable automatic binding redirects</span></span>  
  
1.  <span data-ttu-id="bd114-113">В Visual Studio выберите проект в **обозревателе решений**, а затем выберите **открыть папку в проводнике** в контекстном меню.</span><span class="sxs-lookup"><span data-stu-id="bd114-113">In Visual Studio, select the project in **Solution Explorer**, and then choose **Open Folder in File Explorer** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="bd114-114">В проводнике найдите файл проекта (с расширением .csproj или .vbproj) и откройте его в Блокноте.</span><span class="sxs-lookup"><span data-stu-id="bd114-114">In File Explorer, find the project (.csproj or .vbproj) file, and open it in Notepad.</span></span>  
  
3.  <span data-ttu-id="bd114-115">Найдите в файле проекта следующую запись свойства:</span><span class="sxs-lookup"><span data-stu-id="bd114-115">In the project file, find the following property entry:</span></span>  
  
     `<AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>`  
  
4.  <span data-ttu-id="bd114-116">Измените `true` на `false`:</span><span class="sxs-lookup"><span data-stu-id="bd114-116">Change `true` to `false`:</span></span>  
  
     `<AutoGenerateBindingRedirects>false</AutoGenerateBindingRedirects>`  
  
## <a name="enabling-automatic-binding-redirects-manually"></a><span data-ttu-id="bd114-117">Ручное включение автоматической переадресации привязок</span><span class="sxs-lookup"><span data-stu-id="bd114-117">Enabling automatic binding redirects manually</span></span>  
 <span data-ttu-id="bd114-118">Можно включить автоматические переадресации привязок в существующих приложениях, нацеленных на более старые версии .NET Framework, либо в случаях, когда не появляется автоматический запрос на добавление переадресации.</span><span class="sxs-lookup"><span data-stu-id="bd114-118">You can enable automatic binding redirects in existing apps that target older versions of the .NET Framework, or in cases where you are not automatically prompted to add a redirect.</span></span> <span data-ttu-id="bd114-119">Если вы ориентируетесь на более новую версию платформы, но не получаете автоматический запрос на добавление переадресации, скорее всего, в полученных выходных данных сборки вам будет предложено пересопоставить сборки.</span><span class="sxs-lookup"><span data-stu-id="bd114-119">If you are targeting a newer version of the framework but do not get automatically prompted to add a redirect, you will likely get   build output that suggests you remap assemblies.</span></span>  
  
#### <a name="to-manually-add-an-automatic-binding-redirect-property"></a><span data-ttu-id="bd114-120">Ручное добавление свойства автоматической переадресации привязки</span><span class="sxs-lookup"><span data-stu-id="bd114-120">To manually add an automatic binding redirect property</span></span>  
  
1.  <span data-ttu-id="bd114-121">В Visual Studio выберите проект в **обозревателе решений**, а затем выберите **открыть папку в проводнике** в контекстном меню.</span><span class="sxs-lookup"><span data-stu-id="bd114-121">In Visual Studio, select the project in **Solution Explorer**, and then choose **Open Folder in File Explorer** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="bd114-122">В проводнике найдите файл проекта (с расширением .csproj или .vbproj) и откройте его в Блокноте.</span><span class="sxs-lookup"><span data-stu-id="bd114-122">In File Explorer, find the project (.csproj or .vbproj) file, and open it in Notepad.</span></span>  
  
3.  <span data-ttu-id="bd114-123">Добавьте следующий элемент в первую группу свойств конфигурации (в разделе \<PropertyGroup > тег):</span><span class="sxs-lookup"><span data-stu-id="bd114-123">Add the following element to the first configuration property group (under the \<PropertyGroup> tag):</span></span>  
  
     `<AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>`  
  
     <span data-ttu-id="bd114-124">Ниже показан пример файла проекта со вставленным элементом.</span><span class="sxs-lookup"><span data-stu-id="bd114-124">The following shows an example project file with the element inserted.</span></span>  
  
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
  
4.  <span data-ttu-id="bd114-125">Скомпилируйте приложение.</span><span class="sxs-lookup"><span data-stu-id="bd114-125">Compile your app.</span></span>  
  
## <a name="enabling-automatic-binding-redirects-in-web-apps"></a><span data-ttu-id="bd114-126">Включение автоматической переадресации привязок в веб-приложениях</span><span class="sxs-lookup"><span data-stu-id="bd114-126">Enabling automatic binding redirects in web apps</span></span>  
 <span data-ttu-id="bd114-127">Для веб-приложений автоматические переадресации привязок реализованы иным образом.</span><span class="sxs-lookup"><span data-stu-id="bd114-127">Automatic binding redirects are implemented differently for web apps.</span></span> <span data-ttu-id="bd114-128">Поскольку в исходный файл конфигурации (web.config) для веб-приложений должны вноситься изменения, переадресации привязки не добавляются в файл конфигурации автоматически.</span><span class="sxs-lookup"><span data-stu-id="bd114-128">Because the source configuration (web.config) file must be modified for web apps, binding redirects are not automatically added to the configuration file.</span></span> <span data-ttu-id="bd114-129">Однако Visual Studio уведомляет вас о конфликтах привязки, и вы можете добавлять переадресации привязок для разрешения конфликтов.</span><span class="sxs-lookup"><span data-stu-id="bd114-129">However, Visual Studio notifies you of binding conflicts, and you can add binding redirects to resolve the conflicts.</span></span> <span data-ttu-id="bd114-130">Поскольку на добавление переадресации привязок всегда выводятся запросы, нет необходимости явно отключать эту функцию для веб-приложения.</span><span class="sxs-lookup"><span data-stu-id="bd114-130">Because you are always prompted to add binding redirects, you do not need to explicitly disable this feature for a web app.</span></span>  
  
#### <a name="to-add-binding-redirects-to-a-webconfig-file"></a><span data-ttu-id="bd114-131">Добавление переадресаций привязок в файл web.config</span><span class="sxs-lookup"><span data-stu-id="bd114-131">To add binding redirects to a web.config file</span></span>  
  
1.  <span data-ttu-id="bd114-132">В Visual Studio скомпилируйте приложение и проверьте его на наличие предупреждений сборки.</span><span class="sxs-lookup"><span data-stu-id="bd114-132">In Visual Studio, compile the app, and check for build warnings.</span></span>  
  
     <span data-ttu-id="bd114-133">![Предупреждение сборки для конфликтов ссылок сборок](../../../docs/framework/configure-apps/media/clr-assemblyrefwarning.png "CLR_AssemblyRefWarning")</span><span class="sxs-lookup"><span data-stu-id="bd114-133">![Build warning for assembly reference conflicts](../../../docs/framework/configure-apps/media/clr-assemblyrefwarning.png "CLR_AssemblyRefWarning")</span></span>  
  
2.  <span data-ttu-id="bd114-134">При наличии конфликтов привязки сборок выводится предупреждение.</span><span class="sxs-lookup"><span data-stu-id="bd114-134">If there are assembly binding conflicts, a warning appears.</span></span> <span data-ttu-id="bd114-135">Дважды щелкните предупреждение.</span><span class="sxs-lookup"><span data-stu-id="bd114-135">Double-click the warning.</span></span> <span data-ttu-id="bd114-136">(Клавиатура: выберите предупреждение и нажмите клавишу **ввод**.)</span><span class="sxs-lookup"><span data-stu-id="bd114-136">(Keyboard: Select the warning and press **Enter**.)</span></span>  
  
     <span data-ttu-id="bd114-137">Откроется диалоговое окно, которое позволяет автоматически добавить необходимые переадресации привязки в исходный файл web.config.</span><span class="sxs-lookup"><span data-stu-id="bd114-137">A dialog box that enables you to automatically add the necessary binding redirects to the source web.config file appears.</span></span>  
  
     <span data-ttu-id="bd114-138">![Диалоговое окно разрешений перенаправления привязки](../../../docs/framework/configure-apps/media/clr-addbindingredirect.png "CLR_AddBindingRedirect")</span><span class="sxs-lookup"><span data-stu-id="bd114-138">![Binding redirect permission dialog](../../../docs/framework/configure-apps/media/clr-addbindingredirect.png "CLR_AddBindingRedirect")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd114-139">См. также</span><span class="sxs-lookup"><span data-stu-id="bd114-139">See Also</span></span>  
 [<span data-ttu-id="bd114-140">\<bindingRedirect > элемент</span><span class="sxs-lookup"><span data-stu-id="bd114-140">\<bindingRedirect> Element</span></span>](../../../docs/framework/configure-apps/file-schema/runtime/bindingredirect-element.md)  
 [<span data-ttu-id="bd114-141">Перенаправление версий сборки</span><span class="sxs-lookup"><span data-stu-id="bd114-141">Redirecting Assembly Versions</span></span>](../../../docs/framework/configure-apps/redirect-assembly-versions.md)
