---
title: Предложение Skip (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QuerySkip
helpviewer_keywords:
- queries [Visual Basic], Skip
- Skip statement [Visual Basic]
- Skip clause [Visual Basic]
ms.assetid: f00eb172-3907-4c43-9745-d8546ab86234
ms.openlocfilehash: e52de186e1475bfabd02821a0cd2384d8350eed3
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004763"
---
# <a name="skip-clause-visual-basic"></a>Предложение Skip (Visual Basic)
Пропускает заданное число элементов в коллекции и возвращает остальные элементы.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
Skip count  
```  
  
## <a name="parts"></a>Части  
 `count`  
 Обязательный. Значение или выражение, результатом которого является число пропускаемых элементов последовательности.  
  
## <a name="remarks"></a>Примечания  
 Предложение `Skip` заставляет запрос обходить элементы в начале списка результатов и возвращать оставшиеся элементы. Число пропускаемых элементов определяется параметром `count`.  
  
 Предложение `Skip` можно использовать с предложением `Take` для возврата диапазона данных из любого сегмента запроса. Для этого передайте индекс первого элемента диапазона в предложение `Skip` и размер диапазона в предложение `Take`.  
  
 При использовании предложения `Skip` в запросе может также потребоваться убедиться, что результаты возвращены в порядке, который позволит использовать предложение `Skip` для обхода предполагаемых результатов. Дополнительные сведения о упорядочении результатов запроса см. в разделе [предложение ORDER BY](../../../visual-basic/language-reference/queries/order-by-clause.md).  
  
 Можно использовать предложение `SkipWhile`, чтобы указать, что в зависимости от указанного условия игнорируются только определенные элементы.  
  
## <a name="example"></a>Пример  
 В следующем примере кода используется предложение `Skip` вместе с предложением `Take` для возврата данных из запроса на страницах. Функция `GetCustomers` использует предложение `Skip` для обхода клиентов в списке до получения значения начального индекса и использует предложение @no__t 2 для возврата страницы клиентов, начиная с этого значения индекса.  
  
 [!code-vb[VbSimpleQuerySamples#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#1)]  
  
## <a name="see-also"></a>См. также

- [Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)
- [Запросы](../../../visual-basic/language-reference/queries/index.md)
- [Предложение Select](../../../visual-basic/language-reference/queries/select-clause.md)
- [Предложение From](../../../visual-basic/language-reference/queries/from-clause.md)
- [Предложение Order By](../../../visual-basic/language-reference/queries/order-by-clause.md)
- [Предложение Skip While](../../../visual-basic/language-reference/queries/skip-while-clause.md)
- [Предложение Take](../../../visual-basic/language-reference/queries/take-clause.md)
