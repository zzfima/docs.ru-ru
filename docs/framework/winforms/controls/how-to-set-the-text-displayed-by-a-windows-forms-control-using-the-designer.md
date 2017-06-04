---
title: "Практическое руководство. Установка текста, отображаемого элементом управления Windows Forms, с помощью конструктора | Microsoft Docs"
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
  - "элементы управления [Windows Forms], установка заголовка"
  - "Windows Forms, установка отображаемого текста"
ms.assetid: 9d18e0e0-f17f-4074-837d-e67ceeeaa89d
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Практическое руководство. Установка текста, отображаемого элементом управления Windows Forms, с помощью конструктора
На элементах управления форм Windows Forms обычно отображается текст, связанный с их основной функцией.  Например, элемент управления <xref:System.Windows.Forms.Button> обычно имеет заголовок, указывающий, какое действие выполняется при нажатии этой кнопки.  Для любого элемента управления можно задавать или возвращать текст, используя свойство <xref:System.Windows.Forms.Control.Text%2A>.  Можно изменить шрифт, используя свойство <xref:System.Windows.Forms.Control.Font%2A>.  
  
### Чтобы настроить текст и шрифт в конструкторе, выполните следующие действия:  
  
1.  В окне "Свойства" задайте соответствующее строковое значение для свойства <xref:System.Windows.Forms.Control.Text%2A> элемента управления.  
  
     Чтобы создать сочетание клавиш и подчеркнуть соответствующую ему букву, вставьте знак & перед этой буквой.  
  
2.  В окне "Свойства" нажмите кнопку с многоточием \(![Снимок экрана VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\) рядом со свойством <xref:System.Windows.Forms.Control.Font%2A>.  
  
     В стандартном диалоговом окне выберите шрифт, стиль шрифта, размер, эффекты \(например, зачеркивание или подчеркивание\) и набор символов шрифта.  
  
## См. также  
 [Практическое руководство. Определение текста, отображаемого элементом управления Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)   
 [Шрифты и текст](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)   
 [Создание меток и назначение сочетаний клавиш для элементов управления Windows Forms](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)