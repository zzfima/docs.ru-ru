---
title: Навигация по таблицам данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 202026a1-ec79-435e-b507-12a77f5011b2
ms.openlocfilehash: b5837d647b72f8dd17c4a6d3664faf8976243d36
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/31/2019
ms.locfileid: "70204558"
---
# <a name="navigating-datatables"></a>Навигация по таблицам данных
Объект <xref:System.Data.DataTableReader> получает содержимое одного или нескольких объектов <xref:System.Data.DataTable> в виде одного или нескольких однопроходных результирующих наборов, доступных только для чтения.  
  
 Объект <xref:System.Data.DataTableReader> может содержать несколько результирующих наборов, если он создан методом <xref:System.Data.DataSet.CreateDataReader%2A>. Если имеется несколько результирующих наборов, метод <xref:System.Data.DataTableReader.NextResult%2A> продвигает курсор к следующему результирующему набору. Это однопроходной процесс. Вернуться к предыдущему результирующему набору невозможно.  
  
## <a name="example"></a>Пример  
 В следующем примере `TestConstructor` метод создает два <xref:System.Data.DataTable> экземпляра. Чтобы продемонстрировать этот конструктор для <xref:System.Data.DataTableReader> класса, в примере создается новый объект **DataTableReader** на основе массива, содержащего два **объекта DataTable**, и выполняется простая операция печати содержимого из первых столбцы в окно консоли.  
  
 [!code-csharp[DataWorks DataTableReader.NextResult#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DataTableReader.NextResult/CS/source.cs#1)]
 [!code-vb[DataWorks DataTableReader.NextResult#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DataTableReader.NextResult/VB/source.vb#1)]  
  
## <a name="see-also"></a>См. также

- [Объекты DataTableReader](datatablereaders.md)
- [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)
