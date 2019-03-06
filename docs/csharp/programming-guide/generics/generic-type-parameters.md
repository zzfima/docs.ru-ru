---
title: Руководство по программированию на C#. Параметры универсального типа
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], type parameters
- type parameters [C#]
ms.assetid: a03b0ab2-0606-4b41-b7bf-e64d5bb4d18f
ms.openlocfilehash: f6acbfee5c6b5ec426076d7bf766a3c6894b736f
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56972187"
---
# <a name="generic-type-parameters-c-programming-guide"></a>Параметры универсального типа (Руководство по программированию на C#)
В определении универсального типа или метода параметр типа является заполнителем для определенного типа, который клиент задает при создании экземпляра переменной универсального типа. Универсальный класс, например `GenericList<T>` из раздела [Общие сведения об универсальных шаблонах](../../../csharp/programming-guide/generics/introduction-to-generics.md), нельзя использовать в исходном виде, поскольку он представляет собой не фактически тип, а, скорее, заготовку типа. Чтобы использовать класс `GenericList<T>`, в коде клиента необходимо объявить сконструированный тип и создать его экземпляр, указав аргумент типа в угловых скобках. Аргумент типа для этого конкретного класса может иметь любой тип, распознаваемый компилятором. Можно создать любое число экземпляров сконструированного типа, каждый из которых будет использовать разные аргументы типа, как показано ниже:  
  
 [!code-csharp[csProgGuideGenerics#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#7)]  
  
 В каждом из этих экземпляров `GenericList<T>` каждое вхождение `T` в классе во время выполнения будет заменяться аргументом типа. Посредством такой замены в этом случае создается три отдельных типобезопасных эффективных объекта, использующих одно определение класса. Дополнительные сведения о том, как в среде CLR реализуется эта замена, см. в разделе [Универсальные типы во время выполнения](../../../csharp/programming-guide/generics/generics-in-the-run-time.md).  
  
## <a name="type-parameter-naming-guidelines"></a>Правила именования параметра типа  
  
-   **Присваивайте** параметрам универсального типа описательные имена, кроме случаев, когда достаточно одной буквы и описательное имя не имеет практической ценности.  
  
     [!code-csharp[csProgGuideGenerics#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#8)]  
  
-   **Используйте** имя параметра типа T для типов, содержащих только однобуквенный параметр типа.  
  
     [!code-csharp[csProgGuideGenerics#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#9)]  
  
-   **Используйте** префикс "T" для описательных имен параметров типа.  
  
     [!code-csharp[csProgGuideGenerics#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#10)]  
  
-   **Указывайте** ограничения, связанные с параметром типа, в его имени. Например, параметр с ограничением `ISession` может называться `TSession`.  
  
## <a name="see-also"></a>См. также

- <xref:System.Collections.Generic>
- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)
- [Универсальные шаблоны](../../../csharp/programming-guide/generics/index.md)
- [Различия между шаблонами языка C++ и универсальными шаблонами языка C#](../../../csharp/programming-guide/generics/differences-between-cpp-templates-and-csharp-generics.md)
