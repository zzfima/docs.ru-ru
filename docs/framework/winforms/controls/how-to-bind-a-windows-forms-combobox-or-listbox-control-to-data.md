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
ms.openlocfilehash: f361526c44f8fbb9ab282fe15ae109b67e8f01dd
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69922743"
---
# <a name="how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data"></a><span data-ttu-id="380fe-102">Практическое руководство. Связывание элемента управления ComboBox или ListBox с данными в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="380fe-102">How to: Bind a Windows Forms ComboBox or ListBox Control to Data</span></span>
<span data-ttu-id="380fe-103">Можно привязывать <xref:System.Windows.Forms.ComboBox> и <xref:System.Windows.Forms.ListBox> к данным для выполнения таких задач, как просмотр данных в базе данных, ввод новых данных или изменение существующих данных.</span><span class="sxs-lookup"><span data-stu-id="380fe-103">You can bind the <xref:System.Windows.Forms.ComboBox> and <xref:System.Windows.Forms.ListBox> to data to perform tasks such as browsing data in a database, entering new data, or editing existing data.</span></span>  
  
### <a name="to-bind-a-combobox-or-listbox-control"></a><span data-ttu-id="380fe-104">Привязка элемента управления ComboBox или ListBox</span><span class="sxs-lookup"><span data-stu-id="380fe-104">To bind a ComboBox or ListBox control</span></span>  
  
1. <span data-ttu-id="380fe-105">`DataSource` Задайте свойство для объекта источника данных.</span><span class="sxs-lookup"><span data-stu-id="380fe-105">Set the `DataSource` property to a data source object.</span></span> <span data-ttu-id="380fe-106">Возможные источники данных включают <xref:System.Windows.Forms.BindingSource> в себя привязку к данным, таблице данных, представлению данных, набору данных, диспетчеру представления данных, массиву или любому классу, <xref:System.Collections.IList> реализующему интерфейс.</span><span class="sxs-lookup"><span data-stu-id="380fe-106">Possible data sources include a <xref:System.Windows.Forms.BindingSource> bound to data, a data table, a data view, a dataset, a data view manager, an array, or any class that implements the <xref:System.Collections.IList> interface.</span></span> <span data-ttu-id="380fe-107">Дополнительные сведения см. [в разделе Data Sources Supported by Windows Forms](../data-sources-supported-by-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="380fe-107">For more information, see [Data Sources Supported by Windows Forms](../data-sources-supported-by-windows-forms.md).</span></span>  
  
2. <span data-ttu-id="380fe-108">При привязке к таблице присвойте `DisplayMember` свойству имя столбца в источнике данных.</span><span class="sxs-lookup"><span data-stu-id="380fe-108">If you are binding to a table, set the `DisplayMember` property to the name of a column in the data source.</span></span>  
  
     <span data-ttu-id="380fe-109">\- или -</span><span class="sxs-lookup"><span data-stu-id="380fe-109">\- or -</span></span>  
  
     <span data-ttu-id="380fe-110">При привязке к <xref:System.Collections.IList>присвойте элементу вывода открытое свойство типа в списке.</span><span class="sxs-lookup"><span data-stu-id="380fe-110">If you are binding to an <xref:System.Collections.IList>, set the display member to a public property of the type in the list.</span></span>  
  
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
    > <span data-ttu-id="380fe-111">При привязке к источнику данных, который не реализует <xref:System.ComponentModel.IBindingList> интерфейс, например <xref:System.Collections.ArrayList>, данные привязанного элемента управления не будут обновляться при обновлении источника данных.</span><span class="sxs-lookup"><span data-stu-id="380fe-111">If you are bound to a data source that does not implement the <xref:System.ComponentModel.IBindingList> interface, such as an <xref:System.Collections.ArrayList>, the bound control's data will not be updated when the data source is updated.</span></span> <span data-ttu-id="380fe-112">Например, при наличии поля со списком, привязанного к <xref:System.Collections.ArrayList> <xref:System.Collections.ArrayList>, и к которому добавляются данные, эти новые элементы не будут отображаться в поле со списком.</span><span class="sxs-lookup"><span data-stu-id="380fe-112">For example, if you have a combo box bound to an <xref:System.Collections.ArrayList> and data is added to the <xref:System.Collections.ArrayList>, these new items will not appear in the combo box.</span></span> <span data-ttu-id="380fe-113">Однако можно принудительно обновить поле со списком, вызвав <xref:System.Windows.Forms.BindingManagerBase.SuspendBinding%2A> методы и <xref:System.Windows.Forms.BindingManagerBase.ResumeBinding%2A> <xref:System.Windows.Forms.BindingContext> в экземпляре класса, к которому привязан элемент управления.</span><span class="sxs-lookup"><span data-stu-id="380fe-113">However, you can force the combo box to be updated by calling the <xref:System.Windows.Forms.BindingManagerBase.SuspendBinding%2A> and <xref:System.Windows.Forms.BindingManagerBase.ResumeBinding%2A> methods on the instance of the <xref:System.Windows.Forms.BindingContext> class to which the control is bound.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="380fe-114">См. также</span><span class="sxs-lookup"><span data-stu-id="380fe-114">See also</span></span>

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- [<span data-ttu-id="380fe-115">Привязка данных Windows Forms</span><span class="sxs-lookup"><span data-stu-id="380fe-115">Windows Forms Data Binding</span></span>](../windows-forms-data-binding.md)
- [<span data-ttu-id="380fe-116">Привязка данных и Windows Forms</span><span class="sxs-lookup"><span data-stu-id="380fe-116">Data Binding and Windows Forms</span></span>](../data-binding-and-windows-forms.md)
- [<span data-ttu-id="380fe-117">Создание списка для выбора элементов в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="380fe-117">Windows Forms Controls Used to List Options</span></span>](windows-forms-controls-used-to-list-options.md)
