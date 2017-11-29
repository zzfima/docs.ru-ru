---
title: "Практическое руководство. Использование пользовательского контекстного меню в RichTextBox"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom context menus [WPF], positioning
- positioning custom context menus [WPF]
- RichTextBox control [WPF], positioning custom context menus
- context menus [WPF], positioning
ms.assetid: bf77c930-a546-4573-9a56-9af345ba189a
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1c0a4fd8d2df15dcca2d9d1751f3089922d9a5ad
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-position-a-custom-context-menu-in-a-richtextbox"></a>Практическое руководство. Использование пользовательского контекстного меню в RichTextBox
В этом примере показано, как разместить пользовательское контекстное меню для <xref:System.Windows.Controls.RichTextBox>.  
  
 При реализации пользовательского контекстного меню для **RichTextBox** вы несете ответственность за обработку размещения контекстного меню.  По умолчанию пользовательское контекстное меню открывается в центре **RichTextBox**.  
  
## <a name="example"></a>Пример  
 Чтобы переопределить поведение расположения по умолчанию, добавьте прослушиватель для <xref:System.Windows.FrameworkContentElement.ContextMenuOpening> события.  В приведенном ниже примере показано, как это сделать программным способом.  
  
 [!code-csharp[RichTextBox_ContextMenu#_AddListener](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBox_ContextMenu/CSharp/app.xaml.cs#_addlistener)]
 [!code-vb[RichTextBox_ContextMenu#_AddListener](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBox_ContextMenu/VisualBasic/app.xaml.vb#_addlistener)]  
  
## <a name="example"></a>Пример  
 В следующем примере показана реализация соответствующего <xref:System.Windows.FrameworkContentElement.ContextMenuOpening> прослушиватель событий.  
  
 [!code-csharp[RichTextBox_ContextMenu#_ListenerBody](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBox_ContextMenu/CSharp/app.xaml.cs#_listenerbody)]
 [!code-vb[RichTextBox_ContextMenu#_ListenerBody](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBox_ContextMenu/VisualBasic/app.xaml.vb#_listenerbody)]  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)  
 [Общие сведения о TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)
