---
title: Практическое руководство. Отображение созданного SQL
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 626492c0-5ee3-4675-88e8-8c40379510b6
ms.openlocfilehash: edc0f8fea2768391a47e12940cbe083e41852f1f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33361712"
---
# <a name="how-to-display-generated-sql"></a><span data-ttu-id="80c07-102">Практическое руководство. Отображение созданного SQL</span><span class="sxs-lookup"><span data-stu-id="80c07-102">How to: Display Generated SQL</span></span>
<span data-ttu-id="80c07-103">Для просмотра кода SQL, созданного для запросов, и изменения обработки используется свойство <xref:System.Data.Linq.DataContext.Log%2A>.</span><span class="sxs-lookup"><span data-stu-id="80c07-103">You can view the SQL code generated for queries and change processing by using the <xref:System.Data.Linq.DataContext.Log%2A> property.</span></span> <span data-ttu-id="80c07-104">Такой подход может оказаться полезным для получения основных сведений о функциях [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] и для отладки конкретных проблем.</span><span class="sxs-lookup"><span data-stu-id="80c07-104">This approach can be useful for understanding [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] functionality and for debugging specific problems.</span></span>  
  
## <a name="example"></a><span data-ttu-id="80c07-105">Пример</span><span class="sxs-lookup"><span data-stu-id="80c07-105">Example</span></span>  
 <span data-ttu-id="80c07-106">В следующем примере для отображения кода SQL в окне консоли перед его выполнением использовано свойство <xref:System.Data.Linq.DataContext.Log%2A>.</span><span class="sxs-lookup"><span data-stu-id="80c07-106">The following example uses the <xref:System.Data.Linq.DataContext.Log%2A> property to display SQL code in the console window before the code is executed.</span></span>  <span data-ttu-id="80c07-107">Это свойство можно применять с командами выполнения запросов, вставки, обновления и удаления.</span><span class="sxs-lookup"><span data-stu-id="80c07-107">You can use this property with query, insert, update, and delete commands.</span></span>  
  
 <span data-ttu-id="80c07-108">Строки в окне консоли соответствуют результату при выполнении, следующий код Visual Basic или C#.</span><span class="sxs-lookup"><span data-stu-id="80c07-108">The lines from the console window are what you see when you execute the Visual Basic or C# code that follows.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="80c07-109">См. также</span><span class="sxs-lookup"><span data-stu-id="80c07-109">See Also</span></span>  
 [<span data-ttu-id="80c07-110">Поддержка отладки</span><span class="sxs-lookup"><span data-stu-id="80c07-110">Debugging Support</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/debugging-support.md)
