---
title: "Практическое руководство. Сортировка и фильтрация данных ADO.NET с помощью компонента BindingSource в Windows Forms"
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
- sorting data
- data sorting [Windows Forms], ADO.NET
- data [Windows Forms], filtering
- BindingSource component [Windows Forms], sorting and filtering data
- filtering [Windows Forms], ADO.NET
- data [Windows Forms], sorting
- ADO.NET [Windows Forms]
ms.assetid: 6c206daf-d706-4602-9dbe-435343052063
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 46947e314394d56b5ef0439f33910bb493012db3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-sort-and-filter-adonet-data-with-the-windows-forms-bindingsource-component"></a><span data-ttu-id="9ca19-102">Практическое руководство. Сортировка и фильтрация данных ADO.NET с помощью компонента BindingSource в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9ca19-102">How to: Sort and Filter ADO.NET Data with the Windows Forms BindingSource Component</span></span>
<span data-ttu-id="9ca19-103">Можно предоставить возможность фильтрации и сортировки <xref:System.Windows.Forms.BindingSource> управление с помощью <xref:System.Windows.Forms.BindingSource.Sort%2A> и <xref:System.Windows.Forms.BindingSource.Filter%2A> свойства.</span><span class="sxs-lookup"><span data-stu-id="9ca19-103">You can expose the sorting and filtering capability of <xref:System.Windows.Forms.BindingSource> control through the <xref:System.Windows.Forms.BindingSource.Sort%2A> and <xref:System.Windows.Forms.BindingSource.Filter%2A> properties.</span></span> <span data-ttu-id="9ca19-104">Можно применить простую сортировку, когда в источнике данных <xref:System.ComponentModel.IBindingList>, и можно применить фильтрацию и если источником данных является <xref:System.ComponentModel.IBindingListView>.</span><span class="sxs-lookup"><span data-stu-id="9ca19-104">You can apply simple sorting when the underlying data source is an <xref:System.ComponentModel.IBindingList>, and you can apply filtering and advanced sorting when the data source is an <xref:System.ComponentModel.IBindingListView>.</span></span> <span data-ttu-id="9ca19-105"><xref:System.Windows.Forms.BindingSource.Sort%2A> Свойства требуется стандартный [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] синтаксис: строка, представляющая имя столбца данных в источнике данных, за которым следует `ASC` или `DESC` для указания, является ли список должны быть отсортированы в возрастающем или убывающем порядке.</span><span class="sxs-lookup"><span data-stu-id="9ca19-105">The <xref:System.Windows.Forms.BindingSource.Sort%2A> property requires standard [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] syntax: a string representing the name of a column of data in the data source followed by `ASC` or `DESC` to indicate whether the list should be sorted in ascending or descending order.</span></span> <span data-ttu-id="9ca19-106">Можно задать расширенной сортировки или несколько столбцов сортировки, разделив их каждого столбца с разделителем в виде запятой.</span><span class="sxs-lookup"><span data-stu-id="9ca19-106">You can set advanced sorting or multiple-column sorting by separating each column with a comma separator.</span></span> <span data-ttu-id="9ca19-107"><xref:System.Windows.Forms.BindingSource.Filter%2A> Свойство принимает строковое выражение.</span><span class="sxs-lookup"><span data-stu-id="9ca19-107">The <xref:System.Windows.Forms.BindingSource.Filter%2A> property takes a string expression.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9ca19-108">Хранение конфиденциальных сведений (например, пароля) в строке подключения может повлиять на безопасность приложения.</span><span class="sxs-lookup"><span data-stu-id="9ca19-108">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="9ca19-109">Использование проверки подлинности Windows (также называемой встроенными средствами безопасности) — более безопасный способ управления доступом к базе данных.</span><span class="sxs-lookup"><span data-stu-id="9ca19-109">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="9ca19-110">Дополнительные сведения см. в разделе [Защита сведений о подключении](../../../../docs/framework/data/adonet/protecting-connection-information.md).</span><span class="sxs-lookup"><span data-stu-id="9ca19-110">For more information, see [Protecting Connection Information](../../../../docs/framework/data/adonet/protecting-connection-information.md).</span></span>  
  
