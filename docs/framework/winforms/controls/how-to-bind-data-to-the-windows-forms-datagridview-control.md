---
title: Практическое руководство. Привязка данных к элементу управления Windows Forms DataGridView
ms.date: 02/08/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [Windows Forms], grids
- data binding [Windows Forms], DataGridView control
- DataGridView control [Windows Forms], data binding
ms.assetid: 1660f69c-5711-45d2-abc1-e25bc6779124
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cbcc04625a14ebc23cacfb567951bf8f76f14985
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57725107"
---
# <a name="how-to-bind-data-to-the-windows-forms-datagridview-control"></a><span data-ttu-id="4a7a6-102">Практическое руководство. Привязка данных к элементу управления Windows Forms DataGridView</span><span class="sxs-lookup"><span data-stu-id="4a7a6-102">How to: Bind data to the Windows Forms DataGridView control</span></span>

<span data-ttu-id="4a7a6-103"><xref:System.Windows.Forms.DataGridView> Элемент управления поддерживает стандартную Windows Forms модель привязки данных, поэтому его можно привязать к различным источникам данных.</span><span class="sxs-lookup"><span data-stu-id="4a7a6-103">The <xref:System.Windows.Forms.DataGridView> control supports the standard Windows Forms data binding model, so it can bind to a variety of data sources.</span></span> <span data-ttu-id="4a7a6-104">Как правило, можно выполнить привязку к <xref:System.Windows.Forms.BindingSource> , управляет взаимодействием с источником данных.</span><span class="sxs-lookup"><span data-stu-id="4a7a6-104">Usually, you bind to a <xref:System.Windows.Forms.BindingSource> that manages the interaction with the data source.</span></span> <span data-ttu-id="4a7a6-105"><xref:System.Windows.Forms.BindingSource> Может быть любой источник данных Windows Forms, который обеспечивает большую гибкость при выборе или изменении расположения ваших данных.</span><span class="sxs-lookup"><span data-stu-id="4a7a6-105">The <xref:System.Windows.Forms.BindingSource> can be any Windows Forms data source, which gives you great flexibility when choosing or modifying your data's location.</span></span> <span data-ttu-id="4a7a6-106">Дополнительные сведения об источниках данных <xref:System.Windows.Forms.DataGridView> управления поддерживает, см. в разделе [Обзор элемента управления DataGridView](datagridview-control-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="4a7a6-106">For more information about data sources the <xref:System.Windows.Forms.DataGridView> control supports, see the [DataGridView control overview](datagridview-control-overview-windows-forms.md).</span></span>  

<span data-ttu-id="4a7a6-107">Visual Studio имеет расширенную поддержку привязки данных к элементу управления DataGridView.</span><span class="sxs-lookup"><span data-stu-id="4a7a6-107">Visual Studio has extensive support for data binding to the DataGridView control.</span></span> <span data-ttu-id="4a7a6-108">Дополнительные сведения см. в разделе [Как Привязка данных к элементу управления Windows Forms DataGridView, с помощью конструктора](bind-data-to-the-datagrid-using-the-designer.md).</span><span class="sxs-lookup"><span data-stu-id="4a7a6-108">For more information, see [How to: Bind data to the Windows Forms DataGridView control using the Designer](bind-data-to-the-datagrid-using-the-designer.md).</span></span>  

<span data-ttu-id="4a7a6-109">Для подключения элемента управления DataGridView к данным:</span><span class="sxs-lookup"><span data-stu-id="4a7a6-109">To connect a DataGridView control to data:</span></span>

1. <span data-ttu-id="4a7a6-110">Реализуйте метод для обработки сведения о получении данных.</span><span class="sxs-lookup"><span data-stu-id="4a7a6-110">Implement a method to handle the details of retrieving the data.</span></span> <span data-ttu-id="4a7a6-111">В следующем коде реализуется пример `GetData` метод, который инициализирует <xref:System.Data.SqlClient.SqlDataAdapter>и использует его для заполнения <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="4a7a6-111">The following code example implements a `GetData` method that initializes a <xref:System.Data.SqlClient.SqlDataAdapter>, and uses it to populate a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="4a7a6-112">Затем он выполняет привязку <xref:System.Data.DataTable> для <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="4a7a6-112">It then binds the <xref:System.Data.DataTable> to the <xref:System.Windows.Forms.BindingSource>.</span></span> 

