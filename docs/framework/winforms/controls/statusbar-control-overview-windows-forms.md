---
title: Общие сведения об элементе управления StatusBar (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- StatusBar
helpviewer_keywords:
- StatusBar control [Windows Forms], about StatusBar control
- status bars
ms.assetid: b7b9852c-633d-4416-bb2e-94852b989c6c
ms.openlocfilehash: 5fdefa7d7e7c7ef543f677be7beb61dfee54e077
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59077320"
---
# <a name="statusbar-control-overview-windows-forms"></a>Общие сведения об элементе управления StatusBar (Windows Forms)
> [!IMPORTANT]
>  <xref:System.Windows.Forms.StatusStrip> И <xref:System.Windows.Forms.ToolStripStatusLabel> элементы управления заменяют и расширяют функциональные возможности для <xref:System.Windows.Forms.StatusBar> и <xref:System.Windows.Forms.StatusBarPanel> управляет; Однако <xref:System.Windows.Forms.StatusBar> и <xref:System.Windows.Forms.StatusBarPanel> элементы управления сохраняются для обеспечения обратной совместимости и использования в будущем, если вы Выберите этот параметр.  
  
 Windows Forms [элемента управления StatusBar](statusbar-control-windows-forms.md) используется в формах в качестве области, обычно отображается в нижней части окна, в которой выводятся различные сведения о состоянии приложения. <xref:System.Windows.Forms.StatusBar> элементы управления могут иметь панелей строки состояния на них, которые отображают текст или значки, показывающие состояние или набор значков в анимации, которые указывают, что процесс работает; например [!INCLUDE[ofprword](../../../../includes/ofprword-md.md)] означает, что при сохранении документа.  
  
## <a name="using-the-statusbar-control"></a>Использование элемента управления StatusBar  
 Internet Explorer использует строку состояния, чтобы указать URL-адрес страницы при наведении указателя мыши на гиперссылку; [!INCLUDE[ofprword](../../../../includes/ofprword-md.md)] позволяет получить информацию о расположение страницы, раздела и режимах редактирования, такие как замены и отслеживание изменений; и Visual Studio строка состояния используется для предоставления контекстных сведений, таких как закрепляемыми окнами как закрепленные или с плавающей запятой.  
  
 Можно отобразить одно сообщение в строке состояния, задав <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> свойства `false` (по умолчанию) и параметр <xref:System.Windows.Forms.StatusBar.Text%2A> свойства в строке состояния в текст, который будет отображаться в строке состояния. Можно разделить на строке состояния панелей для отображения более чем один тип данных, задав <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> свойства `true` и с помощью <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection.Add%2A> метод <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>.  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [Практическое руководство. Определить, какая из панелей в элемент управления Windows Forms StatusBar была нажата](determine-which-panel-wf-statusbar-control-was-clicked.md)
