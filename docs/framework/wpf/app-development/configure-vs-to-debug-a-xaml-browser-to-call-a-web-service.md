---
title: "Настройка Visual Studio для отладки приложения браузера XAML для вызова веб-службы"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging XBAPs that call a Web service [WPF]
- debugging security exceptions for XBAPs [WPF]
- security exception for XBAPs [WPF], debugging
- configuring Visual Studio to debug XAML browser applications [WPF]
- configuring Visual Studio to debug XBAPs [WPF]
ms.assetid: fd1db082-a7bb-4c4b-9331-6ad74a0682d0
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5db89cf6220f086d2d71b99f3e6440e584d6a5d7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-configure-visual-studio-to-debug-a-xaml-browser-application-to-call-a-web-service"></a><span data-ttu-id="29555-102">Настройка Visual Studio для отладки приложения браузера XAML для вызова веб-службы</span><span class="sxs-lookup"><span data-stu-id="29555-102">How to: Configure Visual Studio to Debug a XAML Browser Application to Call a Web Service</span></span>
[!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)]<span data-ttu-id="29555-103">Запустите в изолированной среде безопасности частичного доверия, которая ограничена набором разрешений зоны Интернета.</span><span class="sxs-lookup"><span data-stu-id="29555-103"> run within a partial-trust security sandbox that is restricted to the Internet zone set of permissions.</span></span> <span data-ttu-id="29555-104">Этот набор разрешений вызовы веб-службы для веб-служб, которые можно найти в папке [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] исходного узла приложения.</span><span class="sxs-lookup"><span data-stu-id="29555-104">This permission set restricts Web service calls to only Web services that are located at the [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] application's site of origin.</span></span> <span data-ttu-id="29555-105">Когда [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] отладке из [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)], хотя не считается имеют тот же исходный узел веб-служба ссылки.</span><span class="sxs-lookup"><span data-stu-id="29555-105">When an [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] is debugged from [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)], though, it is not considered to have the same site of origin as the Web service it references.</span></span> <span data-ttu-id="29555-106">Это причины исключения системы безопасности, вызываемого при [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] пытается вызвать веб-службы.</span><span class="sxs-lookup"><span data-stu-id="29555-106">This causes security exceptions to be raised when the [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] attempts to call the Web service.</span></span> <span data-ttu-id="29555-107">Тем не менее [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)] [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] проекта можно настроить для имитации того же исходный узел веб-служба вызывается во время отладки.</span><span class="sxs-lookup"><span data-stu-id="29555-107">However, a [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)] [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] project can be configured to simulate having the same site of origin as the Web service it calls while debugging.</span></span> <span data-ttu-id="29555-108">Это позволяет [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] безопасно вызвать веб-службу, не вызывая исключения безопасности.</span><span class="sxs-lookup"><span data-stu-id="29555-108">This allows the [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] to safely call the Web service without causing security exceptions.</span></span>  
  
## <a name="configuring-visual-studio"></a><span data-ttu-id="29555-109">Настройка Visual Studio</span><span class="sxs-lookup"><span data-stu-id="29555-109">Configuring Visual Studio</span></span>  
 <span data-ttu-id="29555-110">Чтобы настроить [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)] для отладки [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] , которая вызывает веб-службы:</span><span class="sxs-lookup"><span data-stu-id="29555-110">To configure [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)] to debug an [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] that calls a Web service:</span></span>  
  
1.  <span data-ttu-id="29555-111">Выберите проект в **обозревателе решений**, а затем в меню **Проект** щелкните **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="29555-111">With a project selected in **Solution Explorer**, on the **Project** menu, click **Properties**.</span></span>  
  
2.  <span data-ttu-id="29555-112">В **конструктора проектов**, нажмите кнопку **отладки** вкладки.</span><span class="sxs-lookup"><span data-stu-id="29555-112">In the **Project Designer**, click the **Debug** tab.</span></span>  
  
3.  <span data-ttu-id="29555-113">В **действие при запуске** выберите **запуск внешней программы** и введите следующее:</span><span class="sxs-lookup"><span data-stu-id="29555-113">In the **Start Action** section, select **Start external program** and enter the following:</span></span>  
  
     `C:\WINDOWS\System32\PresentationHost.exe`  
  
