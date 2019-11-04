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
ms.openlocfilehash: d8cfae2fb47876d578c51e5f4acdfe0c31e752fe
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460904"
---
# <a name="how-to-configure-visual-studio-to-debug-a-xaml-browser-application-to-call-a-web-service"></a><span data-ttu-id="7de3a-102">Настройка Visual Studio для отладки приложения браузера XAML для вызова веб-службы</span><span class="sxs-lookup"><span data-stu-id="7de3a-102">How to: Configure Visual Studio to Debug a XAML Browser Application to Call a Web Service</span></span>
<span data-ttu-id="7de3a-103">Приложения браузера XAML (XBAP) выполняются в изолированной среде безопасности с частичным доверием, которая ограничена набором разрешений зоны Интернета.</span><span class="sxs-lookup"><span data-stu-id="7de3a-103">XAML browser applications (XBAPs) run within a partial-trust security sandbox that is restricted to the Internet zone set of permissions.</span></span> <span data-ttu-id="7de3a-104">Этот набор разрешений разрешает вызовы веб-службы только для веб-служб, расположенных на исходном узле приложения XBAP.</span><span class="sxs-lookup"><span data-stu-id="7de3a-104">This permission set restricts Web service calls to only Web services that are located at the XBAP application's site of origin.</span></span> <span data-ttu-id="7de3a-105">Однако при отладке XBAP из Visual Studio 2005 не считается, что исходный сайт совпадает с веб-службой, на которую он ссылается.</span><span class="sxs-lookup"><span data-stu-id="7de3a-105">When an XBAP is debugged from Visual Studio 2005, though, it is not considered to have the same site of origin as the Web service it references.</span></span> <span data-ttu-id="7de3a-106">Это приводит к возникновению исключений безопасности, когда XBAP пытается вызвать веб-службу.</span><span class="sxs-lookup"><span data-stu-id="7de3a-106">This causes security exceptions to be raised when the XBAP attempts to call the Web service.</span></span> <span data-ttu-id="7de3a-107">Однако проект приложения браузера XAML Visual Studio 2005 можно настроить для имитации того же узла происхождения, что и веб-служба, которую он вызывает во время отладки.</span><span class="sxs-lookup"><span data-stu-id="7de3a-107">However, a Visual Studio 2005 XAML Browser Application (WPF) project can be configured to simulate having the same site of origin as the Web service it calls while debugging.</span></span> <span data-ttu-id="7de3a-108">Это позволяет XBAP безопасно вызывать веб-службу, не вызывая исключений безопасности.</span><span class="sxs-lookup"><span data-stu-id="7de3a-108">This allows the XBAP to safely call the Web service without causing security exceptions.</span></span>

## <a name="configuring-visual-studio"></a><span data-ttu-id="7de3a-109">Настройка Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7de3a-109">Configuring Visual Studio</span></span>
 <span data-ttu-id="7de3a-110">Чтобы настроить Visual Studio 2005 для отладки XBAP, вызывающего веб-службу, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="7de3a-110">To configure Visual Studio 2005 to debug an XBAP that calls a Web service:</span></span>

1. <span data-ttu-id="7de3a-111">Выберите проект в **обозревателе решений**, а затем в меню **Проект** щелкните **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="7de3a-111">With a project selected in **Solution Explorer**, on the **Project** menu, click **Properties**.</span></span>

2. <span data-ttu-id="7de3a-112">В **конструкторе проектов**перейдите на вкладку **Отладка** .</span><span class="sxs-lookup"><span data-stu-id="7de3a-112">In the **Project Designer**, click the **Debug** tab.</span></span>

3. <span data-ttu-id="7de3a-113">В разделе **действие при запуске** выберите **Запуск внешней программы** и введите следующее:</span><span class="sxs-lookup"><span data-stu-id="7de3a-113">In the **Start Action** section, select **Start external program** and enter the following:</span></span>

     `C:\WINDOWS\System32\PresentationHost.exe`

