---
title: Определить Проверенные элементы в управлении CheckedListBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- check boxes [Windows Forms], determining checked state
- CheckedListBox control [Windows Forms], determining checked state
ms.assetid: 178b477d-27c9-489c-8914-44a9623a4d41
ms.openlocfilehash: 5d93a63e9c1c6aae91ecfe83590c59450a565afe
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182193"
---
# <a name="how-to-determine-checked-items-in-the-windows-forms-checkedlistbox-control"></a>Практическое руководство. Определение отмеченных элементов в элементе управления CheckedListBox в Windows Forms
При представлении данных <xref:System.Windows.Forms.CheckedListBox> в элементе управления Форм Windows можно <xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A> либо итерировать сбор, <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> хранящийся в свойстве, либо пройти через список, используя метод, чтобы определить, какие элементы проверяются. Метод <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> принимает номер индекса элемента `true` в `false`качестве аргумента и возвращает или . Вопреки ожиданиям, <xref:System.Windows.Forms.ListBox.SelectedItems%2A> свойства и <xref:System.Windows.Forms.ListBox.SelectedIndices%2A> свойства не определяют, какие элементы проверяются; они определяют, какие элементы выделены.  
  
### <a name="to-determine-checked-items-in-a-checkedlistbox-control"></a>Определить проверенные элементы в элементе управления CheckedListBox  
  
1. Итерировать через <xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A> коллекцию, начиная с 0, так как коллекция на нулевой основе. Обратите внимание, что этот метод даст вам номер элемента в списке проверенных элементов, а не общий список. Так что, если первый элемент в списке не проверен и второй элемент проверяется, код ниже будет отображать текст, как "Проверенный пункт 1 и MyListItem2".  
  
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
       for(int x = 0; x < checkedListBox1.CheckedItems.Count ; x++)  
       {  
          s = s + "Checked Item " + (x+1).ToString() + " = " + checkedListBox1.CheckedItems[x].ToString() + "\n";  
       }  
       MessageBox.Show(s);  
    }  
    ```  
  
    ```cpp  
    // Determine if there are any items checked.  
    if(checkedListBox1->CheckedItems->Count != 0)  
    {  
       // If so, loop through all checked items and print results.  
       String ^ s = "";  
       for(int x = 0; x < checkedListBox1->CheckedItems->Count; x++)  
       {  
          s = String::Concat(s, "Checked Item ", (x+1).ToString(),  
             " = ", checkedListBox1->CheckedItems[x]->ToString(),  
             "\n");  
       }  
       MessageBox::Show(s);  
    }  
    ```  
  
     - или -  
  
2. Шаг через <xref:System.Windows.Forms.CheckedListBox.Items%2A> коллекцию, начиная с 0, так как <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> коллекция на нулевой основе, и вызов метод для каждого элемента. Обратите внимание, что этот метод даст вам номер товара в общем списке, так что если первый элемент в списке не проверен и второй элемент проверяется, он будет отображать что-то вроде "Пункт 2 и MyListItem2".  
  
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
  
## <a name="see-also"></a>См. также раздел

- [Создание списка для выбора элементов в Windows Forms](windows-forms-controls-used-to-list-options.md)
