---
title: "Ведущее приложение WPF (PresentationHost.exe)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WPF Host application [WPF]
- PresentationHost.exe
ms.assetid: 3215bfa1-722c-4ac8-a7c5-bdd02d30afbd
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1c5a9df438353701932a3e732d6df28b08402ee8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="wpf-host-presentationhostexe"></a><span data-ttu-id="65d70-102">Ведущее приложение WPF (PresentationHost.exe)</span><span class="sxs-lookup"><span data-stu-id="65d70-102">WPF Host (PresentationHost.exe)</span></span>
[!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]<span data-ttu-id="65d70-103"> Ведущее приложение (PresentationHost.exe) — это приложение, которое позволяет размещать приложения [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] в совместимых браузерах (включая [!INCLUDE[TLA#tla_ie6](../../../../includes/tlasharptla-ie6-md.md)] и более поздние версии).</span><span class="sxs-lookup"><span data-stu-id="65d70-103"> Host (PresentationHost.exe) is the application that enables [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] applications to be hosted in compatible browsers (including [!INCLUDE[TLA#tla_ie6](../../../../includes/tlasharptla-ie6-md.md)] and later).</span></span> <span data-ttu-id="65d70-104">По умолчанию ведущее приложение [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] регистрируется в качестве оболочки и обработчика [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] для размещенного в браузере [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] содержимого, которое включает:</span><span class="sxs-lookup"><span data-stu-id="65d70-104">By default, [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] Host is registered as the shell and [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] handler for browser-hosted [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] content, which includes:</span></span>  
  
-   <span data-ttu-id="65d70-105">Свободные (нескомпилированные) файлы [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] (.xaml).</span><span class="sxs-lookup"><span data-stu-id="65d70-105">Loose (uncompiled) [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] files (.xaml).</span></span>  
  
-   [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)]<span data-ttu-id="65d70-106"> (.xbap).</span><span class="sxs-lookup"><span data-stu-id="65d70-106"> (.xbap).</span></span>  
  
 <span data-ttu-id="65d70-107">Для файлов этих типов ведущее приложение [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="65d70-107">For files of these types, [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] Host:</span></span>  
  
-   <span data-ttu-id="65d70-108">Запускает зарегистрированный обработчик [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] для размещения содержимого [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)].</span><span class="sxs-lookup"><span data-stu-id="65d70-108">Launches the registered [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] handler to host the [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] content.</span></span>  
  
-   <span data-ttu-id="65d70-109">Загружает правильные версии требуемых сборок [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] и [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)].</span><span class="sxs-lookup"><span data-stu-id="65d70-109">Loads the right versions of the required [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] and [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] assemblies.</span></span>  
  
-   <span data-ttu-id="65d70-110">Обеспечивает наличие соответствующих уровней разрешений для зоны развертывания.</span><span class="sxs-lookup"><span data-stu-id="65d70-110">Ensures the appropriate permission levels for the zone of deployment are in place.</span></span>  
  
 <span data-ttu-id="65d70-111">В этом разделе описываются параметры командной строки, которые можно использовать с PresentationHost.exe.</span><span class="sxs-lookup"><span data-stu-id="65d70-111">This topic describes the command line parameters that can be used with PresentationHost.exe.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="65d70-112">Использование</span><span class="sxs-lookup"><span data-stu-id="65d70-112">Usage</span></span>  
 `PresentationHost.exe [parameters] uri|filename`  
  
## <a name="parameters"></a><span data-ttu-id="65d70-113">Параметры</span><span class="sxs-lookup"><span data-stu-id="65d70-113">Parameters</span></span>  
  
|<span data-ttu-id="65d70-114">Параметр</span><span class="sxs-lookup"><span data-stu-id="65d70-114">Parameter</span></span>|<span data-ttu-id="65d70-115">Описание:</span><span class="sxs-lookup"><span data-stu-id="65d70-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="65d70-116">filename</span><span class="sxs-lookup"><span data-stu-id="65d70-116">filename</span></span>|<span data-ttu-id="65d70-117">Путь к файлу, который нужно активировать.</span><span class="sxs-lookup"><span data-stu-id="65d70-117">The path of the file to be activated.</span></span> <span data-ttu-id="65d70-118">Также может быть [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span><span class="sxs-lookup"><span data-stu-id="65d70-118">Can also be a [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span></span>|  
|<span data-ttu-id="65d70-119">-debug</span><span class="sxs-lookup"><span data-stu-id="65d70-119">-debug</span></span>|<span data-ttu-id="65d70-120">При активации приложения не фиксирует его в хранилище и не запускает из хранилища.</span><span class="sxs-lookup"><span data-stu-id="65d70-120">When activating an application, does not commit it to or run it from the store.</span></span> <span data-ttu-id="65d70-121">Работает только при активации локального файла.</span><span class="sxs-lookup"><span data-stu-id="65d70-121">This only works when a local file is activated.</span></span>|  
|<span data-ttu-id="65d70-122">-debugSecurityZoneURL \<url></span><span class="sxs-lookup"><span data-stu-id="65d70-122">-debugSecurityZoneURL \<url></span></span>|<span data-ttu-id="65d70-123">Используется со значением [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] для указания необходимости отладки PresentationHost.exe, как при развертывании из указанного [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)].</span><span class="sxs-lookup"><span data-stu-id="65d70-123">Used with a [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] value to indicate to PresentationHost.exe that an application should be debugged as if it were deployed from the specified [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)].</span></span> <span data-ttu-id="65d70-124">Это определяет как зону развертывания, так и исходный узел.</span><span class="sxs-lookup"><span data-stu-id="65d70-124">This determines both the deployment zone and the site of origin.</span></span>|  
|<span data-ttu-id="65d70-125">-embedding</span><span class="sxs-lookup"><span data-stu-id="65d70-125">-embedding</span></span>|<span data-ttu-id="65d70-126">Требуется для OLE.</span><span class="sxs-lookup"><span data-stu-id="65d70-126">Required by OLE.</span></span> <span data-ttu-id="65d70-127">Если указан параметр `-event` или `-debug`, то не обязательно указывать параметр `-embedding`, поскольку он устанавливается внутренне.</span><span class="sxs-lookup"><span data-stu-id="65d70-127">If the `-event` or `-debug` parameter are specified, it is not necessary to specify the `-embedding` parameter, since that parameter is set internally.</span></span>|  
|<span data-ttu-id="65d70-128">-event \<eventname></span><span class="sxs-lookup"><span data-stu-id="65d70-128">-event \<eventname></span></span>|<span data-ttu-id="65d70-129">Открывает событие с указанным именем и сигнализирует ему при инициализации PresentationHost.exe и готовности к размещению содержимого [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].</span><span class="sxs-lookup"><span data-stu-id="65d70-129">Open the event with this name and signal it when PresentationHost.exe is initialized and ready to host [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] content.</span></span> <span data-ttu-id="65d70-130">Работа PresentationHost.exe будет прервана в случае ошибки при открытии события, например, если оно еще не создано.</span><span class="sxs-lookup"><span data-stu-id="65d70-130">PresentationHost.exe will terminate if there was an error opening the event, such as if it has not already been created.</span></span>|  
|<span data-ttu-id="65d70-131">-launchApplication \<url></span><span class="sxs-lookup"><span data-stu-id="65d70-131">-launchApplication \<url></span></span>|<span data-ttu-id="65d70-132">Запускает автономное приложение [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)] с указанного URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="65d70-132">Launches a standalone [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)] application from the specified URL.</span></span> <span data-ttu-id="65d70-133">Применяется политика безопасности [!INCLUDE[TLA2#tla_iegeneric](../../../../includes/tla2sharptla-iegeneric-md.md)] и WinINet для приложений .NET.</span><span class="sxs-lookup"><span data-stu-id="65d70-133">[!INCLUDE[TLA2#tla_iegeneric](../../../../includes/tla2sharptla-iegeneric-md.md)] and WinINet security policy concerning .NET applications are applied.</span></span>|  
  
## <a name="scenarios"></a><span data-ttu-id="65d70-134">Сценарии</span><span class="sxs-lookup"><span data-stu-id="65d70-134">Scenarios</span></span>  
  
### <a name="shell-handler"></a><span data-ttu-id="65d70-135">Обработчик оболочки</span><span class="sxs-lookup"><span data-stu-id="65d70-135">Shell Handler</span></span>  
 `PresentationHost.exe example.xbap`  
  
### <a name="mime-handler"></a><span data-ttu-id="65d70-136">Обработчик MIME</span><span class="sxs-lookup"><span data-stu-id="65d70-136">MIME Handler</span></span>  
 `PresentationHost.exe -embedding example.xbap`  
  
### <a name="visual-studio-debugging"></a><span data-ttu-id="65d70-137">Отладка в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="65d70-137">Visual Studio Debugging</span></span>  
 `PresentationHost.exe -debug example.xbap`  
  
### <a name="visual-studio-debugging-in-zone"></a><span data-ttu-id="65d70-138">Visual Studio, отладка в зоне</span><span class="sxs-lookup"><span data-stu-id="65d70-138">Visual Studio Debugging In Zone</span></span>  
 `PresentationHost.exe -debug -debugSecurityZoneURL http://www.example.com c:\folderpath\example.xbap`  
  
## <a name="see-also"></a><span data-ttu-id="65d70-139">См. также</span><span class="sxs-lookup"><span data-stu-id="65d70-139">See Also</span></span>  
 [<span data-ttu-id="65d70-140">Безопасность</span><span class="sxs-lookup"><span data-stu-id="65d70-140">Security</span></span>](../../../../docs/framework/wpf/security-wpf.md)
