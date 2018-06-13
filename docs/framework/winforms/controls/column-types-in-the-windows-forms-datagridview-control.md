---
title: Типы столбцов элемента управления DataGridView в Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- columns [Windows Forms], types
- DataGridView control [Windows Forms], column types
- data grids [Windows Forms], columns
ms.assetid: f0a0a9f1-8757-4bfd-891f-d7d12870dbed
ms.openlocfilehash: 6630323b66265f478151ec80ab8b225c0b653917
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33530007"
---
# <a name="column-types-in-the-windows-forms-datagridview-control"></a>Типы столбцов элемента управления DataGridView в Windows Forms
<xref:System.Windows.Forms.DataGridView> Управления использует нескольких типов столбцов для отображения данных и позволяют пользователям изменять или добавлять данные.  
  
 При привязке <xref:System.Windows.Forms.DataGridView> и задание <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A> свойства `true`, столбцы создаются автоматически с использованием типов столбцов по умолчанию для типов данных, содержащихся в привязанного источника данных.  
  
 Можно также создать экземпляры любого класса столбца самостоятельно и добавить их в коллекцию, возвращаемую <xref:System.Windows.Forms.DataGridView.Columns%2A> свойство. Можно создать эти экземпляры для использования в качестве несвязанных столбцов или вы можете привязать их вручную. Привязка столбцов вручную можно использовать, например, при заменить автоматически созданного одного типа столбца со столбцом другого типа.  
  
 В следующей таблице описаны доступные для использования в различных классов столбцов <xref:System.Windows.Forms.DataGridView> элемента управления.  
  
|Класс|Описание|  
|-----------|-----------------|  
|<xref:System.Windows.Forms.DataGridViewTextBoxColumn>|Используется с текстовыми значениями. Создается автоматически при привязке к чисел и строк.|  
|<xref:System.Windows.Forms.DataGridViewCheckBoxColumn>|При использовании <xref:System.Boolean> и <xref:System.Windows.Forms.CheckState> значения. Создается автоматически при привязке к значениям из этих типов.|  
|<xref:System.Windows.Forms.DataGridViewImageColumn>|Используется для отображения изображения. Автоматически созданных при привязке к байтовые массивы <xref:System.Drawing.Image> объектов, или <xref:System.Drawing.Icon> объектов.|  
|<xref:System.Windows.Forms.DataGridViewButtonColumn>|Используется для отображения кнопок в ячейках. Создается автоматически при привязке. Обычно используется в качестве несвязанных столбцов.|  
|<xref:System.Windows.Forms.DataGridViewComboBoxColumn>|Используется для отображения раскрывающихся списков в ячейках. Создается автоматически при привязке. Обычно привязкой к данным вручную.|  
|<xref:System.Windows.Forms.DataGridViewLinkColumn>|Используется для отображения ссылки в ячейках. Создается автоматически при привязке. Обычно привязкой к данным вручную.|  
|Пользовательский тип столбцов|Можно создать свой собственный класс столбца путем наследования <xref:System.Windows.Forms.DataGridViewColumn> класса или любого из его производных классов, чтобы предоставить пользовательское оформление, поведением или размещенные элементы управления. Дополнительные сведения см. в разделе [как: Настройка ячеек и столбцов в элементе управления DataGridView Windows Forms, расширяя их поведение и внешний вид](../../../../docs/framework/winforms/controls/customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md)|  
  
 Эти типы столбцов описаны более подробно в следующих разделах.  
  
## <a name="datagridviewtextboxcolumn"></a>DataGridViewTextBoxColumn  
 <xref:System.Windows.Forms.DataGridViewTextBoxColumn> Является типом столбца общего назначения для использования с текстовыми значениями, например чисел и строк. В режиме редактирования <xref:System.Windows.Forms.TextBox> отображается элемент управления в ячейки, дающий пользователю возможность изменять значение ячейки.  
  
 Ячейка значения автоматически преобразуются в строки для отображения. Чтобы создать значение ячейки соответствующего типа данных автоматически синтаксический анализ значения вводимые или изменяемые пользователем. Эти преобразования можно настроить путем обработки <xref:System.Windows.Forms.DataGridView.CellFormatting> и <xref:System.Windows.Forms.DataGridView.CellParsing> события <xref:System.Windows.Forms.DataGridView> элемента управления.  
  
 Тип данных значения ячейки столбца указывается в <xref:System.Windows.Forms.DataGridViewColumn.ValueType%2A> свойство столбца.  
  
