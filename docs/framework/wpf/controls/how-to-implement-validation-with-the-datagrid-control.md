---
title: "Практическое руководство. реализация проверки с помощью элемента управления DataGrid | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "DataGrid [WPF], проверка"
  - "проверка [WPF], DataGrid"
ms.assetid: ec6078a8-1e42-4648-b414-f4348e81bda1
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Практическое руководство. реализация проверки с помощью элемента управления DataGrid
Элемент управления <xref:System.Windows.Controls.DataGrid> позволяет выполнять проверку на уровне ячеек и на уровне строк.  Когда пользователь обновляет значение, в ходе проверки на уровне ячеек проверяются отдельные свойства объекта, привязанного к данным.  Когда пользователь вносит изменения в строку, в ходе проверки на уровне строк проверяются целые объекты данных.  Также можно реализовать визуальную реакцию на ошибки проверки или использовать стандартные сигналы, предоставляемые элементом управления <xref:System.Windows.Controls.DataGrid>.  
  
 В следующих процедурах описано применение правил проверки к привязкам <xref:System.Windows.Controls.DataGrid> и настройка визуальной реакции.  
  
### Проверка значений отдельных ячеек  
  
-   Укажите одно или несколько правил проверки для привязки, используемой со столбцом.  Это аналогично проверке данных в простых элементах управления, описанной в разделе [Общие сведения о связывании данных](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
     В следующем примере показан элемент управления <xref:System.Windows.Controls.DataGrid>, четыре столбца которого привязаны к различным свойствам бизнес\-объекта.  В трех из этих столбцов правило <xref:System.Windows.Controls.ExceptionValidationRule> задается путем установки свойства <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> в значение `true`.  
  
     [!code-xml[DataGrid_Validation#BasicXaml](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/window1.xaml#basicxaml)]  
  
     Если пользователь вводит недопустимое значение \(например, нецелое число в столбец Course ID\), то вокруг ячейки появляется красная рамка.  В следующей процедуре показано, как можно изменить эту визуальную реакцию по умолчанию.  
  
### Настройка сигнала о проверке ячейки  
  
-   Установите в свойстве <xref:System.Windows.Controls.DataGridBoundColumn.EditingElementStyle%2A> столбца стиль, подходящий для элемента управления полем ввода.  Поскольку элементы управления полем ввода создаются во время выполнения, нельзя использовать вложенное свойство <xref:System.Windows.Controls.Validation.ErrorTemplate%2A?displayProperty=fullName>, как в случае с простыми элементами управления.  
  
     Следующий пример представляет обновление предыдущего — добавляется стиль ошибки, совместно используемый тремя столбцами с правилами проверки.  Если пользователь вводит недопустимое значение, стиль изменяет цвет фона ячейки и добавляет подсказку.  Заметьте, что определение наличия ошибки проверки выполняется с помощью триггера.  Использование триггера необходимо, поскольку в данной версии для ячеек отсутствует специальный шаблон ошибок.  
  
     [!code-xml[DataGrid_Validation#CellValidationXaml](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#cellvalidationxaml)]  
  
     Можно реализовать дополнительную настройку, заменив свойство <xref:System.Windows.Controls.DataGridColumn.CellStyle%2A>, используемое столбцом.  
  
### Проверка нескольких значений в одной строке  
  
1.  Реализуйте подкласс <xref:System.Windows.Controls.ValidationRule>, который проверяет несколько свойств привязанного к данным объекта.  В реализации метода <xref:System.Windows.Controls.ValidationRule.Validate%2A> приведите значение параметра `value` к экземпляру <xref:System.Windows.Data.BindingGroup>.  После этого доступ к объекту данных можно получить через свойство <xref:System.Windows.Data.BindingGroup.Items%2A>.  
  
     В следующем примере показан этот процесс, проверяющий, является ли значение свойства `StartDate` объекта `Course` более ранним, чем значение свойства `EndDate` этого объекта.  
  
     [!code-csharp[DataGrid_Validation#CourseValidationRule](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml.cs#coursevalidationrule)]
     [!code-vb[DataGrid_Validation#CourseValidationRule](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_validation/vb/mainwindow.xaml.vb#coursevalidationrule)]  
  
2.  Добавьте правило проверки в коллекцию <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A?displayProperty=fullName>.  Свойство <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A> предоставляет прямой доступ к свойству <xref:System.Windows.Data.BindingGroup.ValidationRules%2A> экземпляра <xref:System.Windows.Data.BindingGroup>, который группирует все привязки, используемые элементом управления.  
  
     В следующем примере свойство <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A> устанавливается в XAML.  Свойство <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> устанавливается в значение <xref:System.Windows.Controls.ValidationStep>, чтобы проверка выполнялась только после обновления объекта, привязанного к данным.  
  
     [!code-xml[DataGrid_Validation#RowValidationRulesXaml](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#rowvalidationrulesxaml)]  
  
     Если пользователь задает конечную дату раньше начальной, то в заголовке строки выводится восклицательный знак \(\!\).  В следующей процедуре показано, как можно изменить эту визуальную реакцию по умолчанию.  
  
### Настройка сигнала о проверке строки  
  
-   Установите свойство <xref:System.Windows.Controls.DataGrid.RowValidationErrorTemplate%2A?displayProperty=fullName>.  Это свойство позволяет настраивать визуальные сигналы о проверке строк для отдельных элементов управления <xref:System.Windows.Controls.DataGrid>.  Используя для задания свойства <xref:System.Windows.Controls.DataGridRow.ValidationErrorTemplate%2A?displayProperty=fullName> неявный стиль строки, можно изменить сразу несколько элементов управления.  
  
     В следующем примере визуальная реакция по умолчанию для проверки строки заменяется на более заметный индикатор.  Если пользователь вводит недопустимое значение, в заголовке строки выводится красный круг с белым восклицательным знаком.  Индикатор выводится и для ошибок проверки строк, и для ошибок проверки ячеек.  В подсказке выводится соответствующее сообщение об ошибке.  
  
     [!code-xml[DataGrid_Validation#RowValidationFeedbackXaml](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#rowvalidationfeedbackxaml)]  
  
## Пример  
 В следующем примере приводится полная демонстрация процесса проверки ячеек и строк.  Класс `Course` предоставляет пример объекта данных, в котором реализован интерфейс <xref:System.ComponentModel.IEditableObject> для поддержки транзакций.  Элемент управления <xref:System.Windows.Controls.DataGrid> взаимодействует с интерфейсом <xref:System.ComponentModel.IEditableObject>, позволяя пользователям отменять изменения, нажимая клавишу ESC.  
  
> [!NOTE]
>  Если используется Visual Basic, замените `x:Class="DataGridValidation.MainWindow"` в первой строке файла MainWindow.xaml на `x:Class="MainWindow"`.  
  
 Для тестирования проверки выполните следующие действия.  
  
-   Введите нецелое значение в столбце Course ID.  
  
-   Введите в столбце End Date дату раньше, чем дата в столбце Start Date.  
  
-   Удалите значение в столбце Course ID, Start Date или End Date.  
  
-   Чтобы отменить ввод недопустимого значения ячейки, верните курсор в ячейку и нажмите клавишу ESC.  
  
-   Чтобы отменить изменения для всей строки, когда текущая ячейка находится в режиме редактирования, нажмите клавишу ESC дважды.  
  
-   Когда произойдет ошибка проверки, наведите указатель мыши на индикатор в заголовке строки, чтобы просмотреть сообщение об ошибке.  
  
 [!code-csharp[DataGrid_Validation#FullCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml.cs#fullcode)]
 [!code-vb[DataGrid_Validation#FullCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_validation/vb/mainwindow.xaml.vb#fullcode)]  
  
 [!code-xml[DataGrid_Validation#FullXaml](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#fullxaml)]  
  
## См. также  
 <xref:System.Windows.Controls.DataGrid>   
 [DataGrid](../../../../docs/framework/wpf/controls/datagrid.md)   
 [Привязка данных](../../../../docs/framework/wpf/data/data-binding-wpf.md)   
 [Реализация проверки привязки](../../../../docs/framework/wpf/data/how-to-implement-binding-validation.md)   
 [Реализация логики проверки для пользовательских объектов](../../../../docs/framework/wpf/data/how-to-implement-validation-logic-on-custom-objects.md)