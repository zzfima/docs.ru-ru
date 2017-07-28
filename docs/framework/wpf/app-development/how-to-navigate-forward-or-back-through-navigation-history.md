---
title: "Практическое руководство. Переход вперед или назад по журналу навигации | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "history, переход, переход вперед"
  - "переход, по журналу переходов (вперед)"
ms.assetid: 5939d574-5f53-469e-85f5-1f2b13607caa
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Практическое руководство. Переход вперед или назад по журналу навигации
Этот пример показывает, как перемещаться переднее или обратно к записям в журнале переходов.  
  
## Пример  
 Код, который выполняется от содержимого в следующих основных приложениях могут переходить передний или задний и полный журнал переходов, одна запись одновременно.  
  
-   <xref:System.Windows.Navigation.NavigationWindow> использование  <xref:System.Windows.Navigation.NavigationService>  
  
-   <xref:System.Windows.Controls.Frame> использование  <xref:System.Windows.Navigation.NavigationService>  
  
-   [!INCLUDE[TLA#tla_iegeneric](../../../../includes/tlasharptla-iegeneric-md.md)]  
  
 Прежде чем переходить передняя одна запись, сначала нужно проверить, что записи в журнале переходов с помощью проверки переднем CanGoForward свойство.  Для перехода передняя одна запись, следует вызвать **Вперед** метод.  Это показано в следующем примере:  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateForwardCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigateforwardcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateForwardCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigateforwardcode)]  
  
 Прежде чем переходить обратно одна запись, сначала нужно проверить, что записи в журнале переходов назад путем проверки CanGoBack свойство.  Для перехода обратно одна запись, следует вызвать **Назад** метод.  Это показано в следующем примере:  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateBackCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigatebackcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateBackCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigatebackcode)]  
  
 **CanGoForward**"  **Вперед**"  **CanGoBack**и  **Назад** реализуйте by  <xref:System.Windows.Navigation.NavigationWindow>"  <xref:System.Windows.Controls.Frame>и  <xref:System.Windows.Navigation.NavigationService>.  
  
> [!NOTE]
>  Если вызвать **Вперед**и записи на переднем журнале переходов или если вызвать  **Назад**и записи в журнале переходов назад "  <xref:System.InvalidOperationException> создает исключение.