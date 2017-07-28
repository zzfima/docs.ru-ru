---
title: "Источники данных, поддерживаемые Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "массивы [Windows Forms]"
  - "коллекции [Windows Forms], привязка к"
  - "данные [Windows Forms], поставщики данных"
  - "поставщики данных [Windows Forms]"
  - "источники данных [Windows Forms]"
  - "DataColumn - класс"
  - "DataSet - класс, связывание данных и Windows Forms"
  - "DataTable - класс, связывание данных и Windows Forms"
  - "DataView- класс, связывание данных и Windows Forms"
  - "DataViewManager- класс, связывание данных и Windows Forms"
  - "поставщики OLE DB, Windows Forms"
  - "Windows Forms, привязка данных"
  - "Windows Forms, исходные данные"
ms.assetid: 3d2c43f6-462b-4d35-9c86-13e9afe012e1
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Источники данных, поддерживаемые Windows Forms
Традиционно привязка данных используется в приложениях для получения преимуществ данных, хранящихся в базах данных.  Благодаря привязке данных в Windows Forms можно осуществлять доступ к данным, находящимся в базах данных, а также в других структурах, например в массивах или в коллекциях, при выполнении определенных минимальных требований.  
  
## Структуры для привязки  
 В Windows Forms можно выполнить привязку к самым разнообразными структурам — от простых объектов \(простая привязка\) до сложных списков, таких как таблицы данных ADO.NET \(сложная привязка\).  В случае простой привязки Windows Forms поддерживает привязку к общедоступным свойствам простого объекта.  При привязке Windows Forms на основе списков обычно требуется, чтобы объект поддерживал интерфейс <xref:System.Collections.IList> или <xref:System.ComponentModel.IListSource>.  Кроме того, если при привязке используется компонент <xref:System.Windows.Forms.BindingSource>, можно выполнить привязку к объекту, поддерживающему интерфейс <xref:System.Collections.IEnumerable>.  Дополнительные сведения об интерфейсах, связанных с привязкой данных, см. в разделе [Интерфейсы, относящиеся к связыванию данных](../../../docs/framework/winforms/interfaces-related-to-data-binding.md).  
  
 В представленном ниже списке перечислены структуры, к которым можно выполнить привязку в Windows Forms.  
  
 <xref:System.Windows.Forms.BindingSource>  
 Компонент <xref:System.Windows.Forms.BindingSource> является наиболее распространенным источником данных Windows Forms. Он выполняет функцию прокси между источником данных и элементами управления Windows Forms.  Основной подход при использовании компонента <xref:System.Windows.Forms.BindingSource> заключается в том, чтобы привязать элементы управления к компоненту <xref:System.Windows.Forms.BindingSource>, а затем привязать компонент <xref:System.Windows.Forms.BindingSource> к источнику данных \(например, таблице данных ADO.NET или бизнес\-объекту\).  Компонент <xref:System.Windows.Forms.BindingSource> обеспечивает поддержку привязки данных и позволяет повысить уровень этой поддержки.  К примеру, такие элементы управления Windows Forms на основе списков, как <xref:System.Windows.Forms.DataGridView> и <xref:System.Windows.Forms.ComboBox>, не поддерживают привязку непосредственно к источникам данных <xref:System.Collections.IEnumerable>, однако такую привязку можно осуществить посредством компонента <xref:System.Windows.Forms.BindingSource>.  В этом случае компонент <xref:System.Windows.Forms.BindingSource> преобразует источник данных в интерфейс <xref:System.Collections.IList>.  
  
 Простые объекты  
 Windows Forms поддерживает привязку свойств элементов управления к общедоступным свойствам экземпляра объекта с помощью типа <xref:System.Windows.Forms.Binding>.  Если используется компонент <xref:System.Windows.Forms.BindingSource>, Windows Forms также поддерживает привязку элементов управления на основе списка, таких как <xref:System.Windows.Forms.ListControl> к экземпляру объекта.  
  
 Массив или коллекция  
 Для использования в качестве источника данных список должен реализовывать интерфейс <xref:System.Collections.IList>; в качестве одного из примеров можно привести массив, который является экземпляром класса <xref:System.Array>.  Дополнительные сведения о массивах см. в разделе [How to: Create an Array of Objects \(Visual Basic\)](http://msdn.microsoft.com/ru-ru/6b64e069-0387-400c-9081-3bdc581020c3).  
  
 Как правило, при создании списков объектов для привязки данных необходимо использовать <xref:System.ComponentModel.BindingList%601>.  Класс <xref:System.ComponentModel.BindingList%601> представляет собой универсальную версию интерфейса <xref:System.ComponentModel.IBindingList>.  Интерфейс <xref:System.ComponentModel.IBindingList> является расширением интерфейса <xref:System.Collections.IList>, добавляя свойства, методы и события, необходимые для двусторонней привязки данных.  
  
 <xref:System.Collections.IEnumerable>  
 При использовании компонента <xref:System.Windows.Forms.BindingSource> элементы управления Windows Forms можно привязать к источникам данных, которые поддерживают только интерфейс <xref:System.Collections.IEnumerable>.  
  
 [!INCLUDE[vstecado](../../../includes/vstecado-md.md)] Объекты данных  
 [!INCLUDE[vstecado](../../../includes/vstecado-md.md)] предлагает несколько структур данных, к которым можно выполнить привязку.  Каждая структура отличается своими возможностями и сложностью.  
  
-   <xref:System.Data.DataColumn>.  Объект <xref:System.Data.DataColumn> является основным стандартным блоком для создания объекта <xref:System.Data.DataTable>, в котором несколько столбцов образуют таблицу.  Каждый объект <xref:System.Data.DataColumn> имеет свойство <xref:System.Data.DataColumn.DataType%2A>, которое определяет вид данных, содержащихся в столбце \(например, производителей автомобилей в таблице с описанием автомобилей\).  К столбцу в таблице можно осуществить простую привязку элемента управления \(например, свойства <xref:System.Windows.Forms.Control.Text%2A> элемента управления <xref:System.Windows.Forms.TextBox>\).  
  
-   <xref:System.Data.DataTable>.  Объект <xref:System.Data.DataTable> является представлением таблицы, содержащей строки и столбцы, в [!INCLUDE[vstecado](../../../includes/vstecado-md.md)].  Таблица данных содержит две коллекции: <xref:System.Data.DataColumn>, представляющую столбцы данных в определенной таблице \(столбцы однозначно определяют виды данных, которые можно ввести в таблицу\), и <xref:System.Data.DataRow>, представляющую строки данных в определенной таблице.  К сведениям, содержащимся в таблице данных, можно осуществить сложную привязку \(например, привязку элемента управления <xref:System.Windows.Forms.DataGridView> к таблице данных\).  Однако при привязке к объекту <xref:System.Data.DataTable> фактически выполняется привязка к представлению таблицы по умолчанию.  
  
-   <xref:System.Data.DataView>.  Объект <xref:System.Data.DataView> служит для настраиваемого представления единственной таблицы данных, которую можно отфильтровать или упорядочить.  Представление данных — это "моментальный снимок" данных, используемый элементами управления при сложной привязке.  К данным в представлении данных можно выполнить простую или сложную привязку, однако следует принять во внимание, что привязка осуществляется к "замороженному изображению" данных, а не к достоверному, обновляемому источнику данных.  
  
-   <xref:System.Data.DataSet>.  Объект <xref:System.Data.DataSet> представляет собой коллекцию таблиц, отношений и ограничений данных в базе данных.  К данным в наборе данных можно выполнить простую или сложную привязку, однако следует принять во внимание, что привязка осуществляется к выбранному по умолчанию объекту <xref:System.Data.DataViewManager> объекта <xref:System.Data.DataSet> \(см. следующий пункт\).  
  
-   <xref:System.Data.DataViewManager>.  Объект <xref:System.Data.DataViewManager> представляет собой настраиваемое представление всего объекта <xref:System.Data.DataSet>. Он аналогичен объекту <xref:System.Data.DataView>, но включает в себя отношения.  Коллекция <xref:System.Data.DataViewManager.DataViewSettings%2A> позволяет задавать фильтры по умолчанию и параметры сортировки для любых представлений, которые существуют в объекте <xref:System.Data.DataViewManager> для данной таблицы.  
  
## См. также  
 [Получение уведомления об изменении данных, связанных с элементом управления, в Windows Forms](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)   
 [Связывание данных и Windows Forms](../../../docs/framework/winforms/data-binding-and-windows-forms.md)   
 [Связывание элементов управления Windows Forms с данными](../../../docs/framework/winforms/windows-forms-data-binding.md)