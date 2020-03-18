---
title: Модификатор static. Справочник по C#
ms.date: 01/22/2020
f1_keywords:
- static
- static_CSharpKeyword
helpviewer_keywords:
- static keyword [C#]
ms.assetid: 5509e215-2183-4da3-bab4-6b7e607a4fdf
ms.openlocfilehash: e7671e9db488a7b50f4ed736864d6fa8d95eef1a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "76744661"
---
# <a name="static-c-reference"></a>static (Справочник по C#)

Модификатор `static` используется для объявления статического члена, принадлежащего собственно типу, а не конкретному объекту. Модификатор `static` можно использовать для объявления классов `static`. В классах, интерфейсах и структурах вы можете добавить модификатор `static` к полям, методам, свойствам, операторам, событиям и конструкторам. Модификатор `static` запрещено использовать с индексаторами или методами завершения. Дополнительные сведения см. в статье [Статические классы и члены статических классов](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md).

## <a name="example"></a>Пример

Следующий класс объявляется как `static` и содержит только методы `static`:

[!code-csharp[csrefKeywordsModifiers#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#18)]

Объявление константы или типа неявно является членом `static`. На член `static` невозможно ссылаться через экземпляр, а можно только через имя типа. Например, рассмотрим следующий класс.

[!code-csharp[csrefKeywordsModifiers#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#19)]

Чтобы обратиться к члену `static` `x`, воспользуйтесь полным именем — `MyBaseC.MyStruct.x` (если только член не доступен из той же области действия).

```csharp
Console.WriteLine(MyBaseC.MyStruct.x);
```

Так как экземпляр класса содержит отдельную копию всех полей экземпляра класса, каждому полю `static` соответствует только одна копия.

Невозможно использовать [`this`](this.md) для ссылки на методы `static` или методы доступа к свойствам.

Если к классу применяется ключевое слово `static`, все члены этого класса должны быть `static`.

Классы, интерфейсы и классы `static` могут иметь конструкторы `static`. Конструктор `static` вызывается на определенном этапе между запуском программы и созданием экземпляра класса.

> [!NOTE]
> Ключевое слово `static` имеет более ограниченное применение по сравнению с C++. Сведения о сравнении с ключевым словом С++ см. в статье [Классы хранения (C++)](/cpp/cpp/storage-classes-cpp#static).

В качестве демонстрации членов `static` рассмотрим класс, представляющий сотрудника компании. Предположим, что этот класс содержит метод для подсчета сотрудников и поле для хранения их числа. И метод, и поле не принадлежат никакому экземпляру сотрудника. Они принадлежат всему классу сотрудников. В связи с этим они должны объявляться как члены `static` класса.

## <a name="example"></a>Пример

В этом примере выполняется чтение имени и идентификатора нового сотрудника, увеличение счетчика сотрудников на единицу, а также отображение сведений о новом сотруднике и новом числе сотрудников. Эта программа считывает текущее число сотрудников с клавиатуры.

[!code-csharp[csrefKeywordsModifiers#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#20)]  

## <a name="example"></a>Пример

В этом примере показано, как можно инициализировать поле `static`, используя другое поле `static`, которое еще не объявлено. Результаты будут неопределенными до тех пор, пока вы явно не присвоите значение полю `static`.

[!code-csharp[csrefKeywordsModifiers#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#21)]  

## <a name="c-language-specification"></a>Спецификация языка C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>См. также раздел

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Ключевые слова в C#](index.md)
- [Модификаторы](index.md)
- [Статические классы и члены статических классов](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md)
