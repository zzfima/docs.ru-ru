---
title: Общие сведения об элементе управления StatusBar (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- StatusBar
helpviewer_keywords:
- StatusBar control [Windows Forms], about StatusBar control
- status bars
ms.assetid: b7b9852c-633d-4416-bb2e-94852b989c6c
ms.openlocfilehash: bd58d4c70e3a3c88e57fe242957f669d1944fd71
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964437"
---
# <a name="statusbar-control-overview-windows-forms"></a>Общие сведения об элементе управления StatusBar (Windows Forms)
> [!IMPORTANT]
> <xref:System.Windows.Forms.StatusBarPanel> <xref:System.Windows.Forms.StatusBar> <xref:System.Windows.Forms.StatusBar> <xref:System.Windows.Forms.StatusBarPanel> Элементы управления <xref:System.Windows.Forms.ToolStripStatusLabel> и заменяют и добавляют функциональные возможности в элементы управления и, однако, элементы управления и сохраняются для обратной совместимости и использования в будущем, если <xref:System.Windows.Forms.StatusStrip> выбрали.  
  
 [Элемент управления StatusBar](statusbar-control-windows-forms.md) Windows Forms используется в формах как область, обычно отображаемую в нижней части окна, в которой приложение может отображать различные виды информации о состоянии. <xref:System.Windows.Forms.StatusBar>элементы управления могут иметь панели строки состояния, которые отображают текст или значки, указывающие на состояние, или ряд значков в анимации, указывающих, что процесс работает. Например, Microsoft Word, указывающий, что документ сохраняется.  
  
## <a name="using-the-statusbar-control"></a>Использование элемента управления StatusBar  
 Internet Explorer использует строку состояния для указания URL-адреса страницы при наведении указателя мыши на гиперссылку; Microsoft Word предоставляет сведения о расположении страницы, расположении раздела и режимах редактирования, таких как изменение типа и отслеживание исправлений. и Visual Studio использует строку состояния для предоставления контекстно-зависимой информации, например, о том, как управлять закрепляемыми окнами как закрепленными, так и плавающими.  
  
 В строке состояния можно отобразить одно сообщение, задав <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> для `false` свойства значение ( <xref:System.Windows.Forms.StatusBar.Text%2A> по умолчанию) и установив для свойства строки состояния текст, который должен отображаться в строке состояния. Можно разделить строку состояния на панели, чтобы отобразить более одного типа информации, <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> задав для `true` свойства значение <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>и с помощью <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection.Add%2A> метода.  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [Практическое руководство. Определите, какая панель элемента управления Windows Forms StatusBar была нажата](determine-which-panel-wf-statusbar-control-was-clicked.md)
