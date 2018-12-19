---
title: typeof. Справочник по C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- typeof
- typeof_CSharpKeyword
helpviewer_keywords:
- typeof keyword [C#]
ms.assetid: 0c08d880-515e-46bb-8cd2-48b8dd62c08d
ms.openlocfilehash: 3fa82a6faee345be77fc8ea3f5aa3342adecb0f5
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53244847"
---
# <a name="typeof-c-reference"></a>typeof (справочник по C#)

Позволяет получить объект <xref:System.Type?displayProperty=nameWithType> для типа. Выражение `typeof` принимает следующую форму:

```csharp
System.Type type = typeof(int);
```

## <a name="remarks"></a>Примечания

Получить тип среды выполнения для выражения можно с помощью метода .NET Framework <xref:System.Object.GetType%2A>, как показано в следующем примере:

```csharp
int i = 0;
System.Type type = i.GetType();
```

Оператор `typeof` перегрузить нельзя.

Оператор `typeof` можно также применять к открытым универсальным типам. Типы более чем с одним параметром типа должны иметь соответствующее количество запятых в спецификации. В приведенном ниже примере показано, как определить, является ли тип возвращаемого значения метода универсальным <xref:System.Collections.Generic.IEnumerable%601>. <xref:System.Type.GetInterface%2A?displayProperty=nameWithType> возвращает `null`, если тип возвращаемого значения не является универсальным типом <xref:System.Collections.Generic.IEnumerable%601>.

[!code-csharp[typeof_3.cs](~/samples/snippets/csharp/keywords/typeof/typeof_3.cs)]

## <a name="example"></a>Пример

[!code-csharp[csrefKeywordsOperator#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#12)] 

## <a name="example"></a>Пример

В этом примере метод <xref:System.Object.GetType%2A> используется для определения типа, который служит для хранения результатов числового вычисления. Он зависит от требований к хранилищу для полученного числа.

[!code-csharp[csrefKeywordsOperator#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#13)]

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в разделе [Оператор typeof](~/_csharplang/spec/expressions.md#the-typeof-operator) в [Спецификации языка C#](../language-specification/index.md). Спецификация языка является предписывающим источником информации о синтаксисе и использовании языка C#.

## <a name="see-also"></a>См. также

- <xref:System.Type?displayProperty=nameWithType>
- [Справочник по C#](../../../csharp/language-reference/index.md)
- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)
- [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)
- [is](../../../csharp/language-reference/keywords/is.md)
- [Ключевые слова операторов](../../../csharp/language-reference/keywords/operator-keywords.md)