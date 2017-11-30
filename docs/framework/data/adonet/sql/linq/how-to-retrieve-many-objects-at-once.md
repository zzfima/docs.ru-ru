---
title: "Практическое руководство. Извлечение нескольких объектов одновременно"
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
ms.assetid: 18aff4d8-bde8-461b-9960-ccabb24e9d22
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: c5ae3ace43aeaf13f26724f5edb88dd447603161
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-retrieve-many-objects-at-once"></a><span data-ttu-id="a35f7-102">Практическое руководство. Извлечение нескольких объектов одновременно</span><span class="sxs-lookup"><span data-stu-id="a35f7-102">How to: Retrieve Many Objects At Once</span></span>
<span data-ttu-id="a35f7-103">Для извлечения нескольких объектов из одного запроса используется <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A>.</span><span class="sxs-lookup"><span data-stu-id="a35f7-103">You can retrieve many objects in one query by using <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a35f7-104">Пример</span><span class="sxs-lookup"><span data-stu-id="a35f7-104">Example</span></span>  
 <span data-ttu-id="a35f7-105">В следующем коде для извлечения объекта <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> и `Customer` используется метод `Order`.</span><span class="sxs-lookup"><span data-stu-id="a35f7-105">The following code uses the <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> method to retrieve both `Customer` and `Order` objects.</span></span>  
  
 [!code-csharp[DLinqQueryConcepts#9](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#9)]
 [!code-vb[DLinqQueryConcepts#9](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="a35f7-106">См. также</span><span class="sxs-lookup"><span data-stu-id="a35f7-106">See Also</span></span>  
 [<span data-ttu-id="a35f7-107">Основные принципы запросов</span><span class="sxs-lookup"><span data-stu-id="a35f7-107">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
