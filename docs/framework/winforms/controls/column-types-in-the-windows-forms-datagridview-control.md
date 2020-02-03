---
title: Типы столбцов в элементе управления DataGridView
ms.date: 03/30/2017
helpviewer_keywords:
- columns [Windows Forms], types
- DataGridView control [Windows Forms], column types
- data grids [Windows Forms], columns
ms.assetid: f0a0a9f1-8757-4bfd-891f-d7d12870dbed
ms.openlocfilehash: e918394cca6350854074d4c1567890138b2a1462
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743857"
---
# <a name="column-types-in-the-windows-forms-datagridview-control"></a>Типы столбцов элемента управления DataGridView в Windows Forms
Элемент управления <xref:System.Windows.Forms.DataGridView> использует несколько типов столбцов для вывода сведений и позволяет пользователям изменять или добавлять данные.  
  
 При привязке <xref:System.Windows.Forms.DataGridView> элемента управления и присвоении свойству <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A> значения `true`столбцы автоматически создаются с использованием типов столбцов по умолчанию, соответствующих типам данных, содержащимся в связанном источнике данных.  
  
 Можно также создать экземпляры любого класса столбцов самостоятельно и добавить их в коллекцию, возвращенную свойством <xref:System.Windows.Forms.DataGridView.Columns%2A>. Эти экземпляры можно создать для использования в качестве несвязанных столбцов или можно вручную привязать их. Связанные вручную столбцы полезны, например, когда необходимо заменить автоматически созданный столбец одного типа столбцом другого типа.  
  
 В следующей таблице описаны различные классы столбцов, доступные для использования в элементе управления <xref:System.Windows.Forms.DataGridView>.  
  
|Class|Description|  
|-----------|-----------------|  
|<xref:System.Windows.Forms.DataGridViewTextBoxColumn>|Используется со значениями, основанными на тексте. Создается автоматически при привязке к числам и строкам.|  
|<xref:System.Windows.Forms.DataGridViewCheckBoxColumn>|Используется со значениями <xref:System.Boolean> и <xref:System.Windows.Forms.CheckState>. Создается автоматически при привязке к значениям этих типов.|  
|<xref:System.Windows.Forms.DataGridViewImageColumn>|Используется для вывода изображений. Создается автоматически при привязке к массивам байтов, <xref:System.Drawing.Image> объектам или <xref:System.Drawing.Icon> объектам.|  
|<xref:System.Windows.Forms.DataGridViewButtonColumn>|Используется для вывода кнопок в ячейках. Не создается автоматически при привязке. Обычно используется как непривязанные столбцы.|  
|<xref:System.Windows.Forms.DataGridViewComboBoxColumn>|Используется для вывода раскрывающихся списков в ячейках. Не создается автоматически при привязке. Обычно привязка данных осуществляется вручную.|  
|<xref:System.Windows.Forms.DataGridViewLinkColumn>|Используется для вывода ссылок в ячейках. Не создается автоматически при привязке. Обычно привязка данных осуществляется вручную.|  
|Тип настраиваемого столбца|Можно создать собственный класс столбца, наследуя класс <xref:System.Windows.Forms.DataGridViewColumn> или любой из его производных классов для предоставления пользовательского внешнего вида, поведения или размещенных элементов управления. Дополнительные сведения см. в разделе [как настроить ячейки и столбцы в элементе управления Windows Forms DataGridView путем расширения их поведения и внешнего вида.](customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md)|  
  
 Эти типы столбцов более подробно описаны в следующих разделах.  
  
## <a name="datagridviewtextboxcolumn"></a>датагридвиевтекстбоксколумн  
 <xref:System.Windows.Forms.DataGridViewTextBoxColumn> является типом столбца общего назначения для использования с текстовыми значениями, такими как числа и строки. В режиме редактирования в активной ячейке отображается <xref:System.Windows.Forms.TextBox> элемент управления, позволяющий пользователям изменять значение ячейки.  
  
 Значения ячеек автоматически преобразуются в строки для вывода. Значения, введенные или измененные пользователем, автоматически анализируются для создания значения ячейки соответствующего типа данных. Эти преобразования можно настроить, обрабатывая события <xref:System.Windows.Forms.DataGridView.CellFormatting> и <xref:System.Windows.Forms.DataGridView.CellParsing> элемента управления <xref:System.Windows.Forms.DataGridView>.  
  
 Тип данных значения ячейки столбца указывается в свойстве <xref:System.Windows.Forms.DataGridViewColumn.ValueType%2A> столбца.  
  
