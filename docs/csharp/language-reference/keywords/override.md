---
title: Справочник по C#. Модификатор override
ms.date: 07/20/2015
f1_keywords:
- override
- override_CSharpKeyword
helpviewer_keywords:
- override keyword [C#]
ms.assetid: dd1907a8-acf8-46d3-80b9-c2ca4febada8
ms.openlocfilehash: acad3aa3b196c184132ad1acdf52b18a799b0896
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713252"
---
# <a name="override-c-reference"></a>override (Справочник по C#)

Модификатор `override` требуется для расширения или изменения абстрактной или виртуальной реализации унаследованного метода, свойства, индексатора или события.

## <a name="example"></a>Пример

В этом примере класс `Square` должен предоставить переопределенную реализацию `GetArea`, так как `GetArea` является унаследованным от абстрактного класса `Shape`:

[!code-csharp[csrefKeywordsModifiers#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#1)]

Метод `override` предоставляет новую реализацию члена, унаследованного от базового класса. Метод, переопределенный объявлением `override`, называется переопределенным базовым методом. Переопределенный базовый метод должен иметь ту же сигнатуру, что и метод `override`. Дополнительные сведения о наследовании см. в разделе [Наследование](../../programming-guide/classes-and-structs/inheritance.md).

Невиртуальный или статический метод нельзя переопределить. Переопределенный базовый метод должен иметь тип `virtual`, `abstract` или `override`.

Объявление `override` не может изменить доступность метода `virtual`. Методы `override` и `virtual` должны иметь одинаковый [модификатор уровня доступа](access-modifiers.md).

Модификаторы `new`, `static` и `virtual` нельзя использовать для изменения метода `override`.

Переопределяющее объявление свойства должно задавать такие же модификатор уровня доступа, тип и имя, которые имеются у унаследованного свойства, а переопределенное свойство должно иметь тип `virtual`, `abstract` или `override`.

Дополнительные сведения об использовании ключевого слова `override` см. в разделах [Управление версиями с помощью ключевых слов Override и New](../../programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) и [Использование ключевых слов Override и New](../../programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).

## <a name="example"></a>Пример

В этом примере определяется базовый класс с именем `Employee` и производный класс с именем `SalesEmployee`. Класс `SalesEmployee` включает дополнительное поле `salesbonus`, для использования которого переопределяется метод `CalculatePay`.

[!code-csharp[csrefKeywordsModifiers#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#9)]

## <a name="c-language-specification"></a>Спецификация языка C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Наследование](../../programming-guide/classes-and-structs/inheritance.md)
- [Ключевые слова в C#](index.md)
- [Модификаторы](index.md)
- [abstract](abstract.md)
- [virtual](virtual.md)
- [new (модификатор)](new-modifier.md)
- [Полиморфизм](../../programming-guide/classes-and-structs/polymorphism.md)
