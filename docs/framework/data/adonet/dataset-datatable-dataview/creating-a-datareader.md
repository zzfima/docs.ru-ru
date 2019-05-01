---
title: Создание объекта DataReader
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 49d4422a-7464-4ab8-8ec7-90185fde3ecf
ms.openlocfilehash: 8932f393af58f2014f643c5b6ebd6dc7a127b7eb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62034441"
---
# <a name="creating-a-datareader"></a>Создание объекта DataReader
Классы <xref:System.Data.DataTable> и <xref:System.Data.DataSet> имеют метод <xref:System.Data.DataTable.CreateDataReader%2A>, возвращающий содержимое объекта <xref:System.Data.DataTable> или содержимое объекта <xref:System.Data.DataSet> коллекции <xref:System.Data.DataSet.Tables%2A> в виде одного или нескольких доступных для чтения результирующих наборов с последовательным доступом.  
  
## <a name="example"></a>Пример  
 Следующее приложение командной строки создает экземпляр <xref:System.Data.DataTable>. В примере затем заполненный <xref:System.Data.DataTable> процедура, которая вызывает <xref:System.Data.DataTable.CreateDataReader%2A> метод, который выполняет проход по результатам, содержащимся в <xref:System.Data.DataTableReader>.  
  
 [!code-csharp[DataWorks DataTable.CreateDataReader#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DataTable.CreateDataReader/CS/source.cs#1)]
 [!code-vb[DataWorks DataTable.CreateDataReader#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DataTable.CreateDataReader/VB/source.vb#1)]  
  
 В этом примере в окне консоли отображаются следующие выходные данные:  
  
```  
1 Mary  
2 Andy  
3 Peter  
4 Russ  
```  
  
## <a name="see-also"></a>См. также

- <xref:System.Data.DataTable.CreateDataReader%2A>
- <xref:System.Data.DataSet.CreateDataReader%2A>
- [Объекты DataTableReader](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatablereaders.md)
- [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)
