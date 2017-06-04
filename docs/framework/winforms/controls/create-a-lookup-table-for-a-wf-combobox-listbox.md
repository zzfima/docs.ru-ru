---
title: "Практическое руководство. Создание таблицы подстановки для элемента управления ComboBox, ListBox или CheckedListBox в Windows Forms | Microsoft Docs"
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
  - "CheckedListBox - элемент управления [Windows Forms], создание таблицы подстановок"
  - "поля со списком, таблицы подстановок"
  - "ComboBox - элемент управления [Windows Forms], таблица подстановок"
  - "списки, таблицы подстановок"
  - "ListBox - элемент управления [Windows Forms], создание таблицы подстановок"
  - "ListBox - элемент управления [Windows Forms], таблицы подстановок"
  - "таблицы подстановок"
  - "таблицы подстановок, создание для элементов управления"
ms.assetid: 4ce35f12-1f4e-4317-92d1-af8686a8cfaa
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Практическое руководство. Создание таблицы подстановки для элемента управления ComboBox, ListBox или CheckedListBox в Windows Forms
Иногда полезно отображать данные в удобном для пользователя формате в форме Windows Forms и при этом сохранять их в формате, требуемом в используемой программе.  Например, в бланке заказа продуктов питания могут отображаться элементы меню с названиями продуктов в списке.  Однако таблица данных регистрации заказа будет содержать уникальные идентификаторы, представляющие продукты питания.  В таблице ниже представлен пример хранения и отображения данных бланка заказа продуктов питания.  
  
### OrderDetailsTable  
  
|OrderID|Код элемента|Количество|  
|-------------|------------------|----------------|  
|4085|12|1|  
|4086|13|3|  
  
### ItemTable  
  
|Идентификатор|Имя|  
|-------------------|---------|  
|12|Картофель|  
|13|Цыпленок|  
  
 В этом сценарии одна таблица \(OrderDetailsTable\) содержит фактические сведения, важные с точки зрения отображения и сохранения.  Однако с целью экономии места они представлены в неудобном для восприятия виде.  Другая таблица \(ItemTable\) содержит только данные, связанные с представлением, а именно сведения о том, какой код соответствует тому или иному продукту. Информации о фактических заказах продуктов в ней нет.  
  
 Таблица ItemTable связана с элементом управления <xref:System.Windows.Forms.ComboBox>, <xref:System.Windows.Forms.ListBox> или <xref:System.Windows.Forms.CheckedListBox> с помощью трех свойств.  Свойство  `DataSource`  содержит имя таблицы.  Свойство  `DisplayMember` содержит столбец данных таблицы, который должен отображаться в элементе управления \(название продукта\).  Свойство  `ValueMember`  содержит столбец данных таблицы с сохраняемыми данными \(идентификатор\).  
  
 Таблица OrderDetailsTable связана с элементом управления с помощью коллекции привязок, доступных через свойство <xref:System.Windows.Forms.Control.DataBindings%2A>.  При добавлении объекта привязки в коллекцию свойство элемента управления связывается с определенным элементом данных \(столбцом кодов\) в источнике данных \(таблице OrderDetailsTable\).  Когда в элементе управления делается выбор, в этой таблице сохраняются вводимые данные.  
  
### Создание таблицы подстановок  
  
1.  Добавьте на форму элемент управления <xref:System.Windows.Forms.ComboBox>, <xref:System.Windows.Forms.ListBox> или <xref:System.Windows.Forms.CheckedListBox>.  
  
2.  Произведите подключение к источнику данных.  
  
3.  Установите связь между данными в двух таблицах.  См. раздел [Знакомство с объектами DataRelation](../Topic/Introduction%20to%20DataRelation%20Objects.md).  
  
4.  Задайте перечисленные ниже свойства.  Их можно задать в коде или в конструкторе.  
  
    |Свойство|Параметр|  
    |--------------|--------------|  
    |<xref:System.Windows.Forms.ListControl.DataSource%2A>|Таблица, в которой содержатся сведения о том, какому коду соответствует тот или иной элемент.  В приведенном выше сценарии это  `ItemTable`.|  
    |<xref:System.Windows.Forms.ListControl.DisplayMember%2A>|Столбец таблицы источника данных, который необходимо отобразить в элементе управления.  В приведенном выше сценарии это  `"Name"`  \(для задания в коде используйте кавычки\).|  
    |<xref:System.Windows.Forms.ListControl.ValueMember%2A>|Столбец таблицы источника данных, который содержит сохраняемую информацию.  В приведенном выше сценарии это  `"ID"`  \(для задания в коде используйте кавычки\).|  
  
5.  В процедуре вызовите метод <xref:System.Windows.Forms.ControlBindingsCollection.Add%2A> класса <xref:System.Windows.Forms.ControlBindingsCollection> для привязки свойства <xref:System.Windows.Forms.ListControl.SelectedValue%2A> элемента управления к таблице, в которой регистрируются данные, вводимые в форме.  Кроме того, вместо кода это можно сделать в конструкторе с помощью свойства <xref:System.Windows.Forms.Control.DataBindings%2A> элемента управления в окне **Свойства**.  В приведенном выше сценарии это  `OrderDetailsTable`, а столбец —  `"ItemID"`.  
  
    ```vb  
    ListBox1.DataBindings.Add("SelectedValue", OrderDetailsTable, "ItemID")  
  
    ```  
  
    ```csharp  
    listBox1.DataBindings.Add("SelectedValue", OrderDetailsTable, "ItemID");  
  
    ```  
  
## См. также  
 [Связывание данных и Windows Forms](../../../../docs/framework/winforms/data-binding-and-windows-forms.md)   
 [Общие сведения об элементе управления ListBox](../../../../docs/framework/winforms/controls/listbox-control-overview-windows-forms.md)   
 [Общие сведения об элементе управления ComboBox](../../../../docs/framework/winforms/controls/combobox-control-overview-windows-forms.md)   
 [Общие сведения об элементе управления CheckedListBox](../../../../docs/framework/winforms/controls/checkedlistbox-control-overview-windows-forms.md)   
 [Создание списка для выбора элементов в Windows Forms](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)