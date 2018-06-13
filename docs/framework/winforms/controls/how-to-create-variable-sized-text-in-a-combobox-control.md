---
title: Практическое руководство. Индивидуальное форматирование строк, отображаемых в элементе управления ComboBox
ms.date: 03/30/2017
dev_langs:
- vb
helpviewer_keywords:
- text [Windows Forms], drawing in combo boxes
- examples [Windows Forms], ComboBox control
- combo boxes [Windows Forms], drawing text
- ComboBox control [Windows Forms], examples [C#]
- ComboBox control [Windows Forms], drawing custom text
ms.assetid: ce39b9ea-e626-49fe-bd5a-f567f6d157df
ms.openlocfilehash: a76e1d78cd9fade550fa846488e8bf4a93a21c31
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33533235"
---
# <a name="how-to-create-variable-sized-text-in-a-combobox-control"></a><span data-ttu-id="27ba1-102">Практическое руководство. Индивидуальное форматирование строк, отображаемых в элементе управления ComboBox</span><span class="sxs-lookup"><span data-stu-id="27ba1-102">How to: Create Variable Sized Text in a ComboBox Control</span></span>
<span data-ttu-id="27ba1-103">В этом примере показано пользовательское рисование текста в <xref:System.Windows.Forms.ComboBox> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="27ba1-103">This example demonstrates custom drawing of text in a <xref:System.Windows.Forms.ComboBox> control.</span></span> <span data-ttu-id="27ba1-104">Если элемент удовлетворяет определенным критериям, он рисуется более крупным шрифтом и красным.</span><span class="sxs-lookup"><span data-stu-id="27ba1-104">When an item meets a certain criteria, it is drawn in a larger font and turned red.</span></span>  
  
## <a name="example"></a><span data-ttu-id="27ba1-105">Пример</span><span class="sxs-lookup"><span data-stu-id="27ba1-105">Example</span></span>  
  
```vb  
Private Sub ComboBox1_MeasureItem(ByVal sender As Object, ByVal e As _  
System.Windows.Forms.MeasureItemEventArgs) Handles ComboBox1.MeasureItem  
    Dim bFont As New Font("Arial", 8, FontStyle.Bold)  
    Dim lFont As New Font("Arial", 12, FontStyle.Bold)  
    Dim siText As SizeF  
  
    If ComboBox1.Items().Item(e.Index) = "Two" Then  
        siText = e.Graphics.MeasureString(ComboBox1.Items().Item(e.Index), _  
lFont)  
    Else  
        siText = e.Graphics.MeasureString(ComboBox1.Items().Item(e.Index), bFont)  
    End If  
  
    e.ItemHeight = siText.Height  
    e.ItemWidth = siText.Width  
End Sub  
  
Private Sub ComboBox1_DrawItem(ByVal sender As Object, ByVal e As _  
System.Windows.Forms.DrawItemEventArgs) Handles ComboBox1.DrawItem  
    Dim g As Graphics = e.Graphics  
    Dim bFont As New Font("Arial", 8, FontStyle.Bold)  
    Dim lFont As New Font("Arial", 12, FontStyle.Bold)  
  
    If ComboBox1.Items().Item(e.Index) = "Two" Then  
        g.DrawString(ComboBox1.Items.Item(e.Index), lfont, Brushes.Red, _  
e.Bounds.X, e.Bounds.Y)  
    Else  
        g.DrawString(ComboBox1.Items.Item(e.Index), bFont, Brushes.Black, e.Bounds.X, e.Bounds.Y)  
    End If  
End Sub  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="27ba1-106">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="27ba1-106">Compiling the Code</span></span>  
 <span data-ttu-id="27ba1-107">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="27ba1-107">This example requires:</span></span>  
  
-   <span data-ttu-id="27ba1-108">В Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="27ba1-108">A Windows form.</span></span>  
  
-   <span data-ttu-id="27ba1-109">Объект <xref:System.Windows.Forms.ComboBox> управления с именем `ListBox1` с тремя элементами в <xref:System.Windows.Forms.ComboBox.Items%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="27ba1-109">A <xref:System.Windows.Forms.ComboBox> control named `ListBox1` with three items in the <xref:System.Windows.Forms.ComboBox.Items%2A> property.</span></span> <span data-ttu-id="27ba1-110">В этом примере имена трех элементов `"One", Two", and Three"`.</span><span class="sxs-lookup"><span data-stu-id="27ba1-110">In this example, the three items are named `"One", Two", and Three"`.</span></span> <span data-ttu-id="27ba1-111"><xref:System.Windows.Forms.ComboBox.DrawMode%2A> Свойство `ComboBox1` должно быть присвоено <xref:System.Windows.Forms.DrawMode.OwnerDrawVariable>.</span><span class="sxs-lookup"><span data-stu-id="27ba1-111">The <xref:System.Windows.Forms.ComboBox.DrawMode%2A> property of `ComboBox1` must be set to <xref:System.Windows.Forms.DrawMode.OwnerDrawVariable>.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="27ba1-112">Этот метод также применяется к <xref:System.Windows.Forms.ListBox> управления, можно заменить <xref:System.Windows.Forms.ListBox> для <xref:System.Windows.Forms.ComboBox>.</span><span class="sxs-lookup"><span data-stu-id="27ba1-112">This technique is also applicable to the <xref:System.Windows.Forms.ListBox> control — you can substitute a <xref:System.Windows.Forms.ListBox> for the <xref:System.Windows.Forms.ComboBox>.</span></span>  
  
-   <span data-ttu-id="27ba1-113">Ссылки на пространства имен <xref:System.Windows.Forms?displayProperty=nameWithType> и <xref:System.Drawing?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="27ba1-113">References to the <xref:System.Windows.Forms?displayProperty=nameWithType> and <xref:System.Drawing?displayProperty=nameWithType> namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27ba1-114">См. также</span><span class="sxs-lookup"><span data-stu-id="27ba1-114">See Also</span></span>  
 <xref:System.Windows.Forms.ComboBox.DrawItem>  
 <xref:System.Windows.Forms.DrawItemEventArgs>  
 <xref:System.Windows.Forms.ComboBox.MeasureItem>  
 [<span data-ttu-id="27ba1-115">Элементы управления со встроенной поддержкой рисования владельцем</span><span class="sxs-lookup"><span data-stu-id="27ba1-115">Controls with Built-In Owner-Drawing Support</span></span>](../../../../docs/framework/winforms/controls/controls-with-built-in-owner-drawing-support.md)  
 [<span data-ttu-id="27ba1-116">Элемент управления ListBox</span><span class="sxs-lookup"><span data-stu-id="27ba1-116">ListBox Control</span></span>](../../../../docs/framework/winforms/controls/listbox-control-windows-forms.md)  
 [<span data-ttu-id="27ba1-117">Элемент управления ComboBox</span><span class="sxs-lookup"><span data-stu-id="27ba1-117">ComboBox Control</span></span>](../../../../docs/framework/winforms/controls/combobox-control-windows-forms.md)