4.  <span data-ttu-id="29555-114">В **параметры запуска** введите следующий текст в **аргументы командной строки** текстовое поле:</span><span class="sxs-lookup"><span data-stu-id="29555-114">In the **Start Options** section, enter the following into the **Command line arguments** text box:</span></span>  
  
     <span data-ttu-id="29555-115">`-debug`  *Имя файла*</span><span class="sxs-lookup"><span data-stu-id="29555-115">`-debug`  *filename*</span></span>  
  
     <span data-ttu-id="29555-116">*Filename* значение для **-Отладка** параметр является XBAP-файла, например:</span><span class="sxs-lookup"><span data-stu-id="29555-116">The *filename* value for the **-debug** parameter is the .xbap filename; for example:</span></span>  
  
     `-debug c:\example.xbap`  
  
> [!NOTE]
>  <span data-ttu-id="29555-117">Это конфигурация по умолчанию для решений, созданных с помощью [!INCLUDE[TLA2#tla_visualstu2005](../../../../includes/tla2sharptla-visualstu2005-md.md)] [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] шаблона проекта.</span><span class="sxs-lookup"><span data-stu-id="29555-117">This is the default configuration for solutions that are created with the [!INCLUDE[TLA2#tla_visualstu2005](../../../../includes/tla2sharptla-visualstu2005-md.md)] [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] project template.</span></span>  
  
1.  <span data-ttu-id="29555-118">Выберите проект в **обозревателе решений**, а затем в меню **Проект** щелкните **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="29555-118">With a project selected in **Solution Explorer**, on the **Project** menu, click **Properties**.</span></span>  
  
2.  <span data-ttu-id="29555-119">В **конструктора проектов**, нажмите кнопку **отладки** вкладки.</span><span class="sxs-lookup"><span data-stu-id="29555-119">In the **Project Designer**, click the **Debug** tab.</span></span>  
  
3.  <span data-ttu-id="29555-120">В **параметры запуска** добавьте следующий параметр командной строки для **аргументы командной строки** текстовое поле:</span><span class="sxs-lookup"><span data-stu-id="29555-120">In the **Start Options** section, add the following command-line parameter to the **Command line arguments** text box:</span></span>  
  
     <span data-ttu-id="29555-121">`-debugSecurityZoneURL`  *URL*</span><span class="sxs-lookup"><span data-stu-id="29555-121">`-debugSecurityZoneURL`  *URL*</span></span>  
  
     <span data-ttu-id="29555-122">*URL-адрес* значение для **- debugSecurityZoneURL** параметр [!INCLUDE[TLA#tla_url](../../../../includes/tlasharptla-url-md.md)] для расположения, которое требуется имитировать как узлу приложения.</span><span class="sxs-lookup"><span data-stu-id="29555-122">The *URL* value for the **-debugSecurityZoneURL** parameter is the [!INCLUDE[TLA#tla_url](../../../../includes/tlasharptla-url-md.md)] for the location that you want to simulate as being the site of origin of your application.</span></span>  
  
 <span data-ttu-id="29555-123">Например, рассмотрим [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] , использует веб-службы со следующими [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="29555-123">As an example, consider a [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] that uses a Web service with the following [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)]:</span></span>  
  
 `http://services.msdn.microsoft.com/ContentServices/ContentService.asmx`  
  
 <span data-ttu-id="29555-124">Исходный узел [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] для этого веб-служба является:</span><span class="sxs-lookup"><span data-stu-id="29555-124">The site of origin [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] for this Web service is:</span></span>  
  
 `http://services.msdn.microsoft.com`  
  
 <span data-ttu-id="29555-125">Следовательно, полный **- debugSecurityZoneURL** параметр командной строки и значением является:</span><span class="sxs-lookup"><span data-stu-id="29555-125">Consequently, the complete **-debugSecurityZoneURL** command-line parameter and value is:</span></span>  
  
 `-debugSecurityZoneURL http://services.msdn.microsoft.com`  
  
## <a name="see-also"></a><span data-ttu-id="29555-126">См. также</span><span class="sxs-lookup"><span data-stu-id="29555-126">See Also</span></span>  
 [<span data-ttu-id="29555-127">Основное приложение WPF (PresentationHost.exe)</span><span class="sxs-lookup"><span data-stu-id="29555-127">WPF Host (PresentationHost.exe)</span></span>](../../../../docs/framework/wpf/app-development/wpf-host-presentationhost-exe.md)
