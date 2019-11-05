---
title: Руководство по программированию на C#. Параметры универсального типа
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], type parameters
- type parameters [C#]
ms.assetid: a03b0ab2-0606-4b41-b7bf-e64d5bb4d18f
ms.openlocfilehash: 992b71fa2afa6b511d09c69ade26e3b5bc13acd2
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2019
ms.locfileid: "73195477"
---
# <a name="generic-type-parameters-c-programming-guide"></a>Руководство по программированию на C#. Параметры универсального типа

В определении универсального типа или метода параметр типа является заполнителем для определенного типа, который клиент задает при создании экземпляра переменной универсального типа. Универсальный класс, например `GenericList<T>` из раздела [Общие сведения об универсальных шаблонах](./index.md), нельзя использовать в исходном виде, поскольку он представляет собой не фактически тип, а, скорее, заготовку типа. Чтобы использовать класс `GenericList<T>`, в коде клиента необходимо объявить сконструированный тип и создать его экземпляр, указав аргумент типа в угловых скобках. Аргумент типа для этого конкретного класса может иметь любой тип, распознаваемый компилятором. Можно создать любое число экземпляров сконструированного типа, каждый из которых будет использовать разные аргументы типа, как показано ниже:  
  
[!code-csharp[csProgGuideGenerics#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#7)]  
  
В каждом из этих экземпляров `GenericList<T>` каждое вхождение `T` в классе во время выполнения будет заменяться аргументом типа. Посредством такой замены в этом случае создается три отдельных типобезопасных эффективных объекта, использующих одно определение класса. Дополнительные сведения о том, как в среде CLR реализуется эта замена, см. в разделе [Универсальные типы во время выполнения](./generics-in-the-run-time.md).  
  
## <a name="type-parameter-naming-guidelines"></a>Правила именования параметров типа  
  
- **Присваивайте** параметрам универсального типа описательные имена, кроме случаев, когда достаточно одной буквы и описательное имя не имеет практической ценности.  
  
   [!code-csharp[csProgGuideGenerics#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#8)]  
  
- **Используйте** имя параметра типа T для типов, содержащих только однобуквенный параметр типа.  
  
   [!code-csharp[csProgGuideGenerics#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#9)]  
  
- **Используйте** префикс "T" для описательных имен параметров типа.  
  
   [!code-csharp[csProgGuideGenerics#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#10)]  
  
- **Указывайте** ограничения, связанные с параметром типа, в его имени. Например, параметр с ограничением `ISession` может называться `TSession`.

Правило анализа кода [CA1715](/visualstudio/code-quality/ca1715) можно использовать, чтобы убедиться, что параметры типа, именуются соответствующим образом.
  
## <a name="see-also"></a>См. также

- <xref:System.Collections.Generic>
- [Руководство по программированию на C#](../index.md)
- [Универсальные шаблоны](./index.md)
- [Различия между шаблонами языка C++ и универсальными шаблонами языка C#](./differences-between-cpp-templates-and-csharp-generics.md)
