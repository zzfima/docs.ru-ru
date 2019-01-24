---
title: COLLECTION (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 03228bfa-be3a-4ccc-82f8-eee429f85cf1
ms.openlocfilehash: d4e52bb62412e61e1a71e0fe9a8555068ca18dbd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54506463"
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
- [Справочник по Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
