---
title: "Общие сведения о компоненте ColorDialog (Windows Forms) | Microsoft Docs"
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
  - "ColorDialog"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Цвет - диалоговое окно, сведения о диалоговом окне Цвет"
  - "ColorDialog - компонент, сведения о компоненте ColorDialog"
ms.assetid: 6dbdd8f0-f697-4728-bb09-7ea156f6d800
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Общие сведения о компоненте ColorDialog (Windows Forms)
Компонент Windows Forms <xref:System.Windows.Forms.ColorDialog> является стандартным диалоговым окном, в котором пользователь может выбрать цвет из палитры, а также добавить в палитру дополнительные цвета.  Это окно аналогично диалоговому окну для выбора цветов в других приложениях Windows.  Этот элемент управления используется в приложении Windows в качестве простого решения вместо диалогового окна, настраиваемого самостоятельно.  
  
 Цвет, выбранный в диалоговом окне, возвращается в свойстве <xref:System.Windows.Forms.ColorDialog.Color%2A>.  Если для свойства <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> задано значение `false`, кнопка "Определить цвет" недоступна и пользователь может работать только со стандартными цветами палитры.  Если для свойства <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> задано значение `true`, пользователь не может выбирать полутона.  Для отображения диалогового окна вызывается метод <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>.  
  
## См. также  
 <xref:System.Windows.Forms.ColorDialog>   
 [Компонент ColorDialog](../../../../docs/framework/winforms/controls/colordialog-component-windows-forms.md)   
 [Элементы управления и компоненты диалоговых окон](../../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md)   
 [Практическое руководство. Изменение внешнего вида компонента ColorDialog в Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-colordialog-component.md)