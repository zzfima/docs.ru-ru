---
title: "Практическое руководство. Определение формата элемента управления NumericUpDown в Windows Forms | Microsoft Docs"
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
  - "NumericUpDown - элемент управления [Windows Forms], значения форматирования"
  - "поля со стрелками "вверх/вниз", форматирование числовых значений"
ms.assetid: fa7c5557-6bfb-45b2-975d-8887b23b0ba0
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Практическое руководство. Определение формата элемента управления NumericUpDown в Windows Forms
Существует возможность настройки отображения значений в элементе управления Windows Forms <xref:System.Windows.Forms.NumericUpDown>.  Свойство <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> определяет, сколько знаков отображается после десятичной запятой; значение по умолчанию — 0.  Свойство <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> определяет, нужно ли вставлять разделитель между после каждых трех десятичных разрядов; значение по умолчанию — `false`.  В том случае, если свойству <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> присвоено значение `true`, этот элемент управления может отображать значения в шестнадцатеричном формате вместо десятичного; по умолчанию используется значение `false`.  
  
### Задание формата числового значения  
  
-   Отобразите десятичное значение, присвоив свойству <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> целочисленное значение, а свойству <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> — значение `true` или `false`.  
  
    ```vb  
    NumericUpDown1.DecimalPlaces = 2  
    NumericUpDown1.ThousandsSeparator = True  
  
    ```  
  
    ```csharp  
    numericUpDown1.DecimalPlaces = 2;  
    numericUpDown1.ThousandsSeparator = true;  
  
    ```  
  
    ```cpp  
    numericUpDown1->DecimalPlaces = 2;  
    numericUpDown1->ThousandsSeparator = true;  
    ```  
  
     \-или\-  
  
-   Отобразите шестнадцатеричное число, присвоив свойству <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> значение `true`.  
  
    ```vb  
    NumericUpDown1.Hexadecimal = True  
  
    ```  
  
    ```csharp  
    numericUpDown1.Hexadecimal = true;  
  
    ```  
  
    ```cpp  
    numericUpDown1->Hexadecimal = true;  
    ```  
  
    > [!NOTE]
    >  Даже в том случае, если это значение отображается в шестнадцатеричном формате, в любых проверках для свойства <xref:System.Windows.Forms.NumericUpDown.Value%2A> будет проверяться его десятичное значение.  
  
## См. также  
 <xref:System.Windows.Forms.NumericUpDown>   
 [Элемент управления NumericUpDown](../../../../docs/framework/winforms/controls/numericupdown-control-windows-forms.md)   
 [Общие сведения об элементе управления NumericUpDown](../../../../docs/framework/winforms/controls/numericupdown-control-overview-windows-forms.md)