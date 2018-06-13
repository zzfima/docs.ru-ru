---
title: Предложение Order By (Visual Basic)
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
ms.openlocfilehash: 7c60156ee81618530b42d5f61dbcac6f59c4f675
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604124"
---
# <a name="order-by-clause-visual-basic"></a>Предложение Order By (Visual Basic)
Указывает порядок сортировки для результата запроса.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
Order By orderExp1 [ Ascending | Descending ] [, orderExp2 [...] ]  
```  
  
## <a name="parts"></a>Части  
 `orderExp1`  
 Обязательно. Одно или несколько полей из текущего результата запроса, определяющие порядок возвращаемых значений. Имена полей должны быть разделены запятыми (,). Можно определить каждое поле в возрастающем или убывающем порядке с помощью `Ascending` или `Descending` ключевые слова. Если не `Ascending` или `Descending` указано ключевое слово, порядок сортировки по возрастанию. Поля порядка сортировки получают приоритет слева направо.  
  
## <a name="remarks"></a>Примечания  
 Можно использовать `Order By` предложение для сортировки результатов запроса. `Order By` Предложения можно сортировать только результата, основанного на переменную диапазона для текущей области. Например `Select` предложение вводит новую область в выражении запроса с новыми переменными итерации для этой области. Переменные, определенные до диапазона `Select` предложения в запросе недоступны после `Select` предложения. Таким образом Если необходимо выполнить сортировку результатов по полю, которое недоступно в `Select` предложение, необходимо поместить `Order By` предложение перед `Select` предложения. Один пример при пришлось бы сделать это: необходимо выполнить сортировку по полям, которые не возвращаются как часть результата запроса.  
  
 По возрастанию и убыванию для поля определяется реализация <xref:System.IComparable> интерфейса для типа данных поля. Если тип данных не реализует <xref:System.IComparable> интерфейс, порядок сортировки учитывается.  
  
## <a name="example"></a>Пример  
 В следующем запросе используется выражение `From` предложение для объявления переменной диапазона `book` для `books` коллекции. `Order By` Предложение сортирует результаты запроса по цене в возрастающем порядке (по умолчанию). Книги с той же ценой сортируются по названию в возрастающем порядке. `Select` Предложение выбирает `Title` и `Price` свойств в виде значений, возвращенных запросом.  
  
 [!code-vb[VbSimpleQuerySamples#24](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/order-by-clause_1.vb)]  
  
## <a name="example"></a>Пример  
 В следующем запросе используется выражение `Order By` предложение для сортировки результатов запроса по цене в убывающем порядке. Книги с той же ценой сортируются по названию в возрастающем порядке.  
  
 [!code-vb[VbSimpleQuerySamples#25](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/order-by-clause_2.vb)]  
  
## <a name="example"></a>Пример  
 В следующем запросе используется выражение `Select` предложение выберите название книги, price, дата публикации и создания. Затем заполняет `Title`, `Price`, `PublishDate`, и `Author` поля переменной диапазона для новой области. `Order By` Предложение упорядочивает новую переменную диапазона, имя автора, название книги и price. Каждый столбец сортируется в порядке по умолчанию (по возрастанию).  
  
 [!code-vb[VbSimpleQuerySamples#26](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/order-by-clause_3.vb)]  
  
## <a name="see-also"></a>См. также  
 [Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)  
 [Запросы](../../../visual-basic/language-reference/queries/queries.md)  
 [Предложение Select](../../../visual-basic/language-reference/queries/select-clause.md)  
 [Предложение From](../../../visual-basic/language-reference/queries/from-clause.md)
