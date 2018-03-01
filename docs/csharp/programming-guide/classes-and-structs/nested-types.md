---
title: "Вложенные типы (Руководство по программированию на C#)"
ms.date: 07/10/2017
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- nested types [C#]
ms.assetid: f2e1b315-e3d1-48ce-977f-7bae0960ba99
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: ab13c68b638062ab89c90dbfc51b51b8d72d3bde
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="nested-types-c-programming-guide"></a>Вложенные типы (Руководство по программированию на C#)
Тип, определенный внутри [класса](../../../csharp/language-reference/keywords/class.md) или [структуры](../../../csharp/language-reference/keywords/struct.md), называется вложенным типом. Пример:  
  
[!code-csharp[csProgGuideObjects#68](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_1.cs)]  
  
Независимо от того, является ли внешний тип классом или структурой, вложенным типам по умолчанию присваивается модификатор [private](../../../csharp/language-reference/keywords/private.md), из-за чего они доступны только из содержащего их типа. В предыдущем примере класс `Nested` недоступен для внешних типов. 

Также можно указать [модификатор доступа](../../language-reference/keywords/access-modifiers.md), определяющий доступность вложенного типа, как показано ниже:

- Вложенные типы **класса** может быть [открытый](../../../csharp/language-reference/keywords/public.md), [защищенных](../../../csharp/language-reference/keywords/protected.md), [внутренней](../../../csharp/language-reference/keywords/internal.md), [защищенные внутренние](../../../csharp/language-reference/keywords/protected-internal.md), [закрытый](../../../csharp/language-reference/keywords/private.md) или [private protected](../../../csharp/language-reference/keywords/private-protected.md). 

   Однако определение `protected`, `protected internal` или `private protected` вложенных классов внутри [запечатанный класс](../../language-reference/keywords/sealed.md) приводит к возникновению предупреждения компилятора [CS0628](../../misc/cs0628.md), «новый защищенный член объявлен в запечатанном классе».
  
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
