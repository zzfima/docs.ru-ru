---
title: "Предложение where (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- whereclause_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- where keyword [C#]
- where clause [C#]
ms.assetid: 7f9bf952-7744-4f91-b676-cddb55d107c3
caps.latest.revision: 16
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 97d7c16d6bf8048e621141fff52a47907881fd2f
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="where-clause-c-reference"></a>Предложение where (Справочник по C#)
Предложение `where` используется в выражении запроса для того, чтобы указать, какие элементы из источника данных будут возвращаться в выражении запроса. Оно применяет логическое условие (*предикат*) к каждому исходному элементу (на который ссылается переменная диапазона) и возвращает те из них, для которых указанное условие имеет значение true. Одно выражение запроса может содержать сразу несколько предложений `where`, а одно предложение — несколько частей выражения предиката.  
  
## <a name="example"></a>Пример  
 В следующем примере предложение `where` отфильтровывает все номера, кроме тех, которые меньше пяти. Если удалить предложение `where`, возвращаются все номера из источника данных. Выражение `num < 5` является предикатом, который применяется к каждому элементу.  
  
 [!code-cs[cscsrefQueryKeywords#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-clause_1.cs)]  
  
## <a name="example"></a>Пример  
 В одном предложении `where` можно указать необходимое число предикатов, используя операторы [&&](../../../csharp/language-reference/operators/conditional-and-operator.md) и [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md). В следующем примере запрос определяет два предиката, позволяющие отобрать только четные номера меньше пяти.  
  
 [!code-cs[cscsrefQueryKeywords#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-clause_2.cs)]  
  
## <a name="example"></a>Пример  
 Предложение `where` может содержать один или несколько методов, возвращающих логические значения. В следующем примере предложение `where` использует метод для того, чтобы определить, является ли текущее значение диапазона четным или нечетным.  
  
 [!code-cs[cscsrefQueryKeywords#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-clause_3.cs)]  
  
## <a name="remarks"></a>Примечания  
 Предложение `where` представляет собой механизм фильтрации. Он может располагаться практически в любом месте выражения запроса, но не может быть первым или последним предложением. Предложение `where` может отображаться до или после предложения [group](../../../csharp/language-reference/keywords/group-clause.md) в зависимости от того, необходимо ли отфильтровать исходные элементы до или после их объединения в группы.  
  
 Если указанный предикат недопустим для элементов в источнике данных, это вызовет ошибку компиляции. Это одно из преимуществ надежной проверки типов, предоставляемой [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)].  
  
 Во время компиляции ключевое слово `where` преобразуется в вызов метода стандартного оператора запроса <xref:System.Linq.Enumerable.Where%2A>.  
  
## <a name="see-also"></a>См. также  
 [Ключевые слова запроса (LINQ)](../../../csharp/language-reference/keywords/query-keywords.md)   
 [Предложение From](../../../csharp/language-reference/keywords/from-clause.md)   
 [Предложение Select](../../../csharp/language-reference/keywords/select-clause.md)   
 [Фильтрация данных](http://msdn.microsoft.com/library/cee88d0f-31aa-4c60-9452-cc122ed0057d)   
 [Выражения запросов LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [Приступая к работе с LINQ в C#](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)

