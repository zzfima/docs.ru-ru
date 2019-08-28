---
title: Пошаговое руководство. Обработка ошибок, связанных с вводом данных с помощью элемента управления DataGridView, в Windows Forms
ms.date: 03/30/2017
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
ms.openlocfilehash: cee6fe3b049378fa7bbe2585a3607049eaf231bc
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046079"
---
# <a name="walkthrough-handling-errors-that-occur-during-data-entry-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="bfe37-102">Пошаговое руководство. Обработка ошибок, связанных с вводом данных с помощью элемента управления DataGridView, в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bfe37-102">Walkthrough: Handling Errors that Occur During Data Entry in the Windows Forms DataGridView Control</span></span>

<span data-ttu-id="bfe37-103">Обработка ошибок из базового хранилища данных является обязательной функцией для приложения ввода данных.</span><span class="sxs-lookup"><span data-stu-id="bfe37-103">Handling errors from the underlying data store is a required feature for a data-entry application.</span></span> <span data-ttu-id="bfe37-104">Элемент управления <xref:System.Windows.Forms.DataGridView> Windows Forms делает это простым, предоставляя <xref:System.Windows.Forms.DataGridView.DataError> событие, которое возникает, когда хранилище данных обнаруживает нарушение ограничения или бизнес-правило.</span><span class="sxs-lookup"><span data-stu-id="bfe37-104">The Windows Forms <xref:System.Windows.Forms.DataGridView> control makes this easy by exposing the <xref:System.Windows.Forms.DataGridView.DataError> event, which is raised when the data store detects a constraint violation or a broken business rule.</span></span>

<span data-ttu-id="bfe37-105">В этом пошаговом руководстве вы получите строки из `Customers` таблицы в образце базы данных Northwind и отобразите их <xref:System.Windows.Forms.DataGridView> в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="bfe37-105">In this walkthrough, you will retrieve rows from the `Customers` table in the Northwind sample database and display them in a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="bfe37-106">При обнаружении `CustomerID` повторяющегося значения в новой строке или измененной существующей строке <xref:System.Windows.Forms.DataGridView.DataError> возникает событие, которое будет обработано отображением <xref:System.Windows.Forms.MessageBox> , описывающим исключение.</span><span class="sxs-lookup"><span data-stu-id="bfe37-106">When a duplicate `CustomerID` value is detected in a new row or an edited existing row, the <xref:System.Windows.Forms.DataGridView.DataError> event will occur, which will be handled by displaying a <xref:System.Windows.Forms.MessageBox> that describes the exception.</span></span>

