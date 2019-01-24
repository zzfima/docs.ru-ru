---
title: Объекты DataTableReader
ms.date: 03/30/2017
ms.assetid: 97546ae2-0e42-4d26-961d-e0b244d81ded
ms.openlocfilehash: 9984dc9c215a34ab35524560e4dcbcd6bd12596d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54602849"
---
# <a name="datatablereaders"></a>Объекты DataTableReader
<xref:System.Data.DataTableReader> представляет содержимое объекта <xref:System.Data.DataTable> или <xref:System.Data.DataSet> в виде одного или нескольких результирующих наборов, предназначенных только для чтения и только для перенаправления.  
  
 При создании **DataTableReader** из **DataTable**, полученный в результате **DataTableReader** объект содержит один результирующий набор с теми же данными, как  **DataTable** из которого он был создан, за исключением любых строк, которые были помечены как удаленные. Столбцы отображаются в том же порядке, как и в исходном **DataTable**.  
  
 Объект **DataTableReader** может содержать несколько результирующих наборов, если он был создан путем вызова <xref:System.Data.DataSet.CreateDataReader%2A>. Результаты отображаются в том же порядке **DataTables** в **набора данных** объекта <xref:System.Data.DataSet.Tables%2A> коллекции.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Создание объекта DataReader](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-a-datareader.md)  
 Рассматривается процесс создания **DataTableReader** объекта.  
  
 [Навигация в объектах DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/navigating-datatables.md)  
 Описание использования **чтения** метод для перехода по содержимому объекта **DataTableReader**.  
  
## <a name="see-also"></a>См. также
- [Извлечение и изменение данных в ADO.NET](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)
