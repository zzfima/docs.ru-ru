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
# <a name="how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data"></a><span data-ttu-id="f1780-102">Практическое руководство. Связывание элемента управления ComboBox или ListBox с данными в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f1780-102">How to: Bind a Windows Forms ComboBox or ListBox Control to Data</span></span>
<span data-ttu-id="f1780-103">Можно привязать <xref:System.Windows.Forms.ComboBox> и <xref:System.Windows.Forms.ListBox> к данным для выполнения таких задач, как просмотр данных в базе данных, ввод новых данных или изменение существующих данных.</span><span class="sxs-lookup"><span data-stu-id="f1780-103">You can bind the <xref:System.Windows.Forms.ComboBox> and <xref:System.Windows.Forms.ListBox> to data to perform tasks such as browsing data in a database, entering new data, or editing existing data.</span></span>  
  
### <a name="to-bind-a-combobox-or-listbox-control"></a><span data-ttu-id="f1780-104">Привязка элемента управления ComboBox или ListBox</span><span class="sxs-lookup"><span data-stu-id="f1780-104">To bind a ComboBox or ListBox control</span></span>  
  
1. <span data-ttu-id="f1780-105">Задайте для свойства `DataSource` объект источника данных.</span><span class="sxs-lookup"><span data-stu-id="f1780-105">Set the `DataSource` property to a data source object.</span></span> <span data-ttu-id="f1780-106">К возможным источникам данных относятся <xref:System.Windows.Forms.BindingSource>, привязанные к данным, таблицам данных, представлениям данных, набору данных, диспетчеру представления данных, массиву или любому классу, реализующему интерфейс <xref:System.Collections.IList>.</span><span class="sxs-lookup"><span data-stu-id="f1780-106">Possible data sources include a <xref:System.Windows.Forms.BindingSource> bound to data, a data table, a data view, a dataset, a data view manager, an array, or any class that implements the <xref:System.Collections.IList> interface.</span></span> <span data-ttu-id="f1780-107">Дополнительные сведения см. [в разделе Data Sources Supported by Windows Forms](../data-sources-supported-by-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="f1780-107">For more information, see [Data Sources Supported by Windows Forms](../data-sources-supported-by-windows-forms.md).</span></span>  
  
2. <span data-ttu-id="f1780-108">При привязке к таблице присвойте свойству `DisplayMember` имя столбца в источнике данных.</span><span class="sxs-lookup"><span data-stu-id="f1780-108">If you are binding to a table, set the `DisplayMember` property to the name of a column in the data source.</span></span>  
  
     <span data-ttu-id="f1780-109">\- или -</span><span class="sxs-lookup"><span data-stu-id="f1780-109">\- or -</span></span>  
  
     <span data-ttu-id="f1780-110">При привязке к <xref:System.Collections.IList>присвойте элементу вывода открытое свойство типа в списке.</span><span class="sxs-lookup"><span data-stu-id="f1780-110">If you are binding to an <xref:System.Collections.IList>, set the display member to a public property of the type in the list.</span></span>  
  
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
    > <span data-ttu-id="f1780-111">При привязке к источнику данных, который не реализует интерфейс <xref:System.ComponentModel.IBindingList>, например <xref:System.Collections.ArrayList>, данные привязанного элемента управления не будут обновляться при обновлении источника данных.</span><span class="sxs-lookup"><span data-stu-id="f1780-111">If you are bound to a data source that does not implement the <xref:System.ComponentModel.IBindingList> interface, such as an <xref:System.Collections.ArrayList>, the bound control's data will not be updated when the data source is updated.</span></span> <span data-ttu-id="f1780-112">Например, если имеется поле со списком, привязанное к <xref:System.Collections.ArrayList> и данные добавляются в <xref:System.Collections.ArrayList>, эти новые элементы не будут отображаться в поле со списком.</span><span class="sxs-lookup"><span data-stu-id="f1780-112">For example, if you have a combo box bound to an <xref:System.Collections.ArrayList> and data is added to the <xref:System.Collections.ArrayList>, these new items will not appear in the combo box.</span></span> <span data-ttu-id="f1780-113">Однако можно принудительно обновить поле со списком, вызвав методы <xref:System.Windows.Forms.BindingManagerBase.SuspendBinding%2A> и <xref:System.Windows.Forms.BindingManagerBase.ResumeBinding%2A> в экземпляре <xref:System.Windows.Forms.BindingContext> класса, к которому привязан элемент управления.</span><span class="sxs-lookup"><span data-stu-id="f1780-113">However, you can force the combo box to be updated by calling the <xref:System.Windows.Forms.BindingManagerBase.SuspendBinding%2A> and <xref:System.Windows.Forms.BindingManagerBase.ResumeBinding%2A> methods on the instance of the <xref:System.Windows.Forms.BindingContext> class to which the control is bound.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1780-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f1780-114">See also</span></span>

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- [<span data-ttu-id="f1780-115">Привязка данных Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f1780-115">Windows Forms Data Binding</span></span>](../windows-forms-data-binding.md)
- [<span data-ttu-id="f1780-116">Привязка данных и Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f1780-116">Data Binding and Windows Forms</span></span>](../data-binding-and-windows-forms.md)
- [<span data-ttu-id="f1780-117">Создание списка для выбора элементов в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f1780-117">Windows Forms Controls Used to List Options</span></span>](windows-forms-controls-used-to-list-options.md)
