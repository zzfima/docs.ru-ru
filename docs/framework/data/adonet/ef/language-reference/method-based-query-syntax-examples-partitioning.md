---
title: "Примеры синтаксиса запросов на основе методов. Секционирование"
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
ms.assetid: b7b64874-c3c8-4bdb-862c-89a168d07827
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: f4db203ece2431bd19cc05879dc7d3db88159dec
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="method-based-query-syntax-examples-partitioning"></a><span data-ttu-id="264fb-102">Примеры синтаксиса запросов на основе методов. Секционирование</span><span class="sxs-lookup"><span data-stu-id="264fb-102">Method-Based Query Syntax Examples: Partitioning</span></span>
<span data-ttu-id="264fb-103">Примеры в этом разделе демонстрируют, как использовать <xref:System.Linq.Enumerable.Skip%2A>, и <xref:System.Linq.Enumerable.Take%2A> методы запроса [модели AdventureWorks Sales](http://msdn.microsoft.com/en-us/f16cd988-673f-4376-b034-129ca93c7832) с использованием синтаксиса выражений запроса.</span><span class="sxs-lookup"><span data-stu-id="264fb-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Skip%2A>, and <xref:System.Linq.Enumerable.Take%2A> methods to query the [AdventureWorks Sales Model](http://msdn.microsoft.com/en-us/f16cd988-673f-4376-b034-129ca93c7832) using query expression syntax.</span></span> <span data-ttu-id="264fb-104">Модель AdventureWorks Sales, которая используется в этих примерах, состоит из таблиц Contact, Address, Product, SalesOrderHeader и SalesOrderDetail образца базы данных AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="264fb-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="264fb-105">В примерах в этом разделе используются следующие `using` / `Imports` инструкции:</span><span class="sxs-lookup"><span data-stu-id="264fb-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="skip"></a><span data-ttu-id="264fb-106">Skip</span><span class="sxs-lookup"><span data-stu-id="264fb-106">Skip</span></span>  
  
### <a name="example"></a><span data-ttu-id="264fb-107">Пример</span><span class="sxs-lookup"><span data-stu-id="264fb-107">Example</span></span>  
 <span data-ttu-id="264fb-108">В следующем примере метод <xref:System.Linq.Enumerable.Skip%2A> используется для возврата всех контактов в таблице Contact, за исключением первых пяти.</span><span class="sxs-lookup"><span data-stu-id="264fb-108">The following example uses the <xref:System.Linq.Enumerable.Skip%2A> method to get all but the first five contacts of the Contact table.</span></span>  
  
 [!code-csharp[DP L2E Examples#SkipSimple](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#skipsimple)]
 [!code-vb[DP L2E Examples#SkipSimple](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#skipsimple)]  
  
### <a name="example"></a><span data-ttu-id="264fb-109">Пример</span><span class="sxs-lookup"><span data-stu-id="264fb-109">Example</span></span>  
 <span data-ttu-id="264fb-110">В следующем примере метод <xref:System.Linq.Enumerable.Skip%2A> используется для получения всех адресов в Сиэттле, кроме первых двух.</span><span class="sxs-lookup"><span data-stu-id="264fb-110">The following example uses the <xref:System.Linq.Enumerable.Skip%2A> method to get all but the first two addresses in Seattle.</span></span>  
  
 [!code-csharp[DP L2E Examples#SkipNested](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#skipnested)]
 [!code-vb[DP L2E Examples#SkipNested](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#skipnested)]  
  
## <a name="take"></a><span data-ttu-id="264fb-111">Take</span><span class="sxs-lookup"><span data-stu-id="264fb-111">Take</span></span>  
  
### <a name="example"></a><span data-ttu-id="264fb-112">Пример</span><span class="sxs-lookup"><span data-stu-id="264fb-112">Example</span></span>  
 <span data-ttu-id="264fb-113">В следующем примере метод <xref:System.Linq.Enumerable.Take%2A> используется для возврата первых пяти контактов из таблицы Contact.</span><span class="sxs-lookup"><span data-stu-id="264fb-113">The following example uses the <xref:System.Linq.Enumerable.Take%2A> method to get only the first five contacts from the Contact table.</span></span>  
  
 [!code-csharp[DP L2E Examples#TakeSimple](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#takesimple)]
 [!code-vb[DP L2E Examples#TakeSimple](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#takesimple)]  
  
### <a name="example"></a><span data-ttu-id="264fb-114">Пример</span><span class="sxs-lookup"><span data-stu-id="264fb-114">Example</span></span>  
 <span data-ttu-id="264fb-115">В следующем примере метод <xref:System.Linq.Enumerable.Take%2A> используется для получения первых трех адресов в Сиэттле.</span><span class="sxs-lookup"><span data-stu-id="264fb-115">The following example uses the <xref:System.Linq.Enumerable.Take%2A> method to get the first three addresses in Seattle.</span></span>  
  
 [!code-csharp[DP L2E Examples#TakeNested](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#takenested)]
 [!code-vb[DP L2E Examples#TakeNested](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#takenested)]  
  
## <a name="see-also"></a><span data-ttu-id="264fb-116">См. также</span><span class="sxs-lookup"><span data-stu-id="264fb-116">See Also</span></span>  
 [<span data-ttu-id="264fb-117">Запросы в LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="264fb-117">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
