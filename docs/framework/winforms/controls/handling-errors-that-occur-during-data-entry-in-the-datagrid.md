---
title: Пошаговое руководство. Обработка ошибок, происходящих во время ввода данных в элементе управления DataGridView
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
ms.openlocfilehash: 77a4dcd9cf069ed8bbee6c49aa41db619c8e12ff
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76738734"
---
# <a name="walkthrough-handling-errors-that-occur-during-data-entry-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="e8604-102">Пример. Обработка ошибок, связанных с вводом данных с помощью элемента управления DataGridView, в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e8604-102">Walkthrough: Handling Errors that Occur During Data Entry in the Windows Forms DataGridView Control</span></span>

<span data-ttu-id="e8604-103">Обработка ошибок из базового хранилища данных является обязательной функцией для приложения ввода данных.</span><span class="sxs-lookup"><span data-stu-id="e8604-103">Handling errors from the underlying data store is a required feature for a data-entry application.</span></span> <span data-ttu-id="e8604-104">Элемент управления Windows Forms <xref:System.Windows.Forms.DataGridView> упрощает эту задачу, предоставляя событие <xref:System.Windows.Forms.DataGridView.DataError>, которое возникает, когда хранилище данных обнаруживает нарушение ограничения или бизнес-правило.</span><span class="sxs-lookup"><span data-stu-id="e8604-104">The Windows Forms <xref:System.Windows.Forms.DataGridView> control makes this easy by exposing the <xref:System.Windows.Forms.DataGridView.DataError> event, which is raised when the data store detects a constraint violation or a broken business rule.</span></span>

<span data-ttu-id="e8604-105">В этом пошаговом руководстве вы получите строки из таблицы `Customers` образца базы данных Northwind и отобразите их в элементе управления <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="e8604-105">In this walkthrough, you will retrieve rows from the `Customers` table in the Northwind sample database and display them in a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="e8604-106">При обнаружении повторяющегося `CustomerID` значения в новой строке или измененной существующей строке возникает событие <xref:System.Windows.Forms.DataGridView.DataError>, которое будет обрабатываться с помощью <xref:System.Windows.Forms.MessageBox>, описывающего исключение.</span><span class="sxs-lookup"><span data-stu-id="e8604-106">When a duplicate `CustomerID` value is detected in a new row or an edited existing row, the <xref:System.Windows.Forms.DataGridView.DataError> event will occur, which will be handled by displaying a <xref:System.Windows.Forms.MessageBox> that describes the exception.</span></span>

