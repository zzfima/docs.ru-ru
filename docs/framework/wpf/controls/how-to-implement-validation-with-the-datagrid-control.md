---
title: "Практическое руководство. реализация проверки с помощью элемента управления DataGrid"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGrid [WPF], validation
- validation [WPF], DataGrid
ms.assetid: ec6078a8-1e42-4648-b414-f4348e81bda1
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8c611919b5702877db34e9a02e367312678a1b27
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-implement-validation-with-the-datagrid-control"></a><span data-ttu-id="40135-102">Практическое руководство. реализация проверки с помощью элемента управления DataGrid</span><span class="sxs-lookup"><span data-stu-id="40135-102">How to: Implement Validation with the DataGrid Control</span></span>
<span data-ttu-id="40135-103"><xref:System.Windows.Controls.DataGrid> Управления позволяет выполнять проверку на уровне ячеек и строк.</span><span class="sxs-lookup"><span data-stu-id="40135-103">The <xref:System.Windows.Controls.DataGrid> control enables you to perform validation at both the cell and row level.</span></span> <span data-ttu-id="40135-104">Когда пользователь обновляет значение проверки на уровне ячеек проверяются отдельные свойства объекта, привязанного к данным.</span><span class="sxs-lookup"><span data-stu-id="40135-104">With cell-level validation, you validate individual properties of a bound data object when a user updates a value.</span></span> <span data-ttu-id="40135-105">Когда пользователь вносит изменения в строку проверки на уровне строк проверяются целые объекты данных.</span><span class="sxs-lookup"><span data-stu-id="40135-105">With row-level validation, you validate entire data objects when a user commits changes to a row.</span></span> <span data-ttu-id="40135-106">Также можно реализовать визуальную реакцию на ошибки проверки или использовать стандартные сигналы, <xref:System.Windows.Controls.DataGrid> предоставляет элемент управления.</span><span class="sxs-lookup"><span data-stu-id="40135-106">You can also provide customized visual feedback for validation errors, or use the default visual feedback that the <xref:System.Windows.Controls.DataGrid> control provides.</span></span>  
  
 <span data-ttu-id="40135-107">Следующие процедуры описывают способы применение правил проверки к <xref:System.Windows.Controls.DataGrid> привязок и настроить визуальную обратную связь.</span><span class="sxs-lookup"><span data-stu-id="40135-107">The following procedures describe how to apply validation rules to <xref:System.Windows.Controls.DataGrid> bindings and customize the visual feedback.</span></span>  
  
### <a name="to-validate-individual-cell-values"></a><span data-ttu-id="40135-108">Для проверки значений отдельных ячеек</span><span class="sxs-lookup"><span data-stu-id="40135-108">To validate individual cell values</span></span>  
  
