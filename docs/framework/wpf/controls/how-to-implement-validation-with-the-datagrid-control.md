---
title: Практическое руководство. реализация проверки с помощью элемента управления DataGrid
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGrid [WPF], validation
- validation [WPF], DataGrid
ms.assetid: ec6078a8-1e42-4648-b414-f4348e81bda1
ms.openlocfilehash: 20fcc8ebafb25e4e4f176447972e7637aaa5cd7d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33557879"
---
# <a name="how-to-implement-validation-with-the-datagrid-control"></a>Практическое руководство. реализация проверки с помощью элемента управления DataGrid
<xref:System.Windows.Controls.DataGrid> Управления позволяет выполнять проверку на уровне ячеек и строк. Когда пользователь обновляет значение проверки на уровне ячеек проверяются отдельные свойства объекта, привязанного к данным. Когда пользователь вносит изменения в строку проверки на уровне строк проверяются целые объекты данных. Также можно реализовать визуальную реакцию на ошибки проверки или использовать стандартные сигналы, <xref:System.Windows.Controls.DataGrid> предоставляет элемент управления.  
  
 Следующие процедуры описывают способы применение правил проверки к <xref:System.Windows.Controls.DataGrid> привязок и настроить визуальную обратную связь.  
  
### <a name="to-validate-individual-cell-values"></a>Для проверки значений отдельных ячеек  
  
