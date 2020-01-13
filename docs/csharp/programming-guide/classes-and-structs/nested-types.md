---
title: Руководство по программированию на C#. Вложенные типы
ms.date: 07/10/2017
helpviewer_keywords:
- nested types [C#]
ms.assetid: f2e1b315-e3d1-48ce-977f-7bae0960ba99
ms.openlocfilehash: 982eeceb2088dd6e1e57fe796b38e46c0f2d4de8
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705500"
---
# <a name="nested-types-c-programming-guide"></a>Вложенные типы (Руководство по программированию на C#)
Тип, определенный внутри [класса](../../language-reference/keywords/class.md) или [структуры](../../language-reference/keywords/struct.md), называется вложенным типом. Пример:  
  
 [!code-csharp[csProgGuideObjects#68](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#68)]  
  
Независимо от того, является ли внешний тип классом или структурой, вложенным типам по умолчанию присваивается модификатор [private](../../language-reference/keywords/private.md), из-за чего они доступны только из содержащего их типа. В предыдущем примере класс `Nested` недоступен для внешних типов. 

Также можно указать [модификатор доступа](../../language-reference/keywords/access-modifiers.md), определяющий доступность вложенного типа, как показано ниже:

- Вложенные типы **класса** могут иметь модификаторы [public](../../language-reference/keywords/public.md), [protected](../../language-reference/keywords/protected.md), [internal](../../language-reference/keywords/internal.md), [protected internal](../../language-reference/keywords/protected-internal.md), [private](../../language-reference/keywords/private.md) или [private protected](../../language-reference/keywords/private-protected.md). 

   Тем не менее при определении вложенного класса `protected`, `protected internal` или `private protected` внутри [запечатанного класса](../../language-reference/keywords/sealed.md) возникает предупреждение компилятора [CS0628](../../misc/cs0628.md) "Новый защищенный член объявлен в запечатанном классе".
  
- Вложенные типы **структуры** могут иметь модификаторы [public](../../language-reference/keywords/public.md), [internal](../../language-reference/keywords/internal.md) или [private](../../language-reference/keywords/private.md).
  
В следующем примере класс `Nested` определяется как открытый:
  
 [!code-csharp[csProgGuideObjects#69](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#69)]  
  
 Вложенный (внутренний) тип может получить доступ к вмещающему (внешнему) типу. Чтобы получить доступ к вмещающему типу, передайте его в качестве аргумента в конструктор вложенного типа. Пример:  
  
 [!code-csharp[csProgGuideObjects#70](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#70)]  
  
 Вложенный тип имеет доступ ко всем членам, которые доступны вмещающему типу. Он может получать доступ к закрытым и защищенным членам вмещающего типа, включая любые наследуемые защищенные члены.  
  
 В предыдущем объявлении полным именем класса `Nested` является `Container.Nested`. Это имя используется для создания нового экземпляра вложенного класса, как показано ниже:  
  
 [!code-csharp[csProgGuideObjects#71](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#71)]  
  
## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../index.md)
- [Классы и структуры](./index.md)
- [Модификаторы доступа](./access-modifiers.md)
- [Конструкторы](./constructors.md)