4. <span data-ttu-id="7de3a-114">В разделе **Параметры запуска** введите следующий текст в текстовое поле **аргументы командной строки** :</span><span class="sxs-lookup"><span data-stu-id="7de3a-114">In the **Start Options** section, enter the following into the **Command line arguments** text box:</span></span>

     <span data-ttu-id="7de3a-115">`-debug`  *имя_файла*</span><span class="sxs-lookup"><span data-stu-id="7de3a-115">`-debug`  *filename*</span></span>

     <span data-ttu-id="7de3a-116">Значение *filename* для параметра **-Debug** — имя файла XBAP; Например:</span><span class="sxs-lookup"><span data-stu-id="7de3a-116">The *filename* value for the **-debug** parameter is the .xbap filename; for example:</span></span>

     `-debug c:\example.xbap`

> [!NOTE]
> <span data-ttu-id="7de3a-117">Это конфигурация по умолчанию для решений, созданных с помощью шаблона проекта приложения браузера XAML Visual Studio 2005 (WPF).</span><span class="sxs-lookup"><span data-stu-id="7de3a-117">This is the default configuration for solutions that are created with the Visual Studio 2005 XAML Browser Application (WPF) project template.</span></span>

1. <span data-ttu-id="7de3a-118">Выберите проект в **обозревателе решений**, а затем в меню **Проект** щелкните **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="7de3a-118">With a project selected in **Solution Explorer**, on the **Project** menu, click **Properties**.</span></span>

2. <span data-ttu-id="7de3a-119">В **конструкторе проектов**перейдите на вкладку **Отладка** .</span><span class="sxs-lookup"><span data-stu-id="7de3a-119">In the **Project Designer**, click the **Debug** tab.</span></span>

3. <span data-ttu-id="7de3a-120">В разделе **Параметры запуска** добавьте следующий параметр командной строки в текстовое поле **аргументы командной строки** :</span><span class="sxs-lookup"><span data-stu-id="7de3a-120">In the **Start Options** section, add the following command-line parameter to the **Command line arguments** text box:</span></span>

     <span data-ttu-id="7de3a-121">`-debugSecurityZoneURL`  *URL*</span><span class="sxs-lookup"><span data-stu-id="7de3a-121">`-debugSecurityZoneURL`  *URL*</span></span>

     <span data-ttu-id="7de3a-122">*URL-адрес* параметра **-дебугсекуритизонеурл** — это URL-адрес расположения, которое вы хотите имитировать как исходный сайт приложения.</span><span class="sxs-lookup"><span data-stu-id="7de3a-122">The *URL* value for the **-debugSecurityZoneURL** parameter is the URL for the location that you want to simulate as being the site of origin of your application.</span></span>

 <span data-ttu-id="7de3a-123">В качестве примера рассмотрим приложение браузера XAML (XBAP), использующее веб-службу со следующим URL-адресом:</span><span class="sxs-lookup"><span data-stu-id="7de3a-123">As an example, consider a XAML browser application (XBAP) that uses a Web service with the following URL:</span></span>

 `http://services.msdn.microsoft.com/ContentServices/ContentService.asmx`

 <span data-ttu-id="7de3a-124">URL-адрес исходного узла для этой веб-службы:</span><span class="sxs-lookup"><span data-stu-id="7de3a-124">The site of origin URL for this Web service is:</span></span>

 `http://services.msdn.microsoft.com`

 <span data-ttu-id="7de3a-125">Следовательно, параметр и значение командной строки Complete **-дебугсекуритизонеурл** :</span><span class="sxs-lookup"><span data-stu-id="7de3a-125">Consequently, the complete **-debugSecurityZoneURL** command-line parameter and value is:</span></span>

 `-debugSecurityZoneURL http://services.msdn.microsoft.com`

## <a name="see-also"></a><span data-ttu-id="7de3a-126">См. также</span><span class="sxs-lookup"><span data-stu-id="7de3a-126">See also</span></span>

- [<span data-ttu-id="7de3a-127">Основное приложение WPF (PresentationHost.exe)</span><span class="sxs-lookup"><span data-stu-id="7de3a-127">WPF Host (PresentationHost.exe)</span></span>](wpf-host-presentationhost-exe.md)
