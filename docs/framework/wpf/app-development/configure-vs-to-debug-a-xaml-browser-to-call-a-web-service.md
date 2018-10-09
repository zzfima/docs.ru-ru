---
title: Настройка Visual Studio для отладки приложения браузера XAML для вызова веб-службы
ms.date: 03/30/2017
helpviewer_keywords:
- debugging XBAPs that call a Web service [WPF]
- debugging security exceptions for XBAPs [WPF]
- security exception for XBAPs [WPF], debugging
- configuring Visual Studio to debug XAML browser applications [WPF]
- configuring Visual Studio to debug XBAPs [WPF]
ms.assetid: fd1db082-a7bb-4c4b-9331-6ad74a0682d0
ms.openlocfilehash: 182ceb96385bdca74d1d5c20079f78fe589982cf
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/08/2018
ms.locfileid: "48873207"
---
# <a name="how-to-configure-visual-studio-to-debug-a-xaml-browser-application-to-call-a-web-service"></a><span data-ttu-id="79695-102">Настройка Visual Studio для отладки приложения браузера XAML для вызова веб-службы</span><span class="sxs-lookup"><span data-stu-id="79695-102">How to: Configure Visual Studio to Debug a XAML Browser Application to Call a Web Service</span></span>
[!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] <span data-ttu-id="79695-103">Запустите в изолированной среде безопасности частичного доверия, ограниченной набором разрешений зоны Интернета.</span><span class="sxs-lookup"><span data-stu-id="79695-103"> run within a partial-trust security sandbox that is restricted to the Internet zone set of permissions.</span></span> <span data-ttu-id="79695-104">Этот набор разрешений вызовы веб-службы для веб-служб, расположенных в [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] исходном узле приложения.</span><span class="sxs-lookup"><span data-stu-id="79695-104">This permission set restricts Web service calls to only Web services that are located at the [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] application's site of origin.</span></span> <span data-ttu-id="79695-105">Когда [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] отладке из Visual Studio 2005, однако не считается имеют тот же исходный узел веб-служба ссылки.</span><span class="sxs-lookup"><span data-stu-id="79695-105">When an [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] is debugged from Visual Studio 2005, though, it is not considered to have the same site of origin as the Web service it references.</span></span> <span data-ttu-id="79695-106">Исключения безопасности этой причины, вызываемого при [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] пытается вызвать веб-службы.</span><span class="sxs-lookup"><span data-stu-id="79695-106">This causes security exceptions to be raised when the [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] attempts to call the Web service.</span></span> <span data-ttu-id="79695-107">Тем не менее Visual Studio 2005 [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] проекта можно настроить для имитации того же исходного узла как веб-службу, он вызывает во время отладки.</span><span class="sxs-lookup"><span data-stu-id="79695-107">However, a Visual Studio 2005 [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] project can be configured to simulate having the same site of origin as the Web service it calls while debugging.</span></span> <span data-ttu-id="79695-108">Это позволяет [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] безопасно вызвать веб-службу, не вызывая исключения безопасности.</span><span class="sxs-lookup"><span data-stu-id="79695-108">This allows the [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] to safely call the Web service without causing security exceptions.</span></span>

## <a name="configuring-visual-studio"></a><span data-ttu-id="79695-109">Настройка Visual Studio</span><span class="sxs-lookup"><span data-stu-id="79695-109">Configuring Visual Studio</span></span>
 <span data-ttu-id="79695-110">Чтобы настроить Visual Studio 2005 для отладки [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] , вызывает веб-службы:</span><span class="sxs-lookup"><span data-stu-id="79695-110">To configure Visual Studio 2005 to debug an [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] that calls a Web service:</span></span>

1.  <span data-ttu-id="79695-111">Выберите проект в **обозревателе решений**, а затем в меню **Проект** щелкните **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="79695-111">With a project selected in **Solution Explorer**, on the **Project** menu, click **Properties**.</span></span>

2.  <span data-ttu-id="79695-112">В **конструктор проектов**, нажмите кнопку **Отладка** вкладки.</span><span class="sxs-lookup"><span data-stu-id="79695-112">In the **Project Designer**, click the **Debug** tab.</span></span>

