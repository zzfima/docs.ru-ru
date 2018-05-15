---
title: Практическое руководство. Ввод числовых значений с помощью элемента управления NumericUpDown в Windows Forms
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
ms.openlocfilehash: e214f556224577c3029b2b742784e58932d792f3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-set-and-return-numeric-values-with-the-windows-forms-numericupdown-control"></a><span data-ttu-id="b2d82-102">Практическое руководство. Ввод числовых значений с помощью элемента управления NumericUpDown в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b2d82-102">How to: Set and Return Numeric Values with the Windows Forms NumericUpDown Control</span></span>
<span data-ttu-id="b2d82-103">Числовое значение в Windows Forms <xref:System.Windows.Forms.NumericUpDown> управления определяется его <xref:System.Windows.Forms.NumericUpDown.Value%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="b2d82-103">The numeric value of the Windows Forms <xref:System.Windows.Forms.NumericUpDown> control is determined by its <xref:System.Windows.Forms.NumericUpDown.Value%2A> property.</span></span> <span data-ttu-id="b2d82-104">Как и в случае с любым другим свойством, можно написать проверки условий для значения элемента управления.</span><span class="sxs-lookup"><span data-stu-id="b2d82-104">You can write conditional tests for the control's value just as with any other property.</span></span> <span data-ttu-id="b2d82-105">Один раз <xref:System.Windows.Forms.NumericUpDown.Value%2A> свойство задано, его можно настроить непосредственно, путем написания кода для выполнения над ним операций или можно вызвать <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> и <xref:System.Windows.Forms.NumericUpDown.DownButton%2A> методы.</span><span class="sxs-lookup"><span data-stu-id="b2d82-105">Once the <xref:System.Windows.Forms.NumericUpDown.Value%2A> property is set, you can adjust it directly by writing code to perform operations on it, or you can call the <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> and <xref:System.Windows.Forms.NumericUpDown.DownButton%2A> methods.</span></span>  
  
### <a name="to-set-the-numeric-value"></a><span data-ttu-id="b2d82-106">Чтобы задать числовое значение</span><span class="sxs-lookup"><span data-stu-id="b2d82-106">To set the numeric value</span></span>  
  
1.  <span data-ttu-id="b2d82-107">Присвоить значение <xref:System.Windows.Forms.NumericUpDown.Value%2A> свойства в коде или в окне «Свойства».</span><span class="sxs-lookup"><span data-stu-id="b2d82-107">Assign a value to the <xref:System.Windows.Forms.NumericUpDown.Value%2A> property in code or in the Properties window.</span></span>  
  
    ```vb  
    NumericUpDown1.Value = 55  
    ```  
  
    ```csharp  
    numericUpDown1.Value = 55;  
    ```  
  
    ```cpp  
    numericUpDown1->Value = 55;  
    ```  
  
     <span data-ttu-id="b2d82-108">- или -</span><span class="sxs-lookup"><span data-stu-id="b2d82-108">-or-</span></span>  
  
2.  <span data-ttu-id="b2d82-109">Вызовите <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> или <xref:System.Windows.Forms.NumericUpDown.DownButton%2A> метод для увеличения или уменьшения значения на величину, указанную в <xref:System.Windows.Forms.NumericUpDown.Increment%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="b2d82-109">Call the <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> or <xref:System.Windows.Forms.NumericUpDown.DownButton%2A> method to increase or decrease the value by the amount specified in the <xref:System.Windows.Forms.NumericUpDown.Increment%2A> property.</span></span>  
  
    ```vb  
    NumericUpDown1.UpButton()  
    ```  
  
    ```csharp  
    numericUpDown1.UpButton();  
    ```  
  
    ```cpp  
    numericUpDown1->UpButton();  
    ```  
  
### <a name="to-return-the-numeric-value"></a><span data-ttu-id="b2d82-110">Чтобы возвратить числовое значение</span><span class="sxs-lookup"><span data-stu-id="b2d82-110">To return the numeric value</span></span>  
  
-   <span data-ttu-id="b2d82-111">Доступ <xref:System.Windows.Forms.NumericUpDown.Value%2A> свойства в коде.</span><span class="sxs-lookup"><span data-stu-id="b2d82-111">Access the <xref:System.Windows.Forms.NumericUpDown.Value%2A> property in code.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b2d82-112">См. также</span><span class="sxs-lookup"><span data-stu-id="b2d82-112">See Also</span></span>  
 <xref:System.Windows.Forms.NumericUpDown>  
 <xref:System.Windows.Forms.NumericUpDown.Value%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.NumericUpDown.Increment%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.NumericUpDown.UpButton%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.NumericUpDown.DownButton%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="b2d82-113">Элемент управления NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="b2d82-113">NumericUpDown Control</span></span>](../../../../docs/framework/winforms/controls/numericupdown-control-windows-forms.md)  
 [<span data-ttu-id="b2d82-114">Общие сведения об элементе управления NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="b2d82-114">NumericUpDown Control Overview</span></span>](../../../../docs/framework/winforms/controls/numericupdown-control-overview-windows-forms.md)
