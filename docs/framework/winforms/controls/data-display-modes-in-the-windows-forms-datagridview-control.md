---
title: Режимы вывода данных в элементе управления DataGridView
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms], display modes
- data grids [Windows Forms], display modes
- DataGridView control [Windows Forms], display modes
ms.assetid: 9755a030-3f3f-4705-a661-ba5a48a81875
ms.openlocfilehash: ad6be647e3a36904b055fd6771f539df28938fab
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744017"
---
# <a name="data-display-modes-in-the-windows-forms-datagridview-control"></a>Режимы отображения данных в элементе управления DataGridView в Windows Forms
Элемент управления <xref:System.Windows.Forms.DataGridView> может отображать данные в трех различных режимах: связанные, несвязанные и виртуальные. Выберите наиболее подходящий режим в зависимости от ваших требований.  
  
## <a name="unbound"></a>Несвязанного  
 Несвязанный режим подходит для отображения относительно небольших объемов данных, которыми можно управлять программно. Вы не присоединяете элемент управления <xref:System.Windows.Forms.DataGridView> напрямую к источнику данных, как в связанном режиме. Вместо этого необходимо заполнить элемент управления самостоятельно, обычно с помощью метода <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A?displayProperty=nameWithType>.  
  
 Несвязанный режим может быть особенно полезен для статических данных, предназначенных только для чтения, или при необходимости предоставления собственного кода, взаимодействующего с внешним хранилищем данных. Однако, если требуется, чтобы пользователи взаимодействовали с внешним источником данных, обычно используется режим с привязкой.  
  
 Пример, в котором используется несвязанная <xref:System.Windows.Forms.DataGridView>только для чтения, см. [в разделе как создать несвязанный Windows Forms элемент управления DataGridView](how-to-create-an-unbound-windows-forms-datagridview-control.md).  
  
## <a name="bound"></a>Bound  
 Связанный режим подходит для управления данными с помощью автоматического взаимодействия с хранилищем данных. Можно присоединить элемент управления <xref:System.Windows.Forms.DataGridView> непосредственно к его источнику данных, задав свойство <xref:System.Windows.Forms.DataGridView.DataSource%2A>. Если элемент управления привязан к данным, строки данных отправляются и извлекаются без необходимости явного управления на вашей части. Если свойство <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A> `true`, то каждый столбец в источнике данных приведет к созданию соответствующего столбца в элементе управления. Если вы предпочитаете создавать собственные столбцы, можно присвоить этому свойству значение `false` и использовать свойство <xref:System.Windows.Forms.DataGridViewColumn.DataPropertyName%2A> для привязки каждого столбца при его настройке. Это полезно, если необходимо использовать тип столбца, отличный от типов, создаваемых по умолчанию. Дополнительные сведения см. [в разделе Типы столбцов в элементе управления Windows Forms DataGridView](column-types-in-the-windows-forms-datagridview-control.md).  
  
 Пример использования привязанного элемента управления <xref:System.Windows.Forms.DataGridView> см. в разделе [Пошаговое руководство. Проверка данных в элементе управления Windows Forms DataGridView](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md).  
  
 Можно также добавить несвязанные столбцы в элемент управления <xref:System.Windows.Forms.DataGridView> в связанном режиме. Это полезно, если требуется отобразить столбец кнопок или ссылок, позволяющих пользователям выполнять действия с конкретными строками. Также полезно отображать столбцы со значениями, рассчитанными из связанных столбцов. Можно заполнить значения ячеек для вычисляемых столбцов обработчика событий <xref:System.Windows.Forms.DataGridView.CellFormatting>. Однако при использовании <xref:System.Data.DataSet> или <xref:System.Data.DataTable> в качестве источника данных может потребоваться использовать свойство <xref:System.Data.DataColumn.Expression%2A?displayProperty=nameWithType> для создания вычисляемого столбца. В этом случае элемент управления <xref:System.Windows.Forms.DataGridView> будет рассматривать вычисляемый столбец так же, как любой другой столбец в источнике данных.  
  
 Сортировка по несвязанным столбцам в связанном режиме не поддерживается. При создании несвязанного столбца в связанном режиме, который содержит редактируемые пользователем значения, необходимо реализовать виртуальный режим для поддержки этих значений при сортировке элемента управления по связанному столбцу.  
  
## <a name="virtual"></a>Виртуализаци  
 В виртуальном режиме можно реализовать собственные операции управления данными. Это необходимо для сохранения значений несвязанных столбцов в связанном режиме, когда элемент управления сортируется по связанным столбцам. Однако основное использование виртуального режима заключается в оптимизации производительности при взаимодействии с большими объемами данных.  
  
 Вы подключаете элемент управления <xref:System.Windows.Forms.DataGridView> к кэшу, который управляете, и код контролирует, когда строки данных отправляются и извлекаются. Чтобы сократить объем памяти, размер кэша должен быть похож на число строк, отображаемых в настоящий момент. Когда пользователь прокручивает новые строки в представлении, код запрашивает новые данные из кэша и при необходимости очищает старые данные из памяти.  
  
 При реализации виртуального режима необходимо учитывать, когда в модели данных требуется новая строка и когда нужно откатить Добавление новой строки. Точная реализация этой функции будет зависеть от реализации модели данных и семантики транзакций модели данных. Указывает, находится ли область фиксации на уровне ячейки или строки.  
  
 Дополнительные сведения о виртуальном режиме см. [в разделе виртуальный режим в элементе управления Windows Forms DataGridView](virtual-mode-in-the-windows-forms-datagridview-control.md). Пример, демонстрирующий использование событий виртуального режима, см. в разделе [Пошаговое руководство. Реализация виртуального режима в элементе управления Windows Forms DataGridView](implementing-virtual-mode-wf-datagridview-control.md).  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.VirtualMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.DataGridViewColumn.DataPropertyName%2A?displayProperty=nameWithType>
- [Отображение данных с помощью элемента управления DataGridView в Windows Forms](displaying-data-in-the-windows-forms-datagridview-control.md)
- [Типы столбцов элемента управления DataGridView в Windows Forms](column-types-in-the-windows-forms-datagridview-control.md)
- [Пошаговое руководство. Создание не связанного с данными элемента управления DataGridView в Windows Forms](walkthrough-creating-an-unbound-windows-forms-datagridview-control.md)
- [Практическое руководство. Привязка данных к элементу управления DataGridView в Windows Forms](how-to-bind-data-to-the-windows-forms-datagridview-control.md)
- [Виртуальный режим элемента управления DataGridView в Windows Forms](virtual-mode-in-the-windows-forms-datagridview-control.md)
- [Пошаговое руководство. Реализация виртуального режима для элемента управления DataGridView в Windows Forms](implementing-virtual-mode-wf-datagridview-control.md)
