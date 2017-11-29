---
title: "Предложение group (Справочник по C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- group
- group_CSharpKeyword
helpviewer_keywords:
- group keyword [C#]
- group clause [C#]
ms.assetid: c817242e-b12c-4baa-a57e-73ee138f34d1
caps.latest.revision: "24"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: a2f67b2c90e1cced92d6fc7d47768b58bf155360
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="group-clause-c-reference"></a>Предложение group (Справочник по C#)
Предложение `group` возвращает последовательность объектов <xref:System.Linq.IGrouping%602>, содержащих нуль или более элементов, соответствующих значению ключа группы. Например, можно сгруппировать последовательность строк в соответствии с первой буквой в каждой строке. В этом случае первая буква является ключом и имеет тип [char](../../../csharp/language-reference/keywords/char.md). Она хранится в свойстве `Key` каждого объекта <xref:System.Linq.IGrouping%602>. Тип ключа определяется компилятором.  
  
 Завершить выражение запроса с предложением `group` можно следующим образом:  
  
 [!code-csharp[cscsrefQueryKeywords#10](../../../csharp/language-reference/keywords/codesnippet/CSharp/group-clause_1.cs)]  
  
 Чтобы выполнить дополнительные запросы для каждой из групп, можно указать временный идентификатор, воспользовавшись для этого контекстным ключевым словом [into](../../../csharp/language-reference/keywords/into.md). При использовании ключевого слова `into` необходимо продолжить запрос и завершить его инструкцией `select` или другим предложением `group`, как показано в следующем фрагменте:  
  
 [!code-csharp[cscsrefQueryKeywords#11](../../../csharp/language-reference/keywords/codesnippet/CSharp/group-clause_2.cs)]  
  
 Более подробные примеры использования предложения `group` с ключевым словом `into` и без него см. в подразделе "Пример" этого раздела.  
  
## <a name="enumerating-the-results-of-a-group-query"></a>Перечисление результатов запроса group  
 Так как возвращаемые запросом `group` объекты <xref:System.Linq.IGrouping%602> представляют собой список списков, для доступа к каждому из элементов этих групп необходимо использовать вложенный цикл [foreach](../../../csharp/language-reference/keywords/foreach-in.md). Во внешнем цикле итерация будет выполняться по ключам групп, а во внутреннем цикле — по элементам самих групп. У группы может быть ключ, но не быть элементов. Ниже приведен пример цикла `foreach`, который выполняет запрос, показанный в предыдущих примерах кода:  
  
 [!code-csharp[cscsrefQueryKeywords#12](../../../csharp/language-reference/keywords/codesnippet/CSharp/group-clause_3.cs)]  
  
## <a name="key-types"></a>Типы ключей  
 Ключи групп могут быть любого типа, например строкового, встроенного числового, пользовательского именованного или анонимного типа.  
  
### <a name="grouping-by-string"></a>Группировка по строке  
 В предыдущих примерах кода использовался ключ типа `char`. Вместо него можно было указать строку, например фамилию:  
  
 [!code-csharp[cscsrefQueryKeywords#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/group-clause_4.cs)]  
  
### <a name="grouping-by-bool"></a>Группировка по логическому значению  
 В следующем примере показано разбиение результатов на две группы в зависимости от значения логического ключа. Обратите внимание, что значение формируется с помощью входящего в состав предложения `group` выражения.  
  
 [!code-csharp[cscsrefQueryKeywords#14](../../../csharp/language-reference/keywords/codesnippet/CSharp/group-clause_5.cs)]  
  
### <a name="grouping-by-numeric-range"></a>Группировка по числовому диапазону  
 В следующем примере с помощью выражения создаются числовые ключи групп, обозначающие диапазоны значений в выборке. Обратите внимание на удобное использование [let](../../../csharp/language-reference/keywords/let-clause.md) для хранения результатов вызова метода, чтобы в предложении `group` не приходилось вызывать метод дважды. Также обратите внимание, что в предложении `group` выполняется проверка того, что средний бал студента не равен нулю, чтобы не возникала ситуация деления на нуль. Дополнительные сведения о безопасном использовании методов в выражениях запросов см. в разделе [Практическое руководство. Обработка исключений в выражениях запросов](../../../csharp/programming-guide/linq-query-expressions/how-to-handle-exceptions-in-query-expressions.md).  
  
 [!code-csharp[cscsrefQueryKeywords#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/group-clause_6.cs)]  
  
### <a name="grouping-by-composite-keys"></a>Группировка по составному ключу  
 Составные ключи используются в тех случаях, когда необходимо сгруппировать элементы по более чем одному ключу. Составной ключ создается с помощью анонимного типа или именованного типа для хранения элементов ключа. В следующем примере предполагается, что для класса `Person` были объявлены члены `surname` и `city`. Предложение `group` позволяет создать отдельную группу для каждого набора людей, имеющих одинаковые фамилии и города.  
  
```csharp  
group person by new {name = person.surname, city = person.city};  
```  
  
 Если требуется передать переменную запроса другому методу, следует использовать именованные типы. Создайте особый класс, используя автоматически реализуемые свойства для ключей, а затем переопределите методы <xref:System.Object.Equals%2A> и <xref:System.Object.GetHashCode%2A>. Можно также воспользоваться структурой, чтобы избежать необходимости переопределять эти методы. Дополнительные сведения см. в разделах [Практическое руководство. Реализация облегченного класса с автоматически реализуемыми свойствами](../../../csharp/programming-guide/classes-and-structs/how-to-implement-a-lightweight-class-with-auto-implemented-properties.md) и [Практическое руководство. Запрос повторяющихся файлов в дереве каталогов](../../programming-guide/concepts/linq/how-to-query-for-duplicate-files-in-a-directory-tree-linq.md). В последнем разделе имеется пример кода, демонстрирующий использование составных ключей с именованным типом.  
  
## <a name="example"></a>Пример  
 В следующем примере показан стандартный шаблон для разбиения данных на группы без применения к группам дополнительной логики запроса. Такой прием называется группировкой без продолжения. Элементы массива строк группируются в соответствии со своими первыми буквами. Результатом запроса является тип <xref:System.Linq.IGrouping%602>, который содержит открытое свойство `Key` типа `char` и коллекцию <xref:System.Collections.Generic.IEnumerable%601>, содержащую каждый элемент в группе.  
  
 Результатом выполнения предложения `group` является последовательность из последовательностей. Таким образом, для доступа к отдельным элементам каждой из полученных групп следует использовать вложенный цикл `foreach`, в котором итерация выполняется по ключам групп, как показано в следующем примере.  
  
 [!code-csharp[cscsrefQueryKeywords#16](../../../csharp/language-reference/keywords/codesnippet/CSharp/group-clause_7.cs)]  
  
## <a name="example"></a>Пример  
 В этом примере показано выполнение дополнительных операций над группами после их создания. Для этого используется *continuation* с `into`. Дополнительные сведения см. в разделе [into](../../../csharp/language-reference/keywords/into.md). В следующем примере создается запрос, выбирающий только те группы, элементы которых начинаются на гласную.  
  
 [!code-csharp[cscsrefQueryKeywords#17](../../../csharp/language-reference/keywords/codesnippet/CSharp/group-clause_8.cs)]  
  
## <a name="remarks"></a>Примечания  
 Во время компиляции предложения `group` преобразуются в вызовы метода <xref:System.Linq.Enumerable.GroupBy%2A>.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Linq.IGrouping%602>  
 <xref:System.Linq.Enumerable.GroupBy%2A>  
 <xref:System.Linq.Enumerable.ThenBy%2A>  
 <xref:System.Linq.Enumerable.ThenByDescending%2A>  
 [Ключевые слова запроса (LINQ)](../../../csharp/language-reference/keywords/query-keywords.md)  
 [Выражения запросов LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)  
 [Практическое руководство. Создание вложенной группы](../../../csharp/programming-guide/linq-query-expressions/how-to-create-a-nested-group.md)  
 [Практическое руководство. Группировка результатов запросов](../../../csharp/programming-guide/linq-query-expressions/how-to-group-query-results.md)  
 [Практическое руководство. Вложенный запрос в операции группирования](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-a-subquery-on-a-grouping-operation.md)