## <a name="datagridviewcheckboxcolumn"></a>DataGridViewCheckBoxColumn  
 <xref:System.Windows.Forms.DataGridViewCheckBoxColumn> Используется с <xref:System.Boolean> и <xref:System.Windows.Forms.CheckState> значения. <xref:System.Boolean> значения отображаются как двумя или тремя состояниями флажки, в зависимости от значения <xref:System.Windows.Forms.DataGridViewCheckBoxColumn.ThreeState%2A> свойство. Когда столбец связан с <xref:System.Windows.Forms.CheckState> значения, <xref:System.Windows.Forms.DataGridViewCheckBoxColumn.ThreeState%2A> значение свойства `true` по умолчанию.  
  
 Как правило значения ячеек флажок предназначены для хранения данных, как любые другие данные, либо для выполнения массовых операций. Если вы хотите немедленно при щелчке ячейки с флажком, можно обработать реагировать на <xref:System.Windows.Forms.DataGridView.CellClick> событие, но это событие происходит до обновления значения ячейки. Если необходимо новое значение во время щелчка уже можно вычислить ожидаемое значение на основе текущего значения. Другой подход заключается в фиксировать изменения немедленно и обрабатывать <xref:System.Windows.Forms.DataGridView.CellValueChanged> событие, чтобы реагировать на них. Чтобы применить изменение, при щелчке ячейки, необходимо обрабатывать <xref:System.Windows.Forms.DataGridView.CurrentCellDirtyStateChanged> событий. В обработчике, если текущая ячейка, ячейки с флажком вызвать <xref:System.Windows.Forms.DataGridView.CommitEdit%2A> метод и передайте его в <xref:System.Windows.Forms.DataGridViewDataErrorContexts.Commit> значение.  
  
## <a name="datagridviewimagecolumn"></a>DataGridViewImageColumn  
 <xref:System.Windows.Forms.DataGridViewImageColumn> Используется для отображения изображения. Столбцы изображений можно автоматически заполняется из источника данных, заполняется вручную для несвязанных столбцов или динамически заполнить в обработчике <xref:System.Windows.Forms.DataGridView.CellFormatting> событий.  
  
 Автоматического заполнения столбцов изображений из источника данных могут использоваться байтовые массивы различных форматов изображений, включая все форматы, поддерживаемые <xref:System.Drawing.Image> класс и OLE графический формат, используемый в Microsoft® Access и образец базы данных "Борей".  
  
 Заполнение столбцов изображений вручную полезно, если вы хотите предоставить функциональные возможности <xref:System.Windows.Forms.DataGridViewButtonColumn>, но с настроенными внешним видом. Можно обработать <xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=nameWithType> событий реакция на щелчок мыши внутри ячейки с изображением.  
  
 Заполнение ячеек столбца изображений с помощью обработчика <xref:System.Windows.Forms.DataGridView.CellFormatting> событие полезно, если вы хотите предоставить изображения для вычисляемых значений или значений, не являющихся изображениями. Например, имеется столбец «Риск» со строковыми значениями например `"high"`, `"middle"`, и `"low"` , будет отображаться в виде значков. Кроме того имеется столбец «Image», содержащий расположения изображения, которые должны загружаться вместо двоичного содержимого изображений.  
  
## <a name="datagridviewbuttoncolumn"></a>DataGridViewButtonColumn  
 С <xref:System.Windows.Forms.DataGridViewButtonColumn>, позволяет отображать столбцы ячеек, содержащих кнопки. Это полезно в том случае, если вы хотите упростить для пользователей для выполнения действий над записями, таких как размещение заказа или вывод дочерних записей в отдельном окне.  
  
 Кнопка столбцы не создаются автоматически при связывании <xref:System.Windows.Forms.DataGridView> элемента управления. Для использования кнопки столбцов, необходимо создать их вручную и добавить их в коллекцию, возвращаемую <xref:System.Windows.Forms.DataGridView.Columns%2A?displayProperty=nameWithType> свойство.  
  
 Можно ответить на щелчки мышью кнопок в ячейках, обрабатывая <xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=nameWithType> событий.  
  
