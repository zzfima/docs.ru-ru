---
title: Практическое руководство. Как прямо выполнять команды SQL
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 04671bb0-40c0-4465-86e5-77986f454661
ms.openlocfilehash: eeac6272f176ac8e780b72b0076d032ad9e8f108
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59078906"
---
# <a name="how-to-directly-execute-sql-commands"></a>Практическое руководство. Как прямо выполнять команды SQL
Если предположить наличие подключения <xref:System.Data.Linq.DataContext>, для выполнения команд, которые не возвращают объекты, можно воспользоваться методом <xref:System.Data.Linq.DataContext.ExecuteCommand%2A>.  
  
## <a name="example"></a>Пример  
 В следующем примере SQL Server увеличивает цену за единицу на 1.  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#3)]
 [!code-vb[DLinqCommunicatingWithDatabase#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#3)]  
  
## <a name="see-also"></a>См. также

- [Практическое руководство. Как прямо выполнять запросы SQL](../../../../../../docs/framework/data/adonet/sql/linq/how-to-directly-execute-sql-queries.md)
- [Установка связи с базой данных](../../../../../../docs/framework/data/adonet/sql/linq/communicating-with-the-database.md)
