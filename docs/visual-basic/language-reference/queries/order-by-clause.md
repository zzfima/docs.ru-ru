---
title: Предложение Order By
ms.date: 07/20/2015
f1_keywords:
- vb.QueryOrderBy
- vb.QueryAscending
- vb.QueryDescending
helpviewer_keywords:
- queries [Visual Basic], Order By
- Order By clause [Visual Basic]
- Order By statement [Visual Basic]
ms.assetid: fa911282-6b81-44c7-acfa-46b5bb93df75
ms.openlocfilehash: a7104e3dd82ff2dde2911861ce98a7367faf3b25
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350416"
---
# <a name="order-by-clause-visual-basic"></a>Предложение Order By (Visual Basic)
Задает порядок сортировки для результата запроса.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
Order By orderExp1 [ Ascending | Descending ] [, orderExp2 [...] ]  
```  
  
## <a name="parts"></a>Части  
 `orderExp1`  
 Обязательно. Одно или несколько полей из текущего результата запроса, которые указывают порядок упорядочения возвращаемых значений. Имена полей должны быть разделены запятыми (,). Каждое поле можно найти в порядке возрастания или убывания с помощью ключевых слов `Ascending` или `Descending`. Если не указано ключевое слово `Ascending` или `Descending`, порядок сортировки по умолчанию — по возрастанию. Поля порядка сортировки получают приоритет слева направо.  
  
## <a name="remarks"></a>Примечания  
 Для сортировки результатов запроса можно использовать предложение `Order By`. Предложение `Order By` может сортировать результат только на основе переменной диапазона для текущей области. Например, предложение `Select` вводит новую область в выражении запроса с новыми переменными итерации для этой области. Переменные диапазона, определенные до предложения `Select` в запросе, недоступны после предложения `Select`. Поэтому, если требуется упорядочить результаты по полю, которое недоступно в предложении `Select`, необходимо поместить предложение `Order By` перед предложением `Select`. Одним из примеров того, когда это потребуется, является то, что нужно отсортировать запрос по полям, которые не возвращаются как часть результата.  
  
 Порядок сортировки для поля по возрастанию и убыванию определяется реализацией интерфейса <xref:System.IComparable> для типа данных поля. Если тип данных не реализует интерфейс <xref:System.IComparable>, порядок сортировки игнорируется.  
  
## <a name="example"></a>Пример  
 Следующее выражение запроса использует предложение `From`, чтобы объявить переменную диапазона `book` для коллекции `books`. Предложение `Order By` сортирует результат запроса по цене в возрастающем порядке (по умолчанию). Книги с одинаковой ценой сортируются по названию в возрастающем порядке. Предложение `Select` выбирает свойства `Title` и `Price` в качестве значений, возвращаемых запросом.  
  
 [!code-vb[VbSimpleQuerySamples#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#24)]  
  
## <a name="example"></a>Пример  
 Следующее выражение запроса использует предложение `Order By` для сортировки результатов запроса по цене в убывающем порядке. Книги с одинаковой ценой сортируются по названию в возрастающем порядке.  
  
 [!code-vb[VbSimpleQuerySamples#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#25)]  
  
## <a name="example"></a>Пример  
 Следующее выражение запроса использует предложение `Select` для выбора названия книги, цены, даты публикации и автора. Затем он заполняет поля `Title`, `Price`, `PublishDate`и `Author` переменной диапазона для новой области. Предложение `Order By` упорядочивает новую переменную диапазона по имени автора, названию книги и стоимости. Каждый столбец сортируется в порядке по умолчанию (по возрастанию).  
  
 [!code-vb[VbSimpleQuerySamples#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#26)]  
  
## <a name="see-also"></a>См. также

- [Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)
- [Запросы](../../../visual-basic/language-reference/queries/index.md)
- [Предложение Select](../../../visual-basic/language-reference/queries/select-clause.md)
- [Предложение From](../../../visual-basic/language-reference/queries/from-clause.md)
