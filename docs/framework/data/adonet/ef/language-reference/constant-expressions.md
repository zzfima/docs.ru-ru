---
title: "Постоянные выражения"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 9d98a7be-b110-4edb-8eba-bed10f250b6d
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 328284ce07a0361dbfd25b0d765000b497156ff7
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="constant-expressions"></a>Постоянные выражения
Константное выражение состоит из постоянного значения. Постоянные значения непосредственно преобразуются в константные выражения дерева команд и не преобразуются на клиенте. К ним относятся выражения, результатом которых является постоянное значение. Поэтому для всех выражений с константами следует ожидать поведения источника данных. Это поведение может отличаться от поведения среды CLR.  
  
 В следующем примере показано константное выражение, вычисляемое на сервере.  
  
 [!code-csharp[DP L2E Conceptual Examples#ConstantExpression](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#constantexpression)]
 [!code-vb[DP L2E Conceptual Examples#ConstantExpression](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#constantexpression)]  
  
 Технология [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] не поддерживает использование пользовательского класса в качестве константы. Однако ссылка на свойство пользовательского класса считается константой; она будет преобразована в константное выражение дерева команд и выполнена в источнике данных.  
  
## <a name="see-also"></a>См. также  
 [Выражения в запросах LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/expressions-in-linq-to-entities-queries.md)
