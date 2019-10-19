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
# <a name="how-to-get-and-set-the-main-application-window"></a>Как получить и задать основное окно приложения
В этом примере показано, как получить и задать основное окно приложения.  
  
## <a name="example"></a>Пример  
 Первый <xref:System.Windows.Window>, создаваемый в приложении Windows Presentation Foundation (WPF), автоматически задается <xref:System.Windows.Application> в качестве главного окна приложения. Первым <xref:System.Windows.Window>, для которого создается экземпляр, скорее всего, будет окно, указанное в качестве универсального кода ресурса (URI) запуска (см. <xref:System.Windows.Application.StartupUri%2A>).  
  
 Для первого <xref:System.Windows.Window> также можно создать экземпляр с помощью кода. Одним из примеров является открытие окна во время запуска приложения, как показано ниже:  
  
 [!code-csharp[HOWTOWindowManagementSnippets#FirstWindowUsingCodeCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/App.xaml.cs#firstwindowusingcodecodebehind)]
 [!code-vb[HOWTOWindowManagementSnippets#FirstWindowUsingCodeCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/application.xaml.vb#firstwindowusingcodecodebehind)]  
  
 Иногда первый экземпляр <xref:System.Windows.Window> на самом деле не является главным окном приложения, например, экран-заставка. В этом случае можно указать основное окно приложения, используя разметку следующим образом:  
  
 [!code-xaml[ApplicationMainWindowSnippets#SetApplicationMainWindowXAML](~/samples/snippets/xaml/VS_Snippets_Wpf/ApplicationMainWindowSnippets/XAML/App.xaml#setapplicationmainwindowxaml)]  
  
 Независимо от того, задано ли главное окно автоматически или вручную, можно получить главное окно из <xref:System.Windows.Application.MainWindow%2A> с помощью следующего кода, как в следующем примере:  
  
 [!code-csharp[ApplicationMainWindowSnippets#GetApplicationMainWindowCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationMainWindowSnippets/CSharp/App.xaml.cs#getapplicationmainwindowcode)]
 [!code-vb[ApplicationMainWindowSnippets#GetApplicationMainWindowCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationMainWindowSnippets/visualbasic/application.xaml.vb#getapplicationmainwindowcode)]
