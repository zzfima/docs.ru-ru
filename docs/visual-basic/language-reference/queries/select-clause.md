---
title: "Предложение Select (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.QuerySelect"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "запросы [Visual Basic], Select"
  - "Select - предложение"
  - "Select - оператор"
ms.assetid: 27a3f61c-5960-4692-9b91-4d0c4b6178fe
caps.latest.revision: 21
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 21
---
# Предложение Select (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Определяет результат запроса.  
  
## Синтаксис  
  
```  
Select [ var1 = ] fieldName1 [, [ var2 = ] fieldName2 [...] ]  
```  
  
## Части  
 `var1`  
 Необязательный.  Псевдоним может использоваться для ссылки на результаты выражения столбца.  
  
 `fieldName1`  
 Обязательный.  Имя поля для возврата результатов запроса.  
  
## Заметки  
 Можно использовать предложение `Select`, чтобы определить результаты возврата из запроса.  Это позволяет определить элементы нового анонимного типа, который создается при запросе, или целевые члены именованного типа, возвращаемого запросом.  Предложение `Select` не является обязательным для запроса.  Если предложение `Select` не указано, запрос возвращает тип, основанный на всех членах переменных диапазона для текущей области.  Дополнительные сведения см. в разделе [Анонимные типы](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  Если запрос создает именованный тип, будет возвращен результат типа <xref:System.Collections.Generic.IEnumerable%601> где `T` имеет созданный тип.  
  
 Предложение `Select` может ссылаться на переменные в текущей области.  Это включает диапазон переменных, определенных в предложении `From` \(или в предложениях `From`\).  Также включаются любые новые переменные, созданные с псевдонимом с помощью предложений `Aggregate`, `Let`, `Group By` или `Group Join`, и переменные из предыдущего предложения `Select` в выражении запроса.  Предложение `Select` может также включать статические значения.  Например, ниже приведен пример выражения запроса, в котором предложение `Select` определяет результат запроса как новый анонимный тип с четырьмя элементами: `ProductName`, `Price`, `Discount` и `DiscountedPrice`.  Значения членов `ProductName` и `Price` берутся из переменной диапазона продукта, которая определяется в условии `From`.  Значение члена `DiscountedPrice` вычисляется в предложении `Let`.  Член `Discount` представляет собой статическое значение.  
  
 [!code-vb[VbSimpleQuerySamples#27](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/select-clause_1.vb)]  
  
 Предложение `Select` представляет новый набор переменных диапазонов для последующих запросов предложения, а также предыдущие переменные диапазонов, которые больше не принадлежат области.  Последнее предложение `Select` в выражении запроса определяет возвращаемое значение запроса.  Например, следующий запрос возвращает имя компании и идентификатор каждого заказчика для которого итоговая сумма превышает 500.  Первое предложение `Select` определяет переменные диапазона для предложения `Where` и второго предложения `Select`.  Второе предложение `Select` определяет значения, возвращаемые запросом в виде нового анонимного типа.  
  
 [!code-vb[VbSimpleQuerySamples#28](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/select-clause_2.vb)]  
  
 Если предложение `Select` определяет один элемент для возврата, выражение запроса возвращает коллекцию типа одного элемента.  Если в предложении `Select` определяется несколько возвращаемых элементов, выражение запроса возвращает коллекцию нового анонимного типа на основе выбранных элементов.  Например, следующие два запроса возвращают коллекции двух различных типов на основе предложения `Select`.  В первом запросе возвращается коллекция названий компаний в виде строк.  Второй запрос возвращает коллекцию объектов `Customer`, заполненную названиями компаний и сведениями об адресах.  
  
 [!code-vb[VbSimpleQuerySamples#29](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/select-clause_3.vb)]  
  
## Пример  
 Следующее выражение запроса использует предложение `From` для объявления переменной диапазона `cust` для коллекции `customers`.  Предложение `Select` выбирает имя и идентификатор клиента, после чего заполняет столбцы `CompanyName` и `CustomerID` новой переменной диапазона.  Оператор `For Each` просматривает каждый возвращаемый объект и отображает столбцы `CompanyName` и `CustomerID` для каждой записи.  
  
 [!code-vb[VbSimpleQuerySamples#30](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/select-clause_4.vb)]  
  
## См. также  
 [Знакомство с LINQ в Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Запросы](../../../visual-basic/language-reference/queries/queries.md)   
 [Предложение From](../../../visual-basic/language-reference/queries/from-clause.md)   
 [Предложение Where](../../../visual-basic/language-reference/queries/where-clause.md)   
 [Предложение Order By](../../../visual-basic/language-reference/queries/order-by-clause.md)   
 [Анонимные типы](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)