---
title: Практическое руководство. Добавление и удаление элементов, отображаемых в элементах управления ComboBox, ListBox и CheckedListBox в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- combo boxes [Windows Forms], adding items
- list boxes [Windows Forms], removing items
- ComboBox control [Windows Forms], adding and removing items
- ListBox control [Windows Forms], adding and removing items
- list boxes [Windows Forms], adding items
- combo boxes [Windows Forms], removing items
- CheckedListBox control [Windows Forms], adding and removing items
ms.assetid: 7224c8d2-4118-443e-ae1e-d7c17d1e69ee
ms.openlocfilehash: f9319ffe5e9c4f06565648565ce21dec6fc672f9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33527191"
---
# <a name="how-to-add-and-remove-items-from-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a><span data-ttu-id="502a0-102">Практическое руководство. Добавление и удаление элементов, отображаемых в элементах управления ComboBox, ListBox и CheckedListBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="502a0-102">How to: Add and Remove Items from a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>
<span data-ttu-id="502a0-103">Элементы могут добавляться в Windows Forms со списком, списке или списки с помеченными различными способами, так как эти элементы управления могут быть привязаны к различным источникам данных.</span><span class="sxs-lookup"><span data-stu-id="502a0-103">Items can be added to a Windows Forms combo box, list box, or checked list box in a variety of ways, because these controls can be bound to a variety of data sources.</span></span> <span data-ttu-id="502a0-104">Однако в этом разделе демонстрирует простейший метод и привязка к данным не требуется.</span><span class="sxs-lookup"><span data-stu-id="502a0-104">However, this topic demonstrates the simplest method and requires no data binding.</span></span> <span data-ttu-id="502a0-105">Элементы отображаются обычно представляют собой строки; Тем не менее можно использовать любой объект.</span><span class="sxs-lookup"><span data-stu-id="502a0-105">The items displayed are usually strings; however, any object can be used.</span></span> <span data-ttu-id="502a0-106">Текст, отображаемый в элементе управления является значения, возвращенного объекта `ToString` метод.</span><span class="sxs-lookup"><span data-stu-id="502a0-106">The text that is displayed in the control is the value returned by the object's `ToString` method.</span></span>  
  
### <a name="to-add-items"></a><span data-ttu-id="502a0-107">Добавление элементов</span><span class="sxs-lookup"><span data-stu-id="502a0-107">To add items</span></span>  
  
1.  <span data-ttu-id="502a0-108">Добавьте строку или объект в список с помощью `Add` метод `ObjectCollection` класса.</span><span class="sxs-lookup"><span data-stu-id="502a0-108">Add the string or object to the list by using the `Add` method of the `ObjectCollection` class.</span></span> <span data-ttu-id="502a0-109">Коллекция указывается с помощью `Items` свойство:</span><span class="sxs-lookup"><span data-stu-id="502a0-109">The collection is referenced using the `Items` property:</span></span>  
  
    ```vb  
    ComboBox1.Items.Add("Tokyo")  
    ```  
  
    ```csharp  
    comboBox1.Items.Add("Tokyo");  
    ```  
  
    ```cpp  
    comboBox1->Items->Add("Tokyo");  
    ```  
  
     - <span data-ttu-id="502a0-110">или</span><span class="sxs-lookup"><span data-stu-id="502a0-110">or -</span></span>  
  
2.  <span data-ttu-id="502a0-111">Вставьте строку или объект в нужную точку в списке с `Insert` метод:</span><span class="sxs-lookup"><span data-stu-id="502a0-111">Insert the string or object at the desired point in the list with the `Insert` method:</span></span>  
  
    ```vb  
    CheckedListBox1.Items.Insert(0, "Copenhagen")  
    ```  
  
    ```csharp  
    checkedListBox1.Items.Insert(0, "Copenhagen");  
    ```  
  
    ```cpp  
    checkedListBox1->Items->Insert(0, "Copenhagen");  
    ```  
  
     - <span data-ttu-id="502a0-112">или</span><span class="sxs-lookup"><span data-stu-id="502a0-112">or -</span></span>  
  
