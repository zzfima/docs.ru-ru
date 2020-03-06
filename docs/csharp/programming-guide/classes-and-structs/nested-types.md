---
title: Руководство по программированию на C#. Вложенные типы
ms.date: 02/08/2020
helpviewer_keywords:
- nested types [C#]
ms.assetid: f2e1b315-e3d1-48ce-977f-7bae0960ba99
ms.openlocfilehash: 12e44ccc1254424c152a238c8390f133550fa54c
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/26/2020
ms.locfileid: "77626494"
---
# <a name="nested-types-c-programming-guide"></a>Вложенные типы (Руководство по программированию на C#)

Тип, определенный внутри [класса](../../language-reference/keywords/class.md), [структуры](../../language-reference/builtin-types/struct.md) или [интерфейса](../../language-reference/keywords/interface.md), называется вложенным типом. Пример

[!code-csharp[DeclareNestedClass](~/samples/snippets/csharp/objectoriented/nestedtypes.cs#DeclareNestedClass)]

Независимо от того, является ли внешний тип классом, интерфейсом или структурой, вложенным типам по умолчанию присваивается модификатор [private](../../language-reference/keywords/private.md), из-за чего они доступны только из содержащего их типа. В предыдущем примере класс `Nested` недоступен для внешних типов.

Также можно указать [модификатор доступа](../../language-reference/keywords/access-modifiers.md), определяющий доступность вложенного типа, как показано ниже:

- Вложенные типы **класса** могут иметь модификаторы [public](../../language-reference/keywords/public.md), [protected](../../language-reference/keywords/protected.md), [internal](../../language-reference/keywords/internal.md), [protected internal](../../language-reference/keywords/protected-internal.md), [private](../../language-reference/keywords/private.md) или [private protected](../../language-reference/keywords/private-protected.md).

   Тем не менее при определении вложенного класса `protected`, `protected internal` или `private protected` внутри [запечатанного класса](../../language-reference/keywords/sealed.md) возникает предупреждение компилятора [CS0628](../../misc/cs0628.md) "Новый защищенный член объявлен в запечатанном классе".
  
- Вложенные типы **структуры** могут иметь модификаторы [public](../../language-reference/keywords/public.md), [internal](../../language-reference/keywords/internal.md) или [private](../../language-reference/keywords/private.md).

В следующем примере класс `Nested` определяется как открытый:

[!code-csharp[PublicNestedClass](~/samples/snippets/csharp/objectoriented/nestedtypes.cs#PublicNestedClass)]

Вложенный (внутренний) тип может получить доступ к вмещающему (внешнему) типу. Чтобы получить доступ к вмещающему типу, передайте его в качестве аргумента в конструктор вложенного типа. Пример:

[!code-csharp[DeclareNestedInstance](~/samples/snippets/csharp/objectoriented/nestedtypes.cs#DeclareNestedInstance)]

Вложенный тип имеет доступ ко всем членам, которые доступны вмещающему типу. Он может получать доступ к закрытым и защищенным членам вмещающего типа, включая любые наследуемые защищенные члены.

В предыдущем объявлении полным именем класса `Nested` является `Container.Nested`. Это имя используется для создания нового экземпляра вложенного класса, как показано ниже:

[!code-csharp[UseNestedInstance](~/samples/snippets/csharp/objectoriented/nestedtypes.cs#UseNestedInstance)]

## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../index.md)
- [Классы и структуры](./index.md)
- [Модификаторы доступа](./access-modifiers.md)
- [Конструкторы](./constructors.md)
