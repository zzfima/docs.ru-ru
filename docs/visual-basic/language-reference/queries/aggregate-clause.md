---
title: Предложение Aggregate (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryAggregateIn
- vb.QueryAggregate
- vb.QueryAggregateInto
helpviewer_keywords:
- Aggregate clause [Visual Basic]
- Aggregate statement [Visual Basic]
- queries [Visual Basic], Aggregate
ms.assetid: 1315a814-5db6-4077-b34b-b141e11cc0eb
ms.openlocfilehash: 1db4b7fdcf9c8a38c2c49eca9d874eccea90ab1d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604904"
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
|`element`|Обязательно. Переменная, используемая для итерации элементов коллекции.|  
|`type`|Необязательный. Тип параметра `element`. Если тип не указан, тип `element` выводится из `collection`.|  
|`collection`|Обязательно. Ссылается на коллекцию для работы.|  
|`clause`|Необязательный. Один или несколько запросов предложений, например `Where` предложение для уточнения результатов запроса, применяется предложение aggregate или предложения.|  
|`expressionList`|Обязательно. Один или несколько разделенных запятыми выражения, определяющие агрегатную функцию, применяемую к коллекции. Можно применить псевдоним агрегатной функции, чтобы указать имя члена для результата запроса. Если псевдоним не указан, используется имя агрегатной функции. Примеры см. в разделе агрегатных функций далее в этом разделе.|  
  
## <a name="remarks"></a>Примечания  
 `Aggregate` Предложение может использоваться для включения агрегатных функций в запросах. Агрегатные функции выполняют проверку и вычисление по набору значений и возвращают одиночное значение. Вычисляемое значение доступны с помощью члена типа результата запроса. Стандартные статистические функции, которые можно использовать, `All`, `Any`, `Average`, `Count`, `LongCount`, `Max`, `Min`, и `Sum` функции. Эти функции являются знакомый разработчикам, знакомым с статистических функций в SQL. Они описаны в следующем разделе этой статьи.  
  
 Результат агрегатной функции включается в результат запроса в виде поля типа результата запроса. Можно указать псевдоним для результатов агрегатной функции, чтобы указать имя члена типа результата запроса, который будет содержать значение статистического выражения. Если псевдоним не указан, используется имя агрегатной функции.  
  
 `Aggregate` Предложения можно начать запрос, или он может быть включено как дополнительное предложение в запросе. Если `Aggregate` в начале предложения запроса, в результате одно значение, являющееся результатом агрегатной функции, заданной в `Into` предложения. Если указано несколько агрегатных функций в `Into` предложение, запрос возвращает отдельный тип с отдельные свойства, ссылающиеся на результат каждой статистической функции `Into` предложения. Если `Aggregate` предложение включено как дополнительное предложение в запросе, тип возвращаемой коллекции запроса будет иметь отдельные свойства, ссылающиеся на результат каждой статистической функции `Into` предложения.  
  
## <a name="aggregate-functions"></a>Статистические функции  
 Ниже перечислены стандартные агрегатные функции, которые могут использоваться с `Aggregate` предложения.  
  
|Функция|Описание|  
|---|---|  
|`All`|Возвращает `true` все ли элементы в коллекции удовлетворяют указанному условию; в противном случае возвращает `false`. Ниже представлен пример.<br /><br /> [!code-vb[VbSimpleQuerySamples#5](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_1.vb)]|  
|`Any`|Возвращает `true` , если любой элемент в коллекции удовлетворяет указанному условию; в противном случае возвращает `false`. Ниже представлен пример.<br /><br /> [!code-vb[VbSimpleQuerySamples#6](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_2.vb)]|  
|`Average`|Вычисляет среднее значение всех элементов в коллекции или указанное выражение для всех элементов в коллекции. Ниже представлен пример.<br /><br /> [!code-vb[VbSimpleQuerySamples#7](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_3.vb)]|  
|`Count`|Подсчитывает количество элементов в коллекции. Можно указать необязательное `Boolean` выражение для подсчета числа элементов в коллекции, которые удовлетворяют условию. Ниже представлен пример.<br /><br /> [!code-vb[VbSimpleQuerySamples#8](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_4.vb)]|  
|`Group`|Ссылается на результаты запроса, сгруппированные в результате использования `Group By` или `Group Join` предложения. `Group` Функция допустима только в `Into` предложения `Group By` или `Group Join` предложения. Дополнительные сведения и примеры см. в разделе [предложение Group](../../../visual-basic/language-reference/queries/group-by-clause.md) и [предложения Join группы](../../../visual-basic/language-reference/queries/group-join-clause.md).|  
|`LongCount`|Подсчитывает количество элементов в коллекции. Можно указать необязательное `Boolean` выражение для подсчета числа элементов в коллекции, которые удовлетворяют условию. Возвращает результат в виде `Long`. Пример см. в разделе `Count` агрегатной функции.|  
|`Max`|Вычисляет максимальное значение из коллекции или указанное выражение для всех элементов в коллекции. Ниже представлен пример.<br /><br /> [!code-vb[VbSimpleQuerySamples#9](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_5.vb)]|  
|`Min`|Вычисляет минимальное значение из коллекции или указанное выражение для всех элементов в коллекции. Ниже представлен пример.<br /><br /> [!code-vb[VbSimpleQuerySamples#10](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_6.vb)]|  
|`Sum`|Вычисляет сумму всех элементов в коллекции или указанное выражение для всех элементов в коллекции. Ниже представлен пример.<br /><br /> [!code-vb[VbSimpleQuerySamples#15](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_7.vb)]|  
  
## <a name="example"></a>Пример  
 В следующем примере кода показано, как использовать `Aggregate` предложение для применения статистических функций к результатам запроса.  
  
 [!code-vb[VbSimpleQuerySamples#4](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_8.vb)]  
  
## <a name="creating-user-defined-aggregate-functions"></a>Создание определяемых пользователем агрегатных функций  
 Можно включить пользовательские агрегатные функции в выражении запроса путем добавления методов расширения <xref:System.Collections.Generic.IEnumerable%601> типа. Пользовательский метод может выполнить расчет или операцию на перечисление коллекции, на которую есть ссылки в агрегатной функции. Дополнительные сведения о методах расширения см. в разделе [Методы расширения](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md).  
  
 Например в следующем примере кода показано пользовательской агрегатной функции, которая вычисляет значение медианы из коллекции чисел. Существуют две перегрузки `Median` метода расширения. Первая перегрузка принимает в качестве входных данных, коллекцию типа `IEnumerable(Of Double)`. Если `Median` Агрегатная функция вызывается для поля типа `Double`, этот метод будет вызываться. Вторая перегрузка `Median` метод может быть передан любого универсального типа. Универсальную перегрузку `Median` метод принимает параметр, который ссылается на `Func(Of T, Double)` лямбда-выражения для проецирования значение для типа (из коллекции) как значение соответствующего типа `Double`. Затем он делегирует расчет значения медианы другой перегрузке `Median` метод. Дополнительные сведения о лямбда-выражениях см. в разделе [Лямбда-выражения](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
 [!code-vb[VbSimpleQuerySamples#18](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_9.vb)]  
  
 В следующем примере показана образец запросы, вызывающие кода `Median` агрегатную функцию в коллекцию типа `Integer`и Коллекция типа `Double`. Запрос, который вызывает `Median` агрегатной функции в коллекции с типом `Double` вызывает перегрузку `Median` метода, который принимает в качестве входных данных, коллекцию типа `Double`. Запрос, который вызывает `Median` агрегатной функции в коллекции с типом `Integer` вызывает универсальную перегрузку `Median` метод.  
  
 [!code-vb[VbSimpleQuerySamples#19](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_10.vb)]  
  
## <a name="see-also"></a>См. также  
 [Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)  
 [Запросы](../../../visual-basic/language-reference/queries/queries.md)  
 [Предложение Select](../../../visual-basic/language-reference/queries/select-clause.md)  
 [Предложение From](../../../visual-basic/language-reference/queries/from-clause.md)  
 [Предложения Where](../../../visual-basic/language-reference/queries/where-clause.md)  
 [Предложение Group By](../../../visual-basic/language-reference/queries/group-by-clause.md)
