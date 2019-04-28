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
ms.openlocfilehash: 5957a44c7b07aa1b8d8df32667f023c0873ec1de
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62013196"
---
# <a name="how-to-set-the-format-for-the-windows-forms-numericupdown-control"></a><span data-ttu-id="d4707-102">Практическое руководство. Определение формата элемента управления NumericUpDown в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d4707-102">How to: Set the Format for the Windows Forms NumericUpDown Control</span></span>
<span data-ttu-id="d4707-103">Можно настроить способ отображения значения в Windows Forms <xref:System.Windows.Forms.NumericUpDown> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="d4707-103">You can configure how values are displayed in the Windows Forms <xref:System.Windows.Forms.NumericUpDown> control.</span></span> <span data-ttu-id="d4707-104"><xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> Свойство определяет, сколько номеров появляются после десятичной запятой значение по умолчанию — 0.</span><span class="sxs-lookup"><span data-stu-id="d4707-104">The <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> property determines how many numbers appear after the decimal point; the default is 0.</span></span> <span data-ttu-id="d4707-105"><xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> Ли между каждой из трех цифр вставляется разделитель определяет значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="d4707-105">The <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> property determines whether a separator will be inserted between every three decimal digits; the default is `false`.</span></span> <span data-ttu-id="d4707-106">Элемент управления может отображать значения в шестнадцатеричном формате вместо десятичного формата, если <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> свойству `true`; по умолчанию используется `false`.</span><span class="sxs-lookup"><span data-stu-id="d4707-106">The control can display values in hexadecimal instead of decimal format, if the <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> property is set to `true`; the default is `false`.</span></span>  
  
### <a name="to-format-the-numeric-value"></a><span data-ttu-id="d4707-107">Чтобы отформатировать числовое значение</span><span class="sxs-lookup"><span data-stu-id="d4707-107">To format the numeric value</span></span>  
  
- <span data-ttu-id="d4707-108">Отобразить значение десятичного числа, задав <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> свойство целочисленное значение, а параметр <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> свойства `true` или `false`.</span><span class="sxs-lookup"><span data-stu-id="d4707-108">Display a decimal value by setting the <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> property to an integer and setting the <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> property to `true` or `false`.</span></span>  
  
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
  
     <span data-ttu-id="d4707-109">-или-</span><span class="sxs-lookup"><span data-stu-id="d4707-109">-or-</span></span>  
  
- <span data-ttu-id="d4707-110">Отобразите шестнадцатеричное число, задав <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> свойства `true`.</span><span class="sxs-lookup"><span data-stu-id="d4707-110">Display a hexadecimal value by setting the <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> property to `true`.</span></span>  
  
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
    >  <span data-ttu-id="d4707-111">Даже если значение отображается в форме как шестнадцатеричное значение, все тесты, выполните на <xref:System.Windows.Forms.NumericUpDown.Value%2A> свойство будет тестироваться его десятичное значение.</span><span class="sxs-lookup"><span data-stu-id="d4707-111">Even if the value is displayed on the form as hexadecimal, any tests you perform on the <xref:System.Windows.Forms.NumericUpDown.Value%2A> property will be testing its decimal value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4707-112">См. также</span><span class="sxs-lookup"><span data-stu-id="d4707-112">See also</span></span>

- <xref:System.Windows.Forms.NumericUpDown>
- [<span data-ttu-id="d4707-113">Элемент управления NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="d4707-113">NumericUpDown Control</span></span>](numericupdown-control-windows-forms.md)
- [<span data-ttu-id="d4707-114">Общие сведения об элементе управления NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="d4707-114">NumericUpDown Control Overview</span></span>](numericupdown-control-overview-windows-forms.md)
