---
title: Привязка элемента управления ComboBox или ListBox к данным
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data [Windows Forms], binding to controls
- list boxes [Windows Forms], data binding
- ComboBox control [Windows Forms], data binding
- data binding [Windows Forms], combo boxes
- ListBox control [Windows Forms], data binding
- combo boxes [Windows Forms], data binding
- bound controls [Windows Forms], combo boxes
- Windows Forms controls, data binding
- data-bound controls [Windows Forms], Windows Forms
ms.assetid: dfd7f081-8bea-4a41-86a3-86a1934828ef
ms.openlocfilehash: 99d9b53b32d6faae888b134d4ed486980c05a75b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742032"
---
# <a name="how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data"></a>Практическое руководство. Связывание элемента управления ComboBox или ListBox с данными в Windows Forms
Можно привязать <xref:System.Windows.Forms.ComboBox> и <xref:System.Windows.Forms.ListBox> к данным для выполнения таких задач, как просмотр данных в базе данных, ввод новых данных или изменение существующих данных.  
  
### <a name="to-bind-a-combobox-or-listbox-control"></a>Привязка элемента управления ComboBox или ListBox  
  
1. Задайте для свойства `DataSource` объект источника данных. К возможным источникам данных относятся <xref:System.Windows.Forms.BindingSource>, привязанные к данным, таблицам данных, представлениям данных, набору данных, диспетчеру представления данных, массиву или любому классу, реализующему интерфейс <xref:System.Collections.IList>. Дополнительные сведения см. [в разделе Data Sources Supported by Windows Forms](../data-sources-supported-by-windows-forms.md).  
  
2. При привязке к таблице присвойте свойству `DisplayMember` имя столбца в источнике данных.  
  
     \- или -  
  
     При привязке к <xref:System.Collections.IList>присвойте элементу вывода открытое свойство типа в списке.  
  
    ```vb  
    Private Sub BindComboBox()  
      ComboBox1.DataSource = DataSet1.Tables("Suppliers")  
      ComboBox1.DisplayMember = "ProductName"  
    End Sub  
    ```  
  
    ```csharp  
    private void BindComboBox()  
    {  
      comboBox1.DataSource = dataSet1.Tables["Suppliers"];  
      comboBox1.DisplayMember = "ProductName";  
    }  
    ```  
  
    > [!NOTE]
    > При привязке к источнику данных, который не реализует интерфейс <xref:System.ComponentModel.IBindingList>, например <xref:System.Collections.ArrayList>, данные привязанного элемента управления не будут обновляться при обновлении источника данных. Например, если имеется поле со списком, привязанное к <xref:System.Collections.ArrayList> и данные добавляются в <xref:System.Collections.ArrayList>, эти новые элементы не будут отображаться в поле со списком. Однако можно принудительно обновить поле со списком, вызвав методы <xref:System.Windows.Forms.BindingManagerBase.SuspendBinding%2A> и <xref:System.Windows.Forms.BindingManagerBase.ResumeBinding%2A> в экземпляре <xref:System.Windows.Forms.BindingContext> класса, к которому привязан элемент управления.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- [Привязка данных Windows Forms](../windows-forms-data-binding.md)
- [Привязка данных и Windows Forms](../data-binding-and-windows-forms.md)
- [Создание списка для выбора элементов в Windows Forms](windows-forms-controls-used-to-list-options.md)
