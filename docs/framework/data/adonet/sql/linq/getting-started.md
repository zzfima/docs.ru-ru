---
title: "Начало работы"
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
ms.assetid: db8a557a-fef8-4f4f-bb91-8cff7250ee25
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 0c6db401f710c470ea890a7a7ac090fabef5d64c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="getting-started"></a><span data-ttu-id="aaae2-102">Начало работы</span><span class="sxs-lookup"><span data-stu-id="aaae2-102">Getting Started</span></span>
<span data-ttu-id="aaae2-103">С помощью [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], можно использовать [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] технологии для доступа к SQL базы данных так же, как и к коллекции в памяти.</span><span class="sxs-lookup"><span data-stu-id="aaae2-103">By using [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], you can use the [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] technology to access SQL databases just as you would access an in-memory collection.</span></span>  
  
 <span data-ttu-id="aaae2-104">В следующем примере кода создается объект `nw` для представления базы данных `Northwind`, выполняется запрос к таблице `Customers`, фильтруются строки для поиска клиентов (`Customers`) из Лондона (`London`) и выбирается строка `CompanyName` для извлечения.</span><span class="sxs-lookup"><span data-stu-id="aaae2-104">For example, the `nw` object in the following code is created to represent the `Northwind` database, the `Customers` table is targeted, the rows are filtered for `Customers` from `London`, and a string for `CompanyName` is selected for retrieval.</span></span>  
  
 <span data-ttu-id="aaae2-105">При выполнении цикла извлекается коллекция значений `CompanyName`.</span><span class="sxs-lookup"><span data-stu-id="aaae2-105">When the loop is executed, the collection of `CompanyName` values is retrieved.</span></span>  
  
 [!code-csharp[DLinqGettingStarted#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#1)]
 [!code-vb[DLinqGettingStarted#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#1)]  
  
## <a name="next-steps"></a><span data-ttu-id="aaae2-106">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="aaae2-106">Next Steps</span></span>  
 <span data-ttu-id="aaae2-107">Дополнительные примеры, включая вставки и обновления, см. в разделе [что вам можно выполнять с LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/what-you-can-do-with-linq-to-sql.md).</span><span class="sxs-lookup"><span data-stu-id="aaae2-107">For some additional examples, including inserting and updating, see [What You Can Do With LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/what-you-can-do-with-linq-to-sql.md).</span></span>  
  
 <span data-ttu-id="aaae2-108">Далее ознакомьтесь с некоторыми пошаговыми руководствами и учебниками, чтобы получить практический навык работы с [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aaae2-108">Next, try some walkthroughs and tutorials to have a hands-on experience of using [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="aaae2-109">В разделе [обучения с использованием пошаговых руководств](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md).</span><span class="sxs-lookup"><span data-stu-id="aaae2-109">See [Learning by Walkthroughs](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md).</span></span>  
  
 <span data-ttu-id="aaae2-110">Наконец, узнайте, как приступить к работе в собственном [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] проекта путем чтения [типичные действия по с помощью LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/typical-steps-for-using-linq-to-sql.md).</span><span class="sxs-lookup"><span data-stu-id="aaae2-110">Finally, learn how to get started on your own [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] project by reading [Typical Steps for Using LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/typical-steps-for-using-linq-to-sql.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aaae2-111">См. также</span><span class="sxs-lookup"><span data-stu-id="aaae2-111">See Also</span></span>  
 [<span data-ttu-id="aaae2-112">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="aaae2-112">LINQ to SQL</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/index.md)  
 [<span data-ttu-id="aaae2-113">Введение в LINQ</span><span class="sxs-lookup"><span data-stu-id="aaae2-113">Introduction to LINQ</span></span>](http://msdn.microsoft.com/library/24dddf19-12a0-4707-a4bc-eba4fa7f219e)  
 [<span data-ttu-id="aaae2-114">LINQ to SQL модель объектов</span><span class="sxs-lookup"><span data-stu-id="aaae2-114">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
