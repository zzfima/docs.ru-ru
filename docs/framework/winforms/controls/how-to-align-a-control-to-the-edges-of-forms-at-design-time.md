---
title: "Практическое руководство. Выравнивание элементов управления по границам формы во время выполнения | Microsoft Docs"
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
  - "пользовательские элементы управления [Windows Forms], закрепление с помощью конструктора"
  - "Dock - свойство, выравнивание элементов управления (c помощью конструктора)"
ms.assetid: 51f08998-5e3b-4330-be58-a4edd0eb60f4
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Практическое руководство. Выравнивание элементов управления по границам формы во время выполнения
Можно выровнять элемент управления по границе формы с помощью свойства <xref:System.Windows.Forms.Control.Dock%2A>.  Это свойство определяет, в каком месте формы будет размещаться элемент управления.  Свойство <xref:System.Windows.Forms.Control.Dock%2A> может принимать следующие значения.  
  
|Параметр|Влияние на элемент управления|  
|--------------|-----------------------------------|  
|<xref:System.Windows.Forms.DockStyle>|Фиксирует элемент управления у нижнего края формы.|  
|<xref:System.Windows.Forms.DockStyle>|Заполняет все свободное пространство формы.|  
|<xref:System.Windows.Forms.DockStyle>|Фиксирует элемент управления у левого края формы.|  
|<xref:System.Windows.Forms.DockStyle>|Не фиксирует элемент нигде, он отображается в месте, указанном в свойстве <xref:System.Windows.Forms.Control.Location%2A>.|  
|<xref:System.Windows.Forms.DockStyle>|Фиксирует элемент управления у правого края формы.|  
|<xref:System.Windows.Forms.DockStyle>|Фиксирует элемент управления у верхнего края формы.|  
  
 Эти значения также могут быть заданы в коде.  Дополнительные сведения см. в разделе [Практическое руководство. Выравнивание элементов управления по границам формы](../../../../docs/framework/winforms/controls/how-to-align-a-control-to-the-edges-of-forms.md).  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих настроек или выпуска.  Чтобы изменить параметры, в меню **Сервис** выберите команду **Импорт и экспорт параметров**.  Дополнительные сведения см. в разделе [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ru-ru/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Чтобы задать свойство "Dock" для элемента управления в режиме разработки  
  
1.  В конструкторе Windows Forms выберите ваш элемент управления.  
  
2.  В окне **Свойства** нажмите кнопку раскрывающегося списка рядом со свойством <xref:System.Windows.Forms.Control.Dock%2A>.  
  
     Отобразится графический интерфейс с шестью возможными значениями свойства <xref:System.Windows.Forms.Control.Dock%2A>.  
  
3.  Выберите соответствующее значение.  
  
4.  Положение элемента управления будет зафиксировано в соответствии с выбранным значением.  
  
## См. также  
 <xref:System.Windows.Forms.Control.Dock%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.Control.Anchor%2A?displayProperty=fullName>   
 [Практическое руководство. Выравнивание элементов управления по границам формы](../../../../docs/framework/winforms/controls/how-to-align-a-control-to-the-edges-of-forms.md)   
 [Пример. Упорядочение элементов управления в формах Windows Forms с помощью линий привязки](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)   
 [Практическое руководство. Привязка элементов управления в формах Windows Forms](../../../../docs/framework/winforms/controls/how-to-anchor-controls-on-windows-forms.md)   
 [Практическое руководство. Привязка и закрепление дочерних элементов управления в элементе управления TableLayoutPanel](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)   
 [Практическое руководство. Закрепление дочерних элементов управления в элементе управления FlowLayoutPanel](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)   
 [Пошаговое руководство. Упорядочение элементов управления в формах Windows Forms с помощью элемента TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)   
 [Пример. Упорядочение элементов управления в формах Windows Forms с помощью элемента FlowLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)   
 [Создание элементов управления Windows Forms во время разработки](../../../../docs/framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)