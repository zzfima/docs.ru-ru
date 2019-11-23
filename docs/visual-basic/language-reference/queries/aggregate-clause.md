---
title: Предложение Aggregate (Visual Basic)
ms.date: 08/28/2018
f1_keywords:
- vb.QueryAggregateIn
- vb.QueryAggregate
- vb.QueryAggregateInto
helpviewer_keywords:
- Aggregate clause [Visual Basic]
- Aggregate statement [Visual Basic]
- queries [Visual Basic], Aggregate
ms.assetid: 1315a814-5db6-4077-b34b-b141e11cc0eb
ms.openlocfilehash: 50a53cd45cc428541c90fbf82089518be2212fae
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004803"
---
# <a name="aggregate-clause-visual-basic"></a>Предложение Aggregate (Visual Basic)
Применяет одну или несколько агрегатных функций к коллекции.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
Aggregate element [As type] In collection _  
  [, element2 [As type2] In collection2, [...]]  
  [ clause ]  
  Into expressionList  
```  
  
## <a name="parts"></a>Части  
  
|Термин|Определение|  
|---|---|  
|`element`|Обязательное. Переменная, используемая для прохода по элементам коллекции.|  
|`type`|Необязательно. Тип параметра `element`. Если тип не указан, тип `element` выводится из `collection`.|  
|`collection`|Обязательное. Ссылается на коллекцию для обработки.|  
|`clause`|Необязательно. Одно или несколько предложений запроса, например предложение `Where`, для уточнения результата запроса с целью применения предложения Aggregate или предложений к.|  
|`expressionList`|Обязательное. Одно или несколько выражений с разделителями-запятыми, которые обозначают агрегатную функцию, применяемую к коллекции. Можно применить псевдоним к агрегатной функции, чтобы указать имя элемента для результата запроса. Если псевдоним не указан, используется имя агрегатной функции. Примеры см. в разделе агрегатные функции далее в этом разделе.|  
  
## <a name="remarks"></a>Примечания  
 Предложение `Aggregate` можно использовать для включения в запросы агрегатных функций. Агрегатные функции выполняют проверки и вычисления для набора значений и возвращают одно значение. Доступ к вычисленному значению можно получить с помощью члена типа результата запроса. Стандартные агрегатные функции, которые можно использовать, — это функции `All`, `Any`, `Average`, `Count`, `LongCount`, `Max`, `Min`и `Sum`. Эти функции знакомы разработчикам, знакомым со статистическими выражениями в SQL. Они описаны в следующем разделе этой статьи.  
  
 Результат агрегатной функции включается в результат запроса в виде поля типа результата запроса. Можно указать псевдоним для результата агрегатной функции, чтобы указать имя элемента типа результата запроса, который будет содержать статистическое значение. Если псевдоним не указан, используется имя агрегатной функции.  
  
 Предложение `Aggregate` может начать запрос или его можно добавить как дополнительное предложение в запросе. Если предложение `Aggregate` начинает запрос, результатом является единственное значение, которое является результатом агрегатной функции, указанной в предложении `Into`. Если в предложении `Into` указано более одной агрегатной функции, запрос возвращает один тип с отдельным свойством для ссылки на результат каждой агрегатной функции в предложении `Into`. Если предложение `Aggregate` включено в запрос в качестве дополнительного предложения, то тип, возвращаемый в коллекции запросов, будет иметь отдельное свойство для ссылки на результат каждой агрегатной функции в предложении `Into`.  
  
## <a name="aggregate-functions"></a>Статистические функции

Ниже приведены стандартные агрегатные функции, которые можно использовать с предложением `Aggregate`.  
  
### <a name="all"></a>Все

Возвращает `true`, если все элементы в коллекции соответствуют заданному условию. в противном случае возвращает `false`. Ниже рассматривается пример:

 [!code-vb[VbSimpleQuerySamples#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#5)]

### <a name="any"></a>Любой

Возвращает `true`, если любой элемент в коллекции удовлетворяет заданному условию. в противном случае возвращает `false`. Ниже рассматривается пример:

 [!code-vb[VbSimpleQuerySamples#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#6)]

### <a name="average"></a>Метод Average

Вычисляет среднее значение всех элементов в коллекции или вычисляет заданное выражение для всех элементов в коллекции. Ниже рассматривается пример:

 [!code-vb[VbSimpleQuerySamples#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#7)]

### <a name="count"></a>Число

Подсчитывает количество элементов в коллекции. Можно указать необязательное выражение `Boolean`, чтобы подсчитать только число элементов в коллекции, удовлетворяющее условию. Ниже рассматривается пример:

 [!code-vb[VbSimpleQuerySamples#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#8)]

### <a name="group"></a>Группа

Относится к результатам запроса, сгруппированным в результате предложения `Group By` или `Group Join`. Функция `Group` допустима только в предложении `Into` предложения `Group By` или `Group Join`. Дополнительные сведения и примеры см. в разделе предложение [Group By](../../../visual-basic/language-reference/queries/group-by-clause.md) и [предложение Group Join](../../../visual-basic/language-reference/queries/group-join-clause.md).

### <a name="longcount"></a>LongCount

Подсчитывает количество элементов в коллекции. Можно указать необязательное выражение `Boolean`, чтобы подсчитать только число элементов в коллекции, удовлетворяющее условию. Возвращает результат в виде `Long`. Пример см. в разделе агрегатная функция `Count`.

### <a name="max"></a>Max

Вычисление максимального значения из коллекции или вычисление заданного выражения для всех элементов в коллекции. Ниже рассматривается пример:

 [!code-vb[VbSimpleQuerySamples#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#9)]

### <a name="min"></a>Min

Вычисление минимального значения из коллекции или вычисление заданного выражения для всех элементов в коллекции. Ниже рассматривается пример:

 [!code-vb[VbSimpleQuerySamples#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#10)]

### <a name="sum"></a>Sum

Вычисляет сумму всех элементов в коллекции или вычисляет заданное выражение для всех элементов в коллекции. Ниже рассматривается пример:

 [!code-vb[VbSimpleQuerySamples#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#15)]

## <a name="example"></a>Пример  

В следующем примере показано, как использовать предложение `Aggregate` для применения агрегатных функций к результату запроса.  
  
 [!code-vb[VbSimpleQuerySamples#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#4)]  
  
## <a name="creating-user-defined-aggregate-functions"></a>Создание определяемых пользователем агрегатных функций

 В выражение запроса можно включить собственные пользовательские агрегатные функции, добавив методы расширения в тип <xref:System.Collections.Generic.IEnumerable%601>. Пользовательский метод может затем выполнить вычисление или операцию над перечислимой коллекцией, на которую ссылается агрегатная функция. Дополнительные сведения о методах расширения см. в разделе [Методы расширения](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md).  
  
 Например, в следующем примере показана пользовательская агрегатная функция, которая вычисляет медианное значение коллекции чисел. Существует две перегрузки метода расширения `Median`. Первая перегрузка принимает в качестве входных данных коллекцию типов `IEnumerable(Of Double)`. Если для поля запроса типа `Double`вызывается агрегатная функция `Median`, будет вызван этот метод. Второй перегрузкой метода `Median` может быть передан любой универсальный тип. Универсальная перегрузка метода `Median` принимает второй параметр, который ссылается на `Func(Of T, Double)` лямбда-выражение для проецирования значения типа (из коллекции) в качестве соответствующего значения типа `Double`. Затем оно делегирует вычисление значения медианы другой перегрузке метода `Median`. Дополнительные сведения о лямбда-выражениях см. в разделе [Лямбда-выражения](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
 [!code-vb[VbSimpleQuerySamples#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/UserDefinedAggregates.vb#18)]  
  
 В следующем примере показаны образцы запросов, которые вызывают `Median` агрегатную функцию для коллекции типа `Integer`и коллекцию типа `Double`. Запрос, который вызывает агрегатную функцию `Median` для коллекции типа `Double` вызывает перегрузку метода `Median`, который принимает в качестве входных данных коллекцию типов `Double`. Запрос, который вызывает агрегатную функцию `Median` для коллекции типа `Integer` вызывает универсальную перегрузку метода `Median`.  
  
 [!code-vb[VbSimpleQuerySamples#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/UserDefinedAggregates.vb#19)]  
  
## <a name="see-also"></a>См. также:

- [Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)
- [Запросы](../../../visual-basic/language-reference/queries/index.md)
- [Предложение Select](../../../visual-basic/language-reference/queries/select-clause.md)
- [Предложение From](../../../visual-basic/language-reference/queries/from-clause.md)
- [Предложения Where](../../../visual-basic/language-reference/queries/where-clause.md)
- [Предложение Group By](../../../visual-basic/language-reference/queries/group-by-clause.md)
