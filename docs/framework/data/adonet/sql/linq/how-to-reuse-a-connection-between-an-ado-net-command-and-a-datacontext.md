---
title: "Практическое руководство. Повторное использование соединения между командой ADO.NET и контекстом DataContext"
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
ms.assetid: 7e26c7eb-c18a-43b5-a8f0-28fd8b04b0f0
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 196b3c8735168ea935aa1a0d3917dd34b2aa390f
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-reuse-a-connection-between-an-adonet-command-and-a-datacontext"></a>Практическое руководство. Повторное использование соединения между командой ADO.NET и контекстом DataContext
Поскольку [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] является частью [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] семейства технологий и основан на службах, предоставленных [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)], вы можете повторно использовать соединение между [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] команды и <xref:System.Data.Linq.DataContext>.  
  
## <a name="example"></a>Пример  
 В следующем примере показано повторное использование подключения между командой [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] и <xref:System.Data.Linq.DataContext>.  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#4)]
 [!code-vb[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#4)]  
  
## <a name="see-also"></a>См. также  
 [Основные сведения](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)  
 [ADO.NET и LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/ado-net-and-linq-to-sql.md)  
 [Установка связи с базой данных](../../../../../../docs/framework/data/adonet/sql/linq/communicating-with-the-database.md)
