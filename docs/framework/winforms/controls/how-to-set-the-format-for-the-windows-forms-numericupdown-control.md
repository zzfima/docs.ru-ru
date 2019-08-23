---
title: Практическое руководство. Определение формата элемента управления NumericUpDown в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- NumericUpDown control [Windows Forms], formatting values
- up-down controls [Windows Forms], formatting numeric values
ms.assetid: fa7c5557-6bfb-45b2-975d-8887b23b0ba0
ms.openlocfilehash: 6db7a1b2aeb7282c3ac827cb8319706ed348fc22
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69949154"
---
# <a name="how-to-set-the-format-for-the-windows-forms-numericupdown-control"></a>Практическое руководство. Определение формата элемента управления NumericUpDown в Windows Forms
Можно настроить отображение значений в элементе управления Windows Forms <xref:System.Windows.Forms.NumericUpDown> . <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> Свойство определяет, сколько чисел отображается после десятичной запятой; значение по умолчанию — 0. Свойство определяет, будет ли вставляться разделитель между всеми тремя десятичными цифрами; значение по умолчанию — `false`. <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> Элемент управления может отображать значения в шестнадцатеричном формате вместо десятичного формата, <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> если свойство имеет `true`значение; значение по умолчанию — `false`.  
  
### <a name="to-format-the-numeric-value"></a>Форматирование числового значения  
  
- Отобразите десятичное значение, задав <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> свойству целое число и <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> задав для `true` свойства значение `false`или.  
  
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
  
- Отобразите шестнадцатеричное значение, задав <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> для `true`свойства значение.  
  
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
    > Даже если значение отображается в форме как шестнадцатеричное, все тесты, выполняемые в <xref:System.Windows.Forms.NumericUpDown.Value%2A> свойстве, будут проверять его десятичное значение.  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.NumericUpDown>
- [Элемент управления NumericUpDown](numericupdown-control-windows-forms.md)
- [Общие сведения об элементе управления NumericUpDown](numericupdown-control-overview-windows-forms.md)