<span data-ttu-id="e8604-107">Сведения о копировании кода в этом разделе в виде одного списка см. в разделе [как управлять ошибками, происходящими при вводе данных в элементе управления Windows Forms DataGridView](handle-errors-that-occur-during-data-entry-in-the-datagrid.md).</span><span class="sxs-lookup"><span data-stu-id="e8604-107">To copy the code in this topic as a single listing, see [How to: Handle Errors That Occur During Data Entry in the Windows Forms DataGridView Control](handle-errors-that-occur-during-data-entry-in-the-datagrid.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e8604-108">предварительные требования</span><span class="sxs-lookup"><span data-stu-id="e8604-108">Prerequisites</span></span>

<span data-ttu-id="e8604-109">Для выполнения задач этого руководства необходимы:</span><span class="sxs-lookup"><span data-stu-id="e8604-109">In order to complete this walkthrough, you will need:</span></span>

- <span data-ttu-id="e8604-110">Доступ к серверу с образцом базы данных Northwind SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e8604-110">Access to a server that has the Northwind SQL Server sample database.</span></span>

## <a name="creating-the-form"></a><span data-ttu-id="e8604-111">Создание формы</span><span class="sxs-lookup"><span data-stu-id="e8604-111">Creating the Form</span></span>

#### <a name="to-handle-data-entry-errors-in-the-datagridview-control"></a><span data-ttu-id="e8604-112">Обработку ошибок ввода данных в элементе управления DataGridView</span><span class="sxs-lookup"><span data-stu-id="e8604-112">To handle data-entry errors in the DataGridView control</span></span>

1. <span data-ttu-id="e8604-113">Создайте класс, производный от <xref:System.Windows.Forms.Form> и содержащий элемент управления <xref:System.Windows.Forms.DataGridView> и компонент <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="e8604-113">Create a class that derives from <xref:System.Windows.Forms.Form> and contains a <xref:System.Windows.Forms.DataGridView> control and a <xref:System.Windows.Forms.BindingSource> component.</span></span>

    <span data-ttu-id="e8604-114">В следующем примере кода показана базовая инициализация и включается метод `Main`.</span><span class="sxs-lookup"><span data-stu-id="e8604-114">The following code example provides basic initialization and includes a `Main` method.</span></span>

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#01](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#01)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#01](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#01)]
    [!code-csharp[System.Windows.Forms.DataGridView.DataError#02](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#02](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#02)]

2. <span data-ttu-id="e8604-115">Реализуйте метод в определении класса формы для обработки сведений о подключении к базе данных.</span><span class="sxs-lookup"><span data-stu-id="e8604-115">Implement a method in your form's class definition for handling the details of connecting to the database.</span></span>

    <span data-ttu-id="e8604-116">В этом примере кода используется метод `GetData`, который возвращает заполненный объект <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="e8604-116">This code example uses a `GetData` method that returns a populated <xref:System.Data.DataTable> object.</span></span> <span data-ttu-id="e8604-117">Убедитесь, что для переменной `connectionString` задано значение, подходящее для вашей базы данных.</span><span class="sxs-lookup"><span data-stu-id="e8604-117">Be sure that you set the `connectionString` variable to a value that is appropriate for your database.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="e8604-118">Хранение конфиденциальных сведений (например, пароля) в строке подключения может повлиять на безопасность приложения.</span><span class="sxs-lookup"><span data-stu-id="e8604-118">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="e8604-119">Использование проверки подлинности Windows (также называемой встроенными средствами безопасности) — более безопасный способ управления доступом к базе данных.</span><span class="sxs-lookup"><span data-stu-id="e8604-119">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="e8604-120">Дополнительные сведения см. в разделе [Защита сведений о подключении](../../data/adonet/protecting-connection-information.md).</span><span class="sxs-lookup"><span data-stu-id="e8604-120">For more information, see [Protecting Connection Information](../../data/adonet/protecting-connection-information.md).</span></span>

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#30)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#30)]

3. <span data-ttu-id="e8604-121">Реализуйте обработчик для события <xref:System.Windows.Forms.Form.Load> формы, которое инициализирует <xref:System.Windows.Forms.DataGridView> и <xref:System.Windows.Forms.BindingSource> и настраивает привязку данных.</span><span class="sxs-lookup"><span data-stu-id="e8604-121">Implement a handler for your form's <xref:System.Windows.Forms.Form.Load> event that initializes the <xref:System.Windows.Forms.DataGridView> and <xref:System.Windows.Forms.BindingSource> and sets up the data binding.</span></span>

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#10)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#10)]

4. <span data-ttu-id="e8604-122">Обработайте событие <xref:System.Windows.Forms.DataGridView.DataError> в <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="e8604-122">Handle the <xref:System.Windows.Forms.DataGridView.DataError> event on the <xref:System.Windows.Forms.DataGridView>.</span></span>

    <span data-ttu-id="e8604-123">Если контекст ошибки является операцией фиксации, отобразите ошибку в <xref:System.Windows.Forms.MessageBox>.</span><span class="sxs-lookup"><span data-stu-id="e8604-123">If the context for the error is a commit operation, display the error in a <xref:System.Windows.Forms.MessageBox>.</span></span>

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#20)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#20)]

## <a name="testing-the-application"></a><span data-ttu-id="e8604-124">Тестирование приложения</span><span class="sxs-lookup"><span data-stu-id="e8604-124">Testing the Application</span></span>

<span data-ttu-id="e8604-125">Теперь можно проверить форму, чтобы убедиться, что она ведет себя так, как ожидалось.</span><span class="sxs-lookup"><span data-stu-id="e8604-125">You can now test the form to make sure it behaves as expected.</span></span>

#### <a name="to-test-the-form"></a><span data-ttu-id="e8604-126">Тестирование формы</span><span class="sxs-lookup"><span data-stu-id="e8604-126">To test the form</span></span>

- <span data-ttu-id="e8604-127">Нажмите клавишу F5 для запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="e8604-127">Press F5 to run the application.</span></span>

  <span data-ttu-id="e8604-128">Вы увидите <xref:System.Windows.Forms.DataGridView> элемент управления, заполненный данными из таблицы Customers.</span><span class="sxs-lookup"><span data-stu-id="e8604-128">You will see a <xref:System.Windows.Forms.DataGridView> control filled with data from the Customers table.</span></span> <span data-ttu-id="e8604-129">Если ввести повторяющееся значение для `CustomerID` и сохранить изменения, значение ячейки будет автоматически отменено, и появится <xref:System.Windows.Forms.MessageBox>, отображающая ошибку ввода данных.</span><span class="sxs-lookup"><span data-stu-id="e8604-129">If you enter a duplicate value for `CustomerID` and commit the edit, the cell value will revert automatically and you will see a <xref:System.Windows.Forms.MessageBox> that displays the data entry error.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e8604-130">Next Steps</span><span class="sxs-lookup"><span data-stu-id="e8604-130">Next Steps</span></span>

<span data-ttu-id="e8604-131">Это приложение предоставляет базовое представление о возможностях элемента управления <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="e8604-131">This application gives you a basic understanding of the <xref:System.Windows.Forms.DataGridView> control's capabilities.</span></span> <span data-ttu-id="e8604-132">Внешний вид и поведение элемента управления <xref:System.Windows.Forms.DataGridView> можно настроить несколькими способами.</span><span class="sxs-lookup"><span data-stu-id="e8604-132">You can customize the appearance and behavior of the <xref:System.Windows.Forms.DataGridView> control in several ways:</span></span>

- <span data-ttu-id="e8604-133">Изменение стилей границ и заголовков.</span><span class="sxs-lookup"><span data-stu-id="e8604-133">Change border and header styles.</span></span> <span data-ttu-id="e8604-134">Дополнительные сведения см. в разделе [инструкции. изменение стилей границ и линий сетки в элементе управления Windows Forms DataGridView](change-the-border-and-gridline-styles-in-the-datagrid.md).</span><span class="sxs-lookup"><span data-stu-id="e8604-134">For more information, see [How to: Change the Border and Gridline Styles in the Windows Forms DataGridView Control](change-the-border-and-gridline-styles-in-the-datagrid.md).</span></span>

- <span data-ttu-id="e8604-135">Включение или ограничение ввода данных пользователем для элемента управления <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="e8604-135">Enable or restrict user input to the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="e8604-136">Дополнительные сведения см. в статьях [как предотвратить добавление и удаление строк в элементе управления Windows Forms DataGridView](prevent-row-addition-and-deletion-datagridview.md)и [как сделать столбцы доступны только для чтения в элементе управления Windows Forms DataGridView](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="e8604-136">For more information, see [How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control](prevent-row-addition-and-deletion-datagridview.md), and [How to: Make Columns Read-Only in the Windows Forms DataGridView Control](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).</span></span>

- <span data-ttu-id="e8604-137">Проверьте введенные пользователем данные в элементе управления <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="e8604-137">Validate user input to the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="e8604-138">Дополнительные сведения см. в разделе [Пошаговое руководство. Проверка данных в элементе управления Windows Forms DataGridView](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="e8604-138">For more information, see [Walkthrough: Validating Data in the Windows Forms DataGridView Control](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md).</span></span>

- <span data-ttu-id="e8604-139">Обрабатывайте очень большие наборы данных с помощью виртуального режима.</span><span class="sxs-lookup"><span data-stu-id="e8604-139">Handle very large data sets using virtual mode.</span></span> <span data-ttu-id="e8604-140">Дополнительные сведения см. [в разделе Пошаговое руководство. Реализация виртуального режима в элементе управления Windows Forms DataGridView](implementing-virtual-mode-wf-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="e8604-140">For more information, see [Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control](implementing-virtual-mode-wf-datagridview-control.md).</span></span>

- <span data-ttu-id="e8604-141">Настройка внешнего вида ячеек.</span><span class="sxs-lookup"><span data-stu-id="e8604-141">Customize the appearance of cells.</span></span> <span data-ttu-id="e8604-142">Дополнительные сведения см. в разделе [как настроить внешний вид ячеек в элементе управления Windows Forms DataGridView](customize-the-appearance-of-cells-in-the-datagrid.md) и [как задать стили ячеек по умолчанию для элемента управления Windows Forms DataGridView](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="e8604-142">For more information, see [How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control](customize-the-appearance-of-cells-in-the-datagrid.md) and [How to: Set Default Cell Styles for the Windows Forms DataGridView Control](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e8604-143">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e8604-143">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="e8604-144">Ввод данных с помощью элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e8604-144">Data Entry in the Windows Forms DataGridView Control</span></span>](data-entry-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="e8604-145">Практическое руководство. Обработка ошибок, связанных с вводом данных в элемент управления DataGridView, в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e8604-145">How to: Handle Errors That Occur During Data Entry in the Windows Forms DataGridView Control</span></span>](handle-errors-that-occur-during-data-entry-in-the-datagrid.md)
- [<span data-ttu-id="e8604-146">Пример. Проверка данных элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e8604-146">Walkthrough: Validating Data in the Windows Forms DataGridView Control</span></span>](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="e8604-147">Защита сведений о подключении</span><span class="sxs-lookup"><span data-stu-id="e8604-147">Protecting Connection Information</span></span>](../../data/adonet/protecting-connection-information.md)
