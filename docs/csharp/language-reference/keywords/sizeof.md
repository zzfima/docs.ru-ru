---
title: sizeof. Справочник по C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- sizeof_CSharpKeyword
- sizeof
helpviewer_keywords:
- sizeof keyword [C#]
ms.assetid: c548592c-677c-4f40-a4ce-e613f7529141
ms.openlocfilehash: 1c5526366651d7e6623724c939b08ac46aa7db56
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53242637"
---
# <a name="sizeof-c-reference"></a>sizeof (Справочник по C#)

Позволяет получить размер в байтах для неуправляемого типа.

К неуправляемым типам относятся:

- Простые типы, которые перечислены в следующей таблице:

   |Выражение|Константа|
   |----------------|--------------------|
   |`sizeof(sbyte)`|1|
   |`sizeof(byte)`|1|
   |`sizeof(short)`|2|
   |`sizeof(ushort)`|2|
   |`sizeof(int)`|4|
   |`sizeof(uint)`|4|
   |`sizeof(long)`|8|
   |`sizeof(ulong)`|8|
   |`sizeof(char)`|2 (Юникод)|
   |`sizeof(float)`|4|
   |`sizeof(double)`|8|
   |`sizeof(decimal)`|16|
   |`sizeof(bool)`|1|

- Типы перечисления.

- Типы указателей.

- Определяемые пользователем структуры, которые не содержат полей экземпляров или автоматически реализуемых свойств, являющихся ссылочными или сконструированными типами.

В приведенном ниже примере показано, как извлекать размер переменной типа `int`.

```csharp
// Constant value 4:
int intSize = sizeof(int);
```

## <a name="remarks"></a>Примечания

Начиная с версии 2.0 языка C# применение `sizeof` к простым типам или типам перечисления больше не требует компиляции кода в [небезопасном](unsafe.md) контексте.

Оператор `sizeof` перегрузить нельзя. Возвращаемые оператором `sizeof` значения принадлежат типу `int`. В предыдущей таблице показаны константы, которые заменяются выражениями `sizeof`, содержащими некоторые операнды простых типов.

Для всех остальных типов, в том числе для структур, оператор `sizeof` можно использовать только в блоках небезопасного кода. Несмотря на то, что вы можете использовать метод <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType>, возвращаемое им значение не всегда совпадает со значением, которое возвращает метод `sizeof`. Метод <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> возвращает размер после маршалинга типа, тогда как оператор `sizeof` возвращает размер сразу после выделения памяти средой CLR, включая заполнения.

## <a name="example"></a>Пример

[!code-csharp[csrefKeywordsOperator#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#11)]

## <a name="c-language-specification"></a>Спецификация языка C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Ключевые слова в C#](index.md)
- [Ключевые слова операторов](operator-keywords.md)
- [enum](enum.md)
- [Небезопасный код и указатели](../../programming-guide/unsafe-code-pointers/index.md)
- [Структуры](../../programming-guide/classes-and-structs/structs.md)
- [Константы](../../programming-guide/classes-and-structs/constants.md)