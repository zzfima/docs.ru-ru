---
title: Ключевое слово const (справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- const_CSharpKeyword
- const
helpviewer_keywords:
- const keyword [C#]
ms.assetid: 79eb447c-117b-4418-933f-97c50aa472db
ms.openlocfilehash: f586b6d097a8592fd74e92df7886b519d623e478
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2018
ms.locfileid: "43393009"
---
# <a name="const-c-reference"></a>const (Справочник по C#)

Для объявления константного поля или константной локальной используется ключевое слово `const`. Константные поля и локальные не являются переменными и не могут быть изменены. Константы могут быть числами, логическими значениями, строками или нулевыми ссылками. Не создавайте константу для предоставления сведений, которые могут измениться в любое время. Например, не используйте константное поле для хранения цены услуги, номера версии продукта или торгового названия компании. Эти значения могут со временем измениться, а поскольку константы распространяются компиляторами, для отражения изменений потребуется повторная компиляция остальных кодов, скомпилированных с использованием ваших библиотек. См. также описание ключевого слова [readonly](../../../csharp/language-reference/keywords/readonly.md). Пример:

```csharp
const int x = 0;
public const double gravitationalConstant = 6.673e-11;
private const string productName = "Visual C#";
```

## <a name="remarks"></a>Примечания

Тип объявления константы указывает на тип членов, которые вводятся объявлением. Инициализатор локальной константы или константного поля должен быть выражением константы, поддерживающим неявное преобразование в конечный тип.

Выражение константы — это выражение, которое можно полностью вычислить во время компиляции. Таким образом, единственно возможными значениями для констант типов ссылок являются `string` и нулевые ссылки.

Объявление константы может объявлять несколько констант, например:

```csharp
public const double x = 1.0, y = 2.0, z = 3.0;
```

Модификатор `static` в объявлении константы не допускается.

Константа может участвовать в выражении константы следующим образом:

```csharp
public const int c1 = 5;
public const int c2 = c1 + 100;
```

> [!NOTE]
> Ключевое слово [readonly](../../../csharp/language-reference/keywords/readonly.md) отличается от ключевого слова `const`. Поле `const` может быть инициализировано только при объявлении поля. Поле `readonly` может быть инициализировано при объявлении или в конструкторе. Таким образом, поля `readonly` могут иметь разные значения в зависимости от использованного конструктора. Также, несмотря на то, что поле `const` является константой во время компиляции, поле `readonly` можно использовать для констант во время выполнения, как в следующей строке: `public static readonly uint l1 = (uint)DateTime.Now.Ticks;`

## <a name="example"></a>Пример

[!code-csharp[csrefKeywordsModifiers#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#5)]

## <a name="example"></a>Пример

В этом примере показан способ использования констант в качестве локальных переменных.

[!code-csharp[csrefKeywordsModifiers#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#6)]

## <a name="c-language-specification"></a>Спецификация языка C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>См. также

- [Справочник по C#](../../../csharp/language-reference/index.md)  
- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
- [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)  
- [Модификаторы](../../../csharp/language-reference/keywords/modifiers.md)  
- [readonly](../../../csharp/language-reference/keywords/readonly.md)
