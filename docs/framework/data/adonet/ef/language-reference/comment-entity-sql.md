---
title: -- (комментарий) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5d9de735-2099-47f1-b7e7-60856f494924
ms.openlocfilehash: 43b8cdbf5dbca8822645c27711f6984b8d741ea7
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040278"
---
# <a name="---comment-entity-sql"></a><span data-ttu-id="fe0ab-102">-- (комментарий) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="fe0ab-102">-- (Comment) (Entity SQL)</span></span>
<span data-ttu-id="fe0ab-103">Запросы[!INCLUDE[esql](../../../../../../includes/esql-md.md)] могут содержать комментарии.</span><span class="sxs-lookup"><span data-stu-id="fe0ab-103">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] queries can contain comments.</span></span> <span data-ttu-id="fe0ab-104">Строка комментария начинается с двух дефисов (`--`).</span><span class="sxs-lookup"><span data-stu-id="fe0ab-104">Two dashes (`--`) start a comment line.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe0ab-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fe0ab-105">Syntax</span></span>  
  
```csharp  
-- text_of_comment  
```  
  
## <a name="arguments"></a><span data-ttu-id="fe0ab-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="fe0ab-106">Arguments</span></span>  
 `text_of_comment`  
 <span data-ttu-id="fe0ab-107">Строка символов, содержащая текст комментария.</span><span class="sxs-lookup"><span data-stu-id="fe0ab-107">Is the character string that contains the text of the comment.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fe0ab-108">Пример</span><span class="sxs-lookup"><span data-stu-id="fe0ab-108">Example</span></span>  
 <span data-ttu-id="fe0ab-109">Следующий запрос Entity SQL демонстрирует использование комментариев.</span><span class="sxs-lookup"><span data-stu-id="fe0ab-109">The following Entity SQL query demonstrates how to use comments.</span></span> <span data-ttu-id="fe0ab-110">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="fe0ab-110">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="fe0ab-111">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="fe0ab-111">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="fe0ab-112">Выполните процедуру из статьи [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="fe0ab-112">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="fe0ab-113">Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="fe0ab-113">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#COMMENT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#comment)]  
  
## <a name="see-also"></a><span data-ttu-id="fe0ab-114">См. также</span><span class="sxs-lookup"><span data-stu-id="fe0ab-114">See also</span></span>

- [<span data-ttu-id="fe0ab-115">Общие сведения об Entity SQL</span><span class="sxs-lookup"><span data-stu-id="fe0ab-115">Entity SQL Overview</span></span>](entity-sql-overview.md)
- [<span data-ttu-id="fe0ab-116">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="fe0ab-116">Entity SQL Reference</span></span>](entity-sql-reference.md)
