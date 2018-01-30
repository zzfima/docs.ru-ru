---
title: "Приступая к работе (WPF)"
ms.custom: 
ms.date: 01/26/2018
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- getting started [WPF]
- introduction [WPF]
- WPF [WPF], getting started
ms.assetid: 04f91da8-708c-46c7-8172-f1695ec847cd
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: eded6de5de269e7b49a87da31590267a5350f161
ms.sourcegitcommit: f28752eab00d2bd97e971542c0f49ce63cfbc239
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2018
---
# <a name="getting-started-wpf"></a><span data-ttu-id="22b34-102">Приступая к работе (WPF)</span><span class="sxs-lookup"><span data-stu-id="22b34-102">Getting Started (WPF)</span></span>
<span data-ttu-id="22b34-103">Windows Presentation Foundation (WPF) — это платформа пользовательского интерфейса для создания клиентских приложений для настольных систем.</span><span class="sxs-lookup"><span data-stu-id="22b34-103">Windows Presentation Foundation (WPF) is a UI framework that creates desktop client applications.</span></span> <span data-ttu-id="22b34-104">Платформа разработки WPF поддерживает широкий набор компонентов для разработки приложений, включая модель приложения, ресурсы, элементы управления, графику, макет, привязки данных, документы и безопасность.</span><span class="sxs-lookup"><span data-stu-id="22b34-104">The WPF development platform supports a broad set of application development features, including an application model, resources, controls, graphics, layout, data binding, documents, and security.</span></span> <span data-ttu-id="22b34-105">Она является частью платформы .NET Framework, и если ранее вы создавали приложения в .NET Framework с помощью ASP.NET или Windows Forms, то должны быть знакомы с принципами программирования.</span><span class="sxs-lookup"><span data-stu-id="22b34-105">It is a subset of the .NET Framework, so if you have previously built applications with the .NET Framework using ASP.NET or Windows Forms, the programming experience should be familiar.</span></span> <span data-ttu-id="22b34-106">WPF использует расширяемый язык разметки для приложений (XAML), чтобы предоставить декларативную модель для программирования приложений.</span><span class="sxs-lookup"><span data-stu-id="22b34-106">WPF uses the Extensible Application Markup Language (XAML) to provide a declarative model for application programming.</span></span> <span data-ttu-id="22b34-107">В этот раздел включены темы, содержащие вводные сведения и помогающие начать работу с WPF.</span><span class="sxs-lookup"><span data-stu-id="22b34-107">This section has topics that introduce and help you get started with WPF.</span></span>  
  
## <a name="where-should-i-start"></a><span data-ttu-id="22b34-108">Подготовка к изучению темы</span><span class="sxs-lookup"><span data-stu-id="22b34-108">Where Should I Start?</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="22b34-109">Необходимо перейти непосредственно к…</span><span class="sxs-lookup"><span data-stu-id="22b34-109">I want to jump right in…</span></span>|[<span data-ttu-id="22b34-110">Пошаговое руководство. Создание первого классического приложения WPF</span><span class="sxs-lookup"><span data-stu-id="22b34-110">Walkthrough: My first WPF desktop application</span></span>](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md)|  
|<span data-ttu-id="22b34-111">Как проектировать пользовательский интерфейс приложения?</span><span class="sxs-lookup"><span data-stu-id="22b34-111">How do I design the application UI?</span></span>|[<span data-ttu-id="22b34-112">Проектирование XAML в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="22b34-112">Designing XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)|  
|<span data-ttu-id="22b34-113">Не знакомы с .NET?</span><span class="sxs-lookup"><span data-stu-id="22b34-113">New to .NET?</span></span>|<span data-ttu-id="22b34-114">[Общие сведения о платформе .NET Framework](https://msdn.microsoft.com/library/zw4w595w\(v=vs.140\).aspx)</span><span class="sxs-lookup"><span data-stu-id="22b34-114">[Overview of the .NET Framework](https://msdn.microsoft.com/library/zw4w595w\(v=vs.140\).aspx)</span></span><br /><br /> [<span data-ttu-id="22b34-115">Основные сведения о приложениях .NET Framework</span><span class="sxs-lookup"><span data-stu-id="22b34-115">.NET Framework Application Essentials</span></span>](../../../../docs/standard/application-essentials.md)<br /><br /> <span data-ttu-id="22b34-116">[Начало работы с Visual C# и Visual Basic](https://msdn.microsoft.com/library/dd492171\(v=vs.140\).aspx)</span><span class="sxs-lookup"><span data-stu-id="22b34-116">[Getting Started with Visual C# and Visual Basic](https://msdn.microsoft.com/library/dd492171\(v=vs.140\).aspx)</span></span>|  
|<span data-ttu-id="22b34-117">Дополнительные сведения о WPF...</span><span class="sxs-lookup"><span data-stu-id="22b34-117">Tell me more about WPF…</span></span>|[<span data-ttu-id="22b34-118">Введение в WPF в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="22b34-118">Introduction to WPF in Visual Studio</span></span>](../../../../docs/framework/wpf/getting-started/introduction-to-wpf-in-vs.md)<br /><br /> [<span data-ttu-id="22b34-119">Общие сведения о языке XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="22b34-119">XAML Overview (WPF)</span></span>](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)<br /><br /> [<span data-ttu-id="22b34-120">Элементы управления</span><span class="sxs-lookup"><span data-stu-id="22b34-120">Controls</span></span>](../../../../docs/framework/wpf/controls/index.md)<br /><br /> [<span data-ttu-id="22b34-121">Общие сведения о привязке данных</span><span class="sxs-lookup"><span data-stu-id="22b34-121">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)|  
|<span data-ttu-id="22b34-122">Вы разработчик Windows Forms?</span><span class="sxs-lookup"><span data-stu-id="22b34-122">Are you a Windows Forms developer?</span></span>|[<span data-ttu-id="22b34-123">Элементы управления Windows Forms и эквивалентные элементы управления WPF</span><span class="sxs-lookup"><span data-stu-id="22b34-123">Windows Forms Controls and Equivalent WPF Controls</span></span>](../../../../docs/framework/wpf/advanced/windows-forms-controls-and-equivalent-wpf-controls.md)<br /><br /> [<span data-ttu-id="22b34-124">Взаимодействие WPF и Windows Forms</span><span class="sxs-lookup"><span data-stu-id="22b34-124">WPF and Windows Forms Interoperation</span></span>](../../../../docs/framework/wpf/advanced/wpf-and-windows-forms-interoperation.md)|  
  
## <a name="see-also"></a><span data-ttu-id="22b34-125">См. также</span><span class="sxs-lookup"><span data-stu-id="22b34-125">See Also</span></span>  
 [<span data-ttu-id="22b34-126">Библиотека классов</span><span class="sxs-lookup"><span data-stu-id="22b34-126">Class Library</span></span>](../../../../docs/framework/wpf/class-library-wpf.md)  
 [<span data-ttu-id="22b34-127">Разработка приложений</span><span class="sxs-lookup"><span data-stu-id="22b34-127">Application Development</span></span>](../../../../docs/framework/wpf/app-development/index.md)  
 [<span data-ttu-id="22b34-128">Центр разработчиков .NET Framework</span><span class="sxs-lookup"><span data-stu-id="22b34-128">.NET Framework Developer Center</span></span>](https://www.microsoft.com/net)
