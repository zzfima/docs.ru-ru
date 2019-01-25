---
title: Применение элемента управления ComboBox вместо элемента управления ListBox в Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- ListBox control [Windows Forms], adding and removing items
- ListBox control [Windows Forms], vs. ComboBox
- bound controls [Windows Forms], combo boxes
- Windows Forms controls, data binding
- ComboBox control [Windows Forms], compared to ListBox
- combo boxes [Windows Forms], compared to list boxes
- ListBox control [Windows Forms], accessing items
- ListCount property
ms.assetid: 7bcaea58-1cfa-46db-9baf-b75a69d8f9ec
ms.openlocfilehash: e6cdc7f0d54d54448a7b9ed42603b07c93eba719
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54668344"
---
# <a name="when-to-use-a-windows-forms-combobox-instead-of-a-listbox"></a><span data-ttu-id="f9826-102">Применение элемента управления ComboBox вместо элемента управления ListBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f9826-102">When to Use a Windows Forms ComboBox Instead of a ListBox</span></span>
<span data-ttu-id="f9826-103"><xref:System.Windows.Forms.ComboBox> И <xref:System.Windows.Forms.ListBox> элементы управления имеют аналогичные поведения, а в некоторых случаях они взаимозаменяемы.</span><span class="sxs-lookup"><span data-stu-id="f9826-103">The <xref:System.Windows.Forms.ComboBox> and the <xref:System.Windows.Forms.ListBox> controls have similar behaviors, and in some cases may be interchangeable.</span></span> <span data-ttu-id="f9826-104">Бывают случаи, тем не менее, если одно из них подходит больше в задачу.</span><span class="sxs-lookup"><span data-stu-id="f9826-104">There are times, however, when one or the other is more appropriate to a task.</span></span>  
  
 <span data-ttu-id="f9826-105">Как правило поле со списком используется, когда имеется список возможных вариантов, и поле со списком подходит, если вы хотите ограничить данные, вводимые в список.</span><span class="sxs-lookup"><span data-stu-id="f9826-105">Generally, a combo box is appropriate when there is a list of suggested choices, and a list box is appropriate when you want to limit input to what is on the list.</span></span> <span data-ttu-id="f9826-106">Поле со списком содержит текстовое поле, поэтому варианты, отсутствующие в списке могут быть введены в.</span><span class="sxs-lookup"><span data-stu-id="f9826-106">A combo box contains a text box field, so choices not on the list can be typed in.</span></span> <span data-ttu-id="f9826-107">Исключение возникает, когда <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> свойству <xref:System.Windows.Forms.ComboBoxStyle.DropDownList>.</span><span class="sxs-lookup"><span data-stu-id="f9826-107">The exception is when the <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> property is set to <xref:System.Windows.Forms.ComboBoxStyle.DropDownList>.</span></span> <span data-ttu-id="f9826-108">В этом случае элемент управления будет выберите элемент, при вводе его первую букву.</span><span class="sxs-lookup"><span data-stu-id="f9826-108">In that case, the control will select an item if you type its first letter.</span></span>  
  
 <span data-ttu-id="f9826-109">Кроме того поля со списком экономии места в форме.</span><span class="sxs-lookup"><span data-stu-id="f9826-109">In addition, combo boxes save space on a form.</span></span> <span data-ttu-id="f9826-110">Так как полный список не отображается, пока пользователь не щелкнет стрелку вниз, поле со списком можно легко разместить на небольшом пространстве, где не уместится поле со списком.</span><span class="sxs-lookup"><span data-stu-id="f9826-110">Because the full list is not displayed until the user clicks the down arrow, a combo box can easily fit in a small space where a list box would not fit.</span></span> <span data-ttu-id="f9826-111">Исключение возникает, когда <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> свойству <xref:System.Windows.Forms.ComboBoxStyle.Simple>: полный список и поля со списком может занимать больше места, чем поле со списком.</span><span class="sxs-lookup"><span data-stu-id="f9826-111">An exception is when the <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> property is set to <xref:System.Windows.Forms.ComboBoxStyle.Simple>: the full list is displayed, and the combo box takes up more room than a list box would.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9826-112">См. также</span><span class="sxs-lookup"><span data-stu-id="f9826-112">See also</span></span>
- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- [<span data-ttu-id="f9826-113">Практическое руководство. Добавление и удаление элементов Windows Forms ComboBox, ListBox или элементе управления CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="f9826-113">How to: Add and Remove Items from a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](../../../../docs/framework/winforms/controls/add-and-remove-items-from-a-wf-combobox.md)
- [<span data-ttu-id="f9826-114">Практическое руководство. Сортировка содержимого элемента Windows Forms ComboBox, ListBox или элементе управления CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="f9826-114">How to: Sort the Contents of a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](../../../../docs/framework/winforms/controls/sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)
- [<span data-ttu-id="f9826-115">Создание списка для выбора элементов в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f9826-115">Windows Forms Controls Used to List Options</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)
