---
title: LIMIT (Entity SQL)
ms.date: 03/30/2017
ms.assetid: c22ffede-0a52-44d1-99b9-4a91e651e1b9
ms.openlocfilehash: 3c38fd3fc20ad19bdeeca5c02c25de6c8269def6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54493824"
---
# <a name="limit-entity-sql"></a>LIMIT (Entity SQL)
Вложенное предложение LIMIT в предложении ORDER BY позволяет проводить физическое разбиение на страницы. Ключевое слово LIMIT не может использоваться отдельно от предложения ORDER BY.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
[ LIMIT n ]  
```  
  
## <a name="arguments"></a>Аргументы  
 `n`  
 Число элементов, которые будут выбраны.  
  
 Если в предложении ORDER BY имеется подчиненное выражение LIMIT, результаты запроса будут отсортированы в соответствии со спецификацией сортировки, а количество строк в наборе будет ограничено выражением LIMIT. Например, LIMIT 5 ограничит результирующий набор до пяти экземпляров строк. Ключевое слово LIMIT является функциональным эквивалентом оператора TOP, однако для LIMIT необходимо присутствие предложения ORDER BY. Предложения SKIP и LIMIT могут использоваться в предложении ORDER BY независимо друг от друга.  
  
> [!NOTE]
>  Если в одном выражении запроса присутствуют модификатор TOP и вложенное предложение SKIP, то запрос Entity SQL является недопустимым. Его следует переписать, заменив выражение TOP выражением LIMIT.  
  
## <a name="example"></a>Пример  
 В следующем запросе Entity SQL оператор ORDER BY с предложением LIMIT задает порядок сортировки, используемый для объектов, возвращаемых инструкцией SELECT. Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1.  Выполните процедуру, описанную в [как: Выполнение запроса, возвращающего результаты StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#LIMIT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#limit)]  
  
## <a name="see-also"></a>См. также
- [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md)
- [Практическое руководство. Постранично просмотреть результаты запроса](https://msdn.microsoft.com/library/ffc0f920-e7de-42e0-9b12-ef356421d030)
- [Разбивка на страницы](../../../../../../docs/framework/data/adonet/ef/language-reference/paging-entity-sql.md)
- [TOP](../../../../../../docs/framework/data/adonet/ef/language-reference/top-entity-sql.md)
