---
title: -- (комментарий) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5d9de735-2099-47f1-b7e7-60856f494924
ms.openlocfilehash: 1ea1929b0e6f965f71fbb015ee6795affb3bce7c
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251206"
---
# <a name="---comment-entity-sql"></a><span data-ttu-id="544bd-102">-- (комментарий) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="544bd-102">-- (Comment) (Entity SQL)</span></span>
<span data-ttu-id="544bd-103">Запросы[!INCLUDE[esql](../../../../../../includes/esql-md.md)] могут содержать комментарии.</span><span class="sxs-lookup"><span data-stu-id="544bd-103">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] queries can contain comments.</span></span> <span data-ttu-id="544bd-104">Строка комментария начинается с двух дефисов (`--`).</span><span class="sxs-lookup"><span data-stu-id="544bd-104">Two dashes (`--`) start a comment line.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="544bd-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="544bd-105">Syntax</span></span>  
  
```  
-- text_of_comment  
```  
  
## <a name="arguments"></a><span data-ttu-id="544bd-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="544bd-106">Arguments</span></span>  
 `text_of_comment`  
 <span data-ttu-id="544bd-107">Строка символов, содержащая текст комментария.</span><span class="sxs-lookup"><span data-stu-id="544bd-107">Is the character string that contains the text of the comment.</span></span>  
  
## <a name="example"></a><span data-ttu-id="544bd-108">Пример</span><span class="sxs-lookup"><span data-stu-id="544bd-108">Example</span></span>  
 <span data-ttu-id="544bd-109">Следующий запрос Entity SQL демонстрирует использование комментариев.</span><span class="sxs-lookup"><span data-stu-id="544bd-109">The following Entity SQL query demonstrates how to use comments.</span></span> <span data-ttu-id="544bd-110">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="544bd-110">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="544bd-111">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="544bd-111">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="544bd-112">Выполните процедуру, описанную в [разделе инструкции. Выполнение запроса, возвращающего Структуралтипе](../how-to-execute-a-query-that-returns-structuraltype-results.md)результаты.</span><span class="sxs-lookup"><span data-stu-id="544bd-112">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="544bd-113">Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="544bd-113">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#COMMENT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#comment)]  
  
## <a name="see-also"></a><span data-ttu-id="544bd-114">См. также</span><span class="sxs-lookup"><span data-stu-id="544bd-114">See also</span></span>

- [<span data-ttu-id="544bd-115">Общие сведения об Entity SQL</span><span class="sxs-lookup"><span data-stu-id="544bd-115">Entity SQL Overview</span></span>](entity-sql-overview.md)
- [<span data-ttu-id="544bd-116">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="544bd-116">Entity SQL Reference</span></span>](entity-sql-reference.md)
