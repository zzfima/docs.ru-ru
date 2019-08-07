---
title: Ведущее приложение WPF (PresentationHost.exe)
ms.date: 03/30/2017
helpviewer_keywords:
- WPF Host application [WPF]
- PresentationHost.exe
ms.assetid: 3215bfa1-722c-4ac8-a7c5-bdd02d30afbd
ms.openlocfilehash: 88e4c6895039c84a57ed215a37a10a4b68851b2d
ms.sourcegitcommit: 10736f243dd2296212e677e207102c463e5f143e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/06/2019
ms.locfileid: "68817925"
---
# <a name="wpf-host-presentationhostexe"></a><span data-ttu-id="27fce-102">Ведущее приложение WPF (PresentationHost.exe)</span><span class="sxs-lookup"><span data-stu-id="27fce-102">WPF Host (PresentationHost.exe)</span></span>
<span data-ttu-id="27fce-103">Узел Windows Presentation Foundation (WPF) (PresentationHost. exe) — это приложение, которое [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] позволяет размещать приложения в совместимых браузерах (включая Microsoft Internet Explorer 6 и более поздние версии).</span><span class="sxs-lookup"><span data-stu-id="27fce-103">Windows Presentation Foundation (WPF) Host (PresentationHost.exe) is the application that enables [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] applications to be hosted in compatible browsers (including Microsoft Internet Explorer 6 and later).</span></span> <span data-ttu-id="27fce-104">По умолчанию узел Windows Presentation Foundation (WPF) регистрируется в качестве оболочки и [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] обработчика для содержимого, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] размещенного в браузере, в том числе:</span><span class="sxs-lookup"><span data-stu-id="27fce-104">By default, Windows Presentation Foundation (WPF) Host is registered as the shell and [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] handler for browser-hosted [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] content, which includes:</span></span>  
  
- <span data-ttu-id="27fce-105">Свободные (нескомпилированные) файлы [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] (.xaml).</span><span class="sxs-lookup"><span data-stu-id="27fce-105">Loose (uncompiled) [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] files (.xaml).</span></span>  
  
- [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] <span data-ttu-id="27fce-106">(.xbap).</span><span class="sxs-lookup"><span data-stu-id="27fce-106">(.xbap).</span></span>  
  
 <span data-ttu-id="27fce-107">Для файлов этих типов Windows Presentation Foundation (WPF):</span><span class="sxs-lookup"><span data-stu-id="27fce-107">For files of these types, Windows Presentation Foundation (WPF) Host:</span></span>  
  
- <span data-ttu-id="27fce-108">Запускает зарегистрированный обработчик HTML для размещения содержимого Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="27fce-108">Launches the registered HTML handler to host the Windows Presentation Foundation (WPF) content.</span></span>  
  
- <span data-ttu-id="27fce-109">Загружает правильные версии требуемых сборок среды CLR и Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="27fce-109">Loads the right versions of the required common language runtime (CLR) and Windows Presentation Foundation (WPF) assemblies.</span></span>  
  
- <span data-ttu-id="27fce-110">Обеспечивает наличие соответствующих уровней разрешений для зоны развертывания.</span><span class="sxs-lookup"><span data-stu-id="27fce-110">Ensures the appropriate permission levels for the zone of deployment are in place.</span></span>  
  
 <span data-ttu-id="27fce-111">В этом разделе описываются параметры командной строки, которые можно использовать с PresentationHost.exe.</span><span class="sxs-lookup"><span data-stu-id="27fce-111">This topic describes the command line parameters that can be used with PresentationHost.exe.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="27fce-112">Использование</span><span class="sxs-lookup"><span data-stu-id="27fce-112">Usage</span></span>  
 `PresentationHost.exe [parameters] uri|filename`  
  
## <a name="parameters"></a><span data-ttu-id="27fce-113">Параметры</span><span class="sxs-lookup"><span data-stu-id="27fce-113">Parameters</span></span>  
  
