---
title: "Предложение Group By (Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.QueryGroupByInto
- vb.QueryGroupBy
- vb.QueryGroupRef
- vb.QueryGroupInto
- vb.QueryGroup
dev_langs:
- VB
helpviewer_keywords:
- queries [Visual Basic], Group By
- Group By statement
- Group By clause
ms.assetid: b1b5dcea-6654-473b-a2db-01f7e4c265d7
caps.latest.revision: 20
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: a40074c4602d6c0164c784d497fbfb134402bf62
ms.lasthandoff: 03/13/2017

---
# <a name="group-by-clause-visual-basic"></a>Предложение Group By (Visual Basic)
Группирует элементы результата запроса. Может также использоваться для применения агрегатных функций к каждой группе. Операция группирования основана на одном или нескольких ключах.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
Group [ listField1 [, listField2 [...] ] By keyExp1 [, keyExp2 [...] ]  
  Into aggregateList  
```  
  
## <a name="parts"></a>Части  
  
-   `listField1`, `listField2`  
  
     Необязательно. Одно или несколько полей переменной или переменных запроса, которые явно определяют поля для включения в сгруппированный результат. Если поля не указаны, в сгруппированный результат включаются все поля из переменной или переменных запроса.  
  
-   `keyExp1`  
  
     Обязательный. Выражение, которое определяет ключ, используемый для определения групп элементов. Вы можете указать несколько ключей, чтобы задать составной ключ.  
  
-   `keyExp2`  
  
     Необязательный. Один или несколько дополнительных ключей, которые объединяются с `keyExp1` для создания составного ключа.  
  
-   `aggregateList`  
  
     Обязательный. Одно или несколько выражений, определяющих способ агрегирования групп. Чтобы определить имя элемента для результатов группирования, используйте ключевое слово `Group` , которое может быть в одной из следующих форм:  
  
    ```  
    Into Group  
    ```  
  
     -или-  
  
    ```  
    Into <alias> = Group  
    ```  
  
     Вы также можете включать агрегатные функции для применения к группе.  
  
## <a name="remarks"></a>Примечания  
 Чтобы разбить результат ы запроса на группы, можно использовать предложение `Group By` . Группирование основывается на ключе или составном ключе, состоящем из нескольких ключей. Элементы, связанные с соответствующими значениями ключа, включаются в одну и ту же группу.  
  
 Чтобы определить имя элемента, используемое для ссылки на группу, применяется параметр `aggregateList` предложения `Into` и ключевое слово `Group` . Вы также можете включать в предложение `Into` агрегатные функции, чтобы вычислять значения для сгруппированных элементов. Список стандартных статистических функций, в разделе [предложения Aggregate](../../../visual-basic/language-reference/queries/aggregate-clause.md).  
  
## <a name="example"></a>Пример  
 В следующем примере выполняется группирование списка клиентов на основе их расположения (страна) и вычисляется число клиентов в каждой группе. Результаты упорядочиваются по названию страны. Результаты группирования упорядочиваются по названию города.  
  
 [!code-vb[VbSimpleQuerySamples&11;](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/group-by-clause_1.vb)]  
  
## <a name="see-also"></a>См. также  
 [Введение в LINQ в Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Запросы](../../../visual-basic/language-reference/queries/queries.md)   
 [Предложение SELECT](../../../visual-basic/language-reference/queries/select-clause.md)   
 [Предложение FROM](../../../visual-basic/language-reference/queries/from-clause.md)   
 [Предложение Order By](../../../visual-basic/language-reference/queries/order-by-clause.md)   
 [Aggregate-предложение](../../../visual-basic/language-reference/queries/aggregate-clause.md)   
 [Предложение Group Join](../../../visual-basic/language-reference/queries/group-join-clause.md)
