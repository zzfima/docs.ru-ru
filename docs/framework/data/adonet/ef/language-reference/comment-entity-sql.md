---
title: -- (комментарий) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5d9de735-2099-47f1-b7e7-60856f494924
ms.openlocfilehash: 40a0ee8f6bc2cf8fae5779ecb3d103c77dde161b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59137180"
---
# <a name="---comment-entity-sql"></a><span data-ttu-id="90382-102">-- (комментарий) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="90382-102">-- (Comment) (Entity SQL)</span></span>
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="90382-103">запросы могут содержать комментарии.</span><span class="sxs-lookup"><span data-stu-id="90382-103">queries can contain comments.</span></span> <span data-ttu-id="90382-104">Строка комментария начинается с двух дефисов (`--`).</span><span class="sxs-lookup"><span data-stu-id="90382-104">Two dashes (`--`) start a comment line.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90382-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="90382-105">Syntax</span></span>  
  
```  
-- text_of_comment  
```  
  
## <a name="arguments"></a><span data-ttu-id="90382-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="90382-106">Arguments</span></span>  
 `text_of_comment`  
 <span data-ttu-id="90382-107">Строка символов, содержащая текст комментария.</span><span class="sxs-lookup"><span data-stu-id="90382-107">Is the character string that contains the text of the comment.</span></span>  
  
## <a name="example"></a><span data-ttu-id="90382-108">Пример</span><span class="sxs-lookup"><span data-stu-id="90382-108">Example</span></span>  
 <span data-ttu-id="90382-109">Следующий запрос Entity SQL демонстрирует использование комментариев.</span><span class="sxs-lookup"><span data-stu-id="90382-109">The following Entity SQL query demonstrates how to use comments.</span></span> <span data-ttu-id="90382-110">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="90382-110">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="90382-111">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="90382-111">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="90382-112">Выполните процедуру, описанную в [как: Выполнение запроса, возвращающего результаты StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="90382-112">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="90382-113">Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="90382-113">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#COMMENT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#comment)]  
  
## <a name="see-also"></a><span data-ttu-id="90382-114">См. также</span><span class="sxs-lookup"><span data-stu-id="90382-114">See also</span></span>

- [<span data-ttu-id="90382-115">Общие сведения об Entity SQL</span><span class="sxs-lookup"><span data-stu-id="90382-115">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
- [<span data-ttu-id="90382-116">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="90382-116">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