2. <span data-ttu-id="4a7a6-113">В форме <xref:System.Windows.Forms.Form.Load> обработчик событий, привязка <xref:System.Windows.Forms.DataGridView> управления <xref:System.Windows.Forms.BindingSource>и вызовите `GetData` метод для извлечения данных.</span><span class="sxs-lookup"><span data-stu-id="4a7a6-113">In the form's <xref:System.Windows.Forms.Form.Load> event handler, bind the <xref:System.Windows.Forms.DataGridView> control to the <xref:System.Windows.Forms.BindingSource>, and call the `GetData` method to retrieve the data.</span></span>  

## <a name="example"></a><span data-ttu-id="4a7a6-114">Пример</span><span class="sxs-lookup"><span data-stu-id="4a7a6-114">Example</span></span>

<span data-ttu-id="4a7a6-115">Это полный пример кода извлекает данные из базы данных для заполнения элемента управления DataGridView в форме Windows.</span><span class="sxs-lookup"><span data-stu-id="4a7a6-115">This complete code example retrieves data from a database to populate a DataGridView control in a Windows form.</span></span> <span data-ttu-id="4a7a6-116">В форме также находятся кнопки, чтобы перезагрузить данные и отправить изменения в базу данных.</span><span class="sxs-lookup"><span data-stu-id="4a7a6-116">The form also has buttons to reload data and submit changes to the database.</span></span>  

<span data-ttu-id="4a7a6-117">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="4a7a6-117">This example requires:</span></span> 

- <span data-ttu-id="4a7a6-118">Доступ на образец базы данных "Борей" SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4a7a6-118">Access to a Northwind SQL Server sample database.</span></span> <span data-ttu-id="4a7a6-119">Дополнительные сведения об установке образца базы данных "Борей" см. в разделе [получить образцы баз данных, примеры кода ADO.NET](../../data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="4a7a6-119">For more information about installing the Northwind sample database, see [Get the sample databases for ADO.NET code samples](../../data/adonet/sql/linq/downloading-sample-databases.md).</span></span> 

- <span data-ttu-id="4a7a6-120">Ссылки на сборки System, System.Windows.Forms, System.Data и System.Xml.</span><span class="sxs-lookup"><span data-stu-id="4a7a6-120">References to the System, System.Windows.Forms, System.Data, and System.Xml assemblies.</span></span>  

<span data-ttu-id="4a7a6-121">Чтобы построить и запустить этот пример, вставьте код в *Form1* файл кода в новый проект Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="4a7a6-121">To build and run this example, paste the code into the *Form1* code file in a new Windows Forms project.</span></span> <span data-ttu-id="4a7a6-122">Сведения о сборке из C# или командной строки Visual Basic, см. в разделе [сборка с помощью csc.exe из командной строки](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) или [построения из командной строки](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).</span><span class="sxs-lookup"><span data-stu-id="4a7a6-122">For information about building from the C# or Visual Basic command line, see [Command-line building with csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) or [Build from the command line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).</span></span>  
  
<span data-ttu-id="4a7a6-123">Заполнение `connectionString` переменных в примере со значениями пример подключения к базе данных "Борей" SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4a7a6-123">Populate the `connectionString` variable in the example with the values for your Northwind SQL Server sample database connection.</span></span> <span data-ttu-id="4a7a6-124">Проверка подлинности Windows, также называемый встроенная безопасность является более безопасный способ подключения к базе данных, чем хранение пароля в строке подключения.</span><span class="sxs-lookup"><span data-stu-id="4a7a6-124">Windows Authentication, also called integrated security, is a more secure way to connect to the database than storing a password in the connection string.</span></span> <span data-ttu-id="4a7a6-125">Дополнительные сведения о безопасности подключения, см. в разделе [Защита сведений о подключении](../../data/adonet/protecting-connection-information.md).</span><span class="sxs-lookup"><span data-stu-id="4a7a6-125">For more information about connection security, see [Protect connection information](../../data/adonet/protecting-connection-information.md).</span></span>  

[!code-csharp[System.Windows.Forms.DataGridViewBoundEditable](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/CS/datagridviewboundeditable.cs)]
[!code-vb[System.Windows.Forms.DataGridViewBoundEditable](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/VB/datagridviewboundeditable.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="4a7a6-126">См. также</span><span class="sxs-lookup"><span data-stu-id="4a7a6-126">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="4a7a6-127">Отображение данных в элементе управления Windows Forms DataGridView</span><span class="sxs-lookup"><span data-stu-id="4a7a6-127">Display data in the Windows Forms DataGridView control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="4a7a6-128">Защита сведений о подключении</span><span class="sxs-lookup"><span data-stu-id="4a7a6-128">Protect connection information</span></span>](../../data/adonet/protecting-connection-information.md)
