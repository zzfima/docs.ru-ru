---
title: 'Как: Get и Set в главное окно приложения'
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
ms.openlocfilehash: ae70b482eba8fb4e0bf587def06bb90d751a4312
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-get-and-set-the-main-application-window"></a>Как: Get и Set в главное окно приложения
В этом примере показано, как получить и задать главного окна приложения.  
  
## <a name="example"></a>Пример  
 Первый <xref:System.Windows.Window> , создается в Windows Presentation Foundation (WPF) приложения автоматически устанавливаются <xref:System.Windows.Application> как главное окно приложения. Первый <xref:System.Windows.Window> быть вероятнее всего экземпляра будет иметь окно, которое задается как начальный [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] (см. <xref:System.Windows.Application.StartupUri%2A>).  
  
 Первый <xref:System.Windows.Window> также могут создаваться с помощью кода. Примером является открытие окна во время запуска приложения, следующим образом:  
  
 [!code-csharp[HOWTOWindowManagementSnippets#FirstWindowUsingCodeCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/App.xaml.cs#firstwindowusingcodecodebehind)]
 [!code-vb[HOWTOWindowManagementSnippets#FirstWindowUsingCodeCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/application.xaml.vb#firstwindowusingcodecodebehind)]  
  
 В некоторых случаях первый экземпляр <xref:System.Windows.Window> является фактически не главное окно приложения, например экрана-заставки. В этом случае можно указать в главное окно приложения с помощью разметки следующим образом:  
  
 [!code-xaml[ApplicationMainWindowSnippets#SetApplicationMainWindowXAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/ApplicationMainWindowSnippets/XAML/App.xaml#setapplicationmainwindowxaml)]  
  
 Ли указано главное окно автоматически или вручную, можно получить из главного окна <xref:System.Windows.Application.MainWindow%2A> используя следующий код, как показано ниже:  
  
 [!code-csharp[ApplicationMainWindowSnippets#GetApplicationMainWindowCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationMainWindowSnippets/CSharp/App.xaml.cs#getapplicationmainwindowcode)]
 [!code-vb[ApplicationMainWindowSnippets#GetApplicationMainWindowCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationMainWindowSnippets/visualbasic/application.xaml.vb#getapplicationmainwindowcode)]