3.  <span data-ttu-id="79695-113">В **действие при запуске** выберите **запуск внешней программы** и введите следующее:</span><span class="sxs-lookup"><span data-stu-id="79695-113">In the **Start Action** section, select **Start external program** and enter the following:</span></span>

     `C:\WINDOWS\System32\PresentationHost.exe`

4.  <span data-ttu-id="79695-114">В **параметры запуска** введите следующий текст в **аргументы командной строки** текстового поля:</span><span class="sxs-lookup"><span data-stu-id="79695-114">In the **Start Options** section, enter the following into the **Command line arguments** text box:</span></span>

     <span data-ttu-id="79695-115">`-debug`  *Имя файла*</span><span class="sxs-lookup"><span data-stu-id="79695-115">`-debug`  *filename*</span></span>

     <span data-ttu-id="79695-116">*Filename* значение **-Отладка** параметр является XBAP-файла, например:</span><span class="sxs-lookup"><span data-stu-id="79695-116">The *filename* value for the **-debug** parameter is the .xbap filename; for example:</span></span>

     `-debug c:\example.xbap`

> [!NOTE]
>  <span data-ttu-id="79695-117">Это конфигурация по умолчанию для решений, созданных с помощью Visual Studio 2005 [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] шаблона проекта.</span><span class="sxs-lookup"><span data-stu-id="79695-117">This is the default configuration for solutions that are created with the Visual Studio 2005 [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] project template.</span></span>

1.  <span data-ttu-id="79695-118">Выберите проект в **обозревателе решений**, а затем в меню **Проект** щелкните **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="79695-118">With a project selected in **Solution Explorer**, on the **Project** menu, click **Properties**.</span></span>

2.  <span data-ttu-id="79695-119">В **конструктор проектов**, нажмите кнопку **Отладка** вкладки.</span><span class="sxs-lookup"><span data-stu-id="79695-119">In the **Project Designer**, click the **Debug** tab.</span></span>

3.  <span data-ttu-id="79695-120">В **параметры запуска** разделе, добавьте следующий параметр командной строки для **аргументы командной строки** текстового поля:</span><span class="sxs-lookup"><span data-stu-id="79695-120">In the **Start Options** section, add the following command-line parameter to the **Command line arguments** text box:</span></span>

     <span data-ttu-id="79695-121">`-debugSecurityZoneURL`  *URL*</span><span class="sxs-lookup"><span data-stu-id="79695-121">`-debugSecurityZoneURL`  *URL*</span></span>

     <span data-ttu-id="79695-122">*URL-адрес* значение **- debugSecurityZoneURL** параметр [!INCLUDE[TLA#tla_url](../../../../includes/tlasharptla-url-md.md)] расположения, которое требуется имитировать как узлу вашего приложения.</span><span class="sxs-lookup"><span data-stu-id="79695-122">The *URL* value for the **-debugSecurityZoneURL** parameter is the [!INCLUDE[TLA#tla_url](../../../../includes/tlasharptla-url-md.md)] for the location that you want to simulate as being the site of origin of your application.</span></span>

 <span data-ttu-id="79695-123">Например, рассмотрим [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] , использует веб-службы со следующими [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="79695-123">As an example, consider a [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] that uses a Web service with the following [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)]:</span></span>

 `http://services.msdn.microsoft.com/ContentServices/ContentService.asmx`

 <span data-ttu-id="79695-124">Исходный узел [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] для этого веб-служба является:</span><span class="sxs-lookup"><span data-stu-id="79695-124">The site of origin [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] for this Web service is:</span></span>

 `http://services.msdn.microsoft.com`

 <span data-ttu-id="79695-125">Следовательно, полный **- debugSecurityZoneURL** параметра командной строки и значением является:</span><span class="sxs-lookup"><span data-stu-id="79695-125">Consequently, the complete **-debugSecurityZoneURL** command-line parameter and value is:</span></span>

 `-debugSecurityZoneURL http://services.msdn.microsoft.com`

## <a name="see-also"></a><span data-ttu-id="79695-126">См. также</span><span class="sxs-lookup"><span data-stu-id="79695-126">See Also</span></span>
 [<span data-ttu-id="79695-127">Основное приложение WPF (PresentationHost.exe)</span><span class="sxs-lookup"><span data-stu-id="79695-127">WPF Host (PresentationHost.exe)</span></span>](../../../../docs/framework/wpf/app-development/wpf-host-presentationhost-exe.md)
