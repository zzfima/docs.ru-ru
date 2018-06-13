---
title: COLLECTION (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 03228bfa-be3a-4ccc-82f8-eee429f85cf1
ms.openlocfilehash: 2b13d373e6c54221249b17de4fa91347cbc0f9e6
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32761637"
---
# <a name="collection-entity-sql"></a>COLLECTION (Entity SQL)
Ключевое слово COLLECTION используется только в определении встроенной функции. Функции коллекций — это функции, которые работают с коллекциями значений и возвращают скалярное значение.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
COLLECTION(type_definition)   
```  
  
## <a name="arguments"></a>Аргументы  
 `type_definition`  
 Выражение, возвращающее коллекцию поддерживаемых типов, строк или ссылок.  
  
## <a name="remarks"></a>Примечания  
 Дополнительные сведения о ключевом слове COLLECTION см. в статье [Type Definitions](../../../../../../docs/framework/data/adonet/ef/language-reference/type-definitions-entity-sql.md).  
  
## <a name="example"></a>Пример  
 Следующий образец иллюстрирует использование ключевого слова COLLECTION для объявления коллекции десятичных чисел в качестве аргумента для встроенной функции запроса.  
  
 [!code-csharp[DP EntityServices Concepts 2#Collection_GroupPartition](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#collection_grouppartition)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
