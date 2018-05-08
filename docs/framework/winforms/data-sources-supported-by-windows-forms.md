---
title: Источники данных, поддерживаемые Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- collections [Windows Forms], binding to
- OLE DB providers [Windows Forms], Windows Forms
- DataTable class [Windows Forms], binding and Windows Forms
- Windows Forms, data binding
- DataView class [Windows Forms], binding and Windows Forms
- DataViewManager class [Windows Forms], binding and Windows Forms
- Windows Forms, source data
- arrays [Windows Forms]
- data sources [Windows Forms]
- data providers [Windows Forms]
- DataSet class [Windows Forms], binding and Windows Forms
- data [Windows Forms], data providers
ms.assetid: 3d2c43f6-462b-4d35-9c86-13e9afe012e1
ms.openlocfilehash: 4705c8a7153e94fa1cd23cf6c2f622d5cd66ec77
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="data-sources-supported-by-windows-forms"></a>Источники данных, поддерживаемые Windows Forms
В большинстве случаев привязка данных использовалась в приложениях для использования данных, хранящихся в базах данных. Привязки данных Windows Forms, предоставляет доступ к данным из баз данных, а также данные в другие структуры, таких как массивы и коллекции, при условии, что выполнены определенные минимальные требования.  
  
## <a name="structures-to-bind-to"></a>Структуры для привязки  
 В Windows Forms можно привязать к широкий набор структур, от простых объектов (простая привязка) до сложных списков, таких как таблицы данных ADO.NET (сложная привязка). Простой привязки Windows Forms поддерживает привязку к общим свойствам простого объекта. Привязки на основе списка в Windows Forms обычно требуется, чтобы объект поддерживал <xref:System.Collections.IList> интерфейса или <xref:System.ComponentModel.IListSource> интерфейса. Кроме того при связывании с помощью <xref:System.Windows.Forms.BindingSource> компонента, можно привязать к объекту, который поддерживает <xref:System.Collections.IEnumerable> интерфейса. Дополнительные сведения об интерфейсах, относящиеся к привязке данных см. в разделе [интерфейсах, которые относятся к привязке данных](../../../docs/framework/winforms/interfaces-related-to-data-binding.md).  
  
 Ниже перечислены структуры можно привязать к в Windows Forms.  
  
 <xref:System.Windows.Forms.BindingSource>  
 Объект <xref:System.Windows.Forms.BindingSource> является наиболее распространенным источником данных Windows Forms и выступает посредником между источником данных и элементы управления Windows Forms. Общие <xref:System.Windows.Forms.BindingSource> шаблон использования: для привязки элементов управления к <xref:System.Windows.Forms.BindingSource> и привязать <xref:System.Windows.Forms.BindingSource> к источнику данных (например, таблице данных ADO.NET или бизнес-объекта). <xref:System.Windows.Forms.BindingSource> Предоставляет службы и позволяет повысить уровень поддержки привязки данных. Например, список Windows Forms зависимости элементов управления, таких как <xref:System.Windows.Forms.DataGridView> и <xref:System.Windows.Forms.ComboBox> непосредственно не поддерживает привязку к <xref:System.Collections.IEnumerable> источники данных тем не менее, можно реализовать этот сценарий с помощью привязки через <xref:System.Windows.Forms.BindingSource>. В этом случае <xref:System.Windows.Forms.BindingSource> преобразует источник данных для <xref:System.Collections.IList>.  
  
 Простые объекты  
 Windows Forms поддерживает свойства элемента управления привязки данных к общим свойствам экземпляра объекта с помощью <xref:System.Windows.Forms.Binding> типа. Windows Forms также поддерживает привязка элементов управления на основе списка, например <xref:System.Windows.Forms.ListControl> на объект экземпляра, когда <xref:System.Windows.Forms.BindingSource> используется.  
  
 массив или коллекция  
 В качестве источника данных, список должен реализовывать <xref:System.Collections.IList> интерфейса; один примеров можно привести массив, который является экземпляром класса <xref:System.Array> класса. Дополнительные сведения о массивах см. в разделе [как: создать массив объектов (Visual Basic)](http://msdn.microsoft.com/library/6b64e069-0387-400c-9081-3bdc581020c3).  
  
 В общем случае следует использовать <xref:System.ComponentModel.BindingList%601> при создании списков объектов для привязки данных. <xref:System.ComponentModel.BindingList%601> — универсальная версия <xref:System.ComponentModel.IBindingList> интерфейса. <xref:System.ComponentModel.IBindingList> Расширяет интерфейс <xref:System.Collections.IList> интерфейс, добавляя свойства, методы и события, необходимые для двусторонней привязки данных.  
  
 <xref:System.Collections.IEnumerable>  
 Элементы управления Windows Forms можно привязать к источникам данных, которые поддерживают только <xref:System.Collections.IEnumerable> интерфейс, если они связаны через <xref:System.Windows.Forms.BindingSource> компонента.  
  
 [!INCLUDE[vstecado](../../../includes/vstecado-md.md)] объекты данных  
 [!INCLUDE[vstecado](../../../includes/vstecado-md.md)] предоставляет несколько структур данных, к которым можно выполнить привязку. Каждый зависит от его сложности и сложности.  
  
-   <xref:System.Data.DataColumn>. Объект <xref:System.Data.DataColumn> essential строительный блок <xref:System.Data.DataTable>, в котором несколько столбцов образуют таблицу. Каждый <xref:System.Data.DataColumn> имеет <xref:System.Data.DataColumn.DataType%2A> свойство, которое определяет, какие данные содержит столбец (например, производителей автомобилей в таблице с описанием автомобилей). Можно выполнить простую привязку элемента управления (таких как <xref:System.Windows.Forms.TextBox> элемента управления <xref:System.Windows.Forms.Control.Text%2A> свойство) к столбцу в таблице данных.  
  
-   <xref:System.Data.DataTable>. Объект <xref:System.Data.DataTable> является представлением таблицы, состоящей из строк и столбцов, в [!INCLUDE[vstecado](../../../includes/vstecado-md.md)]. Таблица данных содержит две коллекции: <xref:System.Data.DataColumn>, представляющую столбцы данных в определенной таблице (столбцы однозначно определяют виды данных, которые могут быть введены в этой таблице), и <xref:System.Data.DataRow>, представляющую строки данных в определенной таблице. Вы можете сложную привязку элемента управления к сведениям, содержащимся в таблице данных (например, привязка <xref:System.Windows.Forms.DataGridView> управления к таблице данных). Однако при привязке к <xref:System.Data.DataTable>, фактически выполняется привязка к представлению таблицы по умолчанию.  
  
-   <xref:System.Data.DataView>. Объект <xref:System.Data.DataView> служит для настраиваемого представления одну таблицу данных, можно отфильтровать или упорядочить. Представление данных — «моментальный снимок», используемый элементами управления сложной привязкой данных. Вы можете простую привязку или сложную привязку к данным в представлении данных, но имейте в виду, что привязка осуществляется к «основных изображению» данных, а не к источнику чистой, обновление данных.  
  
-   <xref:System.Data.DataSet>. Объект <xref:System.Data.DataSet> — это коллекция таблиц, связей и ограничений в базе данных. Вы можете простую привязку или сложную привязку к данным в наборе данных, но имейте в виду, что привязка осуществляется по умолчанию <xref:System.Data.DataViewManager> для <xref:System.Data.DataSet> (см. следующий пункт).  
  
-   <xref:System.Data.DataViewManager>. A <xref:System.Data.DataViewManager> служит для настраиваемого представления всей <xref:System.Data.DataSet>, аналогично <xref:System.Data.DataView>, но с отношениями включены. С <xref:System.Data.DataViewManager.DataViewSettings%2A> коллекции, можно задать фильтры по умолчанию и параметры сортировки для любых представлений, <xref:System.Data.DataViewManager> для данной таблицы.  
  
## <a name="see-also"></a>См. также  
 [Уведомления об изменениях в привязке данных Windows Forms](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)  
 [Привязка данных и Windows Forms](../../../docs/framework/winforms/data-binding-and-windows-forms.md)  
 [Привязка данных Windows Forms](../../../docs/framework/winforms/windows-forms-data-binding.md)