-   Укажите одно или несколько правил проверки для привязки, используемой со столбцом. Это аналогично проверке данных в простых элементах управления, как описано в [Общие сведения о привязке данных](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
     В следующем примере показан <xref:System.Windows.Controls.DataGrid> управления с четырьмя столбцами, которые привязаны к различным свойствам бизнес-объекта. Укажите трех из этих столбцов <xref:System.Windows.Controls.ExceptionValidationRule> , установив <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> свойства `true`.  
  
     [!code-xaml[DataGrid_Validation#BasicXaml](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/window1.xaml#basicxaml)]  
  
     Когда пользователь вводит недопустимое значение (например, нецелое число в столбец Course ID), появится красная граница вокруг ячейки. Вы можете изменить этот отзыв проверки по умолчанию, как описано в следующей процедуре.  
  
### <a name="to-customize-cell-validation-feedback"></a>Настройка сигнала о проверке ячейки  
  
-   Задайте столбец <xref:System.Windows.Controls.DataGridBoundColumn.EditingElementStyle%2A> свойства стиля, подходящий для столбца элемента управления полем ввода. Поскольку элементы управления редактирования создаются во время выполнения, нельзя использовать <xref:System.Windows.Controls.Validation.ErrorTemplate%2A?displayProperty=nameWithType> вложенное свойство так же, как с помощью простых элементов управления.  
  
     В следующем примере обновляется предыдущий пример, добавив стиль ошибки, совместно используемый тремя столбцами с правилами проверки. Когда пользователь вводит недопустимое значение, стиль изменяет цвет фона ячеек и появится всплывающая подсказка. Обратите внимание на использование триггера, чтобы определить, является ли ошибка проверки. Это необходимо, поскольку в данный момент отсутствует специальный шаблон ошибок для ячеек.  
  
     [!code-xaml[DataGrid_Validation#CellValidationXaml](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#cellvalidationxaml)]  
  
     Можно реализовать дополнительную настройку, заменив <xref:System.Windows.Controls.DataGridColumn.CellStyle%2A> используемый столбцом.  
  
### <a name="to-validate-multiple-values-in-a-single-row"></a>Проверка нескольких значений в одной строке  
  
1.  Реализуйте <xref:System.Windows.Controls.ValidationRule> подкласс проверки нескольких свойств объекта, привязанного к данным. В вашей <xref:System.Windows.Controls.ValidationRule.Validate%2A> реализации метода необходимо привести `value` значение параметра для <xref:System.Windows.Data.BindingGroup> экземпляра. Теперь можно получить доступ к объект данных через <xref:System.Windows.Data.BindingGroup.Items%2A> свойство.  
  
     В следующем примере демонстрируется этот процесс проверки ли `StartDate` значение свойства для `Course` объекта более ранняя, чем его `EndDate` значение свойства.  
  
     [!code-csharp[DataGrid_Validation#CourseValidationRule](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml.cs#coursevalidationrule)]
     [!code-vb[DataGrid_Validation#CourseValidationRule](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_validation/vb/mainwindow.xaml.vb#coursevalidationrule)]  
  
2.  Добавить правило проверки к <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A?displayProperty=nameWithType> коллекции. <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A> Свойство обеспечивает прямой доступ к <xref:System.Windows.Data.BindingGroup.ValidationRules%2A> свойство <xref:System.Windows.Data.BindingGroup> экземпляр, который группирует все привязки, используемые элементом управления.  
  
     В следующем примере задается <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A> свойства в XAML. <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> Свойству <xref:System.Windows.Controls.ValidationStep.UpdatedValue> , чтобы проверка выполнялась только после обновления объект привязанных данных.  
  
     [!code-xaml[DataGrid_Validation#RowValidationRulesXaml](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#rowvalidationrulesxaml)]  
  
     Если пользователь задает конечную дату, более ранняя, чем дата начала, в заголовке строки отображается красный восклицательный знак (!). Вы можете изменить этот отзыв проверки по умолчанию, как описано в следующей процедуре.  
  
### <a name="to-customize-row-validation-feedback"></a>Настройка сигнала о проверке строки  
  
-   Задайте свойство <xref:System.Windows.Controls.DataGrid.RowValidationErrorTemplate%2A?displayProperty=nameWithType>. Это свойство позволяет настраивать проверки строк для отдельных <xref:System.Windows.Controls.DataGrid> элементов управления. Могут также влиять на несколько элементов управления с помощью неявный стиль строки для установки <xref:System.Windows.Controls.DataGridRow.ValidationErrorTemplate%2A?displayProperty=nameWithType> свойство.  
  
     В следующем примере заменяется сигнала о проверке строки по умолчанию с индикатором в виде более видимым. При вводе недопустимого значения в заголовке строки отображается красный круг с белым восклицательным знаком. Это происходит для ошибок проверки строк и ячеек. Сообщение об ошибке отображается во всплывающей подсказке.  
  
     [!code-xaml[DataGrid_Validation#RowValidationFeedbackXaml](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#rowvalidationfeedbackxaml)]  
  
## <a name="example"></a>Пример  
 Ниже приведен полный демонстрация проверки ячеек и строк. `Course` Класс предоставляет образец данных объект, реализующий <xref:System.ComponentModel.IEditableObject> для поддержки транзакций. <xref:System.Windows.Controls.DataGrid> Элемент управления взаимодействует с <xref:System.ComponentModel.IEditableObject> возможности для пользователей отменить изменения, нажав клавишу ESC.  
  
> [!NOTE]
>  При использовании Visual Basic в первой строке файла MainWindow.XAML замените `x:Class="DataGridValidation.MainWindow"` с `x:Class="MainWindow"`.  
  
 Для тестирования проверки выполните следующие действия:  
  
-   В столбце идентификатор курса ввести нецелое значение.  
  
-   В столбце даты окончания введите дату, более ранняя, чем дата начала.  
  
-   Удаление значения в идентификатор курса, Дата начала или дата окончания.  
  
-   Чтобы отменить недопустимое значение для ячейки, поместите курсор в ячейку и нажать клавишу ESC.  
  
-   Чтобы отменить изменения для всей строки, если текущая ячейка находится в режиме редактирования, дважды нажмите клавишу ESC.  
  
-   При возникновении ошибки проверки, наведите указатель мыши на индикатор в заголовке строки, чтобы просмотреть сообщение об ошибке.  
  
 [!code-csharp[DataGrid_Validation#FullCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml.cs#fullcode)]
 [!code-vb[DataGrid_Validation#FullCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_validation/vb/mainwindow.xaml.vb#fullcode)]  
  
 [!code-xaml[DataGrid_Validation#FullXaml](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#fullxaml)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Controls.DataGrid>  
 [DataGrid](../../../../docs/framework/wpf/controls/datagrid.md)  
 [Привязка данных](../../../../docs/framework/wpf/data/data-binding-wpf.md)  
 [Реализация проверки привязки](../../../../docs/framework/wpf/data/how-to-implement-binding-validation.md)  
 [Реализация логики проверки для пользовательских объектов](../../../../docs/framework/wpf/data/how-to-implement-validation-logic-on-custom-objects.md)
