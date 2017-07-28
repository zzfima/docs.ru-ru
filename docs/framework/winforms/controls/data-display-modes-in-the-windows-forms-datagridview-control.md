---
title: "Режимы отображения данных в элементе управления DataGridView в Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "данные [Windows Forms], режимы отображения"
  - "таблицы данных, режимы отображения"
  - "DataGridView - элемент управления [Windows Forms], режимы отображения"
ms.assetid: 9755a030-3f3f-4705-a661-ba5a48a81875
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Режимы отображения данных в элементе управления DataGridView в Windows Forms
Элемент управления <xref:System.Windows.Forms.DataGridView> может отображать данные в трех разных режимах: в связанном, несвязанном и виртуальном.  При выборе приемлемого метода следует исходить из конкретных потребностей.  
  
## Несвязанный режим  
 Несвязанный режим подходит для отображения относительно небольших объемов данных, управляемых программным образом.  Элемент управления <xref:System.Windows.Forms.DataGridView> не присоединяется напрямую к источнику данных в несвязанном режиме.  Вместо этого элемент управления необходимо заполнить самостоятельно, что обычно делается при помощи метода <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A?displayProperty=fullName>.  
  
 Несвязанный режим может оказаться особенно полезным для статичных данных, предназначенных только для чтения, или когда для взаимодействия с внешнем хранилищем данных требуется собственный код.  При этом, чтобы пользователи могли взаимодействовать с внешним хранилищем данных, как правило, используется связанный режим.  
  
 Пример, в котором используется несвязанный режим только для чтения <xref:System.Windows.Forms.DataGridView>, см. в разделе [Практическое руководство. Создание не связанного с данными элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-an-unbound-windows-forms-datagridview-control.md).  
  
## Связанный режим  
 Связанный режим подходит для управления данными посредством автоматического взаимодействия с хранилищем данных.  Элемент управления <xref:System.Windows.Forms.DataGridView> можно присоединить непосредственно к его источнику данных путем настройки свойства <xref:System.Windows.Forms.DataGridView.DataSource%2A>.  Когда элемент управления привязан к данным, строки с данными передаются и принимаются без необходимости явного управления со стороны пользователя.  Если свойство <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A> имеет значение `true`, каждый столбец в источнике данных будет вызывать создание соответствующего столбца в элементе управления.  Если необходимо создать собственные столбцы, этому свойству можно присвоить значение `false` и использовать свойство <xref:System.Windows.Forms.DataGridViewColumn.DataPropertyName%2A> для привязки каждого столбца по мере его настройки.  Это полезно, когда требуется использовать тип столбца, отличный от типов, создаваемых по умолчанию.  Дополнительные сведения см. в разделе [Типы столбцов элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md).  
  
 Пример с использованием связанного элемента управления <xref:System.Windows.Forms.DataGridView> см. в разделе [Пример. Проверка данных элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/walkthrough-validating-data-in-the-windows-forms-datagridview-control.md).  
  
 Кроме того, несвязанные столбцы можно добавить в элемент управления <xref:System.Windows.Forms.DataGridView> в связанном режиме.  Это может оказаться полезным, когда требуется отобразить столбец с кнопками или ссылками, позволяющими пользователям выполнять действия с определенными строками.  Кроме того, это может пригодиться для отображения столбцов со значениями, рассчитанными из связанных столбцов.  Значения ячеек для рассчитанных столбцов можно заполнить в обработчике для события <xref:System.Windows.Forms.DataGridView.CellFormatting>.  Даже если в качестве источника данных используется <xref:System.Data.DataSet> или <xref:System.Data.DataTable>, может возникнуть необходимость использования свойства <xref:System.Data.DataColumn.Expression%2A?displayProperty=fullName> для создания рассчитанного столбца.  В этом случае, элемент управления <xref:System.Windows.Forms.DataGridView> будет обращаться с рассчитанным столбцом, как с любым другим столбцом в источнике данных.  
  
 Сортировка по несвязанным столбцам в связанном режиме не поддерживается.  Если создать связанный столбец, содержащий изменяемые пользователем значения, в несвязанном режиме, потребуется реализовать виртуальный режим для сохранения этих значений при сортировке элемента управления по связанному столбцу.  
  
## Виртуальный режим  
 Виртуальный режим позволит реализовать собственные операций по управлению данными.  Этот режим необходим для сохранения значений несвязанных столбцов в связанном режиме при сортировке элемента управления по связанным столбцам.  Однако виртуальный режим в большинстве случаев используется для оптимизации производительности при взаимодействии с большими объемами данных.  
  
 Элемент управления <xref:System.Windows.Forms.DataGridView> присоединяется к управляемому кэшу, и код управляет отправкой и получением строк данных.  Чтобы поддерживать небольшой объем памяти, размер кэша должен соответствовать количеству отображаемых строк.  Когда пользователь прокручивает на экране новые строки, код запрашивает новые данные из кэша и может очистить память от старых данных.  
  
 При реализации виртуального режима необходимо отслеживать потребность в строке для добавления новых записей в соответствии с моделью данных, а также потребность в откате добавления строки.  Конкретная реализация данных функциональных возможностей будет зависеть от реализации модели данных и соответствующей семантики транзакций модели данных, например, используется ли область фиксации на уровне ячеек или на уровне строк.  
  
 Дополнительные сведения о виртуальном режиме содержатся в разделе [Виртуальный режим элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md).  Пример, показывающий использование событий виртуального режима содержится в разделе [Пример. Реализация виртуального режима для элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md).  
  
## См. также  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.BindingSource>   
 <xref:System.Windows.Forms.DataGridViewColumn.DataPropertyName%2A?displayProperty=fullName>   
 [Отображение данных с помощью элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)   
 [Типы столбцов элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)   
 [Пример. Создание не связанного с данными элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/walkthrough-creating-an-unbound-windows-forms-datagridview-control.md)   
 [Практическое руководство. Привязка данных к элементу управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-bind-data-to-the-windows-forms-datagridview-control.md)   
 [Виртуальный режим элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md)   
 [Пример. Реализация виртуального режима для элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md)