|<span data-ttu-id="27fce-114">Параметр</span><span class="sxs-lookup"><span data-stu-id="27fce-114">Parameter</span></span>|<span data-ttu-id="27fce-115">Описание</span><span class="sxs-lookup"><span data-stu-id="27fce-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="27fce-116">filename</span><span class="sxs-lookup"><span data-stu-id="27fce-116">filename</span></span>|<span data-ttu-id="27fce-117">Путь к файлу, который нужно активировать.</span><span class="sxs-lookup"><span data-stu-id="27fce-117">The path of the file to be activated.</span></span> <span data-ttu-id="27fce-118">Также может быть [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span><span class="sxs-lookup"><span data-stu-id="27fce-118">Can also be a [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span></span>|  
|<span data-ttu-id="27fce-119">-debug</span><span class="sxs-lookup"><span data-stu-id="27fce-119">-debug</span></span>|<span data-ttu-id="27fce-120">При активации приложения не фиксирует его в хранилище и не запускает из хранилища.</span><span class="sxs-lookup"><span data-stu-id="27fce-120">When activating an application, does not commit it to or run it from the store.</span></span> <span data-ttu-id="27fce-121">Работает только при активации локального файла.</span><span class="sxs-lookup"><span data-stu-id="27fce-121">This only works when a local file is activated.</span></span>|  
|<span data-ttu-id="27fce-122">-debugSecurityZoneURL \<url></span><span class="sxs-lookup"><span data-stu-id="27fce-122">-debugSecurityZoneURL \<url></span></span>|<span data-ttu-id="27fce-123">Используется со значением [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] для указания необходимости отладки PresentationHost.exe, как при развертывании из указанного [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)].</span><span class="sxs-lookup"><span data-stu-id="27fce-123">Used with a [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] value to indicate to PresentationHost.exe that an application should be debugged as if it were deployed from the specified [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)].</span></span> <span data-ttu-id="27fce-124">Это определяет как зону развертывания, так и исходный узел.</span><span class="sxs-lookup"><span data-stu-id="27fce-124">This determines both the deployment zone and the site of origin.</span></span>|  
|<span data-ttu-id="27fce-125">-embedding</span><span class="sxs-lookup"><span data-stu-id="27fce-125">-embedding</span></span>|<span data-ttu-id="27fce-126">Требуется для OLE.</span><span class="sxs-lookup"><span data-stu-id="27fce-126">Required by OLE.</span></span> <span data-ttu-id="27fce-127">Если указан параметр `-event` или `-debug`, то не обязательно указывать параметр `-embedding`, поскольку он устанавливается внутренне.</span><span class="sxs-lookup"><span data-stu-id="27fce-127">If the `-event` or `-debug` parameter are specified, it is not necessary to specify the `-embedding` parameter, since that parameter is set internally.</span></span>|  
|<span data-ttu-id="27fce-128">-event \<eventname></span><span class="sxs-lookup"><span data-stu-id="27fce-128">-event \<eventname></span></span>|<span data-ttu-id="27fce-129">Открывает событие с указанным именем и сигнализирует ему при инициализации PresentationHost.exe и готовности к размещению содержимого [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].</span><span class="sxs-lookup"><span data-stu-id="27fce-129">Open the event with this name and signal it when PresentationHost.exe is initialized and ready to host [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] content.</span></span> <span data-ttu-id="27fce-130">Работа PresentationHost.exe будет прервана в случае ошибки при открытии события, например, если оно еще не создано.</span><span class="sxs-lookup"><span data-stu-id="27fce-130">PresentationHost.exe will terminate if there was an error opening the event, such as if it has not already been created.</span></span>|  
|<span data-ttu-id="27fce-131">-launchApplication \<url></span><span class="sxs-lookup"><span data-stu-id="27fce-131">-launchApplication \<url></span></span>|<span data-ttu-id="27fce-132">Запускает автономное приложение ClickOnce по указанному URL-адресу.</span><span class="sxs-lookup"><span data-stu-id="27fce-132">Launches a standalone ClickOnce application from the specified URL.</span></span> <span data-ttu-id="27fce-133">Применяются политики безопасности Internet Explorer и WinINet в отношении приложений .NET.</span><span class="sxs-lookup"><span data-stu-id="27fce-133">Internet Explorer and WinINet security policy concerning .NET applications are applied.</span></span>|  
  
## <a name="scenarios"></a><span data-ttu-id="27fce-134">Сценарии</span><span class="sxs-lookup"><span data-stu-id="27fce-134">Scenarios</span></span>  
  
### <a name="shell-handler"></a><span data-ttu-id="27fce-135">Обработчик оболочки</span><span class="sxs-lookup"><span data-stu-id="27fce-135">Shell Handler</span></span>  
 `PresentationHost.exe example.xbap`  
  
### <a name="mime-handler"></a><span data-ttu-id="27fce-136">Обработчик MIME</span><span class="sxs-lookup"><span data-stu-id="27fce-136">MIME Handler</span></span>  
 `PresentationHost.exe -embedding example.xbap`  
  
### <a name="visual-studio-debugging"></a><span data-ttu-id="27fce-137">Отладка в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="27fce-137">Visual Studio Debugging</span></span>  
 `PresentationHost.exe -debug example.xbap`  
  
### <a name="visual-studio-debugging-in-zone"></a><span data-ttu-id="27fce-138">Visual Studio, отладка в зоне</span><span class="sxs-lookup"><span data-stu-id="27fce-138">Visual Studio Debugging In Zone</span></span>  
 `PresentationHost.exe -debug -debugSecurityZoneURL http://www.example.com c:\folderpath\example.xbap`  
  
## <a name="see-also"></a><span data-ttu-id="27fce-139">См. также</span><span class="sxs-lookup"><span data-stu-id="27fce-139">See also</span></span>

- [<span data-ttu-id="27fce-140">Безопасность</span><span class="sxs-lookup"><span data-stu-id="27fce-140">Security</span></span>](../security-wpf.md)
