---
title: Доступ к конкретным элементам в элементе управления ComboBox, ListBox или CheckedListBox
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
ms.openlocfilehash: 67673ec7f136f1466d4fd091e691324c53e7de06
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746323"
---
# <a name="how-to-access-specific-items-in-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a><span data-ttu-id="9e020-102">Практическое руководство. Получение доступа к определенным элементам в элементах управления ComboBox, ListBox или CheckedListBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9e020-102">How to: Access Specific Items in a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>
<span data-ttu-id="9e020-103">Получение доступа к конкретным элементам в поле со списком Windows Forms, списка или списка флажков является важнейшей задачей.</span><span class="sxs-lookup"><span data-stu-id="9e020-103">Accessing specific items in a Windows Forms combo box, list box, or checked list box is an essential task.</span></span> <span data-ttu-id="9e020-104">Он позволяет программно определить, что находится в списке, в любой заданной позиции.</span><span class="sxs-lookup"><span data-stu-id="9e020-104">It enables you to programmatically determine what is in a list, at any given position.</span></span>  
  
### <a name="to-access-a-specific-item"></a><span data-ttu-id="9e020-105">Доступ к определенному элементу</span><span class="sxs-lookup"><span data-stu-id="9e020-105">To access a specific item</span></span>  
  
1. <span data-ttu-id="9e020-106">Запросите коллекцию `Items`, используя индекс указанного элемента:</span><span class="sxs-lookup"><span data-stu-id="9e020-106">Query the `Items` collection using the index of the specific item:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9e020-107">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="9e020-107">See also</span></span>

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- <xref:System.Windows.Forms.CheckedListBox>
- [<span data-ttu-id="9e020-108">Создание списка для выбора элементов в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9e020-108">Windows Forms Controls Used to List Options</span></span>](windows-forms-controls-used-to-list-options.md)
