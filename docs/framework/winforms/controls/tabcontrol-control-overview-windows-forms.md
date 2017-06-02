---
title: "Общие сведения об элементе управления TabControl (Windows Forms) | Microsoft Docs"
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
  - "TabControl"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "страницы свойств, Windows Forms"
  - "страницы вкладок, сведения о страницах вкладок"
  - "TabControl - элемент управления [Windows Forms], сведения об элементе управления TabControl"
  - "диалоговые окна Windows Forms, вкладки"
ms.assetid: 2b4ea784-a39d-463c-81d8-af74ce068476
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Общие сведения об элементе управления TabControl (Windows Forms)
Элемент управления Windows Forms <xref:System.Windows.Forms.TabControl> используется для отображения нескольких вкладок, аналогичных разделителям в записной книжке или меткам в наборе папок картотечного блока.  Вкладки могут содержать рисунки и другие элементы управления.  Элемент управления вкладок можно использовать для создания многостраничных диалоговых окон, наподобие тех, что отображаются во многих компонентах интерфейса операционной системы Windows, например в свойствах экрана панели управления.  Кроме того, <xref:System.Windows.Forms.TabControl> можно использовать для создания страниц свойств, служащих для группировки связанных свойств.  
  
## Работа с TabControl  
 Наиболее важным свойством элемента управления <xref:System.Windows.Forms.TabControl> является свойство <xref:System.Windows.Forms.TabControl.TabPages%2A>, содержащее отдельные вкладки.  Каждая вкладка представляет собой объект <xref:System.Windows.Forms.TabPage>.  Если перейти на вкладку, вызывается событие <xref:System.Windows.Forms.Control.Click> для соответствующего объекта <xref:System.Windows.Forms.TabPage>.  
  
## См. также  
 <xref:System.Windows.Forms.TabControl>   
 [Элемент управления TabControl](../../../../docs/framework/winforms/controls/tabcontrol-control-windows-forms.md)   
 [Практическое руководство. Изменение внешнего вида элемента управления TabControl в Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)   
 [Практическое руководство. Добавление элемента управления на вкладку](../../../../docs/framework/winforms/controls/how-to-add-a-control-to-a-tab-page.md)   
 [Практическое руководство. Добавление и удаление вкладок с помощью элемента управления TabControl в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)   
 [Практическое руководство. Блокировка доступа ко вкладкам](../../../../docs/framework/winforms/controls/how-to-disable-tab-pages.md)   
 [Dialog Boxes in Windows Forms](../../../../docs/framework/winforms/dialog-boxes-in-windows-forms.md)