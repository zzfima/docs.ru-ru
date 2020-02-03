---
title: Сортировка и фильтрация данных ADO.NET с помощью компонента BindingSource
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sorting data
- data sorting [Windows Forms], ADO.NET
- data [Windows Forms], filtering
- BindingSource component [Windows Forms], sorting and filtering data
- filtering [Windows Forms], ADO.NET
- data [Windows Forms], sorting
- ADO.NET [Windows Forms]
ms.assetid: 6c206daf-d706-4602-9dbe-435343052063
ms.openlocfilehash: cf1da3bb94b26449eb72b0e4930b262236487acc
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742973"
---
# <a name="how-to-sort-and-filter-adonet-data-with-the-windows-forms-bindingsource-component"></a><span data-ttu-id="eaaba-102">Практическое руководство. Сортировка и фильтрация данных ADO.NET с помощью компонента BindingSource в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="eaaba-102">How to: Sort and Filter ADO.NET Data with the Windows Forms BindingSource Component</span></span>
<span data-ttu-id="eaaba-103">Можно предоставить возможность сортировки и фильтрации <xref:System.Windows.Forms.BindingSource> управления с помощью свойств <xref:System.Windows.Forms.BindingSource.Sort%2A> и <xref:System.Windows.Forms.BindingSource.Filter%2A>.</span><span class="sxs-lookup"><span data-stu-id="eaaba-103">You can expose the sorting and filtering capability of <xref:System.Windows.Forms.BindingSource> control through the <xref:System.Windows.Forms.BindingSource.Sort%2A> and <xref:System.Windows.Forms.BindingSource.Filter%2A> properties.</span></span> <span data-ttu-id="eaaba-104">Можно применить простую сортировку, если базовый источник данных является <xref:System.ComponentModel.IBindingList>ом, и можно применить фильтрацию и расширенную сортировку, если источником данных является <xref:System.ComponentModel.IBindingListView>.</span><span class="sxs-lookup"><span data-stu-id="eaaba-104">You can apply simple sorting when the underlying data source is an <xref:System.ComponentModel.IBindingList>, and you can apply filtering and advanced sorting when the data source is an <xref:System.ComponentModel.IBindingListView>.</span></span> <span data-ttu-id="eaaba-105">Для свойства <xref:System.Windows.Forms.BindingSource.Sort%2A> требуется стандартный синтаксис ADO.NET: строка, представляющая имя столбца данных в источнике данных, за которым следует `ASC` или `DESC`, чтобы указать, должен ли список быть отсортирован в порядке возрастания или убывания.</span><span class="sxs-lookup"><span data-stu-id="eaaba-105">The <xref:System.Windows.Forms.BindingSource.Sort%2A> property requires standard ADO.NET syntax: a string representing the name of a column of data in the data source followed by `ASC` or `DESC` to indicate whether the list should be sorted in ascending or descending order.</span></span> <span data-ttu-id="eaaba-106">Можно задать расширенную сортировку или сортировку по нескольким столбцам, разделив каждый столбец разделителями-запятыми.</span><span class="sxs-lookup"><span data-stu-id="eaaba-106">You can set advanced sorting or multiple-column sorting by separating each column with a comma separator.</span></span> <span data-ttu-id="eaaba-107">Свойство <xref:System.Windows.Forms.BindingSource.Filter%2A> принимает строковое выражение.</span><span class="sxs-lookup"><span data-stu-id="eaaba-107">The <xref:System.Windows.Forms.BindingSource.Filter%2A> property takes a string expression.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="eaaba-108">Хранение конфиденциальных сведений (например, пароля) в строке подключения может повлиять на безопасность приложения.</span><span class="sxs-lookup"><span data-stu-id="eaaba-108">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="eaaba-109">Использование проверки подлинности Windows (также называемой встроенными средствами безопасности) — более безопасный способ управления доступом к базе данных.</span><span class="sxs-lookup"><span data-stu-id="eaaba-109">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="eaaba-110">Дополнительные сведения см. в разделе [Защита сведений о подключении](../../data/adonet/protecting-connection-information.md).</span><span class="sxs-lookup"><span data-stu-id="eaaba-110">For more information, see [Protecting Connection Information](../../data/adonet/protecting-connection-information.md).</span></span>  
  
