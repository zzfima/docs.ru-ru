---
title: "Практическое руководство. Отображение созданного SQL"
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
ms.assetid: 626492c0-5ee3-4675-88e8-8c40379510b6
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 5c75ac8734a92fc76613643c3831d0b767e92feb
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-display-generated-sql"></a>Практическое руководство. Отображение созданного SQL
Для просмотра кода SQL, созданного для запросов, и изменения обработки используется свойство <xref:System.Data.Linq.DataContext.Log%2A>. Такой подход может оказаться полезным для получения основных сведений о функциях [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] и для отладки конкретных проблем.  
  
## <a name="example"></a>Пример  
 В следующем примере для отображения кода SQL в окне консоли перед его выполнением использовано свойство <xref:System.Data.Linq.DataContext.Log%2A>.  Это свойство можно применять с командами выполнения запросов, вставки, обновления и удаления.  
  
 Строки в окне консоли соответствуют результату выполнения следующего кода на [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] или C#.  
  
```  
SELECT [t0].[CustomerID], [t0].[CompanyName], [t0].[ContactName], [t0].[ContactT  
itle], [t0].[Address], [t0].[City], [t0].[Region], [t0].[PostalCode], [t0].[Coun  
try], [t0].[Phone], [t0].[Fax]  
FROM [dbo].[Customers] AS [t0]  
WHERE [t0].[City] = @p0  
-- @p0: Input String (Size = 6; Prec = 0; Scale = 0) [London]  
-- Context: SqlProvider(Sql2005) Model: AttributedMetaModel Build: 3.5.20810.0  
```  
  
```  
AROUT  
BSBEV  
CONSH  
EASTC  
NORTS  
SEVES  
```  
  
 [!code-csharp[DLinqDebuggingSupport#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqDebuggingSupport/cs/Program.cs#1)]
 [!code-vb[DLinqDebuggingSupport#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqDebuggingSupport/vb/Module1.vb#1)]  
  
## <a name="see-also"></a>См. также  
 [Поддержка отладки](../../../../../../docs/framework/data/adonet/sql/linq/debugging-support.md)
