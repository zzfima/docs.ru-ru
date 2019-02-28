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
ms.openlocfilehash: 21781db637c71abbbe9366bc95b6ee4c89ac2246
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56981963"
---
# <a name="aggregate-clause-visual-basic"></a>Предложение Aggregate (Visual Basic)
Применяет один или несколько агрегатных функций к коллекции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
Aggregate element [As type] In collection _  
  [, element2 [As type2] In collection2, [...]]  
  [ clause ]  
  Into expressionList  
```  
  
## <a name="parts"></a>Части  
  
|Термин|Определение|  
|---|---|  
|`element`|Обязательный. Переменная, используемая для итерации по элементам коллекции.|  
|`type`|Необязательный параметр. Тип параметра `element`. Если тип не указан, тип `element` выводится из `collection`.|  
|`collection`|Обязательный. Ссылается на коллекцию для работы.|  
|`clause`|Необязательный параметр. Один или несколько предложения запроса, такие как `Where` предложение для уточнения результатов запроса, чтобы применить предложение aggregate или предложений для.|  
|`expressionList`|Обязательный. Одно или несколько разделенных запятыми выражений, которые идентифицируют агрегатную функцию для применения к коллекции. Псевдоним можно применять в статистической функции, чтобы указать имя элемента для получения результата запроса. Если псевдоним не указан, используется имя агрегатной функции. Примеры см. в разделе об агрегатных функциях, далее в этом разделе.|  
  
## <a name="remarks"></a>Примечания  
 `Aggregate` Предложение может использоваться для включения агрегатных функций в запросах. Агрегатные функции выполняют проверку и вычисление на наборе значений и возвращают одиночное значение. Вычисляемое значение доступны с помощью члена типа результата запроса. Стандартные агрегатные функции, которые можно использовать, `All`, `Any`, `Average`, `Count`, `LongCount`, `Max`, `Min`, и `Sum` функции. Эти функции хорошо знакомы разработчикам, знакомым с помощью статистических функций в SQL. Они описаны в следующем разделе этой статьи.  
  
 Результат агрегатной функции включается в результат запроса как поле типа результата запроса. Можно указать псевдоним для результатов агрегатной функции, чтобы указать имя члена типа результата запроса, который будет содержать значение статистического выражения. Если псевдоним не указан, используется имя агрегатной функции.  
  
 `Aggregate` Предложение можно начать запрос, или он может быть включено как дополнительное предложение в запросе. Если `Aggregate` предложение в начале запроса, в результате одно значение, являющееся результатом агрегатной функцией, указанной в `Into` предложение. Если указано более одной агрегатной функции в `Into` предложение, запрос возвращает отдельный тип с отдельным свойством для ссылки на результат каждая Агрегатная функция в `Into` предложение. Если `Aggregate` предложение включается как дополнительное предложение в запросе, тип возвращаемой коллекции запроса будет иметь отдельные свойства, ссылающиеся на результат каждая Агрегатная функция в `Into` предложение.  
  
## <a name="aggregate-functions"></a>Статистические функции

Ниже приведены стандартные агрегатные функции, которые могут использоваться с `Aggregate` предложение.  
  
### <a name="all"></a>Все

Возвращает `true` все ли элементы в коллекции удовлетворяют указанному условию; в противном случае возвращает `false`. Ниже представлен пример такого кода.

 [!code-vb[VbSimpleQuerySamples#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#5)]

### <a name="any"></a>Любой

Возвращает `true` Если любой элемент в коллекции удовлетворяет указанному условию; в противном случае возвращает `false`. Ниже представлен пример такого кода.

 [!code-vb[VbSimpleQuerySamples#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#6)]

### <a name="average"></a>Метод Average

Вычисляет среднее значение всех элементов в коллекции, или указанное выражение для всех элементов в коллекции. Ниже представлен пример такого кода.

 [!code-vb[VbSimpleQuerySamples#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#7)]

### <a name="count"></a>Количество

Подсчитывает количество элементов в коллекции. Можно указать необязательное `Boolean` выражение для подсчета числа элементов в коллекции, которые удовлетворяют условию. Ниже представлен пример такого кода.

 [!code-vb[VbSimpleQuerySamples#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#8)]

### <a name="group"></a>Группа

Ссылается на результаты запроса, сгруппированные в результате `Group By` или `Group Join` предложение. `Group` Функция допустима только в `Into` предложении `Group By` или `Group Join` предложение. Дополнительные сведения и примеры см. в разделе [предложение Group](../../../visual-basic/language-reference/queries/group-by-clause.md) и [предложение Join группы](../../../visual-basic/language-reference/queries/group-join-clause.md).

### <a name="longcount"></a>LongCount

Подсчитывает количество элементов в коллекции. Можно указать необязательное `Boolean` выражение для подсчета числа элементов в коллекции, которые удовлетворяют условию. Возвращает результат в виде `Long`. Например, см. в разделе `Count` агрегатной функции.

### <a name="max"></a>Максимум

Вычисляет максимальное значение из коллекции, или указанное выражение для всех элементов в коллекции. Ниже представлен пример такого кода.

 [!code-vb[VbSimpleQuerySamples#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#9)]

### <a name="min"></a>Минимум

Вычисляет минимальное значение из коллекции, или указанное выражение для всех элементов в коллекции. Ниже представлен пример такого кода.

 [!code-vb[VbSimpleQuerySamples#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#10)]

### <a name="sum"></a>Sum

Вычисляет сумму всех элементов в коллекции, или указанное выражение для всех элементов в коллекции. Ниже представлен пример такого кода.

 [!code-vb[VbSimpleQuerySamples#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#15)]

## <a name="example"></a>Пример  

В следующем примере показано, как использовать `Aggregate` предложение для применения агрегатных функций к результатам запроса.  
  
 [!code-vb[VbSimpleQuerySamples#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#4)]  
  
## <a name="creating-user-defined-aggregate-functions"></a>Создание определяемых пользователем агрегатных функций

 Собственные пользовательские агрегатные функции в выражении запроса можно включить путем добавления методов расширения для <xref:System.Collections.Generic.IEnumerable%601> типа. Пользовательский метод может выполнить расчет или операцию на перечисление коллекции, на которую есть ссылки в агрегатной функции. Дополнительные сведения о методах расширения см. в разделе [Методы расширения](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md).  
  
 К примеру в следующем примере пользовательской агрегатной функции, которая вычисляет значение медианы из коллекции чисел. Существуют две перегрузки `Median` метода расширения. Первая перегрузка принимает в качестве входных данных, коллекция элементов типа `IEnumerable(Of Double)`. Если `Median` Агрегатная функция вызывается для поля типа `Double`, этот метод будет вызываться. Вторая перегрузка `Median` метод может передаваться любой универсального типа. Универсальная перегрузка `Median` метод принимает второй параметр, который ссылается на `Func(Of T, Double)` лямбда-выражения для проецирования значение для типа (из коллекции), как значение соответствующего типа `Double`. Затем он делегирует расчет значения медианы другой перегрузкой `Median` метод. Дополнительные сведения о лямбда-выражениях см. в разделе [Лямбда-выражения](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
 [!code-vb[VbSimpleQuerySamples#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/UserDefinedAggregates.vb#18)]  
  
 В следующем примере показано примеры запросов, которые вызывают `Median` агрегатную функцию в коллекцию типа `Integer`и коллекция элементов типа `Double`. Запрос, который вызывает `Median` агрегатную функцию в коллекции с типом `Double` вызывает перегрузку `Median` метод, который принимает в качестве входных данных, коллекция элементов типа `Double`. Запрос, который вызывает `Median` агрегатную функцию в коллекции с типом `Integer` вызывает универсальную перегрузку `Median` метод.  
  
 [!code-vb[VbSimpleQuerySamples#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/UserDefinedAggregates.vb#19)]  
  
## <a name="see-also"></a>См. также

- [Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)
- [Запросы](../../../visual-basic/language-reference/queries/index.md)
- [Предложение Select](../../../visual-basic/language-reference/queries/select-clause.md)
- [Предложение From](../../../visual-basic/language-reference/queries/from-clause.md)
- [Предложения Where](../../../visual-basic/language-reference/queries/where-clause.md)
- [Предложение Group By](../../../visual-basic/language-reference/queries/group-by-clause.md)
