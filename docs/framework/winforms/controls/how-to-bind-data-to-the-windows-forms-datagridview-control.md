---
title: Привязка данных к элементу управления DataGridView
ms.date: 02/08/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [Windows Forms], grids
- data binding [Windows Forms], DataGridView control
- DataGridView control [Windows Forms], data binding
ms.assetid: 1660f69c-5711-45d2-abc1-e25bc6779124
ms.openlocfilehash: e2762bf363a469abf8c1e57b851d351c1cb41b62
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745078"
---
# <a name="how-to-bind-data-to-the-windows-forms-datagridview-control"></a><span data-ttu-id="f3c38-102">Как привязать данные к элементу управления Windows Forms DataGridView</span><span class="sxs-lookup"><span data-stu-id="f3c38-102">How to: Bind data to the Windows Forms DataGridView control</span></span>

<span data-ttu-id="f3c38-103">Элемент управления <xref:System.Windows.Forms.DataGridView> поддерживает стандартную Windows Forms модель привязки данных, поэтому она может выполнять привязку к различным источникам данных.</span><span class="sxs-lookup"><span data-stu-id="f3c38-103">The <xref:System.Windows.Forms.DataGridView> control supports the standard Windows Forms data binding model, so it can bind to a variety of data sources.</span></span> <span data-ttu-id="f3c38-104">Как правило, выполняется привязка к <xref:System.Windows.Forms.BindingSource>, который управляет взаимодействием с источником данных.</span><span class="sxs-lookup"><span data-stu-id="f3c38-104">Usually, you bind to a <xref:System.Windows.Forms.BindingSource> that manages the interaction with the data source.</span></span> <span data-ttu-id="f3c38-105"><xref:System.Windows.Forms.BindingSource> может быть любым источником данных Windows Forms, что обеспечивает большую гибкость при выборе или изменении расположения данных.</span><span class="sxs-lookup"><span data-stu-id="f3c38-105">The <xref:System.Windows.Forms.BindingSource> can be any Windows Forms data source, which gives you great flexibility when choosing or modifying your data's location.</span></span> <span data-ttu-id="f3c38-106">Дополнительные сведения об источниках данных, поддерживаемых элементом управления <xref:System.Windows.Forms.DataGridView>, см. в разделе [Общие сведения об элементе управления DataGridView](datagridview-control-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="f3c38-106">For more information about data sources the <xref:System.Windows.Forms.DataGridView> control supports, see the [DataGridView control overview](datagridview-control-overview-windows-forms.md).</span></span>  

<span data-ttu-id="f3c38-107">Visual Studio обладает расширенной поддержкой привязки данных к элементу управления DataGridView.</span><span class="sxs-lookup"><span data-stu-id="f3c38-107">Visual Studio has extensive support for data binding to the DataGridView control.</span></span> <span data-ttu-id="f3c38-108">Дополнительные сведения см. в разделе [инструкции. Привязка данных к элементу управления Windows Forms DataGridView с помощью конструктора](bind-data-to-the-datagrid-using-the-designer.md).</span><span class="sxs-lookup"><span data-stu-id="f3c38-108">For more information, see [How to: Bind data to the Windows Forms DataGridView control using the Designer](bind-data-to-the-datagrid-using-the-designer.md).</span></span>  

<span data-ttu-id="f3c38-109">Подключение элемента управления DataGridView к данным:</span><span class="sxs-lookup"><span data-stu-id="f3c38-109">To connect a DataGridView control to data:</span></span>

1. <span data-ttu-id="f3c38-110">Реализуйте метод для управления деталями извлечения данных.</span><span class="sxs-lookup"><span data-stu-id="f3c38-110">Implement a method to handle the details of retrieving the data.</span></span> <span data-ttu-id="f3c38-111">В следующем примере кода реализуется метод `GetData`, который инициализирует <xref:System.Data.SqlClient.SqlDataAdapter>и использует его для заполнения <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="f3c38-111">The following code example implements a `GetData` method that initializes a <xref:System.Data.SqlClient.SqlDataAdapter>, and uses it to populate a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="f3c38-112">Затем он привязывает <xref:System.Data.DataTable> к <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="f3c38-112">It then binds the <xref:System.Data.DataTable> to the <xref:System.Windows.Forms.BindingSource>.</span></span> 

