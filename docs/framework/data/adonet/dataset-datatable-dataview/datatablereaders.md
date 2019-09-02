---
title: Объекты DataTableReader
ms.date: 03/30/2017
ms.assetid: 97546ae2-0e42-4d26-961d-e0b244d81ded
ms.openlocfilehash: 1ff7868b59c6fdc4e6c443be1b831accc84f36a6
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203817"
---
# <a name="datatablereaders"></a>Объекты DataTableReader
<xref:System.Data.DataTableReader> представляет содержимое объекта <xref:System.Data.DataTable> или <xref:System.Data.DataSet> в виде одного или нескольких результирующих наборов, предназначенных только для чтения и только для перенаправления.  
  
 При создании объекта **DataTableReader** из **таблицы**данных результирующий объект **DataTableReader** содержит один результирующий набор с теми же данными, что и у **таблицы DataTable** , из которой он был создан, за исключением строк, помеченных как удаленной. Столбцы отображаются в том же порядке, что и в исходной **таблице**данных.  
  
 Объект **DataTableReader** может содержать несколько результирующих наборов, если он был создан <xref:System.Data.DataSet.CreateDataReader%2A>путем вызова метода. Результаты находятся в том же порядке, что <xref:System.Data.DataSet.Tables%2A> и **DataTables** в коллекции объекта **DataSet** .  
  
## <a name="in-this-section"></a>В этом разделе  
 [Создание объекта DataReader](creating-a-datareader.md)  
 Описывает, как создать объект **DataTableReader** .  
  
 [Навигация в объектах DataTable](navigating-datatables.md)  
 Описывает использование метода **Read** для перемещения по содержимому объекта **DataTableReader**.  
  
## <a name="see-also"></a>См. также

- [Извлечение и изменение данных в ADO.NET](../retrieving-and-modifying-data.md)
- [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)
