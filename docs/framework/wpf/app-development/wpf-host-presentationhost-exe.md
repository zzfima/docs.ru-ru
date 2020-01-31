---
title: Ведущее приложение WPF (PresentationHost.exe)
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- WPF Host application [WPF]
- PresentationHost.exe
ms.assetid: 3215bfa1-722c-4ac8-a7c5-bdd02d30afbd
ms.openlocfilehash: bda7efbb1b7a4760199215bdb58c12b3063e290c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743397"
---
# <a name="wpf-host-presentationhostexe"></a><span data-ttu-id="d77c4-102">Ведущее приложение WPF (PresentationHost.exe)</span><span class="sxs-lookup"><span data-stu-id="d77c4-102">WPF Host (PresentationHost.exe)</span></span>
<span data-ttu-id="d77c4-103">Узел Windows Presentation Foundation (WPF) (PresentationHost. exe) — это приложение, которое позволяет размещать приложения WPF в совместимых браузерах (включая Microsoft Internet Explorer 6 и более поздние версии).</span><span class="sxs-lookup"><span data-stu-id="d77c4-103">Windows Presentation Foundation (WPF) Host (PresentationHost.exe) is the application that enables WPF applications to be hosted in compatible browsers (including Microsoft Internet Explorer 6 and later).</span></span> <span data-ttu-id="d77c4-104">По умолчанию узел Windows Presentation Foundation (WPF) регистрируется в качестве оболочки и обработчика MIME для содержимого WPF, размещенного в браузере, в том числе:</span><span class="sxs-lookup"><span data-stu-id="d77c4-104">By default, Windows Presentation Foundation (WPF) Host is registered as the shell and MIME handler for browser-hosted WPF content, which includes:</span></span>  
  
- <span data-ttu-id="d77c4-105">Свободные (нескомпилированные) файлы [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] (.xaml).</span><span class="sxs-lookup"><span data-stu-id="d77c4-105">Loose (uncompiled) [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] files (.xaml).</span></span>  
  
- <span data-ttu-id="d77c4-106">Приложение браузера XAML (XBAP).</span><span class="sxs-lookup"><span data-stu-id="d77c4-106">XAML browser application (XBAP) (.xbap).</span></span>  
  
 <span data-ttu-id="d77c4-107">Для файлов этих типов Windows Presentation Foundation (WPF):</span><span class="sxs-lookup"><span data-stu-id="d77c4-107">For files of these types, Windows Presentation Foundation (WPF) Host:</span></span>  
  
- <span data-ttu-id="d77c4-108">Запускает зарегистрированный обработчик HTML для размещения содержимого Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="d77c4-108">Launches the registered HTML handler to host the Windows Presentation Foundation (WPF) content.</span></span>  
  
- <span data-ttu-id="d77c4-109">Загружает правильные версии требуемых сборок среды CLR и Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="d77c4-109">Loads the right versions of the required common language runtime (CLR) and Windows Presentation Foundation (WPF) assemblies.</span></span>  
  
- <span data-ttu-id="d77c4-110">Обеспечивает наличие соответствующих уровней разрешений для зоны развертывания.</span><span class="sxs-lookup"><span data-stu-id="d77c4-110">Ensures the appropriate permission levels for the zone of deployment are in place.</span></span>  
  
 <span data-ttu-id="d77c4-111">В этом разделе описываются параметры командной строки, которые можно использовать с PresentationHost.exe.</span><span class="sxs-lookup"><span data-stu-id="d77c4-111">This topic describes the command line parameters that can be used with PresentationHost.exe.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="d77c4-112">Метрики</span><span class="sxs-lookup"><span data-stu-id="d77c4-112">Usage</span></span>  
 `PresentationHost.exe [parameters] uri|filename`  
  
## <a name="parameters"></a><span data-ttu-id="d77c4-113">Параметры</span><span class="sxs-lookup"><span data-stu-id="d77c4-113">Parameters</span></span>  
  
