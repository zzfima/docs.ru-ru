---
title: Связать данные с управлением DataGridView
ms.date: 02/08/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [Windows Forms], grids
- data binding [Windows Forms], DataGridView control
- DataGridView control [Windows Forms], data binding
ms.assetid: 1660f69c-5711-45d2-abc1-e25bc6779124
ms.openlocfilehash: 643dcd37cd1bb3f8b5938fedff66c67cd68278ff
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182277"
---
# <a name="how-to-bind-data-to-the-windows-forms-datagridview-control"></a><span data-ttu-id="b2c97-102">Как: Привязать данные к управлению Data Forms DataGridView</span><span class="sxs-lookup"><span data-stu-id="b2c97-102">How to: Bind data to the Windows Forms DataGridView control</span></span>

<span data-ttu-id="b2c97-103">Элемент <xref:System.Windows.Forms.DataGridView> управления поддерживает стандартную модель связывания данных Windows Forms, поэтому он может связываться с различными источниками данных.</span><span class="sxs-lookup"><span data-stu-id="b2c97-103">The <xref:System.Windows.Forms.DataGridView> control supports the standard Windows Forms data binding model, so it can bind to a variety of data sources.</span></span> <span data-ttu-id="b2c97-104">Обычно вы привязываетесь к <xref:System.Windows.Forms.BindingSource> тому, кто управляет взаимодействием с источником данных.</span><span class="sxs-lookup"><span data-stu-id="b2c97-104">Usually, you bind to a <xref:System.Windows.Forms.BindingSource> that manages the interaction with the data source.</span></span> <span data-ttu-id="b2c97-105">Это <xref:System.Windows.Forms.BindingSource> может быть любой источник данных Windows Forms, который дает вам большую гибкость при выборе или изменении местоположения данных.</span><span class="sxs-lookup"><span data-stu-id="b2c97-105">The <xref:System.Windows.Forms.BindingSource> can be any Windows Forms data source, which gives you great flexibility when choosing or modifying your data's location.</span></span> <span data-ttu-id="b2c97-106">Для получения дополнительной информации об источниках данных, <xref:System.Windows.Forms.DataGridView> которые поддерживает элемент управления, см. [DataGridView control overview](datagridview-control-overview-windows-forms.md)</span><span class="sxs-lookup"><span data-stu-id="b2c97-106">For more information about data sources the <xref:System.Windows.Forms.DataGridView> control supports, see the [DataGridView control overview](datagridview-control-overview-windows-forms.md).</span></span>  

<span data-ttu-id="b2c97-107">Visual Studio имеет широкую поддержку связывания данных с управлением DataGridView.</span><span class="sxs-lookup"><span data-stu-id="b2c97-107">Visual Studio has extensive support for data binding to the DataGridView control.</span></span> <span data-ttu-id="b2c97-108">Для получения дополнительной информации [см. Как: Привязать данные к управлению Data Forms DataGridView с помощью designer.](bind-data-to-the-datagrid-using-the-designer.md)</span><span class="sxs-lookup"><span data-stu-id="b2c97-108">For more information, see [How to: Bind data to the Windows Forms DataGridView control using the Designer](bind-data-to-the-datagrid-using-the-designer.md).</span></span>  

<span data-ttu-id="b2c97-109">Чтобы подключить элемент управления DataGridView к данным:</span><span class="sxs-lookup"><span data-stu-id="b2c97-109">To connect a DataGridView control to data:</span></span>

1. <span data-ttu-id="b2c97-110">Реализация метода обработки деталей получения данных.</span><span class="sxs-lookup"><span data-stu-id="b2c97-110">Implement a method to handle the details of retrieving the data.</span></span> <span data-ttu-id="b2c97-111">Следующий пример кода `GetData` реализует <xref:System.Data.SqlClient.SqlDataAdapter>метод, который инициализирует, <xref:System.Data.DataTable>и использует его для заполнения .</span><span class="sxs-lookup"><span data-stu-id="b2c97-111">The following code example implements a `GetData` method that initializes a <xref:System.Data.SqlClient.SqlDataAdapter>, and uses it to populate a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="b2c97-112">Затем он связывает <xref:System.Data.DataTable> к <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="b2c97-112">It then binds the <xref:System.Data.DataTable> to the <xref:System.Windows.Forms.BindingSource>.</span></span>

