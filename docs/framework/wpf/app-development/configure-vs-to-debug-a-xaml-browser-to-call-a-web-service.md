---
title: Практическое руководство. Настройка Visual Studio 2005 для отладки приложений браузера XAML для вызова веб-службы
ms.date: 03/30/2017
helpviewer_keywords:
- debugging XBAPs that call a Web service [WPF]
- debugging security exceptions for XBAPs [WPF]
- security exception for XBAPs [WPF], debugging
- configuring Visual Studio to debug XAML browser applications [WPF]
- configuring Visual Studio to debug XBAPs [WPF]
ms.assetid: fd1db082-a7bb-4c4b-9331-6ad74a0682d0
ms.openlocfilehash: 8ec278f2bc66d9b40786123af684f6468b6a9d83
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005670"
---
# <a name="how-to-configure-visual-studio-to-debug-a-xaml-browser-application-to-call-a-web-service"></a><span data-ttu-id="0c017-102">Практическое руководство. Настройка Visual Studio 2005 для отладки приложений браузера XAML для вызова веб-службы</span><span class="sxs-lookup"><span data-stu-id="0c017-102">How to: Configure Visual Studio to Debug a XAML Browser Application to Call a Web Service</span></span>
[!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] <span data-ttu-id="0c017-103">выполняется в песочнице безопасности с частичным доверием, которая ограничена набором разрешений зоны Интернета.</span><span class="sxs-lookup"><span data-stu-id="0c017-103">run within a partial-trust security sandbox that is restricted to the Internet zone set of permissions.</span></span> <span data-ttu-id="0c017-104">Этот набор разрешений разрешает вызовы веб-службы только для веб-служб, расположенных на исходном узле приложения [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0c017-104">This permission set restricts Web service calls to only Web services that are located at the [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] application's site of origin.</span></span> <span data-ttu-id="0c017-105">Однако при отладке [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] из Visual Studio 2005 не считается, что исходный сайт совпадает с веб-службой, на которую он ссылается.</span><span class="sxs-lookup"><span data-stu-id="0c017-105">When an [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] is debugged from Visual Studio 2005, though, it is not considered to have the same site of origin as the Web service it references.</span></span> <span data-ttu-id="0c017-106">Это приводит к возникновению исключений безопасности, когда [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] пытается вызвать веб-службу.</span><span class="sxs-lookup"><span data-stu-id="0c017-106">This causes security exceptions to be raised when the [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] attempts to call the Web service.</span></span> <span data-ttu-id="0c017-107">Однако проект Visual Studio 2005 [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] можно настроить для имитации того же узла происхождения, что и веб-служба, которую он вызывает во время отладки.</span><span class="sxs-lookup"><span data-stu-id="0c017-107">However, a Visual Studio 2005 [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] project can be configured to simulate having the same site of origin as the Web service it calls while debugging.</span></span> <span data-ttu-id="0c017-108">Это позволяет [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] безопасно вызывать веб-службу, не вызывая исключений безопасности.</span><span class="sxs-lookup"><span data-stu-id="0c017-108">This allows the [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] to safely call the Web service without causing security exceptions.</span></span>

## <a name="configuring-visual-studio"></a><span data-ttu-id="0c017-109">Настройка Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0c017-109">Configuring Visual Studio</span></span>
 <span data-ttu-id="0c017-110">Чтобы настроить Visual Studio 2005 для отладки [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)], который вызывает веб-службу, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="0c017-110">To configure Visual Studio 2005 to debug an [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] that calls a Web service:</span></span>

1. <span data-ttu-id="0c017-111">Выберите проект в **обозревателе решений**, а затем в меню **Проект** щелкните **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="0c017-111">With a project selected in **Solution Explorer**, on the **Project** menu, click **Properties**.</span></span>

2. <span data-ttu-id="0c017-112">В **конструкторе проектов**перейдите на вкладку **Отладка** .</span><span class="sxs-lookup"><span data-stu-id="0c017-112">In the **Project Designer**, click the **Debug** tab.</span></span>

3. <span data-ttu-id="0c017-113">В разделе **действие при запуске** выберите **Запуск внешней программы** и введите следующее:</span><span class="sxs-lookup"><span data-stu-id="0c017-113">In the **Start Action** section, select **Start external program** and enter the following:</span></span>

     `C:\WINDOWS\System32\PresentationHost.exe`