|<span data-ttu-id="d77c4-114">Параметр</span><span class="sxs-lookup"><span data-stu-id="d77c4-114">Parameter</span></span>|<span data-ttu-id="d77c4-115">Описание</span><span class="sxs-lookup"><span data-stu-id="d77c4-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d77c4-116">имя_файла</span><span class="sxs-lookup"><span data-stu-id="d77c4-116">filename</span></span>|<span data-ttu-id="d77c4-117">Путь к файлу, который нужно активировать.</span><span class="sxs-lookup"><span data-stu-id="d77c4-117">The path of the file to be activated.</span></span> <span data-ttu-id="d77c4-118">Также может быть URI.</span><span class="sxs-lookup"><span data-stu-id="d77c4-118">Can also be a URI.</span></span>|  
|<span data-ttu-id="d77c4-119">-debug</span><span class="sxs-lookup"><span data-stu-id="d77c4-119">-debug</span></span>|<span data-ttu-id="d77c4-120">При активации приложения не фиксирует его в хранилище и не запускает из хранилища.</span><span class="sxs-lookup"><span data-stu-id="d77c4-120">When activating an application, does not commit it to or run it from the store.</span></span> <span data-ttu-id="d77c4-121">Работает только при активации локального файла.</span><span class="sxs-lookup"><span data-stu-id="d77c4-121">This only works when a local file is activated.</span></span>|  
|<span data-ttu-id="d77c4-122">-debugSecurityZoneURL \<url></span><span class="sxs-lookup"><span data-stu-id="d77c4-122">-debugSecurityZoneURL \<url></span></span>|<span data-ttu-id="d77c4-123">Используется со значением URL-адреса, чтобы указать PresentationHost. exe, что приложение должно быть отлажено, как если бы оно было развернуто с указанного URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="d77c4-123">Used with a URL value to indicate to PresentationHost.exe that an application should be debugged as if it were deployed from the specified URL.</span></span> <span data-ttu-id="d77c4-124">Это определяет как зону развертывания, так и исходный узел.</span><span class="sxs-lookup"><span data-stu-id="d77c4-124">This determines both the deployment zone and the site of origin.</span></span>|  
|<span data-ttu-id="d77c4-125">-embedding</span><span class="sxs-lookup"><span data-stu-id="d77c4-125">-embedding</span></span>|<span data-ttu-id="d77c4-126">Требуется для OLE.</span><span class="sxs-lookup"><span data-stu-id="d77c4-126">Required by OLE.</span></span> <span data-ttu-id="d77c4-127">Если указан параметр `-event` или `-debug`, то не обязательно указывать параметр `-embedding`, поскольку он устанавливается внутренне.</span><span class="sxs-lookup"><span data-stu-id="d77c4-127">If the `-event` or `-debug` parameter are specified, it is not necessary to specify the `-embedding` parameter, since that parameter is set internally.</span></span>|  
|<span data-ttu-id="d77c4-128">-event \<eventname></span><span class="sxs-lookup"><span data-stu-id="d77c4-128">-event \<eventname></span></span>|<span data-ttu-id="d77c4-129">Откройте событие с этим именем и задаст его при инициализации PresentationHost. exe и готовности к размещению содержимого WPF.</span><span class="sxs-lookup"><span data-stu-id="d77c4-129">Open the event with this name and signal it when PresentationHost.exe is initialized and ready to host WPF content.</span></span> <span data-ttu-id="d77c4-130">Работа PresentationHost.exe будет прервана в случае ошибки при открытии события, например, если оно еще не создано.</span><span class="sxs-lookup"><span data-stu-id="d77c4-130">PresentationHost.exe will terminate if there was an error opening the event, such as if it has not already been created.</span></span>|  
|<span data-ttu-id="d77c4-131">-launchApplication \<url></span><span class="sxs-lookup"><span data-stu-id="d77c4-131">-launchApplication \<url></span></span>|<span data-ttu-id="d77c4-132">Запускает автономное приложение ClickOnce по указанному URL-адресу.</span><span class="sxs-lookup"><span data-stu-id="d77c4-132">Launches a standalone ClickOnce application from the specified URL.</span></span> <span data-ttu-id="d77c4-133">Применяются политики безопасности Internet Explorer и WinINet в отношении приложений .NET.</span><span class="sxs-lookup"><span data-stu-id="d77c4-133">Internet Explorer and WinINet security policy concerning .NET applications are applied.</span></span>|  
  
## <a name="scenarios"></a><span data-ttu-id="d77c4-134">Сценарии</span><span class="sxs-lookup"><span data-stu-id="d77c4-134">Scenarios</span></span>  
  
### <a name="shell-handler"></a><span data-ttu-id="d77c4-135">Обработчик оболочки</span><span class="sxs-lookup"><span data-stu-id="d77c4-135">Shell Handler</span></span>  
 `PresentationHost.exe example.xbap`  
  
### <a name="mime-handler"></a><span data-ttu-id="d77c4-136">Обработчик MIME</span><span class="sxs-lookup"><span data-stu-id="d77c4-136">MIME Handler</span></span>  
 `PresentationHost.exe -embedding example.xbap`  
  
### <a name="visual-studio-debugging"></a><span data-ttu-id="d77c4-137">Отладка в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d77c4-137">Visual Studio Debugging</span></span>  
 `PresentationHost.exe -debug example.xbap`  
  
### <a name="visual-studio-debugging-in-zone"></a><span data-ttu-id="d77c4-138">Visual Studio, отладка в зоне</span><span class="sxs-lookup"><span data-stu-id="d77c4-138">Visual Studio Debugging In Zone</span></span>  
 `PresentationHost.exe -debug -debugSecurityZoneURL http://www.example.com c:\folderpath\example.xbap`  
  
## <a name="see-also"></a><span data-ttu-id="d77c4-139">См. также:</span><span class="sxs-lookup"><span data-stu-id="d77c4-139">See also</span></span>

- [<span data-ttu-id="d77c4-140">Security</span><span class="sxs-lookup"><span data-stu-id="d77c4-140">Security</span></span>](../security-wpf.md)