## <a name="datagridviewcomboboxcolumn"></a>DataGridViewComboBoxColumn  
 С <xref:System.Windows.Forms.DataGridViewComboBoxColumn>, позволяет отображать столбцы ячеек, содержащих поля раскрывающегося списка. Это полезно для ввода данных в полях, которые может содержать только определенные значения, например столбце категорий таблицы продуктов в базе данных Northwind.  
  
 Можно заполнить при помощи раскрывающегося списка, используемого для всех ячеек так же, как будет заполнить <xref:System.Windows.Forms.ComboBox> раскрывающегося списка, либо вручную с помощью коллекции, возвращенной <xref:System.Windows.Forms.DataGridViewComboBoxColumn.Items%2A> свойства, или путем его привязки к источнику данных через <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A>, <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A>, и <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> свойства. Дополнительные сведения см. в разделе [управления ComboBox](../../../../docs/framework/winforms/controls/combobox-control-windows-forms.md).  
  
 Фактические значения ячеек можно привязать к источнику данных, используемые <xref:System.Windows.Forms.DataGridView> управления <xref:System.Windows.Forms.DataGridViewColumn.DataPropertyName%2A> свойство <xref:System.Windows.Forms.DataGridViewComboBoxColumn?displayProperty=nameWithType>.  
  
 Столбцы поле со списком не создаются автоматически при связывании <xref:System.Windows.Forms.DataGridView> элемента управления. Для использования столбцов поле со списком, необходимо создать их вручную и добавить их в коллекцию, возвращаемую <xref:System.Windows.Forms.DataGridView.Columns%2A> свойство.  
  
## <a name="datagridviewlinkcolumn"></a>DataGridViewLinkColumn  
 С <xref:System.Windows.Forms.DataGridViewLinkColumn>, позволяет отображать столбцы ячеек, содержащих гиперссылки. Это полезно для URL-адрес в источнике данных или в качестве альтернативы столбец кнопок для особого поведения, например открытия окна с дочерними записями.  
  
 Столбцы ссылок не создаются автоматически при связывании <xref:System.Windows.Forms.DataGridView> элемента управления. Использование столбцов ссылок, необходимо создать их вручную и добавить их в коллекцию, возвращаемую <xref:System.Windows.Forms.DataGridView.Columns%2A> свойство.  
  
 Можно ответить на щелчок мышью по ссылке, обрабатывая <xref:System.Windows.Forms.DataGridView.CellContentClick> событий. Это событие отличается от <xref:System.Windows.Forms.DataGridView.CellClick> и <xref:System.Windows.Forms.DataGridView.CellMouseClick> событий, которые происходят, когда пользователь щелкает любое место в ячейке.  
  
 <xref:System.Windows.Forms.DataGridViewLinkColumn> Класс предоставляет несколько свойств для изменения внешнего вида ссылок до, во время и после их щелкнули.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewColumn>  
 <xref:System.Windows.Forms.DataGridViewButtonColumn>  
 <xref:System.Windows.Forms.DataGridViewCheckBoxColumn>  
 <xref:System.Windows.Forms.DataGridViewComboBoxColumn>  
 <xref:System.Windows.Forms.DataGridViewImageColumn>  
 <xref:System.Windows.Forms.DataGridViewTextBoxColumn>  
 <xref:System.Windows.Forms.DataGridViewLinkColumn>  
 [Элемент управления DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)  
 [Практическое руководство. Вывод изображений в ячейках элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-display-images-in-cells-of-the-windows-forms-datagridview-control.md)  
 [Практическое руководство. Работа со столбцами изображений в элементе управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-work-with-image-columns-in-the-windows-forms-datagridview-control.md)  
 [Настройка элементов управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)
