---
title: Практическое руководство. Определение отмеченных элементов в элементе управления CheckedListBox в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- check boxes [Windows Forms], determining checked state
- CheckedListBox control [Windows Forms], determining checked state
ms.assetid: 178b477d-27c9-489c-8914-44a9623a4d41
ms.openlocfilehash: 98b4ef7c4ac73e1560bd5c68f22898e46585d082
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-determine-checked-items-in-the-windows-forms-checkedlistbox-control"></a>Практическое руководство. Определение отмеченных элементов в элементе управления CheckedListBox в Windows Forms
Представляя данные в Windows Forms <xref:System.Windows.Forms.CheckedListBox> управления, можно либо пройти по коллекции, хранящейся в <xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A> свойства или просмотрите список, используя <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> метод, чтобы определить, какие элементы помечены. <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> Метод принимает номер элемента в качестве аргумента и возвращает `true` или `false`. В отличие от ожидаемого <xref:System.Windows.Forms.ListBox.SelectedItems%2A> и <xref:System.Windows.Forms.ListBox.SelectedIndices%2A> свойства не определяют, какие элементы проверяются; они определяют, какие элементы будут выделены.  
  
### <a name="to-determine-checked-items-in-a-checkedlistbox-control"></a>Чтобы определить, какие элементы в элементе управления CheckedListBox  
  
1.  Итерации <xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A> коллекции, начиная с 0, поскольку коллекция начинается с нуля. Обратите внимание, что этот метод выдаст номер элемента в списке помеченных элементов, а не в полном списке. Если первый элемент в списке не проверяется, и второй элемент проверяется, приведенный ниже код будет отображать текст как «Checked Item 1 = MyListItem2».  
  
    ```vb  
    ' Determine if there are any items checked.  
    If CheckedListBox1.CheckedItems.Count <> 0 Then  
       ' If so, loop through all checked items and print results.  
       Dim x As Integer  
       Dim s As String = ""  
       For x = 0 To CheckedListBox1.CheckedItems.Count - 1  
          s = s & "Checked Item " & (x + 1).ToString & " = " & CheckedListBox1.CheckedItems(x).ToString & ControlChars.CrLf  
       Next x  
       MessageBox.Show(s)  
    End If  
    ```  
  
    ```csharp  
    // Determine if there are any items checked.  
    if(checkedListBox1.CheckedItems.Count != 0)  
    {  
       // If so, loop through all checked items and print results.  
       string s = "";  
       for(int x = 0; x <= checkedListBox1.CheckedItems.Count - 1 ; x++)  
       {  
          s = s + "Checked Item " + (x+1).ToString() + " = " + checkedListBox1.CheckedItems[x].ToString() + "\n";  
       }  
    MessageBox.Show (s);  
    }  
    ```  
  
    ```cpp  
    // Determine if there are any items checked.  
    if(checkedListBox1->CheckedItems->Count != 0)  
    {  
       // If so, loop through all checked items and print results.  
       String ^ s = "";  
       for(int x = 0; x <= checkedListBox1->CheckedItems->Count - 1; x++)  
       {  
          s = String::Concat(s, "Checked Item ", (x+1).ToString(),  
             " = ", checkedListBox1->CheckedItems[x]->ToString(),  
             "\n");  
       }  
       MessageBox::Show(s);  
    }  
    ```  
  
     - или  
  
2.  Пошаговое выполнение <xref:System.Windows.Forms.CheckedListBox.Items%2A> коллекции, начиная с 0, поскольку коллекция начинается с нуля и вызовите <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> для каждого элемента. Обратите внимание, что этот метод выдаст номер элемента в общий список, если первый элемент в списке не проверяется и второй элемент установлен, то он будет отображать примерно «элемент 2 = MyListItem2».  
  
    ```vb  
    Dim i As Integer  
    Dim s As String  
    s = "Checked Items:" & ControlChars.CrLf  
    For i = 0 To (CheckedListBox1.Items.Count - 1)  
       If CheckedListBox1.GetItemChecked(i) = True Then  
          s = s & "Item " & (i + 1).ToString & " = " & CheckedListBox1.Items(i).ToString & ControlChars.CrLf  
       End If  
    Next  
    MessageBox.Show(s)  
    ```  
  
    ```csharp  
    int i;  
    string s;   
    s = "Checked items:\n" ;  
    for (i = 0; i <= (checkedListBox1.Items.Count-1); i++)  
    {  
       if (checkedListBox1.GetItemChecked(i))  
       {  
          s = s + "Item " + (i+1).ToString() + " = " + checkedListBox1.Items[i].ToString() + "\n";  
       }  
    }  
    MessageBox.Show (s);  
    ```  
  
    ```cpp  
    int i;  
    String ^ s;   
    s = "Checked items:\n" ;  
    for (i = 0; i <= (checkedListBox1->Items->Count-1); i++)  
    {  
       if (checkedListBox1->GetItemChecked(i))  
       {  
          s = String::Concat(s, "Item ", (i+1).ToString(), " = ",  
             checkedListBox1->Item[i]->ToString(), "\n");  
       }  
    }  
    MessageBox::Show(s);  
    ```  
  
## <a name="see-also"></a>См. также  
 [Создание списка для выбора элементов в Windows Forms](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)