### <a name="to-filter-data-with-the-bindingsource"></a><span data-ttu-id="eaaba-111">Фильтрация данных с помощью BindingSource</span><span class="sxs-lookup"><span data-stu-id="eaaba-111">To filter data with the BindingSource</span></span>  
  
- <span data-ttu-id="eaaba-112">Задайте для свойства <xref:System.Windows.Forms.BindingSource.Filter%2A> нужное выражение.</span><span class="sxs-lookup"><span data-stu-id="eaaba-112">Set the <xref:System.Windows.Forms.BindingSource.Filter%2A> property to expression that you want.</span></span>  
  
     <span data-ttu-id="eaaba-113">В следующем примере кода выражение представляет собой имя столбца, за которым следует значение, которое требуется для столбца.</span><span class="sxs-lookup"><span data-stu-id="eaaba-113">In the following code example, the expression is a column name followed by value that you want for the column.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#11)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#11)]  
  
### <a name="to-sort-data-with-the-bindingsource"></a><span data-ttu-id="eaaba-114">Сортировка данных с помощью BindingSource</span><span class="sxs-lookup"><span data-stu-id="eaaba-114">To sort data with the BindingSource</span></span>  
  
1. <span data-ttu-id="eaaba-115">Задайте для свойства <xref:System.Windows.Forms.BindingSource.Sort%2A> имя нужного столбца, а затем `ASC` или `DESC`, чтобы указать порядок по возрастанию или по убыванию.</span><span class="sxs-lookup"><span data-stu-id="eaaba-115">Set the <xref:System.Windows.Forms.BindingSource.Sort%2A> property to the column name that you want followed by `ASC` or `DESC` to indicate the ascending or descending order.</span></span>  
  
2. <span data-ttu-id="eaaba-116">Несколько столбцов разделяются запятыми.</span><span class="sxs-lookup"><span data-stu-id="eaaba-116">Separate multiple columns with a comma.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#12)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#12)]  
  
## <a name="example"></a><span data-ttu-id="eaaba-117">Пример</span><span class="sxs-lookup"><span data-stu-id="eaaba-117">Example</span></span>  
 <span data-ttu-id="eaaba-118">Следующий пример кода загружает данные из таблицы Customers образца базы данных Northwind в элемент управления <xref:System.Windows.Forms.DataGridView>, а также фильтрует и сортирует отображаемые данные.</span><span class="sxs-lookup"><span data-stu-id="eaaba-118">The following code example loads data from the Customers table of the Northwind sample database into a <xref:System.Windows.Forms.DataGridView> control, and filters and sorts the displayed data.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="eaaba-119">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="eaaba-119">Compiling the Code</span></span>  
 <span data-ttu-id="eaaba-120">Чтобы выполнить этот пример, вставьте код в форму, содержащую <xref:System.Windows.Forms.BindingSource> с именем `BindingSource1` и <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="eaaba-120">To run this example, paste the code into a form that contains a <xref:System.Windows.Forms.BindingSource> named `BindingSource1` and a <xref:System.Windows.Forms.DataGridView> named `dataGridView1`.</span></span> <span data-ttu-id="eaaba-121">Обработайте событие <xref:System.Windows.Forms.Form.Load> для формы и вызовите `InitializeSortedFilteredBindingSource` в методе обработчика событий Load.</span><span class="sxs-lookup"><span data-stu-id="eaaba-121">Handle the <xref:System.Windows.Forms.Form.Load> event for the form and call `InitializeSortedFilteredBindingSource` in the load event handler method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eaaba-122">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="eaaba-122">See also</span></span>

- <xref:System.Windows.Forms.BindingSource.Sort%2A>
- <xref:System.Windows.Forms.BindingSource.Filter%2A>
- <span data-ttu-id="eaaba-123">[Практическое руководство. Установка образцов баз данных](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/8b6y4c7s(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="eaaba-123">[How to: Install Sample Databases](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/8b6y4c7s(v=vs.120))</span></span>
- [<span data-ttu-id="eaaba-124">Компонент BindingSource</span><span class="sxs-lookup"><span data-stu-id="eaaba-124">BindingSource Component</span></span>](bindingsource-component.md)
