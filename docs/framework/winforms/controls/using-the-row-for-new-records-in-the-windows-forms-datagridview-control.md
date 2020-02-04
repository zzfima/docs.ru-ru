---
title: Использование строки для новых записей в элементе управления DataGridView
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], adding rows for new records
- rows [Windows Forms], new records
- DataGridView control [Windows Forms], data entry
ms.assetid: 6110f1ea-9794-442c-a98a-f104a1feeaf4
ms.openlocfilehash: 2fcd35f8c4d04909cdbc26f6a4293fdd570385b8
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728335"
---
# <a name="using-the-row-for-new-records-in-the-windows-forms-datagridview-control"></a>Использование строки элемента управления DataGridView, предназначенной для ввода новых данных, в Windows Forms
При использовании <xref:System.Windows.Forms.DataGridView> для редактирования данных в приложении часто требуется предоставить пользователям возможность добавлять новые строки данных в хранилище данных. Элемент управления <xref:System.Windows.Forms.DataGridView> поддерживает эту функцию, предоставляя строку для новых записей, которая всегда отображается как последняя строка. Он помечается символом звездочки (*) в заголовке строки. В следующих разделах рассматриваются некоторые моменты, которые следует учитывать при программировании со строкой для включения новых записей.  
  
## <a name="displaying-the-row-for-new-records"></a>Отображение строки для новых записей  
 Используйте свойство <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A>, чтобы указать, отображается ли строка для новых записей. Значение по умолчанию этого свойства равно `true`.  
  
 Для варианта с привязкой к данным строка для новых записей будет отображаться, если одновременно `true`свойство <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> элемента управления и свойство <xref:System.ComponentModel.IBindingList.AllowNew%2A?displayProperty=nameWithType> источника данных. Если значение `false`, строка не будет отображаться.  
  
## <a name="populating-the-row-for-new-records-with-default-data"></a>Заполнение строки для новых записей данными по умолчанию  
 Когда пользователь выбирает строку для новых записей в качестве текущей строки, элемент управления <xref:System.Windows.Forms.DataGridView> вызывает событие <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded>.  
  
 Это событие предоставляет доступ к новому <xref:System.Windows.Forms.DataGridViewRow> и позволяет заполнить новую строку данными по умолчанию. Дополнительные сведения см. в разделе [как указать значения по умолчанию для новых строк в элементе управления Windows Forms DataGridView.](specify-default-values-for-new-rows-in-the-datagrid.md)  
  
## <a name="the-rows-collection"></a>Коллекция Rows  
 Строка для новых записей содержится в <xref:System.Windows.Forms.DataGridView.Rows%2A> коллекции <xref:System.Windows.Forms.DataGridView> элемента управления, но ведет себя по-разному в двух отношениях:  
  
- Строку для новых записей нельзя удалить из коллекции <xref:System.Windows.Forms.DataGridView.Rows%2A> программным способом. При появлении попытки возникает исключение <xref:System.InvalidOperationException>. Пользователь также не может удалить строку для новых записей. Метод <xref:System.Windows.Forms.DataGridViewRowCollection.Clear%2A?displayProperty=nameWithType> не удаляет эту строку из коллекции <xref:System.Windows.Forms.DataGridView.Rows%2A>.  
  
- После строки для новых записей нельзя добавлять строки. При появлении попытки возникает <xref:System.InvalidOperationException>. В результате строка для новых записей всегда является последней строкой элемента управления <xref:System.Windows.Forms.DataGridView>. Методы в <xref:System.Windows.Forms.DataGridViewRowCollection>, которые добавляют строки (<xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A>, <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopy%2A>и <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopies%2A>— все методы вставки вызовов внутренне при наличии строки для новых записей.  
  
## <a name="visual-customization-of-the-row-for-new-records"></a>Визуальная настройка строки для новых записей  
 При создании строки для новых записей она основана на строке, заданной свойством <xref:System.Windows.Forms.DataGridView.RowTemplate%2A>. Все стили ячеек, не указанные для этой строки, наследуются от других свойств. Дополнительные сведения о наследовании стилей ячеек см. [в разделе Стили ячеек в элементе управления Windows Forms DataGridView](cell-styles-in-the-windows-forms-datagridview-control.md).  
  
 Начальные значения, отображаемые ячейками в строке для новых записей, извлекаются из свойства <xref:System.Windows.Forms.DataGridViewCell.DefaultNewRowValue%2A> каждой ячейки. Для ячеек типа <xref:System.Windows.Forms.DataGridViewImageCell>это свойство возвращает изображение заполнителя. В противном случае это свойство возвращает значение `null`. Это свойство можно переопределить, чтобы оно возвращало пользовательское значение. Однако эти начальные значения могут быть заменены <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> обработчиком событий, когда фокус вводит строку для новых записей.  
  
 Стандартные значки для заголовка этой строки, которые являются стрелками или звездочками, не предоставляются публично. Если вы хотите настроить значки, необходимо создать пользовательский класс <xref:System.Windows.Forms.DataGridViewRowHeaderCell>.  
  
 Стандартные значки используют свойство <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> <xref:System.Windows.Forms.DataGridViewCellStyle>, используемое ячейкой заголовка строки. Стандартные значки не отображаются, если недостаточно места для их полного отображения.  
  
 Если в ячейке заголовка строки задано строковое значение, и если недостаточно места для текста и значка, значок удаляется первыми.  
  
## <a name="sorting"></a>Сортировка  
 В несвязанном режиме новые записи всегда будут добавляться в конец <xref:System.Windows.Forms.DataGridView> даже в том случае, если пользователь сортирует содержимое <xref:System.Windows.Forms.DataGridView>. Пользователь должен будет повторно применить сортировку, чтобы отсортировать строку по правильному положению. Такое поведение аналогично поведению элемента управления <xref:System.Windows.Forms.ListView>.  
  
 В связанных с данными и виртуальных режимах поведение вставки при применении сортировки будет зависеть от реализации модели данных. Для ADO.NET строка немедленно сортируется в правильном положении.  
  
## <a name="other-notes-on-the-row-for-new-records"></a>Другие примечания к строке для новых записей  
 Невозможно задать для свойства <xref:System.Windows.Forms.DataGridViewRow.Visible%2A> этой строки значение `false`. При появлении попытки возникает <xref:System.InvalidOperationException>.  
  
 Строка для новых записей всегда создается в невыбранном состоянии.  
  
## <a name="virtual-mode"></a>Виртуальный режим  
 При реализации виртуального режима необходимо учитывать, когда в модели данных требуется строка для новых записей и когда необходимо выполнить откат добавления строки. Точная реализация этой функции зависит от реализации модели данных и ее семантики транзакций, например от того, находится ли область фиксации на уровне ячейки или строки. Дополнительные сведения см. [в статье виртуальный режим в элементе управления Windows Forms DataGridView](virtual-mode-in-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded?displayProperty=nameWithType>
- [Ввод данных с помощью элемента управления DataGridView в Windows Forms](data-entry-in-the-windows-forms-datagridview-control.md)
- [Практическое руководство. Определение значений по умолчанию для новых строк элемента управления DataGridView в Windows Forms](specify-default-values-for-new-rows-in-the-datagrid.md)
