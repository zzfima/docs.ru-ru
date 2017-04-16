---
title: "Общие сведения об элементе управления StatusBar (Windows Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "StatusBar"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "строки состояния"
  - "StatusBar - элемент управления [Windows Forms], сведения об элементе управления StatusBar"
ms.assetid: b7b9852c-633d-4416-bb2e-94852b989c6c
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Общие сведения об элементе управления StatusBar (Windows Forms)
> [!IMPORTANT]
>  Элементы управления <xref:System.Windows.Forms.StatusStrip> и <xref:System.Windows.Forms.ToolStripStatusLabel> заменяют элементы управления <xref:System.Windows.Forms.StatusBar> и <xref:System.Windows.Forms.StatusBarPanel> и расширяют их функциональные возможности; однако при необходимости элементы управления <xref:System.Windows.Forms.StatusBar> и <xref:System.Windows.Forms.StatusBarPanel> можно сохранить для обратной совместимости и использования в будущем.  
  
 Элемент управления [Элемент управления StatusBar](../../../../docs/framework/winforms/controls/statusbar-control-windows-forms.md) Windows Forms используется в формах в виде области внизу окна, в которой приложение отображает различную информацию о состоянии.  Элементы управления <xref:System.Windows.Forms.StatusBar> могут включать панели строки состояния, на которые выводятся текст или значки, показывающие состояние, или анимированный набор значков, показывающий выполнение процесса \(например, такие как при сохранении документа в приложении [!INCLUDE[ofprword](../../../../includes/ofprword-md.md)]\).  
  
## Использование элемента управления StatusBar  
 В приложении Internet Explorer строка состояния используется для указания адреса URL страницы при наведении указателя мыши на гиперссылку; [!INCLUDE[ofprword](../../../../includes/ofprword-md.md)] представляет сведения о расположении страницы и раздела, а также о режимах редактирования, например о режимах замены и правки; в [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] строка состояния используется для предоставления контекстных сведений, таких как описание действий с закрепленными или плавающими закрепляемыми окнами.  
  
 Отдельное сообщение выводится в строке состояния путем задания для свойства <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> значения `false` \(по умолчанию\), а для свойства <xref:System.Windows.Forms.StatusBar.Text%2A> строки состояния — текста, который требуется вывести в строке состояния.  Можно разделить строку состояния в панели с целью отображения различных типов информации. Для этого необходимо присвоить свойству <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> значение `true` и использовать метод <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection.Add%2A> элемента <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>.  
  
## См. также  
 <xref:System.Windows.Forms.StatusBar>   
 <xref:System.Windows.Forms.ToolStripStatusLabel>   
 [Практическое руководство. Идентификация панели элемента управления StatusBar, которую щелкнул пользователь, в Windows Forms](../../../../docs/framework/winforms/controls/determine-which-panel-wf-statusbar-control-was-clicked.md)