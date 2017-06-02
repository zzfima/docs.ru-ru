---
title: "Практическое руководство. Добавление и удаление элементов, отображаемых в элементах управления ComboBox, ListBox и CheckedListBox в Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "CheckedListBox - элемент управления [Windows Forms], добавление и удаление элементов"
  - "поля со списком, добавление элементов"
  - "поля со списком, удаление элементов"
  - "ComboBox - элемент управления [Windows Forms], добавление и удаление элементов"
  - "списки, добавление элементов"
  - "списки, удаление элементов"
  - "ListBox - элемент управления [Windows Forms], добавление и удаление элементов"
ms.assetid: 7224c8d2-4118-443e-ae1e-d7c17d1e69ee
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# Практическое руководство. Добавление и удаление элементов, отображаемых в элементах управления ComboBox, ListBox и CheckedListBox в Windows Forms
В поля со списком, списки или списки с помеченными элементами Windows Forms можно добавлять элементы множеством способов, так как эти элементы управления можно привязать к самым разнообразным источникам данных.  В этом разделе показан простейший способ, для которого привязка к данным не требуется.  Отображаемые элементы обычно представляют собой строки, однако можно использовать любой объект.  Текст, отображаемый в элементе управления, является значением, возвращаемым методом`ToString` этого объекта.  
  
### Добавление элементов  
  
1.  Добавьте строку или объект в список с помощью метода `Add` класса `ObjectCollection`.  Коллекция указывается с помощью свойства`Items` :  
  
    ```vb  
    ComboBox1.Items.Add("Tokyo")  
  
    ```  
  
    ```csharp  
    comboBox1.Items.Add("Tokyo");  
  
    ```  
  
    ```cpp  
    comboBox1->Items->Add("Tokyo");  
    ```  
  
     \-либо\-  
  
2.  Вставьте строку или объект в нужную точку списка с помощью метода`Insert` :  
  
    ```vb  
    CheckedListBox1.Items.Insert(0, "Copenhagen")  
  
    ```  
  
    ```csharp  
    checkedListBox1.Items.Insert(0, "Copenhagen");  
  
    ```  
  
    ```cpp  
    checkedListBox1->Items->Insert(0, "Copenhagen");  
    ```  
  
     \-либо\-  
  
3.  Присвойте коллекции`Items` полный массив:  
  
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
  
### Удаление элемента  
  
1.  Вызовите метод`Remove` или`RemoveAt` , чтобы удалить элементы.  
  
     Метод `Remove` имеет один атрибут, определяющий, какой элемент следует удалить. Метод`RemoveAt` удаляет элемент с указанным номером.  
  
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
  
### Чтобы удалить все элементы  
  
1.  Вызовите метод `Clear`, чтобы удалить из коллекции все элементы:  
  
    ```vb  
    ListBox1.Items.Clear()  
  
    ```  
  
    ```csharp  
    listBox1.Items.Clear();  
  
    ```  
  
    ```cpp  
    listBox1->Items->Clear();  
    ```  
  
## См. также  
 <xref:System.Windows.Forms.ComboBox>   
 <xref:System.Windows.Forms.ListBox>   
 <xref:System.Windows.Forms.CheckedListBox>   
 [Практическое руководство. Сортировка содержимого элемента управления ComboBox, ListBox или CheckedListBox в Windows Forms](../../../../docs/framework/winforms/controls/sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)   
 [Применение элемента управления ComboBox вместо элемента управления ListBox в Windows Forms](../../../../docs/framework/winforms/controls/when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)   
 [Создание списка для выбора элементов в Windows Forms](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)