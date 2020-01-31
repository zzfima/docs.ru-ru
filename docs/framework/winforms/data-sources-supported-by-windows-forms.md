---
title: Поддерживаемые источники данных
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
ms.openlocfilehash: 83ce4bb0d6f0bf81bcad4e38af212dccc3483ca5
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742308"
---
# <a name="data-sources-supported-by-windows-forms"></a>Источники данных, поддерживаемые Windows Forms
Традиционно привязка данных использовалась в приложениях для использования данных, хранящихся в базах данных. С помощью Windows Forms привязки данных можно получить доступ к данным из баз данных, а также к данным в других структурах, таких как массивы и коллекции, при условии соблюдения определенных минимальных требований.  
  
## <a name="structures-to-bind-to"></a>Структуры для привязки  
 В Windows Forms можно выполнить привязку к широкому спектру структур, от простых объектов (простая привязка) до сложных списков, таких как таблицы данных ADO.NET (сложная привязка). Для простой привязки Windows Forms поддерживает привязку к открытым свойствам простого объекта. Привязка на основе списка Windows Forms обычно требует, чтобы объект поддерживал интерфейс <xref:System.Collections.IList> или интерфейс <xref:System.ComponentModel.IListSource>. Кроме того, при привязке с помощью компонента <xref:System.Windows.Forms.BindingSource> можно выполнить привязку к объекту, который поддерживает интерфейс <xref:System.Collections.IEnumerable>. Дополнительные сведения о интерфейсах, связанных с привязкой данных, см. [в разделе интерфейсы, связанные с привязкой данных](interfaces-related-to-data-binding.md).  
  
 В следующем списке показаны структуры, к которым можно выполнить привязку в Windows Forms.  
  
 <xref:System.Windows.Forms.BindingSource>  
 <xref:System.Windows.Forms.BindingSource> является наиболее распространенным Windows Formsным источником данных и выполняет прокси-сервер между источником данных и элементами управления Windows Forms. Шаблон общего использования <xref:System.Windows.Forms.BindingSource> заключается в том, чтобы привязать элементы управления к <xref:System.Windows.Forms.BindingSource> и привязать <xref:System.Windows.Forms.BindingSource> к источнику данных (например, к таблице данных ADO.NET или бизнес-объекту). <xref:System.Windows.Forms.BindingSource> предоставляет службы, обеспечивающие и улучшающие уровень поддержки привязки данных. Например, Windows Forms элементы управления на основе списка, такие как <xref:System.Windows.Forms.DataGridView> и <xref:System.Windows.Forms.ComboBox>, не поддерживают прямую привязку к <xref:System.Collections.IEnumerable>ным источникам данных, однако этот сценарий можно включить путем привязки через <xref:System.Windows.Forms.BindingSource>. В этом случае <xref:System.Windows.Forms.BindingSource> преобразует источник данных в <xref:System.Collections.IList>.  
  
 Простые объекты  
 Windows Forms поддерживает свойства элементов управления привязки данных к общим свойствам экземпляра объекта, используя тип <xref:System.Windows.Forms.Binding>. Windows Forms также поддерживает элементы управления на основе списка привязок, например <xref:System.Windows.Forms.ListControl> к экземпляру объекта при использовании <xref:System.Windows.Forms.BindingSource>.  
  
 массив или коллекция  
 Чтобы использовать в качестве источника данных, список должен реализовывать интерфейс <xref:System.Collections.IList>. одним из примеров может быть массив, который является экземпляром класса <xref:System.Array>. Дополнительные сведения о массивах см. [в разделе инструкции. Создание массива объектов (Visual Basic)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/487y7874(v=vs.100)).  
  
 Как правило, при создании списков объектов для привязки данных следует использовать <xref:System.ComponentModel.BindingList%601>. <xref:System.ComponentModel.BindingList%601> — это универсальная версия интерфейса <xref:System.ComponentModel.IBindingList>. Интерфейс <xref:System.ComponentModel.IBindingList> расширяет интерфейс <xref:System.Collections.IList>, добавляя свойства, методы и события, необходимые для двусторонней привязки данных.  
  
 <xref:System.Collections.IEnumerable>  
 Windows Forms элементы управления могут быть привязаны к источникам данных, которые поддерживают только интерфейс <xref:System.Collections.IEnumerable>, только если они привязаны через компонент <xref:System.Windows.Forms.BindingSource>.  
  
 Объекты данных ADO.NET  
 ADO.NET предоставляет ряд структур данных, подходящих для привязки. Каждый из них может быть различным и сложным.  
  
- <xref:System.Data.DataColumn>. <xref:System.Data.DataColumn> — это важный Стандартный блок <xref:System.Data.DataTable>, в котором ряд столбцов состоит из таблицы. Каждый <xref:System.Data.DataColumn> имеет свойство <xref:System.Data.DataColumn.DataType%2A>, определяющее тип данных, которые содержит столбец (например, создание автомобиля в таблице, описывающей автомобили). Можно выполнить простую привязку элемента управления (например, <xref:System.Windows.Forms.Control.Text%2A> свойства <xref:System.Windows.Forms.TextBox> элемента управления) к столбцу в таблице данных.  
  
- <xref:System.Data.DataTable>. <xref:System.Data.DataTable> — это представление таблицы со строками и столбцами в ADO.NET. Таблица данных содержит две коллекции: <xref:System.Data.DataColumn>, представляющие столбцы данных в определенной таблице (которые в конечном итоге определяют типы данных, которые можно указать в этой таблице) и <xref:System.Data.DataRow>, представляющие строки данных в данной таблице. Можно выполнить сложную привязку элемента управления к информации, содержащейся в таблице данных (например, привязке <xref:System.Windows.Forms.DataGridView> элемента управления к таблице данных). Однако при привязке к <xref:System.Data.DataTable>вы действительно привязываетесь к представлению таблицы по умолчанию.  
  
- <xref:System.Data.DataView>. <xref:System.Data.DataView> — это настраиваемое представление одной таблицы данных, которая может быть отфильтрована или отсортирована. Представление данных — это «моментальный снимок» данных, используемый элементами управления со сложной привязкой. Можно выполнить простую или сложную привязку к данным в представлении данных, но имейте в виду, что привязка выполняется к фиксированному изображению данных, а не к простому обновлению источника данных.  
  
- <xref:System.Data.DataSet>. <xref:System.Data.DataSet> — это коллекция таблиц, связей и ограничений данных в базе данных. Можно выполнить простую или сложную привязку к данным в наборе данных, но имейте в виду, что привязка выполняется к <xref:System.Data.DataViewManager> по умолчанию для <xref:System.Data.DataSet> (см. следующий пункт маркированного списка).  
  
- <xref:System.Data.DataViewManager>. <xref:System.Data.DataViewManager> — это настраиваемое представление всей <xref:System.Data.DataSet>, аналогичное <xref:System.Data.DataView>, но с включенными связями. С помощью коллекции <xref:System.Data.DataViewManager.DataViewSettings%2A> можно задать фильтры по умолчанию и параметры сортировки для всех представлений, которые <xref:System.Data.DataViewManager> в данной таблице.  
  
## <a name="see-also"></a>См. также:

- [Уведомления об изменениях в привязке данных Windows Forms](change-notification-in-windows-forms-data-binding.md)
- [Привязка данных и Windows Forms](data-binding-and-windows-forms.md)
- [Привязка данных Windows Forms](windows-forms-data-binding.md)
