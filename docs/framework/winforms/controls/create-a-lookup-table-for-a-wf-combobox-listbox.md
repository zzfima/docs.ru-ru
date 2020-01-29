---
title: Создание таблицы подстановок для элемента управления ComboBox, ListBox или CheckedListBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CheckedListBox control [Windows Forms], creating lookup tables
- lookup tables
- list boxes [Windows Forms], lookup tables
- ListBox control [Windows Forms], lookup tables
- ComboBox control [Windows Forms], lookup table
- lookup tables [Windows Forms], creating for controls
- combo boxes [Windows Forms], lookup tables
- ListBox control [Windows Forms], creating lookup tables
ms.assetid: 4ce35f12-1f4e-4317-92d1-af8686a8cfaa
ms.openlocfilehash: 4bbbc66a56c7ce269c2dabd593db88f96907d755
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76737371"
---
# <a name="how-to-create-a-lookup-table-for-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a>Практическое руководство. Создание таблицы подстановки для элемента управления ComboBox, ListBox или CheckedListBox в Windows Forms
Иногда полезно отображать данные в удобном для пользователя формате в форме Windows Forms и при этом сохранять их в формате, требуемом в используемой программе. Например, в бланке заказа продуктов питания могут отображаться элементы меню с названиями продуктов в списке. Однако таблица данных регистрации заказа будет содержать уникальные идентификаторы, представляющие продукты питания. В таблице ниже представлен пример хранения и отображения данных бланка заказа продуктов питания.  
  
### <a name="orderdetailstable"></a>OrderDetailsTable  
  
|OrderID|Код элемента|Количество|  
|-------------|------------|--------------|  
|4085|12|1|  
|4086|13|3|  
  
### <a name="itemtable"></a>ItemTable  
  
|ИДЕНТИФИКАТОР|Name|  
|--------|----------|  
|12|Картофель|  
|13|Цыпленок|  
  
 В этом сценарии одна таблица, **ордердетаилстабле**, хранит фактические сведения, которые будут связаны с отображением и сохранением. Однако с целью экономии места они представлены в неудобном для восприятия виде. Другая таблица, **итемтабле**, содержит только сведения о том, какой идентификационный номер эквивалентен имени нектара, и ничего о фактическом заказе на возврат.  
  
 **Итемтабле** подключается к <xref:System.Windows.Forms.ComboBox>, <xref:System.Windows.Forms.ListBox>или <xref:System.Windows.Forms.CheckedListBox> управления через три свойства. Свойство `DataSource` содержит имя этой таблицы. Свойство `DisplayMember` содержит столбец данных этой таблицы, который необходимо отобразить в элементе управления (имя пищи). Свойство `ValueMember` содержит столбец данных этой таблицы с сохраненными данными (ИДЕНТИФИКАТОРом).  
  
 **Ордердетаилстабле** подключается к элементу управления по коллекции привязок, доступ к которому осуществляется через свойство <xref:System.Windows.Forms.Control.DataBindings%2A>. При добавлении объекта привязки в коллекцию свойство элемента управления подключается к определенному элементу данных (столбцу с ИДЕНТИФИКАЦИОНными номерами) в источнике данных ( **ордердетаилстабле**). Когда в элементе управления делается выбор, в этой таблице сохраняются вводимые данные.  
  
### <a name="to-create-a-lookup-table"></a>Создание таблицы подстановок  
  
1. Добавьте на форму элемент управления <xref:System.Windows.Forms.ComboBox>, <xref:System.Windows.Forms.ListBox> или <xref:System.Windows.Forms.CheckedListBox>.  
  
2. Произведите подключение к источнику данных.  
  
3. Установите связь между данными в двух таблицах. См. статью [Общие сведения об объектах DataRelation](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/0k21zcyx(v=vs.120)).  
  
4. Задайте перечисленные ниже свойства. Их можно задать в коде или в конструкторе.  
  
    |Идентификаторы|Параметр|  
    |--------------|-------------|  
    |<xref:System.Windows.Forms.ListControl.DataSource%2A>|Таблица, в которой содержатся сведения о том, какому коду соответствует тот или иной элемент. В предыдущем сценарии это `ItemTable`.|  
    |<xref:System.Windows.Forms.ListControl.DisplayMember%2A>|Столбец таблицы источника данных, который необходимо отобразить в элементе управления. В предыдущем сценарии это `"Name"` (для задания в коде используйте кавычки).|  
    |<xref:System.Windows.Forms.ListControl.ValueMember%2A>|Столбец таблицы источника данных, который содержит сохраняемую информацию. В предыдущем сценарии это `"ID"` (для задания в коде используйте кавычки).|  
  
5. В процедуре вызовите метод <xref:System.Windows.Forms.ControlBindingsCollection.Add%2A> класса <xref:System.Windows.Forms.ControlBindingsCollection> для привязки свойства <xref:System.Windows.Forms.ListControl.SelectedValue%2A> элемента управления к таблице, в которой регистрируются данные, вводимые в форме. Это также можно сделать в конструкторе, а не в коде, обратившись к свойству <xref:System.Windows.Forms.Control.DataBindings%2A> элемента управления в окне **Свойства** . В предыдущем сценарии это `OrderDetailsTable`, а столбец — `"ItemID"`.  
  
    ```vb  
    ListBox1.DataBindings.Add("SelectedValue", OrderDetailsTable, "ItemID")  
    ```  
  
    ```csharp  
    listBox1.DataBindings.Add("SelectedValue", OrderDetailsTable, "ItemID");  
    ```  
  
## <a name="see-also"></a>См. также:

- [Привязка данных и Windows Forms](../data-binding-and-windows-forms.md)
- [Общие сведения об элементе управления ListBox](listbox-control-overview-windows-forms.md)
- [Общие сведения об элементе управления ComboBox](combobox-control-overview-windows-forms.md)
- [Общие сведения об элементе управления CheckedListBox](checkedlistbox-control-overview-windows-forms.md)
- [Создание списка для выбора элементов в Windows Forms](windows-forms-controls-used-to-list-options.md)
