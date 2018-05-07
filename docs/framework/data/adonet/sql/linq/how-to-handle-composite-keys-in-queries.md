---
title: Практическое руководство. Обработка составных ключей в запросах
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ce2f14fd-1038-458a-91e3-a078c61f0d10
ms.openlocfilehash: 26c281445b84d3b3f85980de6ae4076411bb4fba
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-handle-composite-keys-in-queries"></a>Практическое руководство. Обработка составных ключей в запросах
Некоторые операторы могут принимать только один аргумент. Если аргумент должен содержать несколько столбцов базы данных, необходимо создать анонимный тип для представления комбинации столбцов.  
  
## <a name="example"></a>Пример  
 В следующем примере показан запрос, который вызывает оператор `GroupBy`, принимающий только один аргумент `key`.  
  
 [!code-csharp[DLinqCompositeKeys#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCompositeKeys/cs/Program.cs#1)]
 [!code-vb[DLinqCompositeKeys#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCompositeKeys/vb/Module1.vb#1)]  
  
## <a name="example"></a>Пример  
 Та же ситуация возникает в случае соединений, как показано в следующем примере.  
  
 [!code-csharp[DLinqCompositeKeys#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCompositeKeys/cs/Program.cs#2)]
 [!code-vb[DLinqCompositeKeys#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCompositeKeys/vb/Module1.vb#2)]  
  
## <a name="see-also"></a>См. также  
 [Основные принципы запросов](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
