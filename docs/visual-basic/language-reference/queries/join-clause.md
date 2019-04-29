---
title: Предложение Join (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryJoinIn
- vb.QueryJoin
- vb.QueryJoinOn
helpviewer_keywords:
- queries [Visual Basic], Join
- Join statement [Visual Basic]
- Join clause [Visual Basic]
ms.assetid: 6dd37936-b27c-4e00-98ad-154b23f4de64
ms.openlocfilehash: 21432b95b30ae38ac2cbc9e55b5a3066f0bef665
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61945292"
---
# <a name="join-clause-visual-basic"></a>Предложение Join (Visual Basic)
Объединяет две коллекции в одну. Операция соединения основана на сопоставлении ключей и использует `Equals` оператор.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
Join element In collection _  
  [ joinClause _ ]   
  [ groupJoinClause ... _ ]   
On key1 Equals key2 [ And key3 Equals key4 [... ]  
```  
  
## <a name="parts"></a>Части  
 `element`  
 Обязательный. Переменная управления для присоединяемой коллекции.  
  
 `collection`  
 Обязательный. Коллекция для объединения с коллекцией, определенной в левой части `Join` оператор. Объект `Join` предложение может быть вложенным в другой `Join` предложение, или в `Group Join` предложение.  
  
 `joinClause`  
 Необязательный параметр. Один или более дополнительных `Join` предложений для дальнейшего уточнения запроса.  
  
 `groupJoinClause`  
 Необязательный параметр. Один или более дополнительных `Group Join` предложений для дальнейшего уточнения запроса.  
  
 `key1` `Equals` `key2`  
 Обязательный. Определяет ключи для соединяемых коллекций. Необходимо использовать `Equals` оператор для сравнения ключей из соединяемых коллекций. Можно комбинировать условия соединения с помощью `And` оператор для идентификации нескольких ключей. `key1` должен быть из коллекции в левой части `Join` оператор. `key2` должен быть из коллекции в правой части `Join` оператор.  
  
 Ключи, используемые в условии соединения может быть выражений, содержащих более одного элемента из коллекции. Тем не менее каждое ключевое выражение может содержать только элементы из соответствующей коллекции.  
  
## <a name="remarks"></a>Примечания  
 `Join` Предложение объединяет две коллекции, на основе сопоставления значений ключа из соединяемых коллекций. Полученная в результате коллекция может содержать любую комбинацию значений из коллекции в левой части `Join` оператор и коллекции, указанной в `Join` предложение. Запрос будет возвращать только результаты, для которых условие, заданное `Equals` оператор будет выполняться. Это эквивалентно `INNER JOIN` в SQL.  
  
 Можно использовать несколько `Join` предложения в запросе на объединение двух или нескольких коллекций в одну коллекцию.  
  
 Можно выполнить неявное соединение для объединения коллекций без `Join` предложение. Чтобы сделать это, включать несколько `In` предложения в вашей `From` предложения и укажите `Where` предложение, определяющее ключи, которые вы хотите использовать для соединения.  
  
 Можно использовать `Group Join` предложение для объединения коллекций в одну иерархическую коллекцию. Это аналогично `LEFT OUTER JOIN` в SQL.  
  
## <a name="example"></a>Пример  
 В следующем примере кода выполняется неявное соединение для объединения списка клиентов и их заказов.  
  
 [!code-vb[VbSimpleQuerySamples#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#13)]  
  
## <a name="example"></a>Пример  
 В следующем примере объединяются две коллекции с помощью `Join` предложение.  
  
 [!code-vb[VbSimpleQuerySamples#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples2.vb#12)]  
  
 В этом примере выдаст результат, аналогичный приведенному ниже:  
  
 `winlogon (968), Windows Logon`  
  
 `explorer (2424), File Explorer`  
  
 `cmd (5136), Command Window`  
  
## <a name="example"></a>Пример  
 В следующем примере объединяются две коллекции с помощью `Join` предложение с двумя ключевыми столбцами.  
  
 [!code-vb[VbSimpleQuerySamples#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples3.vb#17)]  
  
 Пример выдаст результат, аналогичный приведенному ниже:  
  
 `winlogon (968), Windows Logon, Priority = 13`  
  
 `cmd (700), Command Window, Priority = 8`  
  
 `explorer (2424), File Explorer, Priority = 8`  
  
## <a name="see-also"></a>См. также

- [Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)
- [Запросы](../../../visual-basic/language-reference/queries/index.md)
- [Предложение Select](../../../visual-basic/language-reference/queries/select-clause.md)
- [Предложение From](../../../visual-basic/language-reference/queries/from-clause.md)
- [Предложение Group Join](../../../visual-basic/language-reference/queries/group-join-clause.md)
- [Предложения Where](../../../visual-basic/language-reference/queries/where-clause.md)
