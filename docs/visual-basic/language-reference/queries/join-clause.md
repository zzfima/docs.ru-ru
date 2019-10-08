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
ms.openlocfilehash: 8eab7db00515f55b086b5e1beddd149f966cb27a
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72001935"
---
# <a name="join-clause-visual-basic"></a>Предложение Join (Visual Basic)
Объединяет две коллекции в одну. Операция Join основана на совпадающих ключах и использует оператор `Equals`.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
Join element In collection _  
  [ joinClause _ ]   
  [ groupJoinClause ... _ ]   
On key1 Equals key2 [ And key3 Equals key4 [... ]  
```  
  
## <a name="parts"></a>Части  
 `element`  
 Обязательный. Управляющая переменная для объединяемой коллекции.  
  
 `collection`  
 Обязательный. Коллекция для объединения с коллекцией, указанной в левой части оператора `Join`. Предложение `Join` может быть вложено в другое предложение `Join` или в предложение @no__t 2.  
  
 `joinClause`  
 Необязательный параметр. Одно или несколько дополнительных предложений `Join` для дальнейшего уточнения запроса.  
  
 `groupJoinClause`  
 Необязательный параметр. Одно или несколько дополнительных предложений `Group Join` для дальнейшего уточнения запроса.  
  
 `key1` `Equals` `key2`  
 Обязательный. Определяет ключи для соединяемых коллекций. Для сравнения ключей из объединяемых коллекций необходимо использовать оператор `Equals`. Условия JOIN можно комбинировать с помощью оператора `And` для обнаружения нескольких ключей. `key1` должен быть из коллекции в левой части оператора `Join`. `key2` должен находиться в коллекции с правой стороны оператора `Join`.  
  
 Ключи, используемые в условии объединения, могут быть выражениями, включающими более одного элемента из коллекции. Однако каждое ключевое выражение может содержать только элементы из соответствующей коллекции.  
  
## <a name="remarks"></a>Примечания  
 Предложение `Join` объединяет две коллекции на основе совпадающих значений ключей из объединяемых коллекций. Результирующая коллекция может содержать любое сочетание значений из коллекции, определенной в левой части оператора `Join`, и коллекции, указанной в предложении `Join`. Запрос возвратит только результаты, для которых выполнено условие, заданное оператором `Equals`. Это эквивалентно `INNER JOIN` в SQL.  
  
 Для объединения двух или более коллекций в одну коллекцию можно использовать несколько предложений `Join` в запросе.  
  
 Можно выполнить неявное соединение для объединения коллекций без предложения `Join`. Для этого включите несколько предложений `In` в предложение `From` и укажите предложение @no__t 2, определяющее ключи, которые необходимо использовать для объединения.  
  
 Для объединения коллекций в одну иерархическую коллекцию можно использовать предложение `Group Join`. Это аналогично `LEFT OUTER JOIN` в SQL.  
  
## <a name="example"></a>Пример  
 В следующем примере кода выполняется неявное соединение для объединения списка клиентов с их заказами.  
  
 [!code-vb[VbSimpleQuerySamples#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#13)]  
  
## <a name="example"></a>Пример  
 В следующем примере кода две коллекции объединяются с помощью предложения `Join`.  
  
 [!code-vb[VbSimpleQuerySamples#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples2.vb#12)]  
  
 В этом примере выводятся выходные данные, аналогичные приведенным ниже.  
  
 `winlogon (968), Windows Logon`  
  
 `explorer (2424), File Explorer`  
  
 `cmd (5136), Command Window`  
  
## <a name="example"></a>Пример  
 В следующем примере кода две коллекции объединяются с помощью предложения `Join` с двумя ключевыми столбцами.  
  
 [!code-vb[VbSimpleQuerySamples#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples3.vb#17)]  
  
 В примере будет выведен результат, аналогичный приведенному ниже:  
  
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
