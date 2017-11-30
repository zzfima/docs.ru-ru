---
title: "Практическое руководство. Обработка события Opening компонента ContextMenuStrip"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ContextMenuStrip control [Windows Forms]
- context menus [Windows Forms], event handling
- ToolStrip control [Windows Forms]
- event handling [Windows Forms], context menus
- shortcut menus [Windows Forms], event handling
ms.assetid: b661b3dd-7815-4cc2-a1aa-a9a391ab3427
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 354631e514d9e2ece39d16bf7f259c36e4f90c32
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-handle-the-contextmenustrip-opening-event"></a>Практическое руководство. Обработка события Opening компонента ContextMenuStrip
Можно настроить поведение вашей <xref:System.Windows.Forms.ContextMenuStrip> управления обработкой <xref:System.Windows.Forms.ToolStripDropDown.Opening> событий.  
  
## <a name="example"></a>Пример  
 В следующем примере кода показано, как обрабатывать <xref:System.Windows.Forms.ToolStripDropDown.Opening> событий. Обработчик событий добавляет элементы в динамически <xref:System.Windows.Forms.ContextMenuStrip> элемента управления. Полный пример кода см. в разделе [как: динамическое добавление элементов ToolStrip](../../../../docs/framework/winforms/controls/how-to-add-toolstrip-items-dynamically.md).  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#42)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#42)]  
  
 Задать <xref:System.ComponentModel.CancelEventArgs.Cancel%2A?displayProperty=nameWithType> свойства `true` для предотвращения открытия меню.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.ContextMenuStrip>  
 <xref:System.ComponentModel.CancelEventArgs.Cancel%2A>  
 <xref:System.Windows.Forms.ToolStripDropDown>  
 [Элемент управления ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
