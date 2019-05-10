---
title: Руководство по программированию на C#. Универсальные шаблоны
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, generics
- generics [C#]
ms.assetid: 75ea8509-a4ea-4e7a-a2b3-cf72482e9282
ms.openlocfilehash: fcc905353ada734e50fd56f50c4f705aa400f70d
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64608488"
---
# <a name="generics-c-programming-guide"></a>Универсальные шаблоны (Руководство по программированию на C#)
Универсальные шаблоны были добавлены в язык C# и общеязыковую среду выполнения (CLR) в версии 2.0. Универсальные шаблоны вводят на платформе .NET Framework концепцию параметров универсального типа. Благодаря им вы можете создавать классы и методы с типами, спецификация которых отложена до момента объявления и создания экземпляров в клиентском коде. Как пример, ниже показан класс с параметром T универсального типа. Этот класс может использоваться в другом клиентском коде, не требуя ресурсов и не создавая рисков, связанных с операциями приведения и упаковки-преобразования в среде выполнения.  
  
 [!code-csharp[csProgGuideGenerics#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#1)]  
  
## <a name="generics-overview"></a>Общие сведения об универсальных шаблонах  
  
- Используйте универсальные типы, чтобы получить максимально широкие возможности многократного использования кода, обеспечения безопасности типов и повышения производительности.  
  
- Чаще всего универсальные шаблоны используются для создания классов коллекций.  
  
- Библиотека классов .NET Framework содержит несколько новых универсальных классов коллекций в пространстве имен <xref:System.Collections.Generic>. Рекомендуется как можно чаще использовать их вместо таких классов, как <xref:System.Collections.ArrayList> в пространстве имен <xref:System.Collections>.  
  
- Вы можете создавать собственные универсальные интерфейсы, классы, методы, события и делегаты.  
  
- Универсальные классы можно ограничить, чтобы они разрешали доступ к методам только для определенных типов данных.  
  
- Сведения о типах, используемых в универсальном типе данных, можно получить во время выполнения с помощью отражения.  
  
## <a name="related-sections"></a>Связанные разделы  
 Дополнительные сведения:  
  
- [Введение в универсальные шаблоны](../../../csharp/programming-guide/generics/introduction-to-generics.md)  
  
- [Преимущества универсальных шаблонов](../../../csharp/programming-guide/generics/benefits-of-generics.md)  
  
- [Параметры универсального типа](../../../csharp/programming-guide/generics/generic-type-parameters.md)  
  
- [Ограничения параметров типа](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md)  
  
- [Универсальные классы](../../../csharp/programming-guide/generics/generic-classes.md)  
  
- [Универсальные интерфейсы](../../../csharp/programming-guide/generics/generic-interfaces.md)  
  
- [Универсальные методы](../../../csharp/programming-guide/generics/generic-methods.md)  
  
- [Универсальные делегаты](../../../csharp/programming-guide/generics/generic-delegates.md)  
  
- [Различия между шаблонами языка C++ и универсальными шаблонами языка C#](../../../csharp/programming-guide/generics/differences-between-cpp-templates-and-csharp-generics.md)  
  
- [Универсальные типы и отражение](../../../csharp/programming-guide/generics/generics-and-reflection.md)  
  
- [Универсальные типы во время выполнения](../../../csharp/programming-guide/generics/generics-in-the-run-time.md)  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 Дополнительные сведения см. в [спецификации языка C#](~/_csharplang/spec/types.md#constructed-types).  
  
## <a name="see-also"></a>См. также

- <xref:System.Collections.Generic>
- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)
- [Типы](../../../csharp/programming-guide/types/index.md)
- [\<typeparam>](../../../csharp/programming-guide/xmldoc/typeparam.md)
- [\<typeparamref>](../../../csharp/programming-guide/xmldoc/typeparamref.md)
- [Универсальные шаблоны в .NET](../../../standard/generics/index.md)
