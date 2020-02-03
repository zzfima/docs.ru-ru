---
title: Общие сведения об элементе управления StatusBar
ms.date: 03/30/2017
f1_keywords:
- StatusBar
helpviewer_keywords:
- StatusBar control [Windows Forms], about StatusBar control
- status bars
ms.assetid: b7b9852c-633d-4416-bb2e-94852b989c6c
ms.openlocfilehash: b0b97bc3cb0291871e1fd113d82d0b480b53cdba
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742864"
---
# <a name="statusbar-control-overview-windows-forms"></a>Общие сведения об элементе управления StatusBar (Windows Forms)
> [!IMPORTANT]
> <xref:System.Windows.Forms.StatusStrip> и <xref:System.Windows.Forms.ToolStripStatusLabel> элементы управления заменяют и добавляют функции в элементы управления <xref:System.Windows.Forms.StatusBar> и <xref:System.Windows.Forms.StatusBarPanel>. Однако элементы управления <xref:System.Windows.Forms.StatusBar> и <xref:System.Windows.Forms.StatusBarPanel> сохраняются как для обратной совместимости, так и для будущего использования, если вы решили.  
  
 [Элемент управления StatusBar](statusbar-control-windows-forms.md) Windows Forms используется в формах как область, обычно отображаемую в нижней части окна, в которой приложение может отображать различные виды информации о состоянии. элементы управления <xref:System.Windows.Forms.StatusBar> могут иметь панели строки состояния, которые отображают текст или значки, указывающие на состояние, или ряд значков в анимации, указывающих, что процесс работает. Например, Microsoft Word, указывающий, что документ сохраняется.  
  
## <a name="using-the-statusbar-control"></a>Использование элемента управления StatusBar  
 Internet Explorer использует строку состояния для указания URL-адреса страницы при наведении указателя мыши на гиперссылку; Microsoft Word предоставляет сведения о расположении страницы, расположении раздела и режимах редактирования, таких как изменение типа и отслеживание исправлений. и Visual Studio использует строку состояния для предоставления контекстно-зависимой информации, например, о том, как управлять закрепляемыми окнами как закрепленными, так и плавающими.  
  
 В строке состояния можно отобразить одно сообщение, задав для свойства <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> значение `false` (по умолчанию) и установив для свойства <xref:System.Windows.Forms.StatusBar.Text%2A> строки состояния текст, который должен отображаться в строке состояния. Можно разделить строку состояния на панели, чтобы отобразить более одного типа информации, задав для свойства <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> значение `true` и используя метод <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection.Add%2A> <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [Практическое руководство. Идентификация панели элемента управления StatusBar, которую щелкнул пользователь, в Windows Forms](determine-which-panel-wf-statusbar-control-was-clicked.md)
