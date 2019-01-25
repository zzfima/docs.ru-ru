---
title: -- (комментарий) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5d9de735-2099-47f1-b7e7-60856f494924
ms.openlocfilehash: 477a5f9aefeec46766a93c1e6ae9f3ecb3c3677f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54705701"
---
# <a name="---comment-entity-sql"></a><span data-ttu-id="6a7c6-102">-- (комментарий) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="6a7c6-102">-- (Comment) (Entity SQL)</span></span>
<span data-ttu-id="6a7c6-103">Запросы[!INCLUDE[esql](../../../../../../includes/esql-md.md)] могут содержать комментарии.</span><span class="sxs-lookup"><span data-stu-id="6a7c6-103">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] queries can contain comments.</span></span> <span data-ttu-id="6a7c6-104">Строка комментария начинается с двух дефисов (`--`).</span><span class="sxs-lookup"><span data-stu-id="6a7c6-104">Two dashes (`--`) start a comment line.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a7c6-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6a7c6-105">Syntax</span></span>  
  
```  
-- text_of_comment  
```  
  
## <a name="arguments"></a><span data-ttu-id="6a7c6-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="6a7c6-106">Arguments</span></span>  
 `text_of_comment`  
 <span data-ttu-id="6a7c6-107">Строка символов, содержащая текст комментария.</span><span class="sxs-lookup"><span data-stu-id="6a7c6-107">Is the character string that contains the text of the comment.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6a7c6-108">Пример</span><span class="sxs-lookup"><span data-stu-id="6a7c6-108">Example</span></span>  
 <span data-ttu-id="6a7c6-109">Следующий запрос Entity SQL демонстрирует использование комментариев.</span><span class="sxs-lookup"><span data-stu-id="6a7c6-109">The following Entity SQL query demonstrates how to use comments.</span></span> <span data-ttu-id="6a7c6-110">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="6a7c6-110">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="6a7c6-111">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="6a7c6-111">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="6a7c6-112">Выполните процедуру, описанную в [как: Выполнение запроса, возвращающего результаты StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="6a7c6-112">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="6a7c6-113">Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="6a7c6-113">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#COMMENT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#comment)]  
  
## <a name="see-also"></a><span data-ttu-id="6a7c6-114">См. также</span><span class="sxs-lookup"><span data-stu-id="6a7c6-114">See also</span></span>
- [<span data-ttu-id="6a7c6-115">Общие сведения об Entity SQL</span><span class="sxs-lookup"><span data-stu-id="6a7c6-115">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
- [<span data-ttu-id="6a7c6-116">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="6a7c6-116">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
