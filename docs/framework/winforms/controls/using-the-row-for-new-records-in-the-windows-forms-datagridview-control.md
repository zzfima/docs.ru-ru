---
title: "Использование строки элемента управления DataGridView, предназначенной для ввода новых данных, в Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DataGridView control [Windows Forms], adding rows for new records
- rows [Windows Forms], new records
- DataGridView control [Windows Forms], data entry
ms.assetid: 6110f1ea-9794-442c-a98a-f104a1feeaf4
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e349a33c90d08606da09ebdf32de6dedb8d6a52c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="using-the-row-for-new-records-in-the-windows-forms-datagridview-control"></a>Использование строки элемента управления DataGridView, предназначенной для ввода новых данных, в Windows Forms
При использовании <xref:System.Windows.Forms.DataGridView> для изменения данных в приложении, часто требуется предоставить пользователям возможность добавлять новые строки данных в хранилище данных. <xref:System.Windows.Forms.DataGridView> Элемент управления поддерживает эту функциональность путем предоставления строки для новых записей, которая всегда находится в последней строке. Он помечен с помощью символ звездочки (*) в заголовке строки. В следующих разделах рассматриваются некоторые из действий, рассмотрите возможность при включении программы со строкой для новых записей.  
  
## <a name="displaying-the-row-for-new-records"></a>Отображение строки для новых записей  
 Используйте <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> свойство, указывающее, отображается ли строка для новых записей. По умолчанию этому свойству присваивается значение `true`.  
  
 Для случая, привязанного к данным, строки для новых записей будет отображаться при <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> свойства элемента управления и <xref:System.ComponentModel.IBindingList.AllowNew%2A?displayProperty=nameWithType> свойства источника данных также присутствуют `true`. При выполнении любого `false` не будет отображена строка.  
  
## <a name="populating-the-row-for-new-records-with-default-data"></a>Заполнение строки для новых записей с данными по умолчанию  
 Когда пользователь выбирает строку для новых записей как текущую строку <xref:System.Windows.Forms.DataGridView> управления вызывает <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> событий.  
  
 Это событие предоставляет доступ к новому <xref:System.Windows.Forms.DataGridViewRow> и позволяет заполнять новые строки с данными по умолчанию. Дополнительные сведения см. в разделе [как: задание значений по умолчанию для новых строк в элементе управления DataGridView Windows Forms](../../../../docs/framework/winforms/controls/specify-default-values-for-new-rows-in-the-datagrid.md)  
  
## <a name="the-rows-collection"></a>Набор строк  
 Содержится в строке для новых записей <xref:System.Windows.Forms.DataGridView> элемента управления <xref:System.Windows.Forms.DataGridView.Rows%2A> коллекции но ведет себя по-разному в двух аспектах:  
  
-   Невозможно удалить строку для новых записей из <xref:System.Windows.Forms.DataGridView.Rows%2A> коллекции программным образом. <xref:System.InvalidOperationException> Исключение при попытке. Пользователь не может удалить строку для новых записей. <xref:System.Windows.Forms.DataGridViewRowCollection.Clear%2A?displayProperty=nameWithType> Метод не удаляет эту строку из <xref:System.Windows.Forms.DataGridView.Rows%2A> коллекции.  
  
-   Можно добавить отсутствует строка за строкой для новых записей. <xref:System.InvalidOperationException> Возникает при попытке. В результате строки для новых записей всегда используется последняя строка в <xref:System.Windows.Forms.DataGridView> элемента управления. Методы в <xref:System.Windows.Forms.DataGridViewRowCollection> , которые добавляют строки —<xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A>, <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopy%2A>, и <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopies%2A>— все вызывать методы вставки внутренне при наличии строки для новых записей.  
  
## <a name="visual-customization-of-the-row-for-new-records"></a>Настройка внешнего вида строки для новых записей  
 При создании строки для новых записей, он основан на строки, заданной аргументом <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> свойство. Стили ячеек, которые не определены для этой строки, наследуются от других свойств. Дополнительные сведения о наследовании стилей ячеек см. в разделе [стили ячеек в элементе управления DataGridView Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md).  
  
 Начальные значения, отображаемые в ячейках строки для новых записей, извлекается из каждой ячейки <xref:System.Windows.Forms.DataGridViewCell.DefaultNewRowValue%2A> свойство. Для ячеек типа <xref:System.Windows.Forms.DataGridViewImageCell>, это свойство возвращает изображение-заполнитель. В противном случае это свойство возвращает `null`. Можно переопределить это свойство для возврата пользовательское значение. Тем не менее, можно заменить исходные значения <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> обработчик событий, когда фокус вводит строку для новых записей.  
  
 Стандартные значки для заголовка этой строки, которые стрелка или звездочка, не предоставляются открыто. Если вы хотите настроить значки, необходимо создать настраиваемый <xref:System.Windows.Forms.DataGridViewRowHeaderCell> класса.  
  
 Стандартные значки используют <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> свойство <xref:System.Windows.Forms.DataGridViewCellStyle> используется ячейки заголовка строки. Стандартные значки не отображаются, если не хватает места, чтобы отобразить их полностью.  
  
 Если ячейки заголовка строки задано строковое значение, и не хватает места для текста и значок, значок сначала удалить.  
  
## <a name="sorting"></a>Сортировка  
 В несвязанном режиме новые записи всегда добавляются в конец <xref:System.Windows.Forms.DataGridView> даже если пользователь произвел сортировку содержимого <xref:System.Windows.Forms.DataGridView>. Пользователь должен еще раз применить сортировки для сортировки строк в правильное положение; Это поведение аналогично значению <xref:System.Windows.Forms.ListView> элемента управления.  
  
 В данных связанном и виртуальном режимах результат вставки при применении сортировки будет зависеть от реализации модели данных. Для [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)], строка немедленно упорядочить в правильном положении.  
  
## <a name="other-notes-on-the-row-for-new-records"></a>Другие заметки на строку для новых записей  
 Не удается задать <xref:System.Windows.Forms.DataGridViewRow.Visible%2A> свойства для этой строки `false`. <xref:System.InvalidOperationException> Возникает при попытке.  
  
 Строки для новых записей всегда создается в невыбранном состоянии.  
  
## <a name="virtual-mode"></a>Виртуальный режим  
 При реализации виртуального режима необходимо отследить, когда в модель данных, когда откатывать добавления строки необходимо строку для новых записей. Конкретная реализация этих функций зависит от реализации модели данных и соответствующей семантики транзакций, например, является ли область фиксации на уровне ячейки или строки. Дополнительные сведения см. в разделе [виртуальный режим в элементе управления DataGridView Windows Forms](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded?displayProperty=nameWithType>  
 [Ввод данных с помощью элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)  
 [Практическое руководство. Определение значений по умолчанию для новых строк элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/specify-default-values-for-new-rows-in-the-datagrid.md)
