---
title: COLLECTION (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 03228bfa-be3a-4ccc-82f8-eee429f85cf1
ms.openlocfilehash: 5a1af1aab8a084b19e48fbdbb159d7ddd8a8dd7c
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73039908"
---
# <a name="collection-entity-sql"></a>COLLECTION (Entity SQL)
Ключевое слово COLLECTION используется только в определении встроенной функции. Функции коллекций — это функции, которые работают с коллекциями значений и возвращают скалярное значение.  
  
## <a name="syntax"></a>Синтаксис  
  
```csharp  
COLLECTION(type_definition)
```  
  
## <a name="arguments"></a>Аргументы  
 `type_definition`  
 Выражение, возвращающее коллекцию поддерживаемых типов, строк или ссылок.  
  
## <a name="remarks"></a>Заметки  
 Дополнительные сведения о ключевом слове COLLECTION см. в статье [Type Definitions](type-definitions-entity-sql.md).  
  
## <a name="example"></a>Пример  
 Следующий образец иллюстрирует использование ключевого слова COLLECTION для объявления коллекции десятичных чисел в качестве аргумента для встроенной функции запроса.  
  
 [!code-csharp[DP EntityServices Concepts 2#Collection_GroupPartition](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#collection_grouppartition)]  
  
## <a name="see-also"></a>См. также

- [Справочник по Entity SQL](entity-sql-reference.md)
