---
title: "Использование строки элемента управления DataGridView, предназначенной для ввода новых данных, в Windows Forms | Microsoft Docs"
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
  - "DataGridView - элемент управления [Windows Forms], добавление строк для новых записей"
  - "DataGridView - элемент управления [Windows Forms], ввод данных"
  - "строки, новые записи"
ms.assetid: 6110f1ea-9794-442c-a98a-f104a1feeaf4
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Использование строки элемента управления DataGridView, предназначенной для ввода новых данных, в Windows Forms
При использовании элемента управления <xref:System.Windows.Forms.DataGridView> для редактирования данных в приложении зачастую бывает необходимо предоставить пользователям возможность добавления новых строк данных в хранилище данных.  Эта функциональная возможность обеспечивается элементом управления <xref:System.Windows.Forms.DataGridView> путем предоставления строки для добавления новых записей, которая всегда находится в самом конце сетки.  Она всегда помечается звездочкой \(\*\) в заголовке строки.  В последующих разделах рассматривается ряд особенностей, которые следует учитывать при программировании, если строка для добавления новых записей включена.  
  
## Отображение строки для добавления новых записей  
 Свойство <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> указывает, должна ли отображаться строка для добавления новых записей.  По умолчанию для этого свойства устанавливается значение `true`.  
  
 В случае использования связывания данных строка для добавления новых записей будет отображаться, только если свойство <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> элемента управления и свойство <xref:System.ComponentModel.IBindingList.AllowNew%2A?displayProperty=fullName> источника данных оба установлены в значение `true`.  Если любое из них имеет значение `false`, строка не отображается.  
  
## Заполнение строки для добавления новых записей данными по умолчанию  
 При выборе пользователем строки для добавления новых записей в качестве текущей элемент управления <xref:System.Windows.Forms.DataGridView> вызывает событие <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded>.  
  
 Это событие обеспечивает доступ к новой строке <xref:System.Windows.Forms.DataGridViewRow> и позволяет заполнить ее данными по умолчанию.  Дополнительные сведения см. в разделе [Практическое руководство. Определение значений по умолчанию для новых строк элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/specify-default-values-for-new-rows-in-the-datagrid.md).  
  
## Коллекция строк  
 Строка для добавления новых записей включается в коллекцию <xref:System.Windows.Forms.DataGridView.Rows%2A> элемента управления <xref:System.Windows.Forms.DataGridView>, но имеет два отличия.  
  
-   Строку для добавления новых записей нельзя удалить из коллекции <xref:System.Windows.Forms.DataGridView.Rows%2A> программным путем.  При попытке ее удаления возникает исключение <xref:System.InvalidOperationException>.  Строка для добавления новых записей также не может быть удалена пользователем.  Метод <xref:System.Windows.Forms.DataGridViewRowCollection.Clear%2A?displayProperty=fullName> не удаляет эту строку из коллекции <xref:System.Windows.Forms.DataGridView.Rows%2A>.  
  
-   После строки для добавления новых записей нельзя добавить другую строку.  При попытке присвоения этого значения возникает исключение <xref:System.InvalidOperationException>.  Таким образом, строка для добавления новых записей всегда является последней строкой элемента управления <xref:System.Windows.Forms.DataGridView>.  При наличии строки для добавления новых записей методы <xref:System.Windows.Forms.DataGridViewRowCollection>, используемые для добавления строк — <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A>, <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopy%2A> и <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopies%2A>, — выполняют внутреннюю вставку строк.  
  
## Настройка внешнего вида строки для добавления новых записей  
 При создании строки для добавления новых записей ее внешний вид соответствует строке, указанной в свойстве <xref:System.Windows.Forms.DataGridView.RowTemplate%2A>.  Стили ячеек, которые не определены для этой строки, наследуются от других свойств.  Дополнительные сведения о наследовании стилей ячеек см. в разделе [Стили ячеек элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md).  
  
 Исходные значения, отображаемые в ячейках строки для добавления новых записей, берутся из свойства <xref:System.Windows.Forms.DataGridViewCell.DefaultNewRowValue%2A> каждой ячейки.  Для ячеек типа <xref:System.Windows.Forms.DataGridViewImageCell> это свойство возвращает изображение\-заполнитель.  В противном случае это свойство возвращает значение `null`.  Чтобы это свойство возвращало пользовательское значение, его можно переопределить.  Однако исходные значения могут заменяться обработчиком событий <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded>, когда строка для добавления новых записей получает фокус.  
  
 Стандартные значки для заголовка этой строки, а именно стрелка или звездочка, не предоставлены для открытого доступа.  При необходимости настроить значки потребуется создать пользовательский класс <xref:System.Windows.Forms.DataGridViewRowHeaderCell>.  
  
 Стандартные значки используют свойство <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> свойства <xref:System.Windows.Forms.DataGridViewCellStyle>, используемого ячейкой заголовка строки.  Стандартные значки не отображаются, если для их полного отображения недостаточно места.  
  
 Если для ячейки заголовка строки задано строковое значение, но для одновременного отображения текста и значка недостаточно места, в первую очередь не будет отображаться значок.  
  
## Сортировка  
 В несвязанном режиме новые записи всегда добавляются в конец элемента управления <xref:System.Windows.Forms.DataGridView>, даже если пользователь произвел сортировку содержимого <xref:System.Windows.Forms.DataGridView>.  Чтобы строка заняла правильную позицию, пользователю потребуется произвести сортировку повторно, так же как и в случае с элементом управления <xref:System.Windows.Forms.ListView>.  
  
 В связанном и виртуальном режимах результат вставки при применении сортировки будет зависеть от реализованной модели данных.  В случае с [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] строка автоматически занимает правильную позицию.  
  
## Примечания к использованию строк для добавления новых записей  
 Свойству <xref:System.Windows.Forms.DataGridViewRow.Visible%2A> этой строки нельзя присвоить значение `false`.  При попытке присвоения этого значения возникает исключение <xref:System.InvalidOperationException>.  
  
 При создании строки для добавления новых записей она всегда находится в невыделенном состоянии.  
  
## Виртуальный режим  
 При реализации виртуального режима необходимо отслеживать потребность в строке для добавления новых записей в соответствии с моделью данных, а также потребность в откате добавления строки.  Конкретная реализация данных функциональных возможностей зависит от реализации модели данных и соответствующей семантики транзакций, например, используется ли область фиксации на уровне ячеек или на уровне строк.  Дополнительные сведения см. в разделе [Виртуальный режим элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md).  
  
## См. также  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded?displayProperty=fullName>   
 [Ввод данных с помощью элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)   
 [Практическое руководство. Определение значений по умолчанию для новых строк элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/specify-default-values-for-new-rows-in-the-datagrid.md)