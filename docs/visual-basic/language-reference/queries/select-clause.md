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
ms.openlocfilehash: 087472c51d203be083fea0d39ade6f12066cfcb4
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004745"
---
# <a name="select-clause-visual-basic"></a>Предложение Select (Visual Basic)
Определяет результат запроса.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
Select [ var1 = ] fieldName1 [, [ var2 = ] fieldName2 [...] ]  
```  
  
## <a name="parts"></a>Части  
 `var1`  
 Необязательный параметр. Псевдоним, который может использоваться для ссылки на результаты выражения столбца.  
  
 `fieldName1`  
 Обязательный. Имя поля, возвращаемого в результате запроса.  
  
## <a name="remarks"></a>Примечания  
 Для определения результатов, возвращаемых из запроса, можно использовать предложение `Select`. Это позволяет либо определить члены нового анонимного типа, созданного запросом, либо целевые элементы именованного типа, возвращаемые запросом. Предложение `Select` не требуется для запроса. Если предложение `Select` не указано, запрос возвратит тип, основанный на всех членах переменных диапазона, определенных для текущей области. Дополнительные сведения см. в статье [Анонимные типы](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md). Когда запрос создает именованный тип, он вернет результат типа <xref:System.Collections.Generic.IEnumerable%601>, где `T` — это созданный тип.  
  
 Предложение `Select` может ссылаться на любые переменные в текущей области. Сюда входят переменные диапазона, определенные в предложении `From` (или предложения `From`). Он также включает все новые переменные, созданные с помощью псевдонима, с помощью предложений `Aggregate`, `Let`, `Group By` или `Group Join` или переменных из предыдущего предложения `Select` в выражении запроса. Предложение `Select` также может включать статические значения. Например, в следующем примере кода показано выражение запроса, в котором предложение `Select` определяет результат запроса как новый анонимный тип с четырьмя элементами: `ProductName`, `Price`, `Discount` и `DiscountedPrice`. Значения элементов `ProductName` и `Price` берутся из переменной диапазона продуктов, которая определена в предложении `From`. Значение элемента `DiscountedPrice` вычисляется в предложении `Let`. Элемент `Discount` является статическим значением.  
  
 [!code-vb[VbSimpleQuerySamples#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#27)]  
  
 Предложение `Select` вводит новый набор переменных диапазона для последующих предложений запроса, а предыдущие переменные диапазона больше не находятся в области. Последнее предложение `Select` в выражении запроса определяет возвращаемое значение запроса. Например, следующий запрос возвращает название компании и идентификатор заказа для каждого заказа клиента, для которого сумма превышает 500. Первое предложение `Select` определяет переменные диапазона для предложения `Where` и второе предложение `Select`. Второе предложение `Select` определяет значения, возвращаемые запросом в виде нового анонимного типа.  
  
 [!code-vb[VbSimpleQuerySamples#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#28)]  
  
 Если предложение `Select` определяет один возвращаемый элемент, выражение запроса возвращает коллекцию типа этого отдельного элемента. Если предложение `Select` определяет несколько возвращаемых элементов, выражение запроса возвращает коллекцию нового анонимного типа на основе выбранных элементов. Например, следующие два запроса возвращают коллекции двух разных типов на основе предложения `Select`. Первый запрос возвращает коллекцию названий компаний в виде строк. Второй запрос возвращает коллекцию объектов `Customer`, заполненных названиями и адресами компании.  
  
 [!code-vb[VbSimpleQuerySamples#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#29)]  
  
## <a name="example"></a>Пример  
 Следующее выражение запроса использует предложение `From` для объявления переменной диапазона `cust` для коллекции `customers`. Предложение `Select` выбирает имя клиента и значение идентификатора и заполняет столбцы `CompanyName` и `CustomerID` для новой переменной диапазона. Инструкция `For Each` циклически перебирает каждый возвращенный объект и отображает столбцы `CompanyName` и `CustomerID` для каждой записи.  
  
 [!code-vb[VbSimpleQuerySamples#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#30)]  
  
## <a name="see-also"></a>См. также

- [Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)
- [Запросы](../../../visual-basic/language-reference/queries/index.md)
- [Предложение From](../../../visual-basic/language-reference/queries/from-clause.md)
- [Предложения Where](../../../visual-basic/language-reference/queries/where-clause.md)
- [Предложение Order By](../../../visual-basic/language-reference/queries/order-by-clause.md)
- [Анонимные типы](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
