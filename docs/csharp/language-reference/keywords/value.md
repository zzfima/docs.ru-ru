---
title: Справочник по C#. Контекстное ключевое слово value
ms.date: 07/20/2015
f1_keywords:
- value_CSharpKeyword
helpviewer_keywords:
- value keyword [C#]
ms.assetid: c99d6468-687f-4a46-89b4-a95e1b00bf6d
ms.openlocfilehash: 84d0c51ddafb59144f4ba8c6e73412642fa8fa28
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712901"
---
# <a name="value-c-reference"></a>value (Справочник по C#)

Контекстное ключевое слово `value` используется в методе доступа `set` в объявлениях [свойства](../../programming-guide/classes-and-structs/properties.md) и [индексатора](../../programming-guide/indexers/index.md). Оно аналогично входному параметру метода. Ключевое слово `value` ссылается на значение, которое клиентский код пытается присвоить свойству или индексатору. В приведенном ниже примере класс `MyDerivedClass` имеет свойство с именем `Name`, в котором используется параметр `value` для присвоения новой строки резервному полю `name`. С точки зрения клиентского кода эта операция выглядит как простое присвоение.

[!code-csharp[csrefKeywordsModifiers#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#26)]

Дополнительные сведения см. в статьях [Свойства](../../programming-guide/classes-and-structs/properties.md) и [Индексаторы](../../programming-guide/indexers/index.md).

## <a name="c-language-specification"></a>Спецификация языка C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Ключевые слова в C#](index.md)
