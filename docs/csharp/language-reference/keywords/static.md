---
title: Модификатор static. Справочник по C#
ms.date: 07/20/2015
f1_keywords:
- static
- static_CSharpKeyword
helpviewer_keywords:
- static keyword [C#]
ms.assetid: 5509e215-2183-4da3-bab4-6b7e607a4fdf
ms.openlocfilehash: f4ca3fcf809e723d2144654f1da949eb4d6de1b4
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713070"
---
# <a name="static-c-reference"></a>static (Справочник по C#)

Модификатор `static` используется для объявления статического члена, принадлежащего собственно типу, а не конкретному объекту. Модификатор `static` можно использовать с классами, полями, методами, свойствами, операторами, событиями и конструкторами, но нельзя — с индексаторами, методами завершения или типами, отличными от классов. Дополнительные сведения см. в статье [Статические классы и члены статических классов](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md).

## <a name="example"></a>Пример

Следующий класс объявляется как `static` и содержит только методы `static`:

[!code-csharp[csrefKeywordsModifiers#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#18)]

Объявление константы или типа неявно является статическим членом.

На статический член нельзя ссылаться через экземпляр, а можно только через имя типа. Например, рассмотрим следующий класс.

[!code-csharp[csrefKeywordsModifiers#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#19)]

Чтобы обратиться к статическому члену `x`, воспользуйтесь полным именем — `MyBaseC.MyStruct.x` (если только член не доступен из той же области действия):

```csharp
Console.WriteLine(MyBaseC.MyStruct.x);
```

Так как экземпляр класса содержит отдельную копию всех полей экземпляра класса, каждому статическому полю соответствует только одна копия.

Невозможно использовать [this](this.md) для ссылки на статические методы или методы доступа к свойствам.

Если к классу применяется ключевое слово `static`, все члены этого класса должны быть статическими.

Классы и статические классы могут иметь статические конструкторы. Статические конструкторы вызываются на определенном этапе между запуском программы и созданием экземпляра класса.

> [!NOTE]
> Ключевое слово `static` имеет более ограниченное применение по сравнению с C++. Сведения о сравнении с ключевым словом С++ см. в статье [Классы хранения (C++)](/cpp/cpp/storage-classes-cpp#static).

В качестве демонстрации статических членов рассмотрим класс, представляющий сотрудника компании. Предположим, что этот класс содержит метод для подсчета сотрудников и поле для хранения их числа. И метод, и поле не принадлежат никакому экземпляру сотрудника. Они принадлежат классу компании. В связи с этим они должны объявляться как статические члены класса.

## <a name="example"></a>Пример

В этом примере выполняется чтение имени и идентификатора нового сотрудника, увеличение счетчика сотрудников на единицу, а также отображение сведений о новом сотруднике и новом числе сотрудников. Для простоты эта программа считывает текущее число сотрудников с клавиатуры. В реальном приложении эта информация должна считываться из файла.

[!code-csharp[csrefKeywordsModifiers#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#20)]  

## <a name="example"></a>Пример

Этот пример показывает, что несмотря на то, что вы можете инициализировать статическое поле посредством другого, еще не объявленного статического поля, результаты не будут определены до тех пор, пока статическому полю не будет явно присвоено значение.

[!code-csharp[csrefKeywordsModifiers#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#21)]  

## <a name="c-language-specification"></a>Спецификация языка C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Ключевые слова в C#](index.md)
- [Модификаторы](index.md)
- [Статические классы и члены статических классов](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md)
