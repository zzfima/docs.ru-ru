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
# <a name="how-to-set-the-format-for-the-windows-forms-numericupdown-control"></a><span data-ttu-id="214a6-102">Практическое руководство. Определение формата элемента управления NumericUpDown в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="214a6-102">How to: Set the Format for the Windows Forms NumericUpDown Control</span></span>
<span data-ttu-id="214a6-103">Можно настроить отображение значений в элементе управления Windows Forms <xref:System.Windows.Forms.NumericUpDown> .</span><span class="sxs-lookup"><span data-stu-id="214a6-103">You can configure how values are displayed in the Windows Forms <xref:System.Windows.Forms.NumericUpDown> control.</span></span> <span data-ttu-id="214a6-104"><xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> Свойство определяет, сколько чисел отображается после десятичной запятой; значение по умолчанию — 0.</span><span class="sxs-lookup"><span data-stu-id="214a6-104">The <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> property determines how many numbers appear after the decimal point; the default is 0.</span></span> <span data-ttu-id="214a6-105">Свойство определяет, будет ли вставляться разделитель между всеми тремя десятичными цифрами; значение по умолчанию — `false`. <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A></span><span class="sxs-lookup"><span data-stu-id="214a6-105">The <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> property determines whether a separator will be inserted between every three decimal digits; the default is `false`.</span></span> <span data-ttu-id="214a6-106">Элемент управления может отображать значения в шестнадцатеричном формате вместо десятичного формата, <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> если свойство имеет `true`значение; значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="214a6-106">The control can display values in hexadecimal instead of decimal format, if the <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> property is set to `true`; the default is `false`.</span></span>  
  
### <a name="to-format-the-numeric-value"></a><span data-ttu-id="214a6-107">Форматирование числового значения</span><span class="sxs-lookup"><span data-stu-id="214a6-107">To format the numeric value</span></span>  
  
- <span data-ttu-id="214a6-108">Отобразите десятичное значение, задав <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> свойству целое число и <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> задав для `true` свойства значение `false`или.</span><span class="sxs-lookup"><span data-stu-id="214a6-108">Display a decimal value by setting the <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> property to an integer and setting the <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> property to `true` or `false`.</span></span>  
  
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
  
     <span data-ttu-id="214a6-109">-или-</span><span class="sxs-lookup"><span data-stu-id="214a6-109">-or-</span></span>  
  
- <span data-ttu-id="214a6-110">Отобразите шестнадцатеричное значение, задав <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> для `true`свойства значение.</span><span class="sxs-lookup"><span data-stu-id="214a6-110">Display a hexadecimal value by setting the <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> property to `true`.</span></span>  
  
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
    > <span data-ttu-id="214a6-111">Даже если значение отображается в форме как шестнадцатеричное, все тесты, выполняемые в <xref:System.Windows.Forms.NumericUpDown.Value%2A> свойстве, будут проверять его десятичное значение.</span><span class="sxs-lookup"><span data-stu-id="214a6-111">Even if the value is displayed on the form as hexadecimal, any tests you perform on the <xref:System.Windows.Forms.NumericUpDown.Value%2A> property will be testing its decimal value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="214a6-112">См. также</span><span class="sxs-lookup"><span data-stu-id="214a6-112">See also</span></span>

- <xref:System.Windows.Forms.NumericUpDown>
- [<span data-ttu-id="214a6-113">Элемент управления NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="214a6-113">NumericUpDown Control</span></span>](numericupdown-control-windows-forms.md)
- [<span data-ttu-id="214a6-114">Общие сведения об элементе управления NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="214a6-114">NumericUpDown Control Overview</span></span>](numericupdown-control-overview-windows-forms.md)
