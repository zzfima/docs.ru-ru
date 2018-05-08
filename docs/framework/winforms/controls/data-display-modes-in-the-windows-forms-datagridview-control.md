---
title: Режимы отображения данных в элементе управления DataGridView в Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms], display modes
- data grids [Windows Forms], display modes
- DataGridView control [Windows Forms], display modes
ms.assetid: 9755a030-3f3f-4705-a661-ba5a48a81875
ms.openlocfilehash: f97576218df651553ed1ac5f681d1ec0b4ab5ef3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="data-display-modes-in-the-windows-forms-datagridview-control"></a>Режимы отображения данных в элементе управления DataGridView в Windows Forms
<xref:System.Windows.Forms.DataGridView> Элемент управления может отображать данные в трех разных режимах: связанном, свободных и виртуальном. Выберите наиболее подходящий режим, в зависимости от требований.  
  
## <a name="unbound"></a>Отсутствует привязка  
 Несвязанный режим подходит для отображения сравнительно небольших объемов данных, в которой можно управлять программно. Не присоединять <xref:System.Windows.Forms.DataGridView> элемент управления источником данных, как в режиме привязки. Вместо этого вы должны самостоятельно заполнить элемент управления, обычно с помощью <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A?displayProperty=nameWithType> метод.  
  
 Несвязанный режим может быть особенно полезен для статических, только для чтения данных, или если вы хотите предоставить кода, взаимодействующая с во внешнем хранилище данных. Если требуется, чтобы пользователи могли взаимодействовать с внешним источником данных, однако обычно используется связанный режим.  
  
 Пример, в котором используется только для чтения несвязанных <xref:System.Windows.Forms.DataGridView>, в разделе [как: создание свободного элемента управления DataGridView Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-an-unbound-windows-forms-datagridview-control.md).  
  
## <a name="bound"></a>Привязки  
 Связанный режим подходит для управления данными посредством автоматического взаимодействия с хранилищем данных. Можно присоединить <xref:System.Windows.Forms.DataGridView> элемент управления источником данных, задав <xref:System.Windows.Forms.DataGridView.DataSource%2A> свойство. Когда элемент управления с привязкой к данным, строки данных помещаются и принимаются без необходимости явного управления со стороны пользователя. Когда <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A> свойство `true`, каждый столбец в источнике данных вызовет соответствующего столбца в элементе управления. Если вы предпочитаете создавать свои собственные столбцы, можно установить это свойство в `false` и использовать <xref:System.Windows.Forms.DataGridViewColumn.DataPropertyName%2A> свойство для привязки каждого столбца при его настройке. Это полезно в том случае, если требуется использовать тип столбца, отличным от типов, которые создаются по умолчанию. Дополнительные сведения см. в разделе [типов столбцов в элементе управления DataGridView Windows Forms](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md).  
  
 Пример с использованием связанного <xref:System.Windows.Forms.DataGridView> управления см. в разделе [Пошаговое руководство: проверка данных в элементе управления DataGridView Windows Forms](../../../../docs/framework/winforms/controls/walkthrough-validating-data-in-the-windows-forms-datagridview-control.md).  
  
 Можно также добавить несвязанные столбцы для <xref:System.Windows.Forms.DataGridView> элемента управления в режиме привязки. Это полезно в том случае, если требуется отобразить столбец кнопки или ссылки, которые позволяют пользователям выполнять действия на отдельные строки. Также полезно для отображения столбцов со значениями, рассчитанными из связанных столбцов. Можно заполнить при помощи значений ячеек для вычисляемых столбцов в обработчике <xref:System.Windows.Forms.DataGridView.CellFormatting> событий. Если вы используете <xref:System.Data.DataSet> или <xref:System.Data.DataTable> как источник данных, однако может потребоваться использовать <xref:System.Data.DataColumn.Expression%2A?displayProperty=nameWithType> свойство Создание вычисляемого столбца. В этом случае <xref:System.Windows.Forms.DataGridView> элемент управления будет обрабатывать вычисляемый столбец, так же, как и любой другой столбец в источнике данных.  
  
 Сортировка по несвязанным столбцам в связанном режиме не поддерживается. Если создание непривязанного столбца в режиме привязки, содержащий изменяемые пользователем значения, необходимо реализовать виртуальный режим для сохранения этих значений при сортировке элемента управления по связанному столбцу.  
  
## <a name="virtual"></a>Виртуальный  
 Виртуальный режим позволяет реализовать собственные операции управления данными. Это необходимо для сохранения значений несвязанных столбцов в связанном режиме при сортировке элемента управления по связанным столбцам. Виртуальный режим в основном используются, то для оптимизации производительности при взаимодействии с большими объемами данных.  
  
 Можно присоединить <xref:System.Windows.Forms.DataGridView> управления кэша, в которой можно управлять и код управляет отправкой и получением строк данных. Чтобы сохранить небольшой объем памяти, кэш должен быть похожего размера на число строк, отображаемых в данный момент. При прокрутке новых строк в представлении, код запрашивает новые данные из кэша и при необходимости очищает старые данные из памяти.  
  
 При реализации виртуального режима необходимо отслеживать, если новая строка требуется в модели данных и при откате добавления новой строки. Конкретная реализация этой функции будет зависеть от реализации модели данных и семантика транзакций модели данных. является ли область фиксации на уровне ячейки или строки.  
  
 Дополнительные сведения о виртуальном режиме см. в разделе [виртуальный режим в элементе управления DataGridView Windows Forms](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md). Пример, показывающий, как использовать виртуальный режим события см. в разделе [Пошаговое руководство: реализация виртуального режима в элементе управления DataGridView Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.BindingSource>  
 <xref:System.Windows.Forms.DataGridViewColumn.DataPropertyName%2A?displayProperty=nameWithType>  
 [Отображение данных с помощью элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 [Типы столбцов элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)  
 [Пошаговое руководство. Создание не связанного с данными элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/walkthrough-creating-an-unbound-windows-forms-datagridview-control.md)  
 [Практическое руководство. Привязка данных к элементу управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-bind-data-to-the-windows-forms-datagridview-control.md)  
 [Виртуальный режим элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md)  
 [Пошаговое руководство. Реализация виртуального режима для элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md)
