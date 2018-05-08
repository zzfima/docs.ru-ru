---
title: Практическое руководство. Связывание элемента управления ComboBox или ListBox с данными в Windows Forms
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
ms.openlocfilehash: 270ed1c9fab4013df72b715ce8b074d287616713
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data"></a>Практическое руководство. Связывание элемента управления ComboBox или ListBox с данными в Windows Forms
Можно привязать <xref:System.Windows.Forms.ComboBox> и <xref:System.Windows.Forms.ListBox> к данным для выполнения задач, таких как просмотр данных в базе данных, ввод новых данных и изменение существующих данных.  
  
### <a name="to-bind-a-combobox-or-listbox-control"></a>Для привязки элемента управления ComboBox или ListBox  
  
1.  Задать `DataSource` свойства для объекта источника данных. Возможные источники данных включают <xref:System.Windows.Forms.BindingSource> привязан к данных, таблицу данных, представление данных, набор данных, представление данных диспетчер, массива или любой класс, реализующий <xref:System.Collections.IList> интерфейса. Дополнительные сведения см. в разделе [источники данных, поддерживаемые в Windows Forms](../../../../docs/framework/winforms/data-sources-supported-by-windows-forms.md).  
  
2.  При привязке к таблице, задать `DisplayMember` свойства имя столбца в источнике данных.  
  
     \- или -  
  
     Если выполнить привязку к <xref:System.Collections.IList>, укажите элемент отображения общедоступного свойства типа в списке.  
  
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
    >  При привязке к источнику данных, который не реализует <xref:System.ComponentModel.IBindingList> интерфейса, такие как <xref:System.Collections.ArrayList>, привязанного элемента управления не будет обновлен, при обновлении источника данных. Например, если у вас есть поле со списком привязано <xref:System.Collections.ArrayList> и добавления данных <xref:System.Collections.ArrayList>, эти новые элементы не появляются в поле со списком. Тем не менее, можно принудительно поле со списком обновления путем вызова <xref:System.Windows.Forms.BindingManagerBase.SuspendBinding%2A> и <xref:System.Windows.Forms.BindingManagerBase.ResumeBinding%2A> методы в экземпляре <xref:System.Windows.Forms.BindingContext> класса, к которому привязан элемент управления.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.ComboBox>  
 <xref:System.Windows.Forms.ListBox>  
 [Привязка данных Windows Forms](../../../../docs/framework/winforms/windows-forms-data-binding.md)  
 [Привязка данных и Windows Forms](../../../../docs/framework/winforms/data-binding-and-windows-forms.md)  
 [Создание списка для выбора элементов в Windows Forms](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)
