---
title: "Практическое руководство. Определение отмеченных элементов в элементе управления CheckedListBox в Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "флажки, определение установленного состояния"
  - "CheckedListBox - элемент управления [Windows Forms], определение установленного состояния"
ms.assetid: 178b477d-27c9-489c-8914-44a9623a4d41
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Практическое руководство. Определение отмеченных элементов в элементе управления CheckedListBox в Windows Forms
Представляя данные в элементе управления Windows Forms <xref:System.Windows.Forms.CheckedListBox>, можно либо просмотреть коллекцию, сохраненную в свойстве <xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A>, либо пройти по списку с помощью метода <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A>, чтобы определить, какие элементы помечены.  Метод <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> принимает номер элемента в качестве аргумента и возвращает значение `true` или `false`.  Вопреки ожиданиям, свойства <xref:System.Windows.Forms.ListBox.SelectedItems%2A> и <xref:System.Windows.Forms.ListBox.SelectedIndices%2A> не определяют помеченные элементы: они определяют, какие элементы выделены.  
  
### Чтобы определить, какие элементы помечены в элементе управления CheckedListBox  
  
1.  Пройдите по коллекции <xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A>, начав с 0, поскольку нумерация коллекции начинается с нуля.  Обратите внимание, что этот метод выдаст номер элемента в списке помеченных элементов, а не в полном списке.  Если первый элемент списка не помечен, но помечен второй, в приведенном ниже коде отобразится текст наподобие следующего: "Checked Item 1 \= MyListItem2".  
  
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
  
     \-либо\-  
  
2.  Пройдите по коллекции <xref:System.Windows.Forms.CheckedListBox.Items%2A>, начав с 0, поскольку нумерация коллекции начинается с нуля, и вызовите метод <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> для каждого элемента.  Обратите внимание, что этот метод выдаст номер элемента в полном списке; поэтому если первый элемент списка не помечен, но помечен второй, будет выведен текст наподобие следующего: "Item 2 \= MyListItem2".  
  
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
  
## См. также  
 [Создание списка для выбора элементов в Windows Forms](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)