<span data-ttu-id="bfe37-107">Чтобы скопировать код из этого раздела единым блоком, см. раздел [Практическое руководство. Обрабатывайте ошибки, возникающие при вводе данных в элементе](handle-errors-that-occur-during-data-entry-in-the-datagrid.md)управления Windows Forms DataGridView.</span><span class="sxs-lookup"><span data-stu-id="bfe37-107">To copy the code in this topic as a single listing, see [How to: Handle Errors That Occur During Data Entry in the Windows Forms DataGridView Control](handle-errors-that-occur-during-data-entry-in-the-datagrid.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="bfe37-108">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="bfe37-108">Prerequisites</span></span>

<span data-ttu-id="bfe37-109">Для выполнения данного пошагового руководства требуется:</span><span class="sxs-lookup"><span data-stu-id="bfe37-109">In order to complete this walkthrough, you will need:</span></span>

- <span data-ttu-id="bfe37-110">Доступ к серверу с образцом базы данных Northwind SQL Server.</span><span class="sxs-lookup"><span data-stu-id="bfe37-110">Access to a server that has the Northwind SQL Server sample database.</span></span>

## <a name="creating-the-form"></a><span data-ttu-id="bfe37-111">Создание формы</span><span class="sxs-lookup"><span data-stu-id="bfe37-111">Creating the Form</span></span>

#### <a name="to-handle-data-entry-errors-in-the-datagridview-control"></a><span data-ttu-id="bfe37-112">Обработку ошибок ввода данных в элементе управления DataGridView</span><span class="sxs-lookup"><span data-stu-id="bfe37-112">To handle data-entry errors in the DataGridView control</span></span>

1. <span data-ttu-id="bfe37-113">Создайте класс, производный от <xref:System.Windows.Forms.Form> и <xref:System.Windows.Forms.DataGridView> содержащий элемент управления и <xref:System.Windows.Forms.BindingSource> компонент.</span><span class="sxs-lookup"><span data-stu-id="bfe37-113">Create a class that derives from <xref:System.Windows.Forms.Form> and contains a <xref:System.Windows.Forms.DataGridView> control and a <xref:System.Windows.Forms.BindingSource> component.</span></span>

    <span data-ttu-id="bfe37-114">Следующий пример кода предоставляет базовую инициализацию и включает `Main` метод.</span><span class="sxs-lookup"><span data-stu-id="bfe37-114">The following code example provides basic initialization and includes a `Main` method.</span></span>

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#01](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#01)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#01](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#01)]
    [!code-csharp[System.Windows.Forms.DataGridView.DataError#02](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#02](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#02)]

2. <span data-ttu-id="bfe37-115">Реализуйте метод в определении класса формы для обработки сведений о подключении к базе данных.</span><span class="sxs-lookup"><span data-stu-id="bfe37-115">Implement a method in your form's class definition for handling the details of connecting to the database.</span></span>

    <span data-ttu-id="bfe37-116">В `GetData` этом примере кода используется метод, который возвращает <xref:System.Data.DataTable> заполненный объект.</span><span class="sxs-lookup"><span data-stu-id="bfe37-116">This code example uses a `GetData` method that returns a populated <xref:System.Data.DataTable> object.</span></span> <span data-ttu-id="bfe37-117">Убедитесь, что для `connectionString` переменной задано значение, подходящее для вашей базы данных.</span><span class="sxs-lookup"><span data-stu-id="bfe37-117">Be sure that you set the `connectionString` variable to a value that is appropriate for your database.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="bfe37-118">Хранение конфиденциальных сведений (например, пароля) в строке подключения может повлиять на безопасность приложения.</span><span class="sxs-lookup"><span data-stu-id="bfe37-118">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="bfe37-119">Использование проверки подлинности Windows (также называемой встроенными средствами безопасности) — более безопасный способ управления доступом к базе данных.</span><span class="sxs-lookup"><span data-stu-id="bfe37-119">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="bfe37-120">Дополнительные сведения см. в разделе [Защита сведений о подключении](../../data/adonet/protecting-connection-information.md).</span><span class="sxs-lookup"><span data-stu-id="bfe37-120">For more information, see [Protecting Connection Information](../../data/adonet/protecting-connection-information.md).</span></span>

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#30)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#30)]

3. <span data-ttu-id="bfe37-121">Реализуйте обработчик для <xref:System.Windows.Forms.Form.Load> события формы, которое инициализирует <xref:System.Windows.Forms.DataGridView> и <xref:System.Windows.Forms.BindingSource> и настраивает привязку данных.</span><span class="sxs-lookup"><span data-stu-id="bfe37-121">Implement a handler for your form's <xref:System.Windows.Forms.Form.Load> event that initializes the <xref:System.Windows.Forms.DataGridView> and <xref:System.Windows.Forms.BindingSource> and sets up the data binding.</span></span>

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#10)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#10)]

4. <span data-ttu-id="bfe37-122">Обработайте <xref:System.Windows.Forms.DataGridView>событиев <xref:System.Windows.Forms.DataGridView.DataError> .</span><span class="sxs-lookup"><span data-stu-id="bfe37-122">Handle the <xref:System.Windows.Forms.DataGridView.DataError> event on the <xref:System.Windows.Forms.DataGridView>.</span></span>

    <span data-ttu-id="bfe37-123">Если контекст ошибки является операцией фиксации, отобразите ошибку в <xref:System.Windows.Forms.MessageBox>.</span><span class="sxs-lookup"><span data-stu-id="bfe37-123">If the context for the error is a commit operation, display the error in a <xref:System.Windows.Forms.MessageBox>.</span></span>

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#20)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#20)]

## <a name="testing-the-application"></a><span data-ttu-id="bfe37-124">Тестирование приложения</span><span class="sxs-lookup"><span data-stu-id="bfe37-124">Testing the Application</span></span>

<span data-ttu-id="bfe37-125">Теперь можно проверить форму, чтобы убедиться, что она ведет себя так, как ожидалось.</span><span class="sxs-lookup"><span data-stu-id="bfe37-125">You can now test the form to make sure it behaves as expected.</span></span>

#### <a name="to-test-the-form"></a><span data-ttu-id="bfe37-126">Тестирование формы</span><span class="sxs-lookup"><span data-stu-id="bfe37-126">To test the form</span></span>

- <span data-ttu-id="bfe37-127">Нажмите клавишу F5 для запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="bfe37-127">Press F5 to run the application.</span></span>

  <span data-ttu-id="bfe37-128">Вы увидите <xref:System.Windows.Forms.DataGridView> элемент управления, заполненный данными из таблицы Customers.</span><span class="sxs-lookup"><span data-stu-id="bfe37-128">You will see a <xref:System.Windows.Forms.DataGridView> control filled with data from the Customers table.</span></span> <span data-ttu-id="bfe37-129">Если ввести повторяющееся значение для `CustomerID` и сохранить изменения, значение ячейки будет автоматически отменено, и <xref:System.Windows.Forms.MessageBox> появится сообщение, отображающее ошибку ввода данных.</span><span class="sxs-lookup"><span data-stu-id="bfe37-129">If you enter a duplicate value for `CustomerID` and commit the edit, the cell value will revert automatically and you will see a <xref:System.Windows.Forms.MessageBox> that displays the data entry error.</span></span>

## <a name="next-steps"></a><span data-ttu-id="bfe37-130">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="bfe37-130">Next Steps</span></span>

<span data-ttu-id="bfe37-131">Это приложение предоставляет базовое представление о <xref:System.Windows.Forms.DataGridView> возможностях элемента управления.</span><span class="sxs-lookup"><span data-stu-id="bfe37-131">This application gives you a basic understanding of the <xref:System.Windows.Forms.DataGridView> control's capabilities.</span></span> <span data-ttu-id="bfe37-132">Внешний вид и поведение <xref:System.Windows.Forms.DataGridView> элемента управления можно настроить несколькими способами.</span><span class="sxs-lookup"><span data-stu-id="bfe37-132">You can customize the appearance and behavior of the <xref:System.Windows.Forms.DataGridView> control in several ways:</span></span>

- <span data-ttu-id="bfe37-133">Изменение стилей границ и заголовков.</span><span class="sxs-lookup"><span data-stu-id="bfe37-133">Change border and header styles.</span></span> <span data-ttu-id="bfe37-134">Дополнительные сведения см. в разделе [Практическое руководство. Измените стили границ и линий сетки в элементе управления](change-the-border-and-gridline-styles-in-the-datagrid.md)Windows Forms DataGridView.</span><span class="sxs-lookup"><span data-stu-id="bfe37-134">For more information, see [How to: Change the Border and Gridline Styles in the Windows Forms DataGridView Control](change-the-border-and-gridline-styles-in-the-datagrid.md).</span></span>

- <span data-ttu-id="bfe37-135">Разрешение или запрет на ввод данных пользователем <xref:System.Windows.Forms.DataGridView> для элемента управления.</span><span class="sxs-lookup"><span data-stu-id="bfe37-135">Enable or restrict user input to the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="bfe37-136">Дополнительные сведения см. в разделе [Практическое руководство. Предотвращение добавления и удаления строк в элементе управления](prevent-row-addition-and-deletion-datagridview.md)Windows Forms DataGridView и [последующее: Сделать столбцы только для чтения в элементе управления](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md)Windows Forms DataGridView.</span><span class="sxs-lookup"><span data-stu-id="bfe37-136">For more information, see [How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control](prevent-row-addition-and-deletion-datagridview.md), and [How to: Make Columns Read-Only in the Windows Forms DataGridView Control](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).</span></span>

- <span data-ttu-id="bfe37-137">Проверка входных данных пользователя <xref:System.Windows.Forms.DataGridView> для элемента управления.</span><span class="sxs-lookup"><span data-stu-id="bfe37-137">Validate user input to the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="bfe37-138">Дополнительные сведения см. в разделе [Пошаговое руководство: Проверка данных в элементе управления](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)Windows Forms DataGridView.</span><span class="sxs-lookup"><span data-stu-id="bfe37-138">For more information, see [Walkthrough: Validating Data in the Windows Forms DataGridView Control](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md).</span></span>

- <span data-ttu-id="bfe37-139">Обрабатывайте очень большие наборы данных с помощью виртуального режима.</span><span class="sxs-lookup"><span data-stu-id="bfe37-139">Handle very large data sets using virtual mode.</span></span> <span data-ttu-id="bfe37-140">Дополнительные сведения см. в разделе [Пошаговое руководство: Реализация виртуального режима в элементе управления](implementing-virtual-mode-wf-datagridview-control.md)Windows Forms DataGridView.</span><span class="sxs-lookup"><span data-stu-id="bfe37-140">For more information, see [Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control](implementing-virtual-mode-wf-datagridview-control.md).</span></span>

- <span data-ttu-id="bfe37-141">Настройка внешнего вида ячеек.</span><span class="sxs-lookup"><span data-stu-id="bfe37-141">Customize the appearance of cells.</span></span> <span data-ttu-id="bfe37-142">Дополнительные сведения см. в разделе [Практическое руководство. Настройка внешнего вида ячеек в элементе управления](customize-the-appearance-of-cells-in-the-datagrid.md) Windows Forms DataGridView и [выполнение следующих действий: Задайте стили ячеек по умолчанию для элемента управления](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)Windows Forms DataGridView.</span><span class="sxs-lookup"><span data-stu-id="bfe37-142">For more information, see [How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control](customize-the-appearance-of-cells-in-the-datagrid.md) and [How to: Set Default Cell Styles for the Windows Forms DataGridView Control](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="bfe37-143">См. также</span><span class="sxs-lookup"><span data-stu-id="bfe37-143">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="bfe37-144">Ввод данных с помощью элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bfe37-144">Data Entry in the Windows Forms DataGridView Control</span></span>](data-entry-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="bfe37-145">Практическое руководство. Обработку ошибок, происходящих во время ввода данных в элементе управления Windows Forms DataGridView</span><span class="sxs-lookup"><span data-stu-id="bfe37-145">How to: Handle Errors That Occur During Data Entry in the Windows Forms DataGridView Control</span></span>](handle-errors-that-occur-during-data-entry-in-the-datagrid.md)
- [<span data-ttu-id="bfe37-146">Пошаговое руководство: Проверка данных в элементе управления Windows Forms DataGridView</span><span class="sxs-lookup"><span data-stu-id="bfe37-146">Walkthrough: Validating Data in the Windows Forms DataGridView Control</span></span>](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="bfe37-147">Защита сведений о подключении</span><span class="sxs-lookup"><span data-stu-id="bfe37-147">Protecting Connection Information</span></span>](../../data/adonet/protecting-connection-information.md)