-   <span data-ttu-id="40135-109">Укажите одно или несколько правил проверки для привязки, используемой со столбцом.</span><span class="sxs-lookup"><span data-stu-id="40135-109">Specify one or more validation rules on the binding used with a column.</span></span> <span data-ttu-id="40135-110">Это аналогично проверке данных в простых элементах управления, как описано в [Общие сведения о привязке данных](../../../../docs/framework/wpf/data/data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="40135-110">This is similar to validating data in simple controls, as described in [Data Binding Overview](../../../../docs/framework/wpf/data/data-binding-overview.md).</span></span>  
  
     <span data-ttu-id="40135-111">В следующем примере показан <xref:System.Windows.Controls.DataGrid> управления с четырьмя столбцами, которые привязаны к различным свойствам бизнес-объекта.</span><span class="sxs-lookup"><span data-stu-id="40135-111">The following example shows a <xref:System.Windows.Controls.DataGrid> control with four columns bound to different properties of a business object.</span></span> <span data-ttu-id="40135-112">Укажите трех из этих столбцов <xref:System.Windows.Controls.ExceptionValidationRule> , установив <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> свойства `true`.</span><span class="sxs-lookup"><span data-stu-id="40135-112">Three of the columns specify the <xref:System.Windows.Controls.ExceptionValidationRule> by setting the <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> property to `true`.</span></span>  
  
     [!code-xaml[DataGrid_Validation#BasicXaml](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/window1.xaml#basicxaml)]  
  
     <span data-ttu-id="40135-113">Когда пользователь вводит недопустимое значение (например, нецелое число в столбец Course ID), появится красная граница вокруг ячейки.</span><span class="sxs-lookup"><span data-stu-id="40135-113">When a user enters an invalid value (such as a non-integer in the Course ID column), a red border appears around the cell.</span></span> <span data-ttu-id="40135-114">Вы можете изменить этот отзыв проверки по умолчанию, как описано в следующей процедуре.</span><span class="sxs-lookup"><span data-stu-id="40135-114">You can change this default validation feedback as described in the following procedure.</span></span>  
  
### <a name="to-customize-cell-validation-feedback"></a><span data-ttu-id="40135-115">Настройка сигнала о проверке ячейки</span><span class="sxs-lookup"><span data-stu-id="40135-115">To customize cell validation feedback</span></span>  
  
-   <span data-ttu-id="40135-116">Задайте столбец <xref:System.Windows.Controls.DataGridBoundColumn.EditingElementStyle%2A> свойства стиля, подходящий для столбца элемента управления полем ввода.</span><span class="sxs-lookup"><span data-stu-id="40135-116">Set the column's <xref:System.Windows.Controls.DataGridBoundColumn.EditingElementStyle%2A> property to a style appropriate for the column's editing control.</span></span> <span data-ttu-id="40135-117">Поскольку элементы управления редактирования создаются во время выполнения, нельзя использовать <xref:System.Windows.Controls.Validation.ErrorTemplate%2A?displayProperty=nameWithType> вложенное свойство так же, как с помощью простых элементов управления.</span><span class="sxs-lookup"><span data-stu-id="40135-117">Because the editing controls are created at run time, you cannot use the <xref:System.Windows.Controls.Validation.ErrorTemplate%2A?displayProperty=nameWithType> attached property like you would with simple controls.</span></span>  
  
     <span data-ttu-id="40135-118">В следующем примере обновляется предыдущий пример, добавив стиль ошибки, совместно используемый тремя столбцами с правилами проверки.</span><span class="sxs-lookup"><span data-stu-id="40135-118">The following example updates the previous example by adding an error style shared by the three columns with validation rules.</span></span> <span data-ttu-id="40135-119">Когда пользователь вводит недопустимое значение, стиль изменяет цвет фона ячеек и появится всплывающая подсказка.</span><span class="sxs-lookup"><span data-stu-id="40135-119">When a user enters an invalid value, the style changes the cell background color and adds a ToolTip.</span></span> <span data-ttu-id="40135-120">Обратите внимание на использование триггера, чтобы определить, является ли ошибка проверки.</span><span class="sxs-lookup"><span data-stu-id="40135-120">Note the use of a trigger to determine whether there is a validation error.</span></span> <span data-ttu-id="40135-121">Это необходимо, поскольку в данный момент отсутствует специальный шаблон ошибок для ячеек.</span><span class="sxs-lookup"><span data-stu-id="40135-121">This is required because there is currently no dedicated error template for cells.</span></span>  
  
     [!code-xaml[DataGrid_Validation#CellValidationXaml](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#cellvalidationxaml)]  
  
     <span data-ttu-id="40135-122">Можно реализовать дополнительную настройку, заменив <xref:System.Windows.Controls.DataGridColumn.CellStyle%2A> используемый столбцом.</span><span class="sxs-lookup"><span data-stu-id="40135-122">You can implement more extensive customization by replacing the <xref:System.Windows.Controls.DataGridColumn.CellStyle%2A> used by the column.</span></span>  
  
### <a name="to-validate-multiple-values-in-a-single-row"></a><span data-ttu-id="40135-123">Проверка нескольких значений в одной строке</span><span class="sxs-lookup"><span data-stu-id="40135-123">To validate multiple values in a single row</span></span>  
  
1.  <span data-ttu-id="40135-124">Реализуйте <xref:System.Windows.Controls.ValidationRule> подкласс проверки нескольких свойств объекта, привязанного к данным.</span><span class="sxs-lookup"><span data-stu-id="40135-124">Implement a <xref:System.Windows.Controls.ValidationRule> subclass that checks multiple properties of the bound data object.</span></span> <span data-ttu-id="40135-125">В вашей <xref:System.Windows.Controls.ValidationRule.Validate%2A> реализации метода необходимо привести `value` значение параметра для <xref:System.Windows.Data.BindingGroup> экземпляра.</span><span class="sxs-lookup"><span data-stu-id="40135-125">In your <xref:System.Windows.Controls.ValidationRule.Validate%2A> method implementation, cast the `value` parameter value to a <xref:System.Windows.Data.BindingGroup> instance.</span></span> <span data-ttu-id="40135-126">Теперь можно получить доступ к объект данных через <xref:System.Windows.Data.BindingGroup.Items%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="40135-126">You can then access the data object through the <xref:System.Windows.Data.BindingGroup.Items%2A> property.</span></span>  
  
     <span data-ttu-id="40135-127">В следующем примере демонстрируется этот процесс проверки ли `StartDate` значение свойства для `Course` объекта более ранняя, чем его `EndDate` значение свойства.</span><span class="sxs-lookup"><span data-stu-id="40135-127">The following example demonstrates this process to validate whether the `StartDate` property value for a `Course` object is earlier than its `EndDate` property value.</span></span>  
  
     [!code-csharp[DataGrid_Validation#CourseValidationRule](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml.cs#coursevalidationrule)]
     [!code-vb[DataGrid_Validation#CourseValidationRule](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_validation/vb/mainwindow.xaml.vb#coursevalidationrule)]  
  
2.  <span data-ttu-id="40135-128">Добавить правило проверки к <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A?displayProperty=nameWithType> коллекции.</span><span class="sxs-lookup"><span data-stu-id="40135-128">Add the validation rule to the <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A?displayProperty=nameWithType> collection.</span></span> <span data-ttu-id="40135-129"><xref:System.Windows.Controls.DataGrid.RowValidationRules%2A> Свойство обеспечивает прямой доступ к <xref:System.Windows.Data.BindingGroup.ValidationRules%2A> свойство <xref:System.Windows.Data.BindingGroup> экземпляр, который группирует все привязки, используемые элементом управления.</span><span class="sxs-lookup"><span data-stu-id="40135-129">The <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A> property provides direct access to the <xref:System.Windows.Data.BindingGroup.ValidationRules%2A> property of a <xref:System.Windows.Data.BindingGroup> instance that groups all the bindings used by the control.</span></span>  
  
     <span data-ttu-id="40135-130">В следующем примере задается <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A> свойства в XAML.</span><span class="sxs-lookup"><span data-stu-id="40135-130">The following example sets the <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A> property in XAML.</span></span> <span data-ttu-id="40135-131"><xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> Свойству <xref:System.Windows.Controls.ValidationStep.UpdatedValue> , чтобы проверка выполнялась только после обновления объект привязанных данных.</span><span class="sxs-lookup"><span data-stu-id="40135-131">The <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> property is set to <xref:System.Windows.Controls.ValidationStep.UpdatedValue> so that the validation occurs only after the bound data object is updated.</span></span>  
  
     [!code-xaml[DataGrid_Validation#RowValidationRulesXaml](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#rowvalidationrulesxaml)]  
  
     <span data-ttu-id="40135-132">Если пользователь задает конечную дату, более ранняя, чем дата начала, в заголовке строки отображается красный восклицательный знак (!).</span><span class="sxs-lookup"><span data-stu-id="40135-132">When a user specifies an end date that is earlier than the start date, a red exclamation mark (!) appears in the row header.</span></span> <span data-ttu-id="40135-133">Вы можете изменить этот отзыв проверки по умолчанию, как описано в следующей процедуре.</span><span class="sxs-lookup"><span data-stu-id="40135-133">You can change this default validation feedback as described in the following procedure.</span></span>  
  
### <a name="to-customize-row-validation-feedback"></a><span data-ttu-id="40135-134">Настройка сигнала о проверке строки</span><span class="sxs-lookup"><span data-stu-id="40135-134">To customize row validation feedback</span></span>  
  
-   <span data-ttu-id="40135-135">Задайте свойство <xref:System.Windows.Controls.DataGrid.RowValidationErrorTemplate%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="40135-135">Set the <xref:System.Windows.Controls.DataGrid.RowValidationErrorTemplate%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="40135-136">Это свойство позволяет настраивать проверки строк для отдельных <xref:System.Windows.Controls.DataGrid> элементов управления.</span><span class="sxs-lookup"><span data-stu-id="40135-136">This property enables you to customize row validation feedback for individual <xref:System.Windows.Controls.DataGrid> controls.</span></span> <span data-ttu-id="40135-137">Могут также влиять на несколько элементов управления с помощью неявный стиль строки для установки <xref:System.Windows.Controls.DataGridRow.ValidationErrorTemplate%2A?displayProperty=nameWithType> свойство.</span><span class="sxs-lookup"><span data-stu-id="40135-137">You can also affect multiple controls by using an implicit row style to set the <xref:System.Windows.Controls.DataGridRow.ValidationErrorTemplate%2A?displayProperty=nameWithType> property.</span></span>  
  
     <span data-ttu-id="40135-138">В следующем примере заменяется сигнала о проверке строки по умолчанию с индикатором в виде более видимым.</span><span class="sxs-lookup"><span data-stu-id="40135-138">The following example replaces the default row validation feedback with a more visible indicator.</span></span> <span data-ttu-id="40135-139">При вводе недопустимого значения в заголовке строки отображается красный круг с белым восклицательным знаком.</span><span class="sxs-lookup"><span data-stu-id="40135-139">When a user enters an invalid value, a red circle with a white exclamation mark appears in the row header.</span></span> <span data-ttu-id="40135-140">Это происходит для ошибок проверки строк и ячеек.</span><span class="sxs-lookup"><span data-stu-id="40135-140">This occurs for both row and cell validation errors.</span></span> <span data-ttu-id="40135-141">Сообщение об ошибке отображается во всплывающей подсказке.</span><span class="sxs-lookup"><span data-stu-id="40135-141">The associated error message is displayed in a ToolTip.</span></span>  
  
     [!code-xaml[DataGrid_Validation#RowValidationFeedbackXaml](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#rowvalidationfeedbackxaml)]  
  
## <a name="example"></a><span data-ttu-id="40135-142">Пример</span><span class="sxs-lookup"><span data-stu-id="40135-142">Example</span></span>  
 <span data-ttu-id="40135-143">Ниже приведен полный демонстрация проверки ячеек и строк.</span><span class="sxs-lookup"><span data-stu-id="40135-143">The following example provides a complete demonstration for cell and row validation.</span></span> <span data-ttu-id="40135-144">`Course` Класс предоставляет образец данных объект, реализующий <xref:System.ComponentModel.IEditableObject> для поддержки транзакций.</span><span class="sxs-lookup"><span data-stu-id="40135-144">The `Course` class provides a sample data object that implements <xref:System.ComponentModel.IEditableObject> to support transactions.</span></span> <span data-ttu-id="40135-145"><xref:System.Windows.Controls.DataGrid> Элемент управления взаимодействует с <xref:System.ComponentModel.IEditableObject> возможности для пользователей отменить изменения, нажав клавишу ESC.</span><span class="sxs-lookup"><span data-stu-id="40135-145">The <xref:System.Windows.Controls.DataGrid> control interacts with <xref:System.ComponentModel.IEditableObject> to enable users to revert changes by pressing ESC.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="40135-146">При использовании Visual Basic в первой строке файла MainWindow.XAML замените `x:Class="DataGridValidation.MainWindow"` с `x:Class="MainWindow"`.</span><span class="sxs-lookup"><span data-stu-id="40135-146">If you are using Visual Basic, in the first line of MainWindow.xaml, replace `x:Class="DataGridValidation.MainWindow"` with `x:Class="MainWindow"`.</span></span>  
  
 <span data-ttu-id="40135-147">Для тестирования проверки выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="40135-147">To test the validation, try the following:</span></span>  
  
-   <span data-ttu-id="40135-148">В столбце идентификатор курса ввести нецелое значение.</span><span class="sxs-lookup"><span data-stu-id="40135-148">In the Course ID column, enter a non-integer value.</span></span>  
  
-   <span data-ttu-id="40135-149">В столбце даты окончания введите дату, более ранняя, чем дата начала.</span><span class="sxs-lookup"><span data-stu-id="40135-149">In the End Date column, enter a date that is earlier than the Start Date.</span></span>  
  
-   <span data-ttu-id="40135-150">Удаление значения в идентификатор курса, Дата начала или дата окончания.</span><span class="sxs-lookup"><span data-stu-id="40135-150">Delete the value in Course ID, Start Date, or End Date.</span></span>  
  
-   <span data-ttu-id="40135-151">Чтобы отменить недопустимое значение для ячейки, поместите курсор в ячейку и нажать клавишу ESC.</span><span class="sxs-lookup"><span data-stu-id="40135-151">To undo an invalid cell value, put the cursor back in the cell and press the ESC key.</span></span>  
  
-   <span data-ttu-id="40135-152">Чтобы отменить изменения для всей строки, если текущая ячейка находится в режиме редактирования, дважды нажмите клавишу ESC.</span><span class="sxs-lookup"><span data-stu-id="40135-152">To undo changes for an entire row when the current cell is in edit mode, press the ESC key twice.</span></span>  
  
-   <span data-ttu-id="40135-153">При возникновении ошибки проверки, наведите указатель мыши на индикатор в заголовке строки, чтобы просмотреть сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="40135-153">When a validation error occurs, move your mouse pointer over the indicator in the row header to see the associated error message.</span></span>  
  
 [!code-csharp[DataGrid_Validation#FullCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml.cs#fullcode)]
 [!code-vb[DataGrid_Validation#FullCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_validation/vb/mainwindow.xaml.vb#fullcode)]  
  
 [!code-xaml[DataGrid_Validation#FullXaml](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#fullxaml)]  
  
## <a name="see-also"></a><span data-ttu-id="40135-154">См. также</span><span class="sxs-lookup"><span data-stu-id="40135-154">See Also</span></span>  
 <xref:System.Windows.Controls.DataGrid>  
 [<span data-ttu-id="40135-155">DataGrid</span><span class="sxs-lookup"><span data-stu-id="40135-155">DataGrid</span></span>](../../../../docs/framework/wpf/controls/datagrid.md)  
 [<span data-ttu-id="40135-156">Привязка данных</span><span class="sxs-lookup"><span data-stu-id="40135-156">Data Binding</span></span>](../../../../docs/framework/wpf/data/data-binding-wpf.md)  
 [<span data-ttu-id="40135-157">Реализация проверки привязки</span><span class="sxs-lookup"><span data-stu-id="40135-157">Implement Binding Validation</span></span>](../../../../docs/framework/wpf/data/how-to-implement-binding-validation.md)  
 [<span data-ttu-id="40135-158">Реализация логики проверки для пользовательских объектов</span><span class="sxs-lookup"><span data-stu-id="40135-158">Implement Validation Logic on Custom Objects</span></span>](../../../../docs/framework/wpf/data/how-to-implement-validation-logic-on-custom-objects.md)
