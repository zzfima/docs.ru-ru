---
title: Предложение Select (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.QuerySelect
helpviewer_keywords:
- Select statement [Visual Basic]
- Select clause [Visual Basic]
- queries [Visual Basic], Select
ms.assetid: 27a3f61c-5960-4692-9b91-4d0c4b6178fe
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a9d8cabcbd8554ca2aee639eaac8a52f0485a266
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="select-clause-visual-basic"></a>Предложение Select (Visual Basic)
Определяет результат запроса.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
Select [ var1 = ] fieldName1 [, [ var2 = ] fieldName2 [...] ]  
```  
  
## <a name="parts"></a>Части  
 `var1`  
 Необязательно. Псевдоним, который может использоваться для ссылки на результаты выражения столбца.  
  
 `fieldName1`  
 Обязательный. Имя поля для возврата в результатах запроса.  
  
## <a name="remarks"></a>Примечания  
 Можно использовать `Select` предложение для определения результатов, возвращаемых из запроса. Это позволяет определить элементы нового анонимного типа, созданный запрос или целевые члены именованного типа, возвращенные запросом. `Select` Предложение не является обязательным для запроса. Если не `Select` указано предложение, запрос будет возвращать тип, основанный на всех членах переменных диапазона для текущей области. Дополнительные сведения см. в статье [Анонимные типы](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md). Когда запрос создает именованный тип, он вернет результат типа <xref:System.Collections.Generic.IEnumerable%601> где `T` созданный тип.  
  
 `Select` Предложение может ссылаться на переменные в текущей области. Это включает в себя переменные диапазона, определенные в `From` предложение (или `From` предложения). Он также включает любые новые переменные, созданные с использованием псевдонима, `Aggregate`, `Let`, `Group By`, или `Group Join` предложений или переменные с предыдущей `Select` предложение в выражении запроса. `Select` Предложение также могут включать статические значения. Например, в следующем примере кода показано выражение запроса, в котором `Select` предложение определяет результат запроса как новый анонимный тип с четырьмя элементами: `ProductName`, `Price`, `Discount`, и `DiscountedPrice`. `ProductName` И `Price` член значения берутся из переменной диапазона продукта, определенного в `From` предложения. `DiscountedPrice` Значение элемента вычисляется в `Let` предложения. `Discount` Член имеет статическое значение.  
  
 [!code-vb[VbSimpleQuerySamples#27](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/select-clause_1.vb)]  
  
 `Select` Предложение представляет новый набор переменных диапазона для последующих запросов предложения, а предыдущие переменные диапазона больше не находятся в области. Последний `Select` предложение в выражении запроса определяет возвращаемое значение запроса. Например следующий запрос возвращает компании имя и идентификатор каждого заказчика, для которого итоговая сумма превышает 500. Первый `Select` предложение определяет переменные диапазона для `Where` предложение, а второй — `Select` предложения. Второй `Select` предложение определяет значения, возвращаемые методом запроса в виде нового анонимного типа.  
  
 [!code-vb[VbSimpleQuerySamples#28](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/select-clause_2.vb)]  
  
 Если `Select` предложение определяет один элемент для возврата, выражение запроса возвращает коллекцию типа одного элемента. Если `Select` предложение определяет несколько возвращаемых элементов, выражение запроса возвращает коллекцию анонимного типа, на основе выбранных элементов. Например, следующие два запроса возвращают коллекции двух различных типов на основе `Select` предложения. Первый запрос возвращает коллекцию имен компании как строки. Второй запрос возвращает коллекцию `Customer` объектов, заполненных названия компаний и сведения об адресе.  
  
 [!code-vb[VbSimpleQuerySamples#29](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/select-clause_3.vb)]  
  
## <a name="example"></a>Пример  
 В следующем запросе используется выражение `From` предложение для объявления переменной диапазона `cust` для `customers` коллекции. `Select` Предложение выбирает имя клиента и значение идентификатора и заполняет `CompanyName` и `CustomerID` столбцов новой переменной диапазона. `For Each` Инструкция обрабатывает в цикле каждый возвращаемый объект и отображает `CompanyName` и `CustomerID` столбцов для каждой записи.  
  
 [!code-vb[VbSimpleQuerySamples#30](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/select-clause_4.vb)]  
  
## <a name="see-also"></a>См. также  
 [Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)  
 [Запросы](../../../visual-basic/language-reference/queries/queries.md)  
 [Предложение From](../../../visual-basic/language-reference/queries/from-clause.md)  
 [Предложения Where](../../../visual-basic/language-reference/queries/where-clause.md)  
 [Предложение Order By](../../../visual-basic/language-reference/queries/order-by-clause.md)  
 [Анонимные типы](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