2. <span data-ttu-id="f3c38-113">В обработчике событий <xref:System.Windows.Forms.Form.Load> формы свяжите элемент управления <xref:System.Windows.Forms.DataGridView> с <xref:System.Windows.Forms.BindingSource>и вызовите метод `GetData` для получения данных.</span><span class="sxs-lookup"><span data-stu-id="f3c38-113">In the form's <xref:System.Windows.Forms.Form.Load> event handler, bind the <xref:System.Windows.Forms.DataGridView> control to the <xref:System.Windows.Forms.BindingSource>, and call the `GetData` method to retrieve the data.</span></span>  

## <a name="example"></a><span data-ttu-id="f3c38-114">Пример</span><span class="sxs-lookup"><span data-stu-id="f3c38-114">Example</span></span>

<span data-ttu-id="f3c38-115">Этот полный пример кода извлекает данные из базы данных для заполнения элемента управления DataGridView в форме Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="f3c38-115">This complete code example retrieves data from a database to populate a DataGridView control in a Windows form.</span></span> <span data-ttu-id="f3c38-116">Форма также содержит кнопки для перезагрузки данных и отправки изменений в базу данных.</span><span class="sxs-lookup"><span data-stu-id="f3c38-116">The form also has buttons to reload data and submit changes to the database.</span></span>  

<span data-ttu-id="f3c38-117">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="f3c38-117">This example requires:</span></span> 

- <span data-ttu-id="f3c38-118">Доступ к образцу базы данных Northwind SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f3c38-118">Access to a Northwind SQL Server sample database.</span></span> <span data-ttu-id="f3c38-119">Дополнительные сведения об установке образца базы данных Northwind см. [в статье получение образцов баз данных для ADO.NET кода](../../data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="f3c38-119">For more information about installing the Northwind sample database, see [Get the sample databases for ADO.NET code samples](../../data/adonet/sql/linq/downloading-sample-databases.md).</span></span> 

- <span data-ttu-id="f3c38-120">Ссылки на сборки System, System. Windows. Forms, System. Data и System. XML.</span><span class="sxs-lookup"><span data-stu-id="f3c38-120">References to the System, System.Windows.Forms, System.Data, and System.Xml assemblies.</span></span>  

<span data-ttu-id="f3c38-121">Чтобы выполнить сборку и запуск этого примера, вставьте код в файл кода *Form1* в новом Windows Forms проекте.</span><span class="sxs-lookup"><span data-stu-id="f3c38-121">To build and run this example, paste the code into the *Form1* code file in a new Windows Forms project.</span></span> <span data-ttu-id="f3c38-122">Сведения о построении из командной C# строки или Visual Basic см. в разделе Построение из командной строки [с помощью csc. exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) или [Сборка из командной строки](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).</span><span class="sxs-lookup"><span data-stu-id="f3c38-122">For information about building from the C# or Visual Basic command line, see [Command-line building with csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) or [Build from the command line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).</span></span>  
  
<span data-ttu-id="f3c38-123">Заполните переменную `connectionString` в примере значениями для SQL Server образца подключения к базе данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="f3c38-123">Populate the `connectionString` variable in the example with the values for your Northwind SQL Server sample database connection.</span></span> <span data-ttu-id="f3c38-124">Проверка подлинности Windows, называемая также встроенной безопасностью, является более безопасным способом подключения к базе данных, чем сохранение пароля в строке подключения.</span><span class="sxs-lookup"><span data-stu-id="f3c38-124">Windows Authentication, also called integrated security, is a more secure way to connect to the database than storing a password in the connection string.</span></span> <span data-ttu-id="f3c38-125">Дополнительные сведения о безопасности подключения см. в разделе [Защита сведений о подключении](../../data/adonet/protecting-connection-information.md).</span><span class="sxs-lookup"><span data-stu-id="f3c38-125">For more information about connection security, see [Protect connection information](../../data/adonet/protecting-connection-information.md).</span></span>  

[!code-csharp[System.Windows.Forms.DataGridViewBoundEditable](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/CS/datagridviewboundeditable.cs)]
[!code-vb[System.Windows.Forms.DataGridViewBoundEditable](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/VB/datagridviewboundeditable.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="f3c38-126">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f3c38-126">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="f3c38-127">Отображение данных в элементе управления Windows Forms DataGridView</span><span class="sxs-lookup"><span data-stu-id="f3c38-127">Display data in the Windows Forms DataGridView control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="f3c38-128">Защита сведений о соединении</span><span class="sxs-lookup"><span data-stu-id="f3c38-128">Protect connection information</span></span>](../../data/adonet/protecting-connection-information.md)