### <a name="to-filter-data-with-the-bindingsource"></a><span data-ttu-id="9ca19-111">Для фильтрации данных с использованием компонента BindingSource</span><span class="sxs-lookup"><span data-stu-id="9ca19-111">To filter data with the BindingSource</span></span>  
  
-   <span data-ttu-id="9ca19-112">Задать <xref:System.Windows.Forms.BindingSource.Filter%2A> свойства необходимое выражение.</span><span class="sxs-lookup"><span data-stu-id="9ca19-112">Set the <xref:System.Windows.Forms.BindingSource.Filter%2A> property to expression that you want.</span></span>  
  
     <span data-ttu-id="9ca19-113">В следующем примере кода выражение представляет собой имя столбца, за которым следует значение для столбца.</span><span class="sxs-lookup"><span data-stu-id="9ca19-113">In the following code example, the expression is a column name followed by value that you want for the column.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#11)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#11)]  
  
### <a name="to-sort-data-with-the-bindingsource"></a><span data-ttu-id="9ca19-114">Сортировка данных с использованием компонента BindingSource</span><span class="sxs-lookup"><span data-stu-id="9ca19-114">To sort data with the BindingSource</span></span>  
  
1.  <span data-ttu-id="9ca19-115">Задать <xref:System.Windows.Forms.BindingSource.Sort%2A> свойство имени столбца, который будет следуют `ASC` или `DESC` чтобы указать порядок сортировки по возрастанию или по убыванию.</span><span class="sxs-lookup"><span data-stu-id="9ca19-115">Set the <xref:System.Windows.Forms.BindingSource.Sort%2A> property to the column name that you want followed by `ASC` or `DESC` to indicate the ascending or descending order.</span></span>  
  
2.  <span data-ttu-id="9ca19-116">Несколько столбцов разделяются запятыми.</span><span class="sxs-lookup"><span data-stu-id="9ca19-116">Separate multiple columns with a comma.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#12)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#12)]  
  
## <a name="example"></a><span data-ttu-id="9ca19-117">Пример</span><span class="sxs-lookup"><span data-stu-id="9ca19-117">Example</span></span>  
 <span data-ttu-id="9ca19-118">В следующем примере кода загружает данные из таблицы Customers базы данных "Борей" в <xref:System.Windows.Forms.DataGridView> управления, фильтры и сортирует отображаемых данных.</span><span class="sxs-lookup"><span data-stu-id="9ca19-118">The following code example loads data from the Customers table of the Northwind sample database into a <xref:System.Windows.Forms.DataGridView> control, and filters and sorts the displayed data.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9ca19-119">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="9ca19-119">Compiling the Code</span></span>  
 <span data-ttu-id="9ca19-120">Чтобы выполнить этот пример, вставьте код в форму, содержащую <xref:System.Windows.Forms.BindingSource> с именем `BindingSource1` и <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="9ca19-120">To run this example, paste the code into a form that contains a <xref:System.Windows.Forms.BindingSource> named `BindingSource1` and a <xref:System.Windows.Forms.DataGridView> named `dataGridView1`.</span></span> <span data-ttu-id="9ca19-121">Обрабатывать <xref:System.Windows.Forms.Form.Load> событий для формы и вызовите `InitializeSortedFilteredBindingSource` в методе обработчика событий загрузки.</span><span class="sxs-lookup"><span data-stu-id="9ca19-121">Handle the <xref:System.Windows.Forms.Form.Load> event for the form and call `InitializeSortedFilteredBindingSource` in the load event handler method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ca19-122">См. также</span><span class="sxs-lookup"><span data-stu-id="9ca19-122">See Also</span></span>  
 <xref:System.Windows.Forms.BindingSource.Sort%2A>  
 <xref:System.Windows.Forms.BindingSource.Filter%2A>  
 [<span data-ttu-id="9ca19-123">Практическое руководство. Установка образцов баз данных</span><span class="sxs-lookup"><span data-stu-id="9ca19-123">How to: Install Sample Databases</span></span>](http://msdn.microsoft.com/library/ed1291f6-604c-4972-ae22-0345c6dea12e)  
 [<span data-ttu-id="9ca19-124">Компонент BindingSource</span><span class="sxs-lookup"><span data-stu-id="9ca19-124">BindingSource Component</span></span>](../../../../docs/framework/winforms/controls/bindingsource-component.md)
