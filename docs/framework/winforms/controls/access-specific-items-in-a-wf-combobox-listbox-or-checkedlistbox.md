---
title: Практическое руководство. Получение доступа к определенным элементам в Windows Forms ComboBox, ListBox или элементе управления CheckedListBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ComboBox control [Windows Forms], accessing items
- ListBox control [Windows Forms], returning item information
- list boxes [Windows Forms], accessing items
- ListBox control [Windows Forms], accessing items
- combo boxes [Windows Forms], accessing items
- CheckedListBox control [Windows Forms], accessing items
ms.assetid: 1216742f-bcf9-4ff8-8a62-d7c9053c2b96
ms.openlocfilehash: 33dcefa39cd6a8c981d03ce5fb63fc8135613640
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57714025"
---
# <a name="how-to-access-specific-items-in-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a>Практическое руководство. Получение доступа к определенным элементам в Windows Forms ComboBox, ListBox или элементе управления CheckedListBox
Доступ к определенным элементам в поле со списком Windows Forms, поле со списком или список с установленными флажками является важнейшей задачей. Он позволяет программно определить с помощью списка, в любом месте.  
  
### <a name="to-access-a-specific-item"></a>Для доступа к определенного элемента  
  
1.  Запрос `Items` коллекции с помощью индекса определенного элемента:  
  
    ```vb  
    Private Function GetItemText(i As Integer) As String  
       ' Return the text of the item using the index:  
       Return ComboBox1.Items(i).ToString  
    End Function  
    ```  
  
    ```csharp  
    private string GetItemText(int i)  
    {  
       // Return the text of the item using the index:  
       return (comboBox1.Items[i].ToString());  
    }  
    ```  
  
    ```cpp  
    private:  
       String^ GetItemText(int i)  
       {  
          // Return the text of the item using the index:  
          return (comboBox1->Items->Item[i]->ToString());  
       }  
    ```  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- <xref:System.Windows.Forms.CheckedListBox>
- [Создание списка для выбора элементов в Windows Forms](windows-forms-controls-used-to-list-options.md)
