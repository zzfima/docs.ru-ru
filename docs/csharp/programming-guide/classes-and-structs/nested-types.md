---
title: Вложенные типы (Руководство по программированию на C#)
ms.date: 07/10/2017
helpviewer_keywords:
- nested types [C#]
ms.assetid: f2e1b315-e3d1-48ce-977f-7bae0960ba99
ms.openlocfilehash: 57356fbf4bff218932d1f1b4c62532f10c175757
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="nested-types-c-programming-guide"></a>Вложенные типы (Руководство по программированию на C#)
Тип, определенный внутри [класса](../../../csharp/language-reference/keywords/class.md) или [структуры](../../../csharp/language-reference/keywords/struct.md), называется вложенным типом. Пример:  
  
[!code-csharp[csProgGuideObjects#68](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_1.cs)]  
  
Независимо от того, является ли внешний тип классом или структурой, вложенным типам по умолчанию присваивается модификатор [private](../../../csharp/language-reference/keywords/private.md), из-за чего они доступны только из содержащего их типа. В предыдущем примере класс `Nested` недоступен для внешних типов. 

Также можно указать [модификатор доступа](../../language-reference/keywords/access-modifiers.md), определяющий доступность вложенного типа, как показано ниже:

- Вложенные типы **класса** могут иметь модификаторы [public](../../../csharp/language-reference/keywords/public.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md), [protected internal](../../../csharp/language-reference/keywords/protected-internal.md), [private](../../../csharp/language-reference/keywords/private.md) или [private protected](../../../csharp/language-reference/keywords/private-protected.md). 

   Тем не менее при определении вложенного класса `protected`, `protected internal` или `private protected` внутри [запечатанного класса](../../language-reference/keywords/sealed.md) возникает предупреждение компилятора [CS0628](../../misc/cs0628.md) "Новый защищенный член объявлен в запечатанном классе".
  
- Вложенные типы **структуры** могут иметь модификаторы [public](../../../csharp/language-reference/keywords/public.md), [internal](../../../csharp/language-reference/keywords/internal.md) или [private](../../../csharp/language-reference/keywords/private.md).
  
В следующем примере класс `Nested` определяется как открытый:
  
[!code-csharp[csProgGuideObjects#69](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_2.cs)]  
  
 Вложенный тип может получить доступ к вмещающему типу, а внутренний тип — к внешнему. Чтобы получить доступ к вмещающему типу, передайте его в качестве аргумента в конструктор вложенного типа. Пример:  
  
 [!code-csharp[csProgGuideObjects#70](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_3.cs)]  
  
 Вложенный тип имеет доступ ко всем членам, которые доступны вмещающему типу. Он может получать доступ к закрытым и защищенным членам вмещающего типа, включая любые наследуемые защищенные члены.  
  
 В предыдущем объявлении полным именем класса `Nested` является `Container.Nested`. Это имя используется для создания нового экземпляра вложенного класса, как показано ниже:  
  
 [!code-csharp[csProgGuideObjects#71](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_4.cs)]  
  
## <a name="see-also"></a>См. также  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Классы и структуры](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [Модификаторы доступа](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)  
 [Конструкторы](../../../csharp/programming-guide/classes-and-structs/constructors.md)
