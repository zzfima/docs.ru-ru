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
ms.openlocfilehash: 401949aa4bea924b458a91dc00c454c97aff4895
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458457"
---
# <a name="how-to-implement-validation-with-the-datagrid-control"></a>Практическое руководство. реализация проверки с помощью элемента управления DataGrid
Элемент управления <xref:System.Windows.Controls.DataGrid> позволяет выполнять проверку на уровне ячеек и строк. При проверке на уровне ячейки вы проверяете отдельные свойства привязанного объекта данных, когда пользователь обновляет значение. При проверке на уровне строк выполняется проверка всех объектов данных, когда пользователь фиксирует изменения в строке. Можно также предоставить настраиваемые визуальные Отзывы об ошибках проверки или использовать визуальный отзыв по умолчанию, предоставляемый элементом управления <xref:System.Windows.Controls.DataGrid>.  
  
 В следующих процедурах описывается применение правил проверки для <xref:System.Windows.Controls.DataGrid> привязок и настройки визуальной обратной связи.  
  
### <a name="to-validate-individual-cell-values"></a>Проверка значений отдельных ячеек  
  
- Укажите одно или несколько правил проверки для привязки, используемой со столбцом. Это похоже на проверку данных в простых элементах управления, как описано в разделе [Общие сведения о привязке данных](../data/data-binding-overview.md).  
  
     В следующем примере показан элемент управления <xref:System.Windows.Controls.DataGrid> с четырьмя столбцами, привязанными к различным свойствам бизнес-объекта. Три столбца указывают <xref:System.Windows.Controls.ExceptionValidationRule>, установив для свойства <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> значение `true`.  
  
     [!code-xaml[DataGrid_Validation#BasicXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/window1.xaml#basicxaml)]  
  
     Когда пользователь вводит недопустимое значение (например, не целое число в столбце Course ID), вокруг ячейки появляется красная граница. Можно изменить этот отзыв по проверке по умолчанию, как описано в следующей процедуре.  
  
### <a name="to-customize-cell-validation-feedback"></a>Настройка обратной связи по проверке ячейки  
  
- Задайте для свойства <xref:System.Windows.Controls.DataGridBoundColumn.EditingElementStyle%2A> столбца стиль, соответствующий элементу управления для редактирования столбца. Поскольку элементы управления редактирования создаются во время выполнения, нельзя использовать присоединенное свойство <xref:System.Windows.Controls.Validation.ErrorTemplate%2A?displayProperty=nameWithType>, как и для простых элементов управления.  
  
     Следующий пример обновляет предыдущий пример, добавляя стиль ошибки, совместно используемый тремя столбцами с правилами проверки. Когда пользователь вводит недопустимое значение, стиль изменяет цвет фона ячейки и добавляет подсказку. Обратите внимание на использование триггера для определения наличия ошибки проверки. Это необходимо, так как в настоящее время нет выделенного шаблона ошибок для ячеек.  
  
     [!code-xaml[DataGrid_Validation#CellValidationXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#cellvalidationxaml)]  
  
     Можно реализовать более обширную настройку, заменив <xref:System.Windows.Controls.DataGridColumn.CellStyle%2A>, используемые столбцом.  
  
### <a name="to-validate-multiple-values-in-a-single-row"></a>Проверка нескольких значений в одной строке  
  
1. Реализуйте подкласс <xref:System.Windows.Controls.ValidationRule>, который проверяет несколько свойств привязанного объекта данных. В реализации метода <xref:System.Windows.Controls.ValidationRule.Validate%2A> приведите `value` значение параметра к экземпляру <xref:System.Windows.Data.BindingGroup>. Затем можно получить доступ к объекту данных с помощью свойства <xref:System.Windows.Data.BindingGroup.Items%2A>.  
  
     В следующем примере показан этот процесс для проверки того, является ли значение свойства `StartDate` для объекта `Course` более ранним, чем значение свойства `EndDate`.  
  
     [!code-csharp[DataGrid_Validation#CourseValidationRule](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml.cs#coursevalidationrule)]
     [!code-vb[DataGrid_Validation#CourseValidationRule](~/samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_validation/vb/mainwindow.xaml.vb#coursevalidationrule)]  
  
2. Добавьте правило проверки в коллекцию <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A?displayProperty=nameWithType>. Свойство <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A> предоставляет прямой доступ к свойству <xref:System.Windows.Data.BindingGroup.ValidationRules%2A> экземпляра <xref:System.Windows.Data.BindingGroup>, который группирует все привязки, используемые элементом управления.  
  
     В следующем примере задается свойство <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A> в XAML. Свойство <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> имеет значение <xref:System.Windows.Controls.ValidationStep.UpdatedValue>, поэтому проверка выполняется только после обновления привязанного объекта данных.  
  
     [!code-xaml[DataGrid_Validation#RowValidationRulesXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#rowvalidationrulesxaml)]  
  
     Когда пользователь указывает дату окончания, предшествующую дате начала, в заголовке строки появляется красный восклицательный знак (!). Можно изменить этот отзыв по проверке по умолчанию, как описано в следующей процедуре.  
  
### <a name="to-customize-row-validation-feedback"></a>Настройка обратной связи по проверке строк  
  
- Задайте свойство <xref:System.Windows.Controls.DataGrid.RowValidationErrorTemplate%2A?displayProperty=nameWithType>. Это свойство позволяет настроить отзыв о проверке строк для отдельных элементов управления <xref:System.Windows.Controls.DataGrid>. Можно также повлиять на несколько элементов управления, используя неявный стиль строк для задания свойства <xref:System.Windows.Controls.DataGridRow.ValidationErrorTemplate%2A?displayProperty=nameWithType>.  
  
     В следующем примере отменяется обратная связь по проверке строк по умолчанию с более видимым индикатором. Когда пользователь вводит недопустимое значение, в заголовке строки появляется красный кружок с белым восклицательным знаком. Это происходит как для ошибок проверки строк, так и для ячеек. Связанное сообщение об ошибке отображается в подсказке.  
  
     [!code-xaml[DataGrid_Validation#RowValidationFeedbackXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#rowvalidationfeedbackxaml)]  
  
## <a name="example"></a>Пример  
 В следующем примере приведена полная демонстрация проверки ячеек и строк. Класс `Course` предоставляет образец объекта данных, который реализует <xref:System.ComponentModel.IEditableObject> для поддержки транзакций. <xref:System.Windows.Controls.DataGrid> элемент управления взаимодействует с <xref:System.ComponentModel.IEditableObject>, чтобы пользователи могли отменить изменения, нажав клавишу ESC.  
  
> [!NOTE]
> При использовании Visual Basic в первой строке файла MainWindow. XAML замените `x:Class="DataGridValidation.MainWindow"` на `x:Class="MainWindow"`.  
  
 Чтобы проверить проверку, попробуйте выполнить следующие действия.  
  
- В столбце Course ID (идентификатор курса) введите значение, отличное от целого.  
  
- В столбце Дата окончания введите дату, предшествующую дате начала.  
  
- Удалите значение в поле идентификатор курса, Дата начала или Дата окончания.  
  
- Чтобы отменить недопустимое значение ячейки, установите курсор обратно в ячейку и нажмите клавишу ESC.  
  
- Чтобы отменить изменения для всей строки, если текущая ячейка находится в режиме редактирования, нажмите клавишу ESC дважды.  
  
- При возникновении ошибки проверки наведите указатель мыши на индикатор в заголовке строки, чтобы просмотреть соответствующее сообщение об ошибке.  
  
 [!code-csharp[DataGrid_Validation#FullCode](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml.cs#fullcode)]
 [!code-vb[DataGrid_Validation#FullCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_validation/vb/mainwindow.xaml.vb#fullcode)]  
  
 [!code-xaml[DataGrid_Validation#FullXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#fullxaml)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Controls.DataGrid>
- [DataGrid](datagrid.md)
- [Привязка данных](../../../desktop-wpf/data/data-binding-overview.md)
- [Реализация проверки привязки](../data/how-to-implement-binding-validation.md)
- [Реализация логики проверки для пользовательских объектов](../data/how-to-implement-validation-logic-on-custom-objects.md)
