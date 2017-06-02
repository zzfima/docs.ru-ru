---
title: "Практическое руководство. Выравнивание элементов управления по границам формы | Microsoft Docs"
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
  - "элементы управления [Windows Forms], выравнивание в формах"
  - "пользовательские элементы управления [Windows Forms], закрепление с помощью кода"
  - "Dock - свойство, выравнивание элементов управления (использование кода)"
  - "формы, выравнивание элементов управления"
ms.assetid: 5994cb59-242b-4e75-bd0e-62879c34d702
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Практическое руководство. Выравнивание элементов управления по границам формы
Элемент управления можно выровнять по границе формы с помощью свойства <xref:System.Windows.Forms.Control.Dock%2A>.  Это свойство определяет, в каком месте формы будет размещаться элемент управления.  Свойство <xref:System.Windows.Forms.Control.Dock%2A> может принимать указанные ниже значения.  
  
|Параметр|Влияние на элемент управления|  
|--------------|-----------------------------------|  
|<xref:System.Windows.Forms.DockStyle>|Фиксирует элемент управления у нижнего края формы.|  
|<xref:System.Windows.Forms.DockStyle>|Заполняет все свободное пространство формы.|  
|<xref:System.Windows.Forms.DockStyle>|Фиксирует элемент управления у левого края формы.|  
|<xref:System.Windows.Forms.DockStyle>|Не фиксирует элемент нигде; он отображается в месте, указанном в свойстве <xref:System.Windows.Forms.Control.Location%2A>.|  
|<xref:System.Windows.Forms.DockStyle>|Фиксирует элемент управления у правого края формы.|  
|<xref:System.Windows.Forms.DockStyle>|Фиксирует элемент управления у верхнего края формы.|  
  
 Эта возможность поддерживается на этапе разработки в Visual Studio.  
  
### Задание свойства Dock для элемента управления во время выполнения  
  
1.  Присвойте свойству <xref:System.Windows.Forms.Control.Dock%2A> соответствующее значение в коде.  
  
    ```vb  
    ' To set the Dock property internally.  
    Me.Dock = DockStyle.Top  
    ' To set the Dock property from another object.  
    UserControl1.Dock = DockStyle.Top  
    ```  
  
    ```csharp  
    // To set the Dock property internally.  
    this.Dock = DockStyle.Top;  
    // To set the Dock property from another object.  
    UserControl1.Dock = DockStyle.Top;  
    ```  
  
## См. также  
 <xref:System.Windows.Forms.Control.Dock%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.Control.Anchor%2A?displayProperty=fullName>   
 [Разработка пользовательских элементов управления Windows Forms в .NET Framework](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)   
 [Практическое руководство. Закрепление дочерних элементов управления в элементе управления FlowLayoutPanel](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)   
 [Практическое руководство. Привязка и закрепление дочерних элементов управления в элементе управления TableLayoutPanel](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)   
 [Свойство AutoSize](../../../../docs/framework/winforms/controls/autosize-property-overview.md)