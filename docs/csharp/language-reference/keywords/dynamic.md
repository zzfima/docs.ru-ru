---
title: dynamic (Справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- dynamic_CSharpKeyword
helpviewer_keywords:
- dynamic [C#]
- dynamic keyword [C#]
ms.assetid: 9e797102-cc83-4964-bf58-afe4f54d16bc
ms.openlocfilehash: bddcb8890ef7312047d05794ccef0b638de4ed78
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2018
ms.locfileid: "43484019"
---
# <a name="dynamic-c-reference"></a>dynamic (Справочник по C#)

Тип `dynamic` включает операции, в которых он применяется для обхода проверки типов во время компиляции. Такие операции разрешаются во время выполнения. Тип `dynamic` упрощает доступ к API COM, таким как API автоматизации Office, а также к динамическим API, таким как библиотеки IronPython, и к HTML-модели DOM.

Тип `dynamic` в большинстве случаев ведет себя как тип `object`. При этом операции, содержащие выражения типа `dynamic`, не разрешаются или тип проверяется компилятором. Компилятор объединяет сведения об операции, которые впоследствии будут использоваться для оценки этой операции во время выполнения. В рамках этого процесса переменные типа `dynamic` компилируются в переменные типа `object`. Таким образом, тип `dynamic` существует только во время компиляции, но не во время выполнения.

В следующем примере переменной типа `dynamic` противопоставляется переменная типа `object`. Чтобы проверить тип каждой переменной во время компиляции, наведите указатель мыши на `dyn` или `obj` в операторах `WriteLine`. IntelliSense отображает **dynamic** для `dyn` и **object** для `obj`.

[!code-csharp[csrefKeywordsTypes#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/dynamic1.cs#21)]

Операторы `WriteLine` отображают типы времени выполнения `dyn` и `obj`. На этом этапе оба имеют один и тот же тип — целое число. Выводятся следующие результаты.

`System.Int32`

`System.Int32`

Чтобы увидеть разницу между `dyn` и `obj` во время компиляции, добавьте между объявлениями и операторами `WriteLine` в предыдущем примере следующие две строки:

```csharp
dyn = dyn + 3;
obj = obj + 3;
```

 При попытке добавления целого числа и объекта в выражение `obj + 3` выдается ошибка компилятора. При этом для `dyn + 3` ошибка не возникает. Выражение, которое содержит `dyn`, не проверяется во время компиляции, поскольку тип `dyn` имеет значение `dynamic`.

## <a name="context"></a>Контекст

В следующих ситуациях ключевое слово `dynamic` может отображаться как есть или как компонент сконструированного типа:

- В объявлениях: как тип свойства, поля, индексатора, параметра возвращаемого значения, локальной переменной или ограничения типа. В представленном ниже определении класса ключевое слово `dynamic` используется сразу в нескольких различных объявлениях.

    [!code-csharp[csrefKeywordsTypes#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/dynamic1.cs#22)]

- В явных преобразованиях типа: как целевой тип преобразования.

    [!code-csharp[csrefKeywordsTypes#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/dynamic1.cs#23)]

- В любом контексте, где типы служат в качестве значений, например справа от оператора `is` или `as`, либо в качестве аргумента для `typeof` в рамках сконструированного типа. Например, ключевое слово `dynamic` можно использовать в следующих выражениях:

    [!code-csharp[csrefKeywordsTypes#24](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/dynamic1.cs#24)]

## <a name="example"></a>Пример

В следующем примере `dynamic` используется в нескольких объявлениях. Метод `Main` также противопоставляет проверку типов во время компиляции.

[!code-csharp[csrefKeywordsTypes#25](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/dynamic2.cs#25)]

Дополнительные сведения и примеры см. в разделе [Использование типа dynamic](../../../csharp/programming-guide/types/using-type-dynamic.md).

## <a name="see-also"></a>См. также

- <xref:System.Dynamic.ExpandoObject?displayProperty=nameWithType>  
- <xref:System.Dynamic.DynamicObject?displayProperty=nameWithType>  
- [Использование типа dynamic](../../../csharp/programming-guide/types/using-type-dynamic.md)  
- [object](../../../csharp/language-reference/keywords/object.md)  
- [is](../../../csharp/language-reference/keywords/is.md)  
- [as](../../../csharp/language-reference/keywords/as.md)  
- [typeof](../../../csharp/language-reference/keywords/typeof.md)  
- [Практическое руководство. Безопасное приведение с помощью операторов as и is](../../../csharp/programming-guide/types/how-to-safely-cast-by-using-as-and-is-operators.md)  
- [Пошаговое руководство. Создание и использование динамических объектов](../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)
