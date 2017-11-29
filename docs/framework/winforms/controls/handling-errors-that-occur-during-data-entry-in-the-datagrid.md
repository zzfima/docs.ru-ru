---
title: "Пример. Обработка ошибок, связанных с вводом данных с помощью элемента управления DataGridView, в Windows Forms"
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
- error handling [Windows Forms], dataGridView control
- data grids [Windows Forms], error handling
- DataGridView control [Windows Forms], error handling
- data entry [Windows Forms], error handling
- error handling [Windows Forms], data entry
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: 30a68b85-d3af-4946-83c1-1e2d010d0511
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7c602af6799da57fec904c87da7bed77c0040eff
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-handling-errors-that-occur-during-data-entry-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="c7a90-102">Пример. Обработка ошибок, связанных с вводом данных с помощью элемента управления DataGridView, в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c7a90-102">Walkthrough: Handling Errors that Occur During Data Entry in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="c7a90-103">Обработка ошибок из базового хранилища данных является обязательной функцией приложения ввода данных.</span><span class="sxs-lookup"><span data-stu-id="c7a90-103">Handling errors from the underlying data store is a required feature for a data-entry application.</span></span> <span data-ttu-id="c7a90-104">Windows Forms <xref:System.Windows.Forms.DataGridView> управления упрощает этот процесс, предоставляя <xref:System.Windows.Forms.DataGridView.DataError> событие, которое возникает, когда хранилище данных обнаруживает нарушение ограничения или бизнес-правила.</span><span class="sxs-lookup"><span data-stu-id="c7a90-104">The Windows Forms <xref:System.Windows.Forms.DataGridView> control makes this easy by exposing the <xref:System.Windows.Forms.DataGridView.DataError> event, which is raised when the data store detects a constraint violation or a broken business rule.</span></span>  
  
 <span data-ttu-id="c7a90-105">В этом пошаговом руководстве будет извлекать строки из `Customers` таблицы в базе данных Northwind и отобразить их в <xref:System.Windows.Forms.DataGridView> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="c7a90-105">In this walkthrough, you will retrieve rows from the `Customers` table in the Northwind sample database and display them in a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="c7a90-106">Если дубликат `CustomerID` значение обнаруживается в новой строке или измененной существующей строке <xref:System.Windows.Forms.DataGridView.DataError> происходит событие, которое будет обработано, отображая <xref:System.Windows.Forms.MessageBox> с описанием исключения.</span><span class="sxs-lookup"><span data-stu-id="c7a90-106">When a duplicate `CustomerID` value is detected in a new row or an edited existing row, the <xref:System.Windows.Forms.DataGridView.DataError> event will occur, which will be handled by displaying a <xref:System.Windows.Forms.MessageBox> that describes the exception.</span></span>  
  
 <span data-ttu-id="c7a90-107">Скопируйте код из этой темы, в разделе [как: обработки ошибок, возникает во время ввода данных в элементе управления DataGridView Windows Forms](../../../../docs/framework/winforms/controls/handle-errors-that-occur-during-data-entry-in-the-datagrid.md).</span><span class="sxs-lookup"><span data-stu-id="c7a90-107">To copy the code in this topic as a single listing, see [How to: Handle Errors That Occur During Data Entry in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/handle-errors-that-occur-during-data-entry-in-the-datagrid.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c7a90-108">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="c7a90-108">Prerequisites</span></span>  
 <span data-ttu-id="c7a90-109">Для выполнения данного пошагового руководства требуется:</span><span class="sxs-lookup"><span data-stu-id="c7a90-109">In order to complete this walkthrough, you will need:</span></span>  
  
-   <span data-ttu-id="c7a90-110">Доступ к серверу с учебной базе данных "Борей" SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c7a90-110">Access to a server that has the Northwind SQL Server sample database.</span></span>  
  
## <a name="creating-the-form"></a><span data-ttu-id="c7a90-111">Создание формы</span><span class="sxs-lookup"><span data-stu-id="c7a90-111">Creating the Form</span></span>  
  
#### <a name="to-handle-data-entry-errors-in-the-datagridview-control"></a><span data-ttu-id="c7a90-112">Обработка ошибок ввода данных в элементе управления DataGridView</span><span class="sxs-lookup"><span data-stu-id="c7a90-112">To handle data-entry errors in the DataGridView control</span></span>  
  
1.  <span data-ttu-id="c7a90-113">Создайте класс, производный от <xref:System.Windows.Forms.Form> и содержит <xref:System.Windows.Forms.DataGridView> управления и <xref:System.Windows.Forms.BindingSource> компонента.</span><span class="sxs-lookup"><span data-stu-id="c7a90-113">Create a class that derives from <xref:System.Windows.Forms.Form> and contains a <xref:System.Windows.Forms.DataGridView> control and a <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
     <span data-ttu-id="c7a90-114">В следующем примере кода представлена базовая реализация и включает в себя `Main` метод.</span><span class="sxs-lookup"><span data-stu-id="c7a90-114">The following code example provides basic initialization and includes a `Main` method.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#01](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#01)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#01](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#01)]  
    [!code-csharp[System.Windows.Forms.DataGridView.DataError#02](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#02](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#02)]  
  
2.  <span data-ttu-id="c7a90-115">Реализуйте метод в определении класса формы для обработки сведения о подключении к базе данных.</span><span class="sxs-lookup"><span data-stu-id="c7a90-115">Implement a method in your form's class definition for handling the details of connecting to the database.</span></span>  
  
     <span data-ttu-id="c7a90-116">Этот пример кода использует `GetData` метод, возвращающий заполненный <xref:System.Data.DataTable> объекта.</span><span class="sxs-lookup"><span data-stu-id="c7a90-116">This code example uses a `GetData` method that returns a populated <xref:System.Data.DataTable> object.</span></span> <span data-ttu-id="c7a90-117">Убедитесь, что значение `connectionString` переменной значение, соответствующее базе данных.</span><span class="sxs-lookup"><span data-stu-id="c7a90-117">Be sure that you set the `connectionString` variable to a value that is appropriate for your database.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="c7a90-118">Хранение конфиденциальных сведений (например, пароля) в строке подключения может повлиять на безопасность приложения.</span><span class="sxs-lookup"><span data-stu-id="c7a90-118">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="c7a90-119">Использование проверки подлинности Windows (также называемой встроенными средствами безопасности) — более безопасный способ управления доступом к базе данных.</span><span class="sxs-lookup"><span data-stu-id="c7a90-119">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="c7a90-120">Дополнительные сведения см. в разделе [Защита сведений о подключении](../../../../docs/framework/data/adonet/protecting-connection-information.md).</span><span class="sxs-lookup"><span data-stu-id="c7a90-120">For more information, see [Protecting Connection Information](../../../../docs/framework/data/adonet/protecting-connection-information.md).</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#30)]  
  
3.  <span data-ttu-id="c7a90-121">Реализуйте обработчик для формы <xref:System.Windows.Forms.Form.Load> событие, которое инициализирует <xref:System.Windows.Forms.DataGridView> и <xref:System.Windows.Forms.BindingSource> и задает привязку данных.</span><span class="sxs-lookup"><span data-stu-id="c7a90-121">Implement a handler for your form's <xref:System.Windows.Forms.Form.Load> event that initializes the <xref:System.Windows.Forms.DataGridView> and <xref:System.Windows.Forms.BindingSource> and sets up the data binding.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#10)]  
  
4.  <span data-ttu-id="c7a90-122">Обрабатывать <xref:System.Windows.Forms.DataGridView.DataError> события <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="c7a90-122">Handle the <xref:System.Windows.Forms.DataGridView.DataError> event on the <xref:System.Windows.Forms.DataGridView>.</span></span>  
  
     <span data-ttu-id="c7a90-123">Если контекст ошибки операции фиксации, выведите ошибку в <xref:System.Windows.Forms.MessageBox>.</span><span class="sxs-lookup"><span data-stu-id="c7a90-123">If the context for the error is a commit operation, display the error in a <xref:System.Windows.Forms.MessageBox>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#20)]  
  
## <a name="testing-the-application"></a><span data-ttu-id="c7a90-124">Тестирование приложения</span><span class="sxs-lookup"><span data-stu-id="c7a90-124">Testing the Application</span></span>  
 <span data-ttu-id="c7a90-125">Теперь можно проверить форму, чтобы убедиться в том, что оно правильно работает.</span><span class="sxs-lookup"><span data-stu-id="c7a90-125">You can now test the form to make sure it behaves as expected.</span></span>  
  
#### <a name="to-test-the-form"></a><span data-ttu-id="c7a90-126">Чтобы проверить форму</span><span class="sxs-lookup"><span data-stu-id="c7a90-126">To test the form</span></span>  
  
-   <span data-ttu-id="c7a90-127">Нажмите клавишу F5 для запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="c7a90-127">Press F5 to run the application.</span></span>  
  
     <span data-ttu-id="c7a90-128">Вы увидите <xref:System.Windows.Forms.DataGridView> заполнения элемента управления данными из таблицы Customers.</span><span class="sxs-lookup"><span data-stu-id="c7a90-128">You will see a <xref:System.Windows.Forms.DataGridView> control filled with data from the Customers table.</span></span> <span data-ttu-id="c7a90-129">При вводе повторяющиеся значения для `CustomerID` и фиксации изменения, будет автоматически восстановлено значение ячейки, и вы увидите <xref:System.Windows.Forms.MessageBox> с указанием ошибки ввода данных.</span><span class="sxs-lookup"><span data-stu-id="c7a90-129">If you enter a duplicate value for `CustomerID` and commit the edit, the cell value will revert automatically and you will see a <xref:System.Windows.Forms.MessageBox> that displays the data entry error.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="c7a90-130">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="c7a90-130">Next Steps</span></span>  
 <span data-ttu-id="c7a90-131">Это приложение позволяет основные <xref:System.Windows.Forms.DataGridView> возможности элемента управления.</span><span class="sxs-lookup"><span data-stu-id="c7a90-131">This application gives you a basic understanding of the <xref:System.Windows.Forms.DataGridView> control's capabilities.</span></span> <span data-ttu-id="c7a90-132">Можно настроить внешний вид и поведение <xref:System.Windows.Forms.DataGridView> управления несколькими способами:</span><span class="sxs-lookup"><span data-stu-id="c7a90-132">You can customize the appearance and behavior of the <xref:System.Windows.Forms.DataGridView> control in several ways:</span></span>  
  
-   <span data-ttu-id="c7a90-133">Изменение стилей границ и заголовка.</span><span class="sxs-lookup"><span data-stu-id="c7a90-133">Change border and header styles.</span></span> <span data-ttu-id="c7a90-134">Дополнительные сведения см. в разделе [как: изменения границ и стили линий сетки в элементе управления DataGridView Windows Forms](../../../../docs/framework/winforms/controls/change-the-border-and-gridline-styles-in-the-datagrid.md).</span><span class="sxs-lookup"><span data-stu-id="c7a90-134">For more information, see [How to: Change the Border and Gridline Styles in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/change-the-border-and-gridline-styles-in-the-datagrid.md).</span></span>  
  
-   <span data-ttu-id="c7a90-135">Включения или отключения пользовательского ввода для <xref:System.Windows.Forms.DataGridView> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="c7a90-135">Enable or restrict user input to the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="c7a90-136">Дополнительные сведения см. в разделе [как: запретить добавление и удаление строк в элементе управления DataGridView Windows Forms](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md), и [как: сделать столбцы только для чтения в элементе управления DataGridView Windows Forms](../../../../docs/framework/winforms/controls/how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="c7a90-136">For more information, see [How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md), and [How to: Make Columns Read-Only in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).</span></span>  
  
-   <span data-ttu-id="c7a90-137">Проверка пользовательского ввода для <xref:System.Windows.Forms.DataGridView> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="c7a90-137">Validate user input to the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="c7a90-138">Дополнительные сведения см. в разделе [Пошаговое руководство: проверка данных в элементе управления DataGridView Windows Forms](../../../../docs/framework/winforms/controls/walkthrough-validating-data-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="c7a90-138">For more information, see [Walkthrough: Validating Data in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/walkthrough-validating-data-in-the-windows-forms-datagridview-control.md).</span></span>  
  
-   <span data-ttu-id="c7a90-139">Обработка очень больших наборов данных в виртуальном режиме.</span><span class="sxs-lookup"><span data-stu-id="c7a90-139">Handle very large data sets using virtual mode.</span></span> <span data-ttu-id="c7a90-140">Дополнительные сведения см. в разделе [Пошаговое руководство: реализация виртуального режима в элементе управления DataGridView Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="c7a90-140">For more information, see [Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md).</span></span>  
  
-   <span data-ttu-id="c7a90-141">Настройте внешний вид ячеек.</span><span class="sxs-lookup"><span data-stu-id="c7a90-141">Customize the appearance of cells.</span></span> <span data-ttu-id="c7a90-142">Дополнительные сведения см. в разделе [как: Настройка внешнего вида ячеек в элементе управления DataGridView Windows Forms](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md) и [как: набор стилей ячейки по умолчанию для элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="c7a90-142">For more information, see [How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md) and [How to: Set Default Cell Styles for the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7a90-143">См. также</span><span class="sxs-lookup"><span data-stu-id="c7a90-143">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.BindingSource>  
 [<span data-ttu-id="c7a90-144">Ввод данных с помощью элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c7a90-144">Data Entry in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="c7a90-145">Практическое руководство. Обработка ошибок, связанных с вводом данных в элемент управления DataGridView, в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c7a90-145">How to: Handle Errors That Occur During Data Entry in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/handle-errors-that-occur-during-data-entry-in-the-datagrid.md)  
 [<span data-ttu-id="c7a90-146">Пример. Проверка данных элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c7a90-146">Walkthrough: Validating Data in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="c7a90-147">Защита сведений о подключении</span><span class="sxs-lookup"><span data-stu-id="c7a90-147">Protecting Connection Information</span></span>](../../../../docs/framework/data/adonet/protecting-connection-information.md)
