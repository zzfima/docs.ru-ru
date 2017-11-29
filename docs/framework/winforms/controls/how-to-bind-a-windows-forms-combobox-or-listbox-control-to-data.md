---
title: "Практическое руководство. Связывание элемента управления ComboBox или ListBox с данными в Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6193e4cc86a470f046c220dc21150e0fc0bf792a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data"></a><span data-ttu-id="cbe44-102">Практическое руководство. Связывание элемента управления ComboBox или ListBox с данными в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cbe44-102">How to: Bind a Windows Forms ComboBox or ListBox Control to Data</span></span>
<span data-ttu-id="cbe44-103">Можно привязать <xref:System.Windows.Forms.ComboBox> и <xref:System.Windows.Forms.ListBox> к данным для выполнения задач, таких как просмотр данных в базе данных, ввод новых данных и изменение существующих данных.</span><span class="sxs-lookup"><span data-stu-id="cbe44-103">You can bind the <xref:System.Windows.Forms.ComboBox> and <xref:System.Windows.Forms.ListBox> to data to perform tasks such as browsing data in a database, entering new data, or editing existing data.</span></span>  
  
### <a name="to-bind-a-combobox-or-listbox-control"></a><span data-ttu-id="cbe44-104">Для привязки элемента управления ComboBox или ListBox</span><span class="sxs-lookup"><span data-stu-id="cbe44-104">To bind a ComboBox or ListBox control</span></span>  
  
1.  <span data-ttu-id="cbe44-105">Задать `DataSource` свойства для объекта источника данных.</span><span class="sxs-lookup"><span data-stu-id="cbe44-105">Set the `DataSource` property to a data source object.</span></span> <span data-ttu-id="cbe44-106">Возможные источники данных включают <xref:System.Windows.Forms.BindingSource> привязан к данных, таблицу данных, представление данных, набор данных, представление данных диспетчер, массива или любой класс, реализующий <xref:System.Collections.IList> интерфейса.</span><span class="sxs-lookup"><span data-stu-id="cbe44-106">Possible data sources include a <xref:System.Windows.Forms.BindingSource> bound to data, a data table, a data view, a dataset, a data view manager, an array, or any class that implements the <xref:System.Collections.IList> interface.</span></span> <span data-ttu-id="cbe44-107">Дополнительные сведения см. в разделе [источники данных, поддерживаемые в Windows Forms](../../../../docs/framework/winforms/data-sources-supported-by-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="cbe44-107">For more information, see [Data Sources Supported by Windows Forms](../../../../docs/framework/winforms/data-sources-supported-by-windows-forms.md).</span></span>  
  
2.  <span data-ttu-id="cbe44-108">При привязке к таблице, задать `DisplayMember` свойства имя столбца в источнике данных.</span><span class="sxs-lookup"><span data-stu-id="cbe44-108">If you are binding to a table, set the `DisplayMember` property to the name of a column in the data source.</span></span>  
  
     <span data-ttu-id="cbe44-109">\- или -</span><span class="sxs-lookup"><span data-stu-id="cbe44-109">\- or -</span></span>  
  
     <span data-ttu-id="cbe44-110">Если выполнить привязку к <xref:System.Collections.IList>, укажите элемент отображения общедоступного свойства типа в списке.</span><span class="sxs-lookup"><span data-stu-id="cbe44-110">If you are binding to an <xref:System.Collections.IList>, set the display member to a public property of the type in the list.</span></span>  
  
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
    >  <span data-ttu-id="cbe44-111">При привязке к источнику данных, который не реализует <xref:System.ComponentModel.IBindingList> интерфейса, такие как <xref:System.Collections.ArrayList>, привязанного элемента управления не будет обновлен, при обновлении источника данных.</span><span class="sxs-lookup"><span data-stu-id="cbe44-111">If you are bound to a data source that does not implement the <xref:System.ComponentModel.IBindingList> interface, such as an <xref:System.Collections.ArrayList>, the bound control's data will not be updated when the data source is updated.</span></span> <span data-ttu-id="cbe44-112">Например, если у вас есть поле со списком привязано <xref:System.Collections.ArrayList> и добавления данных <xref:System.Collections.ArrayList>, эти новые элементы не появляются в поле со списком.</span><span class="sxs-lookup"><span data-stu-id="cbe44-112">For example, if you have a combo box bound to an <xref:System.Collections.ArrayList> and data is added to the <xref:System.Collections.ArrayList>, these new items will not appear in the combo box.</span></span> <span data-ttu-id="cbe44-113">Тем не менее, можно принудительно поле со списком обновления путем вызова <xref:System.Windows.Forms.BindingManagerBase.SuspendBinding%2A> и <xref:System.Windows.Forms.BindingManagerBase.ResumeBinding%2A> методы в экземпляре <xref:System.Windows.Forms.BindingContext> класса, к которому привязан элемент управления.</span><span class="sxs-lookup"><span data-stu-id="cbe44-113">However, you can force the combo box to be updated by calling the <xref:System.Windows.Forms.BindingManagerBase.SuspendBinding%2A> and <xref:System.Windows.Forms.BindingManagerBase.ResumeBinding%2A> methods on the instance of the <xref:System.Windows.Forms.BindingContext> class to which the control is bound.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbe44-114">См. также</span><span class="sxs-lookup"><span data-stu-id="cbe44-114">See Also</span></span>  
 <xref:System.Windows.Forms.ComboBox>  
 <xref:System.Windows.Forms.ListBox>  
 [<span data-ttu-id="cbe44-115">Привязка данных Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cbe44-115">Windows Forms Data Binding</span></span>](../../../../docs/framework/winforms/windows-forms-data-binding.md)  
 [<span data-ttu-id="cbe44-116">Привязка данных и Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cbe44-116">Data Binding and Windows Forms</span></span>](../../../../docs/framework/winforms/data-binding-and-windows-forms.md)  
 [<span data-ttu-id="cbe44-117">Создание списка для выбора элементов в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cbe44-117">Windows Forms Controls Used to List Options</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)