4. <span data-ttu-id="0c017-114">В разделе **Параметры запуска** введите следующий текст в текстовое поле **аргументы командной строки** :</span><span class="sxs-lookup"><span data-stu-id="0c017-114">In the **Start Options** section, enter the following into the **Command line arguments** text box:</span></span>

     <span data-ttu-id="0c017-115">`-debug`  *имя_файла*</span><span class="sxs-lookup"><span data-stu-id="0c017-115">`-debug`  *filename*</span></span>

     <span data-ttu-id="0c017-116">Значение *filename* для параметра **-Debug** — имя файла XBAP; Например:</span><span class="sxs-lookup"><span data-stu-id="0c017-116">The *filename* value for the **-debug** parameter is the .xbap filename; for example:</span></span>

     `-debug c:\example.xbap`

> [!NOTE]
> <span data-ttu-id="0c017-117">Это конфигурация по умолчанию для решений, созданных с помощью шаблона проекта Visual Studio 2005 [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0c017-117">This is the default configuration for solutions that are created with the Visual Studio 2005 [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] project template.</span></span>

1. <span data-ttu-id="0c017-118">Выберите проект в **обозревателе решений**, а затем в меню **Проект** щелкните **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="0c017-118">With a project selected in **Solution Explorer**, on the **Project** menu, click **Properties**.</span></span>

2. <span data-ttu-id="0c017-119">В **конструкторе проектов**перейдите на вкладку **Отладка** .</span><span class="sxs-lookup"><span data-stu-id="0c017-119">In the **Project Designer**, click the **Debug** tab.</span></span>

3. <span data-ttu-id="0c017-120">В разделе **Параметры запуска** добавьте следующий параметр командной строки в текстовое поле **аргументы командной строки** :</span><span class="sxs-lookup"><span data-stu-id="0c017-120">In the **Start Options** section, add the following command-line parameter to the **Command line arguments** text box:</span></span>

     <span data-ttu-id="0c017-121">`-debugSecurityZoneURL`  *URL*</span><span class="sxs-lookup"><span data-stu-id="0c017-121">`-debugSecurityZoneURL`  *URL*</span></span>

     <span data-ttu-id="0c017-122">*URL-адрес* для параметра **-дебугсекуритизонеурл** — это [!INCLUDE[TLA#tla_url](../../../../includes/tlasharptla-url-md.md)] для расположения, которое нужно имитировать как исходный сайт приложения.</span><span class="sxs-lookup"><span data-stu-id="0c017-122">The *URL* value for the **-debugSecurityZoneURL** parameter is the [!INCLUDE[TLA#tla_url](../../../../includes/tlasharptla-url-md.md)] for the location that you want to simulate as being the site of origin of your application.</span></span>

 <span data-ttu-id="0c017-123">В качестве примера рассмотрим [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)], который использует веб-службу со следующим URL-адресом:</span><span class="sxs-lookup"><span data-stu-id="0c017-123">As an example, consider a [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] that uses a Web service with the following URL:</span></span>

 `http://services.msdn.microsoft.com/ContentServices/ContentService.asmx`

 <span data-ttu-id="0c017-124">URL-адрес исходного узла для этой веб-службы:</span><span class="sxs-lookup"><span data-stu-id="0c017-124">The site of origin URL for this Web service is:</span></span>

 `http://services.msdn.microsoft.com`

 <span data-ttu-id="0c017-125">Следовательно, параметр и значение командной строки Complete **-дебугсекуритизонеурл** :</span><span class="sxs-lookup"><span data-stu-id="0c017-125">Consequently, the complete **-debugSecurityZoneURL** command-line parameter and value is:</span></span>

 `-debugSecurityZoneURL http://services.msdn.microsoft.com`

## <a name="see-also"></a><span data-ttu-id="0c017-126">См. также</span><span class="sxs-lookup"><span data-stu-id="0c017-126">See also</span></span>

- [<span data-ttu-id="0c017-127">Основное приложение WPF (PresentationHost.exe)</span><span class="sxs-lookup"><span data-stu-id="0c017-127">WPF Host (PresentationHost.exe)</span></span>](wpf-host-presentationhost-exe.md)
