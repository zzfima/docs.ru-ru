---
title: Объекты DataTableReader
ms.date: 03/30/2017
ms.assetid: 97546ae2-0e42-4d26-961d-e0b244d81ded
ms.openlocfilehash: 1559cde9cb786ccb2baf920347064b8b28d472c3
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70785342"
---
# <a name="datatablereaders"></a>Объекты DataTableReader
<xref:System.Data.DataTableReader> представляет содержимое объекта <xref:System.Data.DataTable> или <xref:System.Data.DataSet> в виде одного или нескольких результирующих наборов, предназначенных только для чтения и только для перенаправления.  
  
 При создании объекта **DataTableReader** из **таблицы**данных результирующий объект **DataTableReader** содержит один результирующий набор с теми же данными, что и у **таблицы DataTable** , из которой он был создан, за исключением строк, помеченных как удаленной. Столбцы отображаются в том же порядке, что и в исходной **таблице**данных.  
  
 Объект **DataTableReader** может содержать несколько результирующих наборов, если он был создан <xref:System.Data.DataSet.CreateDataReader%2A>путем вызова метода. Результаты находятся в том же порядке, что и **DataTables** в <xref:System.Data.DataSet.Tables%2A> коллекции объекта **DataSet** .  
  
## <a name="in-this-section"></a>В этом разделе  
 [Создание объекта DataReader](creating-a-datareader.md)  
 Описывает, как создать объект **DataTableReader** .  
  
 [Навигация в объектах DataTable](navigating-datatables.md)  
 Описывает использование метода **Read** для перемещения по содержимому объекта **DataTableReader**.  
  
## <a name="see-also"></a>См. также

- [Извлечение и изменение данных в ADO.NET](../retrieving-and-modifying-data.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
