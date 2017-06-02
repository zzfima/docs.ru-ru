---
title: "Общие сведения об элементе управления NumericUpDown (Windows Forms) | Microsoft Docs"
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
  - "NumericUpDown"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "числовый счетчик - элемент управления, Windows Forms"
  - "NumericUpDown - элемент управления [Windows Forms], сведения об элементе управления NumericUpDown"
  - "счетчик - элемент управления, Windows Forms"
ms.assetid: cff3cf30-4d46-4381-87df-37bfe83c71c5
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Общие сведения об элементе управления NumericUpDown (Windows Forms)
Элемент управления <xref:System.Windows.Forms.NumericUpDown> представляет собой сочетание текстового поля и пары кнопок со стрелками для выбора значения пользователем.  Он выводит и задает отдельное числовое значение в списке вариантов фиксированных числовых значений.  Пользователь может увеличивать и уменьшать число, нажимая кнопки со стрелками вверх и вниз или клавиши со стрелками ВВЕРХ и ВНИЗ, а также вводя число в области текстового поля элемента управления.  При нажатии клавиши со стрелкой ВВЕРХ число увеличивается до максимума; при нажатии клавиши со стрелкой ВНИЗ число уменьшается до минимума.  
  
 Благодаря своим универсальным функциональным возможностям, этот элемент управления – очевидный выбор для создания регулятора громкости приложения музыкального проигрывателя.  Элемент управления <xref:System.Windows.Forms.NumericUpDown> используется во многих приложениях панели управления Windows.  
  
## Ключевые свойства и методы  
 Выводимые значения могут быть представлены текстовом поле элемента управления в различных форматах, в том числе в шестнадцатеричном.  Дополнительные сведения см. в разделе [Практическое руководство. Определение формата элемента управления NumericUpDown в Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-the-format-for-the-windows-forms-numericupdown-control.md).  Ключевые свойства элемента управления: <xref:System.Windows.Forms.NumericUpDown.Value%2A>, <xref:System.Windows.Forms.NumericUpDown.Maximum%2A> \(значение по умолчанию – 100\), <xref:System.Windows.Forms.NumericUpDown.Minimum%2A> \(значение по умолчанию – 0\) и <xref:System.Windows.Forms.NumericUpDown.Increment%2A> \(значение по умолчанию – 1\).  Свойство <xref:System.Windows.Forms.NumericUpDown.Value%2A> задает текущее число, выбранное в элементе управления.  Свойство <xref:System.Windows.Forms.NumericUpDown.Increment%2A> задает шаг изменения значения при нажатии кнопки со стрелкой вверх или вниз.  При снятии фокуса с элемента управления любые введенные данные проверяются на соответствие с минимальным и максимальным числовыми значениями.  Для увеличения скорости перемещения элемента управления в зависимости от непрерывности нажатия пользователем клавиш со стрелкой вверх и вниз можно использовать свойство <xref:System.Windows.Forms.NumericUpDown.Accelerations%2A>.  Основными методами этого элемента управления являются методы <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> и <xref:System.Windows.Forms.NumericUpDown.DownButton%2A>.  
  
## См. также  
 <xref:System.Windows.Forms.NumericUpDown>   
 [Элемент управления NumericUpDown](../../../../docs/framework/winforms/controls/numericupdown-control-windows-forms.md)   
 [Практическое руководство. Определение формата элемента управления NumericUpDown в Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-the-format-for-the-windows-forms-numericupdown-control.md)   
 [Элемент управления TextBox](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)