---
title: Создание объекта DataReader
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 49d4422a-7464-4ab8-8ec7-90185fde3ecf
ms.openlocfilehash: 696eb4dfc334390e1968dd317d441f3c987a1f77
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040113"
---
# <a name="creating-a-datareader"></a>Создание объекта DataReader
Классы <xref:System.Data.DataTable> и <xref:System.Data.DataSet> имеют метод <xref:System.Data.DataTable.CreateDataReader%2A>, возвращающий содержимое объекта <xref:System.Data.DataTable> или содержимое объекта <xref:System.Data.DataSet> коллекции <xref:System.Data.DataSet.Tables%2A> в виде одного или нескольких доступных для чтения результирующих наборов с последовательным доступом.  
  
## <a name="example"></a>Пример  
 Следующее приложение командной строки создает экземпляр <xref:System.Data.DataTable>. Затем в примере закрашенный <xref:System.Data.DataTable> передается в процедуру, которая вызывает метод <xref:System.Data.DataTable.CreateDataReader%2A>, который выполняет итерацию по результатам, содержащимся в <xref:System.Data.DataTableReader>.  
  
 [!code-csharp[DataWorks DataTable.CreateDataReader#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DataTable.CreateDataReader/CS/source.cs#1)]
 [!code-vb[DataWorks DataTable.CreateDataReader#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DataTable.CreateDataReader/VB/source.vb#1)]  
  
 В этом примере в окне консоли отображаются следующие выходные данные:  
  
```output  
1 Mary  
2 Andy  
3 Peter  
4 Russ  
```  
  
## <a name="see-also"></a>См. также

- <xref:System.Data.DataTable.CreateDataReader%2A>
- <xref:System.Data.DataSet.CreateDataReader%2A>
- [Объекты DataTableReader](datatablereaders.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
