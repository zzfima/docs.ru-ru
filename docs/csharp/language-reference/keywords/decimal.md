---
title: Ключевое слово decimal (справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- decimal_CSharpKeyword
- decimal
helpviewer_keywords:
- decimal keyword [C#]
ms.assetid: b6522132-b5ee-4be3-ad13-3adfdb7de7a1
ms.openlocfilehash: c9d40238ca4c34238d5663185f93afbce73195cf
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43506523"
---
# <a name="decimal-c-reference"></a>decimal (Справочник по C#)

Ключевое слово `decimal` обозначает 128-разрядный тип данных. По сравнению с другими типами данных с плавающей запятой, диапазон значений `decimal` меньше, а точность выше, благодаря чему этот тип подходит для финансовых расчетов. В следующей таблице представлен приблизительный диапазон значений и точность для типа `decimal`.

|Тип|Приблизительный диапазон значений|Точность|Тип .NET|
|----------|-----------------------|---------------|-------------------------|
|`decimal`|от ±1,0 x 10<sup>-28</sup> до ±7,9228 x 10<sup>28</sup>|28–29 значащих цифр|<xref:System.Decimal?displayProperty=nameWithType>|

Значением переменной `decimal` по умолчанию является 0m.

## <a name="literals"></a>Литералы

Если требуется, чтобы числовой действительный литерал рассматривался как `decimal`, следует использовать суффикс m или M, например:

```csharp
decimal myMoney = 300.5m;
```

Если суффикс m отсутствует, число рассматривается как [double](../../../csharp/language-reference/keywords/double.md) и возникает ошибка компилятора.

## <a name="conversions"></a>Преобразования

Целочисленные типы неявно преобразуются в тип `decimal` и результатом является тип `decimal`. Поэтому инициализацию десятичной переменной можно выполнить с помощью целочисленного литерала без суффикса следующим образом:

```csharp
decimal myMoney = 300;
```

Неявное преобразование между другими типами с плавающей запятой и типом `decimal` отсутствует, поэтому для преобразования между этими двумя типами следует использовать приведение. Пример:

```csharp
decimal myMoney = 99.9m;
double x = (double)myMoney;
myMoney = (decimal)x;
```

Тип `decimal` можно использовать в одном выражении вместе с целочисленными типами числовых данных. Однако использование типа `decimal` вместе с другими типами с плавающей запятой без приведения вызовет ошибку компиляции.

Дополнительные сведения о неявных числовых преобразованиях см. в разделе [Таблица неявных числовых преобразований](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).

Дополнительные сведения о явных числовых преобразованиях см. в разделе [Таблица явных числовых преобразований](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md).

## <a name="formatting-decimal-output"></a>Форматирование десятичных выходных данных

Для форматирования результатов можно воспользоваться методом `String.Format` или методом <xref:System.Console.Write%2A?displayProperty=nameWithType>, вызывающим метод `String.Format()`. Формат денежных единиц задается с помощью стандартной строки формата денежных единиц "C" или "c", как показано во втором примере далее в данной статье. Дополнительные сведения о методе `String.Format` см. в разделе <xref:System.String.Format%2A?displayProperty=nameWithType>.

## <a name="example"></a>Пример

В приведенном ниже примере возникает ошибка компилятора при попытке сложить переменные типов [double](../../../csharp/language-reference/keywords/double.md) и `decimal`.

```csharp
decimal dec = 0m;
double dub = 9;
// The following line causes an error that reads "Operator '+' cannot be applied to
// operands of type 'double' and 'decimal'"
Console.WriteLine(dec + dub);

// You can fix the error by using explicit casting of either operand.
Console.WriteLine(dec + (decimal)dub);
Console.WriteLine((double)dec + dub);
```

В результате выводится следующее сообщение об ошибке:

`Operator '+' cannot be applied to operands of type 'double' and 'decimal'`

В приведенном ниже примере в одном выражении используются переменные типов `decimal` и [int](../../../csharp/language-reference/keywords/int.md). В результате возвращается тип `decimal`.

[!code-csharp[csrefKeywordsTypes#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#6)]

## <a name="example"></a>Пример

В следующем примере для форматирования выходных данных используется строка формата денежных единиц. Обратите внимание на округление переменной `x`, поскольку десятичные разряды превышают 0,99 долл. США. Переменная `y`, представляющая максимально точные цифры, отображается в правильном формате.

[!code-csharp[csrefKeywordsTypes#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#7)]

## <a name="c-language-specification"></a>Спецификация языка C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>См. также

- <xref:System.Decimal>  
- [Справочник по C#](../../../csharp/language-reference/index.md)  
- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
- [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)  
- [Таблица целых типов](../../../csharp/language-reference/keywords/integral-types-table.md)  
- [Таблица встроенных типов](../../../csharp/language-reference/keywords/built-in-types-table.md)  
- [Таблица неявных числовых преобразований](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
- [Таблица явных числовых преобразований](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)  
- [Строки стандартных числовых форматов](../../../standard/base-types/standard-numeric-format-strings.md)