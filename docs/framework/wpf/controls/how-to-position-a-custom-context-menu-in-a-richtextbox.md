---
title: "Практическое руководство. Использование пользовательского контекстного меню в RichTextBox | Microsoft Docs"
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
  - "настраиваемые контекстных меню, размещение"
  - "размещение настраиваемых контекстных меню"
  - "Элемент управления RichTextBox, размещение настраиваемых контекстных меню"
  - "контекстные меню, размещение"
ms.assetid: bf77c930-a546-4573-9a56-9af345ba189a
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Практическое руководство. Использование пользовательского контекстного меню в RichTextBox
В этом примере показано, как расположение пользовательского контекстного меню для <xref:System.Windows.Controls.RichTextBox>.  
  
 При реализации пользовательского контекстного меню для **RichTextBox**, вы несете ответственность за Обработка местоположения контекстного меню.  По умолчанию пользовательское контекстное меню открывается в центре **RichTextBox**.  
  
## <a name="example"></a>Пример  
 Чтобы переопределить поведение расположения по умолчанию, добавьте прослушиватель для <xref:System.Windows.FrameworkContentElement.ContextMenuOpening> событий.  В следующем примере показано, как сделать это программным путем.  
  
 [!code-csharp[RichTextBox_ContextMenu#_AddListener](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBox_ContextMenu/CSharp/app.xaml.cs#_addlistener)]
 [!code-vb[RichTextBox_ContextMenu#_AddListener](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBox_ContextMenu/VisualBasic/app.xaml.vb#_addlistener)]  
  
## <a name="example"></a>Пример  
 В следующем примере показана реализация соответствующего <xref:System.Windows.FrameworkContentElement.ContextMenuOpening> прослушиватель событий.  
  
 [!code-csharp[RichTextBox_ContextMenu#_ListenerBody](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBox_ContextMenu/CSharp/app.xaml.cs#_listenerbody)]
 [!code-vb[RichTextBox_ContextMenu#_ListenerBody](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBox_ContextMenu/VisualBasic/app.xaml.vb#_listenerbody)]  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)   
 [Общие сведения о TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)