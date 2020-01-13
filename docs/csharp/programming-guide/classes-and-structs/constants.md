---
title: Руководство по программированию на C#. Константы
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, constants
- constants [C#]
ms.assetid: 1fb39621-1738-49b1-a1b3-8587f109123f
ms.openlocfilehash: 0abb728c58d50e3d7709d680dd91794c4be6afef
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705747"
---
# <a name="constants-c-programming-guide"></a>Константы (Руководство по программированию на C#)
Константы — это постоянные значения, которые известны во время компиляции и не изменяются во время выполнения программы. Константы должны объявляться с модификатором [const](../../language-reference/keywords/const.md). Только встроенные типы C# (за исключением <xref:System.Object?displayProperty=nameWithType>) можно объявлять как `const`. Список встроенных типов см. в [таблице встроенных типов](../../language-reference/keywords/built-in-types-table.md). Пользовательские типы, включая классы, структуры и массивы, не могут объявляться как `const`. Модификатор [readonly](../../language-reference/keywords/readonly.md) позволяет создать класс, структуру или массив, которые инициализируются один раз (например, в конструкторе), и впоследствии изменить их нельзя.  
  
 C# не поддерживает методы, свойства или события `const`.  
  
 Тип перечисления позволяет определять именованные константы для целочисленных встроенных типов (например `int`, `uint`, `long` и т. д.). Дополнительные сведения см. в разделе [Перечисление](../../language-reference/builtin-types/enum.md).  
  
 Константы должны инициализироваться сразу после объявления. Пример:  
  
 [!code-csharp[csProgGuideObjects#64](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#64)]  
  
 В этом примере константа `months` всегда имеет значение 12, и его не может изменить даже сам класс. На самом деле в случае, если компилятор встречает идентификатор константы в исходном коде C# (например, `months`), он подставляет значение литерала непосредственно в создаваемый им промежуточный язык (IL). Поскольку с константой в среде выполнения не связан адрес ни одной переменной, поля `const` не могут передаваться по ссылке и отображаться в выражении как левостороннее значение.  
  
> [!NOTE]
> Будьте внимательны, ссылаясь на постоянные значения, определенные в другом коде, например, в DLL. Если в новой версии DLL для константы определяется новое значение, старое значение литерала хранится в вашей программе вплоть до повторной компиляции для новой версии.  
  
 Несколько констант одного типа можно объявить одновременно, например:  
  
 [!code-csharp[csProgGuideObjects#65](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#65)]  
  
 Выражение, которое используется для инициализации константы, может ссылаться на другую константу, если не создает циклическую ссылку. Пример:  
  
 [!code-csharp[csProgGuideObjects#66](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#66)]  
  
 Константы могут иметь пометку [public](../../language-reference/keywords/public.md), [private](../../language-reference/keywords/private.md), [protected](../../language-reference/keywords/protected.md), [internal](../../language-reference/keywords/internal.md), [protected internal](../../language-reference/keywords/protected-internal.md) или [private protected](../../language-reference/keywords/private-protected.md). Эти модификаторы доступа определяют, каким образом пользователи класса смогут получать доступ к константе. Дополнительные сведения см. в разделе [Модификаторы доступа](./access-modifiers.md).  
  
 Доступ к константам осуществляется так, как если бы они были [статическими](../../language-reference/keywords/static.md) полями, поскольку значение константы одинаково для всех экземпляров типа. Для их объявления используйте ключевое слово `static`. Выражения, которые не относятся к классу, определяющему константу, должны включать имя класса, период и имя константы для доступа к этой константе. Пример:  
  
 [!code-csharp[csProgGuideObjects#67](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#67)]  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../index.md)
- [Классы и структуры](./index.md)
- [Свойства](./properties.md)
- [Типы](../types/index.md)
- [readonly](../../language-reference/keywords/readonly.md)
- [Immutability in C# Part One: Kinds of Immutability](https://blogs.msdn.microsoft.com/ericlippert/2007/11/13/immutability-in-c-part-one-kinds-of-immutability) (Неизменность в C#, часть 1. Виды неизменности)