## <a name="datagridviewcheckboxcolumn"></a>датагридвиевчеккбоксколумн  
 <xref:System.Windows.Forms.DataGridViewCheckBoxColumn> используется со значениями <xref:System.Boolean> и <xref:System.Windows.Forms.CheckState>. <xref:System.Boolean> значения отображаются как флажки с двумя состояниями или три состояния, в зависимости от значения свойства <xref:System.Windows.Forms.DataGridViewCheckBoxColumn.ThreeState%2A>. Если столбец привязан к <xref:System.Windows.Forms.CheckState> значениям, значение свойства <xref:System.Windows.Forms.DataGridViewCheckBoxColumn.ThreeState%2A> по умолчанию равно `true`.  
  
 Как правило, значения ячеек флажков предназначены для хранения, например для любых других данных, или для выполнения операций с массовыми операциями. Если вы хотите ответить немедленно, когда пользователь нащелкнул ячейку флажка, можно обработать событие <xref:System.Windows.Forms.DataGridView.CellClick>, но это событие происходит перед обновлением значения ячейки. Если требуется новое значение во время щелчка, можно вычислить ожидаемое значение на основе текущего значения. Другой подход заключается в фиксации изменения немедленно и обработке события <xref:System.Windows.Forms.DataGridView.CellValueChanged> для реагирования на него. Чтобы зафиксировать изменение при щелчке ячейки, необходимо выполнить обработку события <xref:System.Windows.Forms.DataGridView.CurrentCellDirtyStateChanged>. Если в обработчике текущая ячейка является ячейкой флажка, вызовите метод <xref:System.Windows.Forms.DataGridView.CommitEdit%2A> и передайте значение <xref:System.Windows.Forms.DataGridViewDataErrorContexts.Commit>.  
  
## <a name="datagridviewimagecolumn"></a>датагридвиевимажеколумн  
 <xref:System.Windows.Forms.DataGridViewImageColumn> используется для вывода изображений. Столбцы изображений могут автоматически заполняться из источника данных, заполняться вручную для несвязанных столбцов или динамически заполняться в обработчике для события <xref:System.Windows.Forms.DataGridView.CellFormatting>.  
  
 Автоматическое заполнение столбца Image из источника данных работает с массивами байтов в различных форматах изображений, включая все форматы, поддерживаемые классом <xref:System.Drawing.Image>, и формат OLE Picture, используемый в Microsoft® Access и образце базы данных Northwind.  
  
 Заполнение столбца Image вручную полезно, если требуется предоставить функциональные возможности <xref:System.Windows.Forms.DataGridViewButtonColumn>, но с пользовательским видом. Можно обработать событие <xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=nameWithType>, чтобы реагировать на щелчки в ячейке изображения.  
  
 Заполнение ячеек столбца Image в обработчике для события <xref:System.Windows.Forms.DataGridView.CellFormatting> полезно, если требуется предоставить изображения для вычисляемых значений или значений в форматах, отличных от изображений. Например, у вас может быть столбец "риск" со строковыми значениями, такими как `"high"`, `"middle"`и `"low"`, которые должны отображаться в виде значков. Кроме того, может существовать столбец "Image", содержащий расположения изображений, которые должны быть загружены, а не двоичное содержимое изображений.  
  
## <a name="datagridviewbuttoncolumn"></a>датагридвиевбуттонколумн  
 С помощью <xref:System.Windows.Forms.DataGridViewButtonColumn>можно отобразить столбец ячеек, содержащих кнопки. Это полезно, если необходимо предоставить пользователям простой способ выполнения действий с конкретными записями, например, размещение заказа или отображение дочерних записей в отдельном окне.  
  
 Столбцы кнопок не создаются автоматически при привязке данных к элементу управления <xref:System.Windows.Forms.DataGridView>. Чтобы использовать столбцы кнопки, необходимо создать их вручную и добавить их в коллекцию, возвращенную свойством <xref:System.Windows.Forms.DataGridView.Columns%2A?displayProperty=nameWithType>.  
  
 Вы можете реагировать на нажатия пользователем в ячейках кнопки, обрабатывая событие <xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=nameWithType>.  
  
