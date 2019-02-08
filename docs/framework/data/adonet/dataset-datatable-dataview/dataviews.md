---
title: Объекты DataView
ms.date: 03/30/2017
ms.assetid: 0fe5dfa2-c1cd-435f-90b6-b4dd2e3ef34b
ms.openlocfilehash: bcf370e30c50bf5d992279c7abe02bfc6262ea40
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/07/2019
ms.locfileid: "55825879"
---
# <a name="dataviews"></a>Объекты DataView
<xref:System.Data.DataView> позволяет создавать различные представления данных, которые хранятся в <xref:System.Data.DataTable>. Эта возможность часто используется в приложениях связывания данных. С помощью **DataView**, можно представлять данные в таблице с различными порядками сортировки, и можно фильтровать данные по состоянию строки или на основе критерия фильтра.  
  
 Объект **DataView** обеспечивает динамическое представление данных в базовом **DataTable**: содержимое, упорядочение и членство отображают изменения по мере их появления. Это поведение отличается от **выберите** метод **DataTable**, который возвращает <xref:System.Data.DataRow> массива из таблицы на основании определенного фильтра или порядка сортировки: это содержимое отражает изменения базовые таблицы, но при этом членство и упорядочение остаются в статический. Динамические возможности **DataView** идеально подходит для приложений привязки данных.  
  
 Объект **DataView** обеспечивает динамическое представление единого набора данных, как представление базы данных, к которому можно применить различные критерии сортировки и фильтрации. В отличие от представления базы данных, однако **DataView** не может рассматриваться как таблицы и не может обеспечить представление соединяемых таблиц. Кроме того, нельзя исключать столбцы, существующие в исходной таблице, добавлять столбцы (например, вычисляемые), которых нет в исходной таблице.  
  
 Можно использовать <xref:System.Data.DataView.DataViewManager%2A> управлять настройками представления для всех таблиц в **набора данных**. **DataViewManager** предоставляет удобный способ управления настройками представления по умолчанию для каждой таблицы. При привязке элемента управления к более чем одну таблицу **набора данных**привязка **DataViewManager** является идеальным выбором.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Создание DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-a-dataview.md)  
 Описывает создание **DataView** для **DataTable**.  
  
 [Сортировка и фильтрация данных](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md)  
 Описывает настройку свойств **DataView** для возвращения подмножеств строк данных, отвечающих определенным критериям фильтрации, или для возвращения данных в определенном порядке сортировки.  
  
 [Объекты DataRow и DataRowView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datarows-and-datarowviews.md)  
 Описание способов доступа к данными, предоставляемыми **DataView**.  
  
 [Поиск строк](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/finding-rows.md)  
 Описаны способы поиска конкретной строки в **DataView**.  
  
 [ChildView и отношения](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/childviews-and-relations.md)  
 Описывает способ создания представлений данных из отношения родитель потомок с помощью **DataView**.  
  
 [Изменение объектов DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/modifying-dataviews.md)  
 Содержит описание процесса изменения данных в базовом **DataTable** через **DataView**, в том числе включение и отключение обновлений.  
  
 [Обработка событий DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-dataview-events.md)  
 Описывает использование **ListChanged** событие для получения уведомлений при содержимого или порядка **DataView** обновляется.  
  
 [Управление объектами DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/managing-dataviews.md)  
 Описывает использование **DataViewManager** для управления **DataView** параметры для каждой таблицы в **набора данных**.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Веб-приложения ASP.NET](https://docs.microsoft.com/previous-versions/655cec97(v=vs.100))  
 Описывает обзоры и подробные пошаговые инструкции по созданию приложений ASP.NET, Web Forms и веб-служб.  
  
 [Приложения Windows](https://docs.microsoft.com/previous-versions/ms184421(v=vs.100))  
 Содержит подробные сведения о работе с консольными приложениями и Windows Forms.  
  
 [Наборы данных, таблицы данных и объекты DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 Описывает **набора данных** объекта и его использовании для управления данными приложения.  
  
 [DataTables](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 Описывает **DataTable** объекта и его использовании для управления данными приложений самостоятельно или в составе **набора данных**.  
  
 [ADO.NET](../../../../../docs/framework/data/adonet/index.md)  
 Описывает архитектуру и компоненты ADO.NET, а также использование ADO.NET для доступа к существующим источникам данных и управления данными приложений.  
  
## <a name="see-also"></a>См. также
- [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)