3.  <span data-ttu-id="502a0-113">Присвойте полный массив `Items` коллекции:</span><span class="sxs-lookup"><span data-stu-id="502a0-113">Assign an entire array to the `Items` collection:</span></span>  
  
    ```vb  
    Dim ItemObject(9) As System.Object  
    Dim i As Integer  
       For i = 0 To 9  
       ItemObject(i) = "Item" & i  
    Next i  
    ListBox1.Items.AddRange(ItemObject)  
    ```  
  
    ```csharp  
    System.Object[] ItemObject = new System.Object[10];  
    for (int i = 0; i <= 9; i++)  
    {  
       ItemObject[i] = "Item" + i;  
    }  
    listBox1.Items.AddRange(ItemObject);  
    ```  
  
    ```cpp  
    Array<System::Object^>^ ItemObject = gcnew Array<System::Object^>(10);  
    for (int i = 0; i <= 9; i++)  
    {  
       ItemObject[i] = String::Concat("Item", i.ToString());  
    }  
    listBox1->Items->AddRange(ItemObject);  
    ```  
  
### <a name="to-remove-an-item"></a><span data-ttu-id="502a0-114">Удаление элемента</span><span class="sxs-lookup"><span data-stu-id="502a0-114">To remove an item</span></span>  
  
1.  <span data-ttu-id="502a0-115">Вызовите `Remove` или `RemoveAt` метод для удаления элементов.</span><span class="sxs-lookup"><span data-stu-id="502a0-115">Call the `Remove` or `RemoveAt` method to delete items.</span></span>  
  
     <span data-ttu-id="502a0-116">`Remove` имеет один аргумент, который задает удаляемый элемент.`RemoveAt`</span><span class="sxs-lookup"><span data-stu-id="502a0-116">`Remove` has one argument that specifies the item to remove.`RemoveAt`</span></span> <span data-ttu-id="502a0-117">Удаляет элемент с заданным индексом.</span><span class="sxs-lookup"><span data-stu-id="502a0-117">removes the item with the specified index number.</span></span>  
  
    ```vb  
    ' To remove item with index 0:  
    ComboBox1.Items.RemoveAt(0)  
    ' To remove currently selected item:  
    ComboBox1.Items.Remove(ComboBox1.SelectedItem)  
    ' To remove "Tokyo" item:  
    ComboBox1.Items.Remove("Tokyo")  
    ```  
  
    ```csharp  
    // To remove item with index 0:  
    comboBox1.Items.RemoveAt(0);  
    // To remove currently selected item:  
    comboBox1.Items.Remove(comboBox1.SelectedItem);  
    // To remove "Tokyo" item:  
    comboBox1.Items.Remove("Tokyo");  
    ```  
  
    ```cpp  
    // To remove item with index 0:  
    comboBox1->Items->RemoveAt(0);  
    // To remove currently selected item:  
    comboBox1->Items->Remove(comboBox1->SelectedItem);  
    // To remove "Tokyo" item:  
    comboBox1->Items->Remove("Tokyo");  
    ```  
  
### <a name="to-remove-all-items"></a><span data-ttu-id="502a0-118">Чтобы удалить все элементы</span><span class="sxs-lookup"><span data-stu-id="502a0-118">To remove all items</span></span>  
  
1.  <span data-ttu-id="502a0-119">Вызовите `Clear` метод, чтобы удалить все элементы из коллекции:</span><span class="sxs-lookup"><span data-stu-id="502a0-119">Call the `Clear` method to remove all items from the collection:</span></span>  
  
    ```vb  
    ListBox1.Items.Clear()  
    ```  
  
    ```csharp  
    listBox1.Items.Clear();  
    ```  
  
    ```cpp  
    listBox1->Items->Clear();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="502a0-120">См. также</span><span class="sxs-lookup"><span data-stu-id="502a0-120">See Also</span></span>  
 <xref:System.Windows.Forms.ComboBox>  
 <xref:System.Windows.Forms.ListBox>  
 <xref:System.Windows.Forms.CheckedListBox>  
 [<span data-ttu-id="502a0-121">Практическое руководство. Сортировка содержимого элемента управления ComboBox, ListBox или CheckedListBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="502a0-121">How to: Sort the Contents of a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](../../../../docs/framework/winforms/controls/sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)  
 [<span data-ttu-id="502a0-122">Применение элемента управления ComboBox вместо элемента управления ListBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="502a0-122">When to Use a Windows Forms ComboBox Instead of a ListBox</span></span>](../../../../docs/framework/winforms/controls/when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)  
 [<span data-ttu-id="502a0-123">Создание списка для выбора элементов в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="502a0-123">Windows Forms Controls Used to List Options</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)
