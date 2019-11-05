---
title: Предложение where. Справочник по C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- whereclause_CSharpKeyword
helpviewer_keywords:
- where keyword [C#]
- where clause [C#]
ms.assetid: 7f9bf952-7744-4f91-b676-cddb55d107c3
ms.openlocfilehash: 15df6339cec9eabadf5aa4c184d7504c4e065032
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2019
ms.locfileid: "73421935"
---
# <a name="where-clause-c-reference"></a>Предложение where (Справочник по C#)

Предложение `where` используется в выражении запроса для того, чтобы указать, какие элементы из источника данных будут возвращаться в выражении запроса. Оно применяет логическое условие (*предикат*) к каждому исходному элементу (на который ссылается переменная диапазона) и возвращает те из них, для которых указанное условие имеет значение true. Одно выражение запроса может содержать сразу несколько предложений `where`, а одно предложение — несколько частей выражения предиката.

## <a name="example"></a>Пример

В следующем примере предложение `where` отфильтровывает все номера, кроме тех, которые меньше пяти. Если удалить предложение `where`, возвращаются все номера из источника данных. Выражение `num < 5` является предикатом, который применяется к каждому элементу.

[!code-csharp[cscsrefQueryKeywords#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Where.cs#5)]

## <a name="example"></a>Пример

В одном предложении `where` можно указать необходимое число предикатов, используя операторы [&&](../operators/boolean-logical-operators.md#conditional-logical-and-operator-) и [&#124;&#124;](../operators/boolean-logical-operators.md#conditional-logical-or-operator-). В следующем примере запрос определяет два предиката, позволяющие отобрать только четные номера меньше пяти.

[!code-csharp[cscsrefQueryKeywords#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Where.cs#6)]  

## <a name="example"></a>Пример

Предложение `where` может содержать один или несколько методов, возвращающих логические значения. В следующем примере предложение `where` использует метод для того, чтобы определить, является ли текущее значение диапазона четным или нечетным.

[!code-csharp[cscsrefQueryKeywords#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Where.cs#7)]

## <a name="remarks"></a>Примечания

Предложение `where` представляет собой механизм фильтрации. Он может располагаться практически в любом месте выражения запроса, но не может быть первым или последним предложением. Предложение `where` может отображаться до или после предложения [group](group-clause.md) в зависимости от того, необходимо ли отфильтровать исходные элементы до или после их объединения в группы.

Если указанный предикат недопустим для элементов в источнике данных, это вызовет ошибку компиляции. Это одно из преимуществ надежной проверки типов, предоставляемой [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)].

Во время компиляции ключевое слово `where` преобразуется в вызов метода стандартного оператора запроса <xref:System.Linq.Enumerable.Where%2A>.

## <a name="see-also"></a>См. также

- [Ключевые слова запроса (LINQ)](query-keywords.md)
- [предложение from](from-clause.md)
- [предложение select](select-clause.md)
- [Фильтрация данных](../../programming-guide/concepts/linq/filtering-data.md)
- [LINQ в C#](../../linq/index.md)
- [Приступая к работе с LINQ в C#](/dotnet/csharp/programming-guide/concepts/linq/)
