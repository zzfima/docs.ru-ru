---
title: Задание формата для элемента управления NumericUpDown
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- NumericUpDown control [Windows Forms], formatting values
- up-down controls [Windows Forms], formatting numeric values
ms.assetid: fa7c5557-6bfb-45b2-975d-8887b23b0ba0
ms.openlocfilehash: 5ef1c801e96bef7b92e7e69dc36491144c456eeb
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742173"
---
# <a name="how-to-set-the-format-for-the-windows-forms-numericupdown-control"></a>Практическое руководство. Определение формата элемента управления NumericUpDown в Windows Forms
Можно настроить отображение значений в элементе управления Windows Forms <xref:System.Windows.Forms.NumericUpDown>. Свойство <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> определяет, сколько чисел отображается после десятичной запятой; значение по умолчанию — 0. Свойство <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> определяет, будет ли вставляться разделитель между всеми тремя десятичными цифрами; значение по умолчанию — `false`. Элемент управления может отображать значения в шестнадцатеричном формате вместо десятичного формата, если свойство <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> имеет значение `true`; значение по умолчанию — `false`.  
  
### <a name="to-format-the-numeric-value"></a>Форматирование числового значения  
  
- Отобразите десятичное значение, задав для свойства <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> целое число и установив для свойства <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> значение `true` или `false`.  
  
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
  
     -или-  
  
- Отобразите шестнадцатеричное значение, задав для свойства <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> значение `true`.  
  
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
    > Даже если значение отображается в форме как шестнадцатеричное, все тесты, выполняемые в свойстве <xref:System.Windows.Forms.NumericUpDown.Value%2A>, будут проверять его десятичное значение.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.NumericUpDown>
- [Элемент управления NumericUpDown](numericupdown-control-windows-forms.md)
- [Общие сведения об элементе управления NumericUpDown](numericupdown-control-overview-windows-forms.md)