2. <span data-ttu-id="b2c97-113">В <xref:System.Windows.Forms.Form.Load> обработчике событий в <xref:System.Windows.Forms.DataGridView> форме <xref:System.Windows.Forms.BindingSource>свяжите элемент `GetData` управления с методом для извлечения данных.</span><span class="sxs-lookup"><span data-stu-id="b2c97-113">In the form's <xref:System.Windows.Forms.Form.Load> event handler, bind the <xref:System.Windows.Forms.DataGridView> control to the <xref:System.Windows.Forms.BindingSource>, and call the `GetData` method to retrieve the data.</span></span>  

## <a name="example"></a><span data-ttu-id="b2c97-114">Пример</span><span class="sxs-lookup"><span data-stu-id="b2c97-114">Example</span></span>

<span data-ttu-id="b2c97-115">Этот полный пример кода извлекает данные из базы данных для заполнения элемента управления DataGridView в форме Windows.</span><span class="sxs-lookup"><span data-stu-id="b2c97-115">This complete code example retrieves data from a database to populate a DataGridView control in a Windows form.</span></span> <span data-ttu-id="b2c97-116">Форма также имеет кнопки для перезагрузки данных и представления изменений в базу данных.</span><span class="sxs-lookup"><span data-stu-id="b2c97-116">The form also has buttons to reload data and submit changes to the database.</span></span>  

<span data-ttu-id="b2c97-117">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="b2c97-117">This example requires:</span></span>

- <span data-ttu-id="b2c97-118">Доступ к выборочной базе данных Northwind S'L Server.</span><span class="sxs-lookup"><span data-stu-id="b2c97-118">Access to a Northwind SQL Server sample database.</span></span> <span data-ttu-id="b2c97-119">Для получения дополнительной информации об установке базы данных образца Northwind см [ADO.NET.](../../data/adonet/sql/linq/downloading-sample-databases.md)</span><span class="sxs-lookup"><span data-stu-id="b2c97-119">For more information about installing the Northwind sample database, see [Get the sample databases for ADO.NET code samples](../../data/adonet/sql/linq/downloading-sample-databases.md).</span></span>

- <span data-ttu-id="b2c97-120">Ссылки на сборки системы, System.Windows.Forms, System.Data и System.Xml.</span><span class="sxs-lookup"><span data-stu-id="b2c97-120">References to the System, System.Windows.Forms, System.Data, and System.Xml assemblies.</span></span>  

<span data-ttu-id="b2c97-121">Чтобы создать и запустить этот пример, вставьте код в файл кода *Form1* в новом проекте Форм Windows.</span><span class="sxs-lookup"><span data-stu-id="b2c97-121">To build and run this example, paste the code into the *Form1* code file in a new Windows Forms project.</span></span> <span data-ttu-id="b2c97-122">Для получения информации о здании из командной строки C или Visual Basic [Build from the command line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) [см.](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)</span><span class="sxs-lookup"><span data-stu-id="b2c97-122">For information about building from the C# or Visual Basic command line, see [Command-line building with csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) or [Build from the command line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).</span></span>  
  
<span data-ttu-id="b2c97-123">Заполните `connectionString` переменную в примере значениями для подключения к базе данных Northwind s'L Server.</span><span class="sxs-lookup"><span data-stu-id="b2c97-123">Populate the `connectionString` variable in the example with the values for your Northwind SQL Server sample database connection.</span></span> <span data-ttu-id="b2c97-124">Проверка подлинности Windows, также называемая интегрированной безопасностью, является более безопасным способом подключения к базе данных, чем хранение пароля в строке соединения.</span><span class="sxs-lookup"><span data-stu-id="b2c97-124">Windows Authentication, also called integrated security, is a more secure way to connect to the database than storing a password in the connection string.</span></span> <span data-ttu-id="b2c97-125">Для получения дополнительной информации о безопасности соединения [см.](../../data/adonet/protecting-connection-information.md)</span><span class="sxs-lookup"><span data-stu-id="b2c97-125">For more information about connection security, see [Protect connection information](../../data/adonet/protecting-connection-information.md).</span></span>  

[!code-csharp[System.Windows.Forms.DataGridViewBoundEditable](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/CS/datagridviewboundeditable.cs)]
[!code-vb[System.Windows.Forms.DataGridViewBoundEditable](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/VB/datagridviewboundeditable.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="b2c97-126">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b2c97-126">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="b2c97-127">Отображение данных в управлении DataFormsGridView</span><span class="sxs-lookup"><span data-stu-id="b2c97-127">Display data in the Windows Forms DataGridView control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="b2c97-128">Защита информации о подключении</span><span class="sxs-lookup"><span data-stu-id="b2c97-128">Protect connection information</span></span>](../../data/adonet/protecting-connection-information.md)
