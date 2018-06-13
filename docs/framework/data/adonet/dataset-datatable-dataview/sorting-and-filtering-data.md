---
title: Сортировка и фильтрация данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fdd9c753-39df-48cd-9822-2781afe76200
ms.openlocfilehash: 02a67a490eb8339663aac08c97c665ffee09f0df
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32760613"
---
# <a name="sorting-and-filtering-data"></a>Сортировка и фильтрация данных
<xref:System.Data.DataView> предоставляет несколько способов сортировки и фильтрации данных в <xref:System.Data.DataTable>.  
  
-   Можно использовать свойство <xref:System.Data.DataView.Sort%2A> для задания одного или нескольких порядков сортировки столбцов и включить параметры ASC (по возрастанию) и DESC (по убыванию).  
  
-   Свойство <xref:System.Data.DataView.ApplyDefaultSort%2A> служит для автоматического создания порядка сортировки по возрастанию на основании столбца или столбцов первичного ключа таблицы. <xref:System.Data.DataView.ApplyDefaultSort%2A> применяется, только если **сортировки** свойство является пустой ссылкой или пустой строкой, и если таблица имеет первичный ключ.  
  
-   Свойство <xref:System.Data.DataView.RowFilter%2A> можно использовать для задания подмножеств строк на основании значений их столбцов. Дополнительные сведения о допустимых выражениях для **RowFilter** свойства, см. Справочные сведения по <xref:System.Data.DataColumn.Expression%2A> свойство <xref:System.Data.DataColumn> класса.  
  
     Если вы хотите вернуть результаты определенного запроса данных, а не динамическое представление подмножества данных, используйте <xref:System.Data.DataView.Find%2A> или <xref:System.Data.DataView.FindRows%2A> методы **DataView** для достижения наилучшей производительности вместо Установка **RowFilter** свойство. Установка **RowFilter** перестраивается индекс данных, что добавляет нагрузку на приложение и снижает производительность. **RowFilter** свойство лучше всего использовать в приложении с привязкой к данным где элемент связывания отображает отфильтрованные результаты. **Найти** и **FindRows** методы используют текущий индекс, не требуя его перестроения. Дополнительные сведения о **найти** и **FindRows** методов, см. [поиск строки](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/finding-rows.md).  
  
-   Свойство <xref:System.Data.DataView.RowStateFilter%2A> можно использовать для определения, какие версии строк следует просматривать. **DataView** неявно регулирует Выбор версии строк для предоставления зависимости **RowState** базовой строки. Например если **RowStateFilter** равно **DataViewRowState.Deleted**, **DataView** предоставляет **исходного** версии строк все **Deleted** строк, так как отсутствует не **текущей** версию строки. Можно определить, какие версии строки предоставляется с использованием **RowVersion** свойство **DataRowView**.  
  
     В следующей таблице показаны параметры для **DataViewRowState**.  
  
    |Параметры DataViewRowState|Описание|  
    |------------------------------|-----------------|  
    |**CurrentRows**|**Текущей** из всех **Unchanged**, **Added**, и **Modified** строк. Это значение по умолчанию.|  
    |**Добавить**|**Текущей** из всех **Added** строк.|  
    |**удален**|**Исходного** из всех **Deleted** строк.|  
    |**ModifiedCurrent**|**Текущей** из всех **Modified** строк.|  
    |**ModifiedOriginal**|**Исходного** из всех **Modified** строк.|  
    |**None**|Нет строк.|  
    |**OriginalRows**|**Исходного** из всех **Unchanged**, **Modified**, и **Deleted** строк.|  
    |**Без изменений**|**Текущей** из всех **Unchanged** строк.|  
  
 Дополнительные сведения о состояниях и версиях строк см. в разделе [состояния строк и версии строк](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).  
  
 В следующем примере кода создается представление, которое показывает все продукты, где число элементов на складе меньше или равно уровню переупорядочения, отсортированного вначале по идентификаторам поставщиков, а затем по названиям продуктов.  
  
```vb  
Dim prodView As DataView = New DataView(prodDS.Tables("Products"), _  
   "UnitsInStock <= ReorderLevel", _  
   "SupplierID, ProductName", _  
   DataViewRowState.CurrentRows)  
```  
  
```csharp  
DataView prodView = new DataView(prodDS.Tables["Products"],  
   "UnitsInStock <= ReorderLevel",  
   "SupplierID, ProductName",  
   DataViewRowState.CurrentRows);  
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.Data.DataViewRowState>  
 <xref:System.Data.DataColumn.Expression%2A?displayProperty=nameWithType>  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataView>  
 [Объекты DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](http://go.microsoft.com/fwlink/?LinkId=217917)
