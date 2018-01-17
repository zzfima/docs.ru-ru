---
title: "Разработка клиентских приложений с использованием .NET Framework"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- client application services
- applications [Windows Forms]
- Windows Presentation Foundation, in Visual Studio
- WPF, in Visual Studio
- Windows applications
- rich client applications
- .NET applications, Windows applications
- Visual Basic code, creating applications
- Visual C#, creating applications
- client/server applications, Windows applications
ms.assetid: 2dfb50b7-5af2-4e12-9bbb-c5ade0e39a68
caps.latest.revision: "24"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1f90cbac0e7f78d8965a75df281c0db6b213d9e4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="developing-client-applications-with-the-net-framework"></a><span data-ttu-id="5d5db-102">Разработка клиентских приложений с использованием .NET Framework</span><span class="sxs-lookup"><span data-stu-id="5d5db-102">Developing Client Applications with the .NET Framework</span></span>
<span data-ttu-id="5d5db-103">Существует несколько способов разработки приложений Windows с помощью платформы .NET Framework, которые будут выполняться на пользовательских компьютерах и устройствах.</span><span class="sxs-lookup"><span data-stu-id="5d5db-103">There are multiple ways to develop Windows-based applications with the .NET framework that run locally on users' computers or devices.</span></span> <span data-ttu-id="5d5db-104">В этом разделе поясняются способы создания приложений Windows с помощью Windows Presentation Foundation (WPF) и Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="5d5db-104">This section contains topics that describe how to create Windows-based applications by using Windows Presentation Foundation (WPF) or by using Windows Forms.</span></span> <span data-ttu-id="5d5db-105">Однако с помощью .NET Framework вы можете создавать и веб-приложения, а также клиентские приложения для компьютеров и устройств, которые можно предоставлять пользователям через Магазин Windows и Магазин Windows Phone.</span><span class="sxs-lookup"><span data-stu-id="5d5db-105">However, you can also create web applications using the .NET Framework, and client applications for computers or devices that you make available through the Windows Store or Windows Phone Store.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5d5db-106">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="5d5db-106">In This Section</span></span>  
 [<span data-ttu-id="5d5db-107">Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="5d5db-107">Windows Presentation Foundation</span></span>](../../docs/framework/wpf/index.md)  
 <span data-ttu-id="5d5db-108">Сведения о разработке приложений с помощью WPF.</span><span class="sxs-lookup"><span data-stu-id="5d5db-108">Provides information about developing applications by using WPF.</span></span>  
  
 [<span data-ttu-id="5d5db-109">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5d5db-109">Windows Forms</span></span>](../../docs/framework/winforms/index.md)  
 <span data-ttu-id="5d5db-110">Сведения о разработке приложений с помощью Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="5d5db-110">Provides information about developing applications by using Windows Forms.</span></span>  
  
 [<span data-ttu-id="5d5db-111">Общие клиентские технологии</span><span class="sxs-lookup"><span data-stu-id="5d5db-111">Common Client Technologies</span></span>](../../docs/framework/common-client-technologies/index.md)  
 <span data-ttu-id="5d5db-112">Сведения о дополнительных технологиях, которые можно использовать при разработке клиентских приложений.</span><span class="sxs-lookup"><span data-stu-id="5d5db-112">Provides information about additional technologies that can be used when developing client applications.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="5d5db-113">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="5d5db-113">Related Sections</span></span>  
 [<span data-ttu-id="5d5db-114">Приложения для Магазина Windows</span><span class="sxs-lookup"><span data-stu-id="5d5db-114">Windows Store apps</span></span>](http://msdn.microsoft.com/windows/apps/)  
 <span data-ttu-id="5d5db-115">Создание приложений для предоставления пользователям через Магазин Windows</span><span class="sxs-lookup"><span data-stu-id="5d5db-115">Describes how to create apps that you can make available to users through the Windows Store</span></span>  
  
 [<span data-ttu-id="5d5db-116">Приложения .NET для Магазина</span><span class="sxs-lookup"><span data-stu-id="5d5db-116">.NET for Store apps</span></span>](http://msdn.microsoft.com/library/windows/apps/br230302.aspx)  
 <span data-ttu-id="5d5db-117">Поддержка .NET Framework для приложений Магазина, которые можно развернуть на компьютерах и устройствах Windows.</span><span class="sxs-lookup"><span data-stu-id="5d5db-117">Describes the .NET Framework support for Store apps, which can be deployed to Windows computers and devices.</span></span>  
  
 <span data-ttu-id="5d5db-118">[.NET API для Windows Phone Silverlight](http://msdn.microsoft.com/library/windows/apps/xaml/jj207211\(v=vs.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="5d5db-118">[.NET API for Windows Phone Silverlight](http://msdn.microsoft.com/library/windows/apps/xaml/jj207211\(v=vs.105\).aspx)</span></span>  
 <span data-ttu-id="5d5db-119">Список API .NET Framework, которые можно использовать для создания приложений с помощью Windows Phone Silverlight</span><span class="sxs-lookup"><span data-stu-id="5d5db-119">List the .NET Framework APIs you can use for building apps with Windows Phone Silverlight</span></span>  
  
 [<span data-ttu-id="5d5db-120">Разработка для нескольких платформ</span><span class="sxs-lookup"><span data-stu-id="5d5db-120">Developing for Multiple Platforms</span></span>](../../docs/standard/cross-platform/index.md)  
 <span data-ttu-id="5d5db-121">Описание методов, которыми можно использовать .NET Framework для разных типов клиентских приложений.</span><span class="sxs-lookup"><span data-stu-id="5d5db-121">Describes the different methods you can use the .NET Framework to target multiple client app types.</span></span>  
  
 [<span data-ttu-id="5d5db-122">Начало работы с веб-страницами ASP.NET</span><span class="sxs-lookup"><span data-stu-id="5d5db-122">Get Started with ASP.NET Web Sites</span></span>](http://www.asp.net/get-started/websites)  
 <span data-ttu-id="5d5db-123">Способы разработки веб-приложений с помощью ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="5d5db-123">Describes the ways you can develop web apps using ASP.NET.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d5db-124">См. также</span><span class="sxs-lookup"><span data-stu-id="5d5db-124">See Also</span></span>  
 [<span data-ttu-id="5d5db-125">Переносимая библиотека классов</span><span class="sxs-lookup"><span data-stu-id="5d5db-125">Portable Class Library</span></span>](../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md)  
 [<span data-ttu-id="5d5db-126">Обзор набора средств Visual Studio для Unity</span><span class="sxs-lookup"><span data-stu-id="5d5db-126">Overview</span></span>](../../docs/framework/get-started/overview.md)  
 [<span data-ttu-id="5d5db-127">Руководство по разработке</span><span class="sxs-lookup"><span data-stu-id="5d5db-127">Development Guide</span></span>](../../docs/framework/development-guide.md)  
 [<span data-ttu-id="5d5db-128">Практическое руководство. Создание классического приложения Windows</span><span class="sxs-lookup"><span data-stu-id="5d5db-128">How to: Create a Windows Desktop Application</span></span>](http://msdn.microsoft.com/library/47021403-eaca-4c34-946a-a26c42a64148)  
 [<span data-ttu-id="5d5db-129">Приложения служб Windows</span><span class="sxs-lookup"><span data-stu-id="5d5db-129">Windows Service Applications</span></span>](../../docs/framework/windows-services/index.md)
