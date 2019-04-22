---
title: Предложение Select (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QuerySelect
helpviewer_keywords:
- Select statement [Visual Basic]
- Select clause [Visual Basic]
- queries [Visual Basic], Select
ms.assetid: 27a3f61c-5960-4692-9b91-4d0c4b6178fe
ms.openlocfilehash: 367d810c2358963bfe2f092a390443eccdc66941
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58814449"
---
# <a name="select-clause-visual-basic"></a>Предложение Select (Visual Basic)
Определяет результат запроса.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
Select [ var1 = ] fieldName1 [, [ var2 = ] fieldName2 [...] ]  
```  
  
## <a name="parts"></a>Части  
 `var1`  
 Необязательный параметр. Псевдоним, который может использоваться для ссылки на результаты выражения столбца.  
  
 `fieldName1`  
 Обязательный. Имя поля для возврата в результатах запроса.  
  
## <a name="remarks"></a>Примечания  
 Можно использовать `Select` предложение для определения результатов, возвращаемых из запроса. Это позволяет определить элементы нового анонимного типа, который создается по запросу, или целевые члены именованного типа, возвращаемые запросом. `Select` Предложение не является обязательным для запроса. Если нет `Select` указано предложение, запрос будет возвращать тип, основанный на всех участниках переменные диапазона, определенные для текущей области. Дополнительные сведения см. в статье [Анонимные типы](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md). Когда запрос создает именованный тип, возвращается результат типа <xref:System.Collections.Generic.IEnumerable%601> где `T` созданный тип.  
  
 `Select` Предложение может ссылаться на переменные в текущей области. Сюда входят переменные диапазона, определенные в `From` предложения (или `From` предложения). Он также включает любые новые переменные, созданные с псевдонимом, `Aggregate`, `Let`, `Group By`, или `Group Join` предложения, или переменные из предыдущей `Select` предложение в выражении запроса. `Select` Предложение может также включать статические значения. Например, в следующем примере кода показано выражение запроса, в котором `Select` предложение определяет результат запроса как новый анонимный тип с четырьмя элементами: `ProductName`, `Price`, `Discount`, и `DiscountedPrice`. `ProductName` И `Price` член значения берутся из переменной диапазона продукта, который определен в `From` предложение. `DiscountedPrice` Значение элемента вычисляется в `Let` предложение. `Discount` Член представляет собой статическое значение.  
  
 [!code-vb[VbSimpleQuerySamples#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#27)]  
  
 `Select` Предложение вводит новый набор переменных диапазона для последующих запросов предложения, а предыдущие переменные диапазона больше не находятся в области. Последний `Select` предложение в выражении запроса определяет возвращаемое значение запроса. Например следующий запрос возвращает компании имя и идентификатор для каждого заказчика, для которого итоговая сумма превышает 500. Первый `Select` предложение определяет переменные диапазона для `Where` предложение, а второй `Select` предложение. Второй `Select` предложение определяет значения, возвращаемые запросом как новый анонимный тип.  
  
 [!code-vb[VbSimpleQuerySamples#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#28)]  
  
 Если `Select` предложение определяет один элемент для возврата, выражение запроса возвращает коллекцию типа одного элемента. Если `Select` предложение определяет несколько элементов для возврата, выражение запроса возвращает коллекцию нового анонимного типа, на основе выбранных элементов. Например, следующие два запроса возвращают коллекции двух различных типов, на основе `Select` предложение. Первый запрос возвращает коллекцию имен компании как строки. Второй запрос возвращает коллекцию `Customer` объектов, заполненных названия компаний и сведения об адресе.  
  
 [!code-vb[VbSimpleQuerySamples#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#29)]  
  
## <a name="example"></a>Пример  
 В следующем запросе используется выражение `From` предложение для объявления переменной диапазона `cust` для `customers` коллекции. `Select` Предложение выбирает имя клиента и значение идентификатора и заполняет `CompanyName` и `CustomerID` столбцов новой переменной диапазона. `For Each` Инструкция перебирает каждый возвращаемый объект и отображает `CompanyName` и `CustomerID` столбцов для каждой записи.  
  
 [!code-vb[VbSimpleQuerySamples#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#30)]  
  
## <a name="see-also"></a>См. также

- [Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)
- [Запросы](../../../visual-basic/language-reference/queries/index.md)
- [Предложение From](../../../visual-basic/language-reference/queries/from-clause.md)
- [Предложения Where](../../../visual-basic/language-reference/queries/where-clause.md)
- [Предложение Order By](../../../visual-basic/language-reference/queries/order-by-clause.md)
- [Анонимные типы](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
