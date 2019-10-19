---
title: Как получить и задать основное окно приложения
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- windows objects [WPF], setting
- setting windows objects [WPF]
- windows objects [WPF], getting
- getting windows objects [WPF]
ms.assetid: ec902bc4-4a59-46f5-8ec1-963b46789356
ms.openlocfilehash: 5894761c4b6258cbf90d369a722ffc5abca51885
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582547"
---
# <a name="how-to-get-and-set-the-main-application-window"></a><span data-ttu-id="1dff5-102">Как получить и задать основное окно приложения</span><span class="sxs-lookup"><span data-stu-id="1dff5-102">How to: Get and Set the Main Application Window</span></span>
<span data-ttu-id="1dff5-103">В этом примере показано, как получить и задать основное окно приложения.</span><span class="sxs-lookup"><span data-stu-id="1dff5-103">This example shows how to get and set the main application window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1dff5-104">Пример</span><span class="sxs-lookup"><span data-stu-id="1dff5-104">Example</span></span>  
 <span data-ttu-id="1dff5-105">Первый <xref:System.Windows.Window>, создаваемый в приложении Windows Presentation Foundation (WPF), автоматически задается <xref:System.Windows.Application> в качестве главного окна приложения.</span><span class="sxs-lookup"><span data-stu-id="1dff5-105">The first <xref:System.Windows.Window> that is instantiated within a Windows Presentation Foundation (WPF) application is automatically set by <xref:System.Windows.Application> as the main application window.</span></span> <span data-ttu-id="1dff5-106">Первым <xref:System.Windows.Window>, для которого создается экземпляр, скорее всего, будет окно, указанное в качестве универсального кода ресурса (URI) запуска (см. <xref:System.Windows.Application.StartupUri%2A>).</span><span class="sxs-lookup"><span data-stu-id="1dff5-106">The first <xref:System.Windows.Window> to be instantiated will most likely be the window that is specified as the startup uniform resource identifier (URI) (see <xref:System.Windows.Application.StartupUri%2A>).</span></span>  
  
 <span data-ttu-id="1dff5-107">Для первого <xref:System.Windows.Window> также можно создать экземпляр с помощью кода.</span><span class="sxs-lookup"><span data-stu-id="1dff5-107">The first <xref:System.Windows.Window> could also be instantiated using code.</span></span> <span data-ttu-id="1dff5-108">Одним из примеров является открытие окна во время запуска приложения, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="1dff5-108">One example is opening a window during application startup, like the following:</span></span>  
  
 [!code-csharp[HOWTOWindowManagementSnippets#FirstWindowUsingCodeCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/App.xaml.cs#firstwindowusingcodecodebehind)]
 [!code-vb[HOWTOWindowManagementSnippets#FirstWindowUsingCodeCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/application.xaml.vb#firstwindowusingcodecodebehind)]  
  
 <span data-ttu-id="1dff5-109">Иногда первый экземпляр <xref:System.Windows.Window> на самом деле не является главным окном приложения, например, экран-заставка.</span><span class="sxs-lookup"><span data-stu-id="1dff5-109">Sometimes, the first instantiated <xref:System.Windows.Window> is not actually the main application window e.g. a splash screen.</span></span> <span data-ttu-id="1dff5-110">В этом случае можно указать основное окно приложения, используя разметку следующим образом:</span><span class="sxs-lookup"><span data-stu-id="1dff5-110">In this case, you can specify the main application window using markup, like the following:</span></span>  
  
 [!code-xaml[ApplicationMainWindowSnippets#SetApplicationMainWindowXAML](~/samples/snippets/xaml/VS_Snippets_Wpf/ApplicationMainWindowSnippets/XAML/App.xaml#setapplicationmainwindowxaml)]  
  
 <span data-ttu-id="1dff5-111">Независимо от того, задано ли главное окно автоматически или вручную, можно получить главное окно из <xref:System.Windows.Application.MainWindow%2A> с помощью следующего кода, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="1dff5-111">Whether the main window is specified automatically or manually, you can get the main window from <xref:System.Windows.Application.MainWindow%2A> using the following code, like the following:</span></span>  
  
 [!code-csharp[ApplicationMainWindowSnippets#GetApplicationMainWindowCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationMainWindowSnippets/CSharp/App.xaml.cs#getapplicationmainwindowcode)]
 [!code-vb[ApplicationMainWindowSnippets#GetApplicationMainWindowCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationMainWindowSnippets/visualbasic/application.xaml.vb#getapplicationmainwindowcode)]
