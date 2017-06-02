---
title: "Практическое руководство. Перемещение элемента ToolStrip из контейнера ToolStripContainer в форму | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "ToolStrip - элемент управления [Windows Forms], родительский по отношению к формам"
  - "Windows Forms, родительские элементы управления ToolStrip"
ms.assetid: a1c94a7f-6fc5-4e4c-84cf-ff11dc573d33
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Практическое руководство. Перемещение элемента ToolStrip из контейнера ToolStripContainer в форму
Используйте следующую процедуру для перемещения <xref:System.Windows.Forms.ToolStrip> из <xref:System.Windows.Forms.ToolStripContainer> в форму.  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих настроек или выпуска.  Чтобы изменить параметры, в меню **Сервис** выберите команду **Импорт и экспорт параметров**.  Дополнительные сведения см. в разделе [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ru-ru/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Чтобы переместить ToolStrip из контейнера ToolStripContainer в форму  
  
1.  Выберите <xref:System.Windows.Forms.ToolStrip>.  
  
2.  Вырежьте <xref:System.Windows.Forms.ToolStrip> в буфер обмена, нажав CTRL\+X, или щелкните правой кнопкой мыши по <xref:System.Windows.Forms.ToolStrip> и выберите из контекстного меню команду **Вырезать**.  
  
3.  Выберите форму.  
  
4.  Вставьте <xref:System.Windows.Forms.ToolStrip>, нажав CTRL\+V, или выберите из меню **Правка** команду **Вставить**.  
  
5.  Присвойте свойству <xref:System.Windows.Forms.ToolStrip.Dock%2A> элемента <xref:System.Windows.Forms.ToolStrip> значение **По верхнему краю**.  
  
## См. также  
 <xref:System.Windows.Forms.ToolStrip>   
 <xref:System.Windows.Forms.ToolStripContainer>   
 [Общие сведения об элементе управления ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)