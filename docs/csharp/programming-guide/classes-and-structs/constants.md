---
title: Константы (Руководство по программированию на C#)
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, constants
- constants [C#]
ms.assetid: 1fb39621-1738-49b1-a1b3-8587f109123f
ms.openlocfilehash: 90423c868ca303f8e94c16f44bc5e0b23615fc17
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33314061"
---
# <a name="constants-c-programming-guide"></a>Константы (Руководство по программированию на C#)
Константы — это постоянные значения, которые известны во время компиляции и не изменяются во время выполнения программы. Константы должны объявляться с модификатором [const](../../../csharp/language-reference/keywords/const.md). Только встроенные типы C# (за исключением <xref:System.Object?displayProperty=nameWithType>) можно объявлять как `const`. Список встроенных типов см. в [таблице встроенных типов](../../../csharp/language-reference/keywords/built-in-types-table.md). Пользовательские типы, включая классы, структуры и массивы, не могут объявляться как `const`. Модификатор [readonly](../../../csharp/language-reference/keywords/readonly.md) позволяет создать класс, структуру или массив, которые инициализируются один раз (например, в конструкторе), и впоследствии изменить их нельзя.  
  
 C# не поддерживает методы, свойства или события `const`.  
  
 Тип перечисления позволяет определять именованные константы для целочисленных встроенных типов (например `int`, `uint`, `long` и т. д.). Дополнительные сведения см. в разделе [Перечисление](../../../csharp/language-reference/keywords/enum.md).  
  
 Константы должны инициализироваться сразу после объявления. Пример:  
  
 [!code-csharp[csProgGuideObjects#64](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/constants_1.cs)]  
  
 В этом примере константа `months` всегда имеет значение 12, и его не может изменить даже сам класс. На самом деле в случае, если компилятор встречает идентификатор константы в исходном коде C# (например, `months`), он подставляет значение литерала непосредственно в создаваемый им промежуточный язык (IL). Поскольку с константой в среде выполнения не связан адрес ни одной переменной, поля `const` не могут передаваться по ссылке и отображаться в выражении как левостороннее значение.  
  
> [!NOTE]
>  Будьте внимательны, ссылаясь на постоянные значения, определенные в другом коде, например, в DLL. Если в новой версии DLL для константы определяется новое значение, старое значение литерала хранится в вашей программе вплоть до повторной компиляции для новой версии.  
  
 Несколько констант одного типа можно объявить одновременно, например:  
  
 [!code-csharp[csProgGuideObjects#65](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/constants_2.cs)]  
  
 Выражение, которое используется для инициализации константы, может ссылаться на другую константу, если не создает циклическую ссылку. Пример:  
  
 [!code-csharp[csProgGuideObjects#66](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/constants_3.cs)]  
  
 Константы могут иметь пометку [public](../../../csharp/language-reference/keywords/public.md), [private](../../../csharp/language-reference/keywords/private.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md), [protected internal](../../../csharp/language-reference/keywords/protected-internal.md) или [private protected](../../../csharp/language-reference/keywords/private-protected.md). Эти модификаторы доступа определяют, каким образом пользователи класса смогут получать доступ к константе. Дополнительные сведения см. в разделе [Модификаторы доступа](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).  
  
 Доступ к константам осуществляется так, как если бы они были [статическими](../../../csharp/language-reference/keywords/static.md) полями, поскольку значение константы одинаково для всех экземпляров типа. Для их объявления используйте ключевое слово `static`. Выражения, которые не относятся к классу, определяющему константу, должны включать имя класса, период и имя константы для доступа к этой константе. Пример:  
  
 [!code-csharp[csProgGuideObjects#67](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/constants_4.cs)]  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Классы и структуры](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [Свойства](../../../csharp/programming-guide/classes-and-structs/properties.md)  
 [Типы](../../../csharp/programming-guide/types/index.md)  
 [readonly](../../../csharp/language-reference/keywords/readonly.md)  
 [Неизменность в C#, часть 1. Виды неизменности](https://blogs.msdn.microsoft.com/ericlippert/2007/11/13/immutability-in-c-part-one-kinds-of-immutability)