## <a name="datagridviewcomboboxcolumn"></a>DataGridViewComboBoxColumn  
 С помощью <xref:System.Windows.Forms.DataGridViewComboBoxColumn>можно отобразить столбец ячеек, содержащих раскрывающиеся списки. Это полезно для ввода данных в полях, которые могут содержать только определенные значения, например столбец Category таблицы Products в образце базы данных Northwind.  
  
 Раскрывающийся список, используемый для всех ячеек, можно заполнить тем же способом, что и <xref:System.Windows.Forms.ComboBox> раскрывающийся список, вручную через коллекцию, возвращенную свойством <xref:System.Windows.Forms.DataGridViewComboBoxColumn.Items%2A>, или путем привязки к источнику данных с помощью свойств <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A>, <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A>и <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A>. Дополнительные сведения см. в разделе [элемент управления ComboBox](combobox-control-windows-forms.md).  
  
 Фактические значения ячеек можно привязать к источнику данных, используемому элементом управления <xref:System.Windows.Forms.DataGridView>, установив свойство <xref:System.Windows.Forms.DataGridViewColumn.DataPropertyName%2A> <xref:System.Windows.Forms.DataGridViewComboBoxColumn?displayProperty=nameWithType>.  
  
 Столбцы с полями со списками не создаются автоматически при привязке данных к элементу управления <xref:System.Windows.Forms.DataGridView>. Чтобы использовать столбцы поля со списком, необходимо создать их вручную и добавить их в коллекцию, возвращенную свойством <xref:System.Windows.Forms.DataGridView.Columns%2A>.  
  
## <a name="datagridviewlinkcolumn"></a>датагридвиевлинкколумн  
 С помощью <xref:System.Windows.Forms.DataGridViewLinkColumn>можно отобразить столбец ячеек, содержащих гиперссылки. Это полезно для значений URL-адресов в источнике данных или в качестве альтернативы столбцу кнопки для специальных поведений, таких как открытие окна с дочерними записями.  
  
 Столбцы связей не создаются автоматически при привязке данных к элементу управления <xref:System.Windows.Forms.DataGridView>. Чтобы использовать ссылочные столбцы, необходимо создать их вручную и добавить их в коллекцию, возвращенную свойством <xref:System.Windows.Forms.DataGridView.Columns%2A>.  
  
 Вы можете ответить на щелчки по ссылкам, обрабатывая событие <xref:System.Windows.Forms.DataGridView.CellContentClick>. Это событие отличается от событий <xref:System.Windows.Forms.DataGridView.CellClick> и <xref:System.Windows.Forms.DataGridView.CellMouseClick>, происходящих, когда пользователь щелкает в любом месте ячейки.  
  
 Класс <xref:System.Windows.Forms.DataGridViewLinkColumn> предоставляет несколько свойств для изменения внешнего вида ссылок до, во время и после их нажатия.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn>
- <xref:System.Windows.Forms.DataGridViewButtonColumn>
- <xref:System.Windows.Forms.DataGridViewCheckBoxColumn>
- <xref:System.Windows.Forms.DataGridViewComboBoxColumn>
- <xref:System.Windows.Forms.DataGridViewImageColumn>
- <xref:System.Windows.Forms.DataGridViewTextBoxColumn>
- <xref:System.Windows.Forms.DataGridViewLinkColumn>
- [Элемент управления DataGridView](datagridview-control-windows-forms.md)
- [Практическое руководство. Вывод изображений в ячейках элемента управления DataGridView в Windows Forms](how-to-display-images-in-cells-of-the-windows-forms-datagridview-control.md)
- [Практическое руководство. Работа со столбцами изображений в элементе управления DataGridView в Windows Forms](how-to-work-with-image-columns-in-the-windows-forms-datagridview-control.md)
- [Настройка элементов управления DataGridView в Windows Forms](customizing-the-windows-forms-datagridview-control.md)
