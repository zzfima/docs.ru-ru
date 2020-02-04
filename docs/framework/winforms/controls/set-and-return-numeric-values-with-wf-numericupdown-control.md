---
title: Установка и возврат числовых значений с помощью элемента управления NumericUpDown
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- numeric values [Windows Forms], Windows Forms
- Windows Forms, numeric values
- Windows Forms controls, NumericUpDown
- NumericUpDown control [Windows Forms], setting and returning values
ms.assetid: 5bd8f8cd-4c12-49ea-9cc3-2a647d064689
ms.openlocfilehash: a0b264fec9619b467c293bcb96278c4517775ac3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743024"
---
# <a name="how-to-set-and-return-numeric-values-with-the-windows-forms-numericupdown-control"></a>Практическое руководство. Ввод числовых значений с помощью элемента управления NumericUpDown в Windows Forms
Числовое значение элемента управления Windows Forms <xref:System.Windows.Forms.NumericUpDown> определяется его свойством <xref:System.Windows.Forms.NumericUpDown.Value%2A>. Можно писать условные тесты для значения элемента управления точно так же, как и любое другое свойство. После установки свойства <xref:System.Windows.Forms.NumericUpDown.Value%2A> его можно настроить непосредственно, написав код для выполнения операций с ним, или можно вызвать методы <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> и <xref:System.Windows.Forms.NumericUpDown.DownButton%2A>.  
  
### <a name="to-set-the-numeric-value"></a>Задание числового значения  
  
1. Присвойте значение свойству <xref:System.Windows.Forms.NumericUpDown.Value%2A> в коде или в окно свойств.  
  
    ```vb  
    NumericUpDown1.Value = 55  
    ```  
  
    ```csharp  
    numericUpDown1.Value = 55;  
    ```  
  
    ```cpp  
    numericUpDown1->Value = 55;  
    ```  
  
     -или-  
  
2. Вызовите метод <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> или <xref:System.Windows.Forms.NumericUpDown.DownButton%2A>, чтобы увеличить или уменьшить значение на величину, указанную в свойстве <xref:System.Windows.Forms.NumericUpDown.Increment%2A>.  
  
    ```vb  
    NumericUpDown1.UpButton()  
    ```  
  
    ```csharp  
    numericUpDown1.UpButton();  
    ```  
  
    ```cpp  
    numericUpDown1->UpButton();  
    ```  
  
### <a name="to-return-the-numeric-value"></a>Получение числового значения  
  
- Доступ к свойству <xref:System.Windows.Forms.NumericUpDown.Value%2A> в коде.  
  
    ```vb  
    If NumericUpDown1.Value >= 65 Then  
       MessageBox.Show("Age is: " & NumericUpDown1.Value.ToString)  
    Else  
       MessageBox.Show("The customer is ineligible for a senior citizen discount.")  
    End If  
    ```  
  
    ```csharp  
    if(numericUpDown1.Value >= 65)  
    {  
       MessageBox.Show("Age is: " + numericUpDown1.Value.ToString());  
    }  
    else  
    {  
       MessageBox.Show("The customer is ineligible for a senior citizen discount.");  
    }  
    ```  
  
    ```cpp  
    if(numericUpDown1->Value >= 65)  
    {  
       MessageBox::Show(String::Concat("Age is: ",  
          numericUpDown1->Value.ToString()));  
    }  
    else  
    {  
       MessageBox::Show  
          ("The customer is ineligible for a senior citizen discount.");  
    }  
    ```  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.NumericUpDown>
- <xref:System.Windows.Forms.NumericUpDown.Value%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.NumericUpDown.Increment%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.NumericUpDown.UpButton%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.NumericUpDown.DownButton%2A?displayProperty=nameWithType>
- [Элемент управления NumericUpDown](numericupdown-control-windows-forms.md)
- [Общие сведения об элементе управления NumericUpDown](numericupdown-control-overview-windows-forms.md)
