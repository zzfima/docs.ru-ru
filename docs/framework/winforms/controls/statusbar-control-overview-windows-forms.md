---
title: "Общие сведения об элементе управления StatusBar (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: StatusBar
helpviewer_keywords:
- StatusBar control [Windows Forms], about StatusBar control
- status bars
ms.assetid: b7b9852c-633d-4416-bb2e-94852b989c6c
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9c26463fae5beca23026a71dd83b19bf3eb52875
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="statusbar-control-overview-windows-forms"></a>Общие сведения об элементе управления StatusBar (Windows Forms)
> [!IMPORTANT]
>  <xref:System.Windows.Forms.StatusStrip> И <xref:System.Windows.Forms.ToolStripStatusLabel> заменить элементы управления и добавить функциональные возможности в <xref:System.Windows.Forms.StatusBar> и <xref:System.Windows.Forms.StatusBarPanel> управляет; Однако <xref:System.Windows.Forms.StatusBar> и <xref:System.Windows.Forms.StatusBarPanel> элементы управления можно сохранить для обратной совместимости и использования в будущем, если вы Выберите этот параметр.  
  
 Windows Forms [управления StatusBar](../../../../docs/framework/winforms/controls/statusbar-control-windows-forms.md) используется в формах в качестве области, обычно отображаемой в нижней части окна, в которой выводятся различные сведения о состоянии приложения. <xref:System.Windows.Forms.StatusBar>элементы управления могут включать панели строки состояния на них, отображающие текст или значки, показывающие состояние, или набор значков в анимации, указывающие, что процесс работает; например [!INCLUDE[ofprword](../../../../includes/ofprword-md.md)] означает, что при сохранении документа.  
  
## <a name="using-the-statusbar-control"></a>С помощью элемента управления StatusBar  
 Строка состояния Internet Explorer используется для указания URL-адрес страницы, при наведении указателя мыши на гиперссылку; [!INCLUDE[ofprword](../../../../includes/ofprword-md.md)] представлены сведения о расположении страницы, расположение раздела и изменение режимы, такие как замены и правки; и [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] строка состояния используется для предоставления контекстных сведений, например о том, как управлять фиксируемого Windows как закрепленного или с плавающей запятой.  
  
 Можно отобразить одно сообщение в строке состояния, задав <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> свойства `false` (по умолчанию) и параметр <xref:System.Windows.Forms.StatusBar.Text%2A> свойство строки состояния, применяемый к тексту, который будет отображаться в строке состояния. В строке состояния можно разделить на панелей для отображения более чем один тип данных, задав <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> свойства `true` и с помощью <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection.Add%2A> метод <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.StatusBar>  
 <xref:System.Windows.Forms.ToolStripStatusLabel>  
 [Практическое руководство. Идентификация панели элемента управления StatusBar, которую щелкнул пользователь, в Windows Forms](../../../../docs/framework/winforms/controls/determine-which-panel-wf-statusbar-control-was-clicked.md)
