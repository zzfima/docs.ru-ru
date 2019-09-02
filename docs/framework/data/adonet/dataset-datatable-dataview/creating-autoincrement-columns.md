---
title: Создание столбцов AutoIncrement
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cf09732a-ab54-4d98-89e2-4d0a1f28fbce
ms.openlocfilehash: 2548ad9382b406978dac0a3d366207626278f501
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/31/2019
ms.locfileid: "70205130"
---
# <a name="creating-autoincrement-columns"></a>Создание столбцов AutoIncrement
Чтобы обеспечить наличие в столбце уникальных значений, можно указать, что значения в столбце должны увеличиваться автоматически при добавлении новых строк к таблице. Чтобы создать автоматическое приращение <xref:System.Data.DataColumn>, <xref:System.Data.DataColumn.AutoIncrement%2A> присвойте свойству столбца значение **true**. Затем начинается со значения, определенного <xref:System.Data.DataColumn.AutoIncrementSeed%2A> в свойстве, и при добавлении каждой строки значение столбца **AutoIncrement** <xref:System.Data.DataColumn.AutoIncrementStep%2A> увеличивается на значение, определенное в свойстве столбца. <xref:System.Data.DataColumn>  
  
 Для столбцов с автоувеличением рекомендуется, <xref:System.Data.DataColumn.ReadOnly%2A> чтобы свойство **DataColumn** было установлено в **значение true**.  
  
 В следующем примере показано, как создать столбец, значения в котором начинаются с 200 и каждый раз увеличиваются с шагом 3.  
  
```vb  
Dim workColumn As DataColumn = workTable.Columns.Add( _  
    "CustomerID", typeof(Int32))  
workColumn.AutoIncrement = true  
workColumn.AutoIncrementSeed = 200  
workColumn.AutoIncrementStep = 3  
```  
  
```csharp  
DataColumn workColumn = workTable.Columns.Add(  
    "CustomerID", typeof(Int32));  
workColumn.AutoIncrement = true;  
workColumn.AutoIncrementSeed = 200;  
workColumn.AutoIncrementStep = 3;  
```  
  
## <a name="see-also"></a>См. также

- <xref:System.Data.DataColumn>
- [Определение схемы DataTable](datatable-schema-definition.md)
- [DataTables](datatables.md)
- [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)
