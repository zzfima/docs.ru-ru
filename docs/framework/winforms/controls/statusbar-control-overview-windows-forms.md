---
title: Общие сведения об элементе управления StatusBar (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- StatusBar
helpviewer_keywords:
- StatusBar control [Windows Forms], about StatusBar control
- status bars
ms.assetid: b7b9852c-633d-4416-bb2e-94852b989c6c
ms.openlocfilehash: c3e52a91a31eb898d0176bc35a97cda7de9a8368
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54491354"
---
# <a name="statusbar-control-overview-windows-forms"></a>Общие сведения об элементе управления StatusBar (Windows Forms)
> [!IMPORTANT]
>  <xref:System.Windows.Forms.StatusStrip> И <xref:System.Windows.Forms.ToolStripStatusLabel> элементы управления заменяют и расширяют функциональные возможности для <xref:System.Windows.Forms.StatusBar> и <xref:System.Windows.Forms.StatusBarPanel> управляет; Однако <xref:System.Windows.Forms.StatusBar> и <xref:System.Windows.Forms.StatusBarPanel> элементы управления сохраняются для обеспечения обратной совместимости и использования в будущем, если вы Выберите этот параметр.  
  
 Windows Forms [элемента управления StatusBar](../../../../docs/framework/winforms/controls/statusbar-control-windows-forms.md) используется в формах в качестве области, обычно отображается в нижней части окна, в которой выводятся различные сведения о состоянии приложения. <xref:System.Windows.Forms.StatusBar> элементы управления могут иметь панелей строки состояния на них, которые отображают текст или значки, показывающие состояние или набор значков в анимации, которые указывают, что процесс работает; например [!INCLUDE[ofprword](../../../../includes/ofprword-md.md)] означает, что при сохранении документа.  
  
## <a name="using-the-statusbar-control"></a>Использование элемента управления StatusBar  
 Internet Explorer использует строку состояния, чтобы указать URL-адрес страницы при наведении указателя мыши на гиперссылку; [!INCLUDE[ofprword](../../../../includes/ofprword-md.md)] позволяет получить информацию о расположение страницы, раздела и режимах редактирования, такие как замены и отслеживание изменений; и Visual Studio строка состояния используется для предоставления контекстных сведений, таких как закрепляемыми окнами как закрепленные или с плавающей запятой.  
  
 Можно отобразить одно сообщение в строке состояния, задав <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> свойства `false` (по умолчанию) и параметр <xref:System.Windows.Forms.StatusBar.Text%2A> свойства в строке состояния в текст, который будет отображаться в строке состояния. Можно разделить на строке состояния панелей для отображения более чем один тип данных, задав <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> свойства `true` и с помощью <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection.Add%2A> метод <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>.  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [Практическое руководство. Определить, какая из панелей в элемент управления Windows Forms StatusBar была нажата](../../../../docs/framework/winforms/controls/determine-which-panel-wf-statusbar-control-was-clicked.md)
