---
title: Параметры универсального типа (Руководство по программированию на C#)
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], type parameters
- type parameters [C#]
ms.assetid: a03b0ab2-0606-4b41-b7bf-e64d5bb4d18f
ms.openlocfilehash: 35029b90fb7b905a87055596cf8dcd6a84ef9d36
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="generic-type-parameters-c-programming-guide"></a>Параметры универсального типа (Руководство по программированию на C#)
В определении универсального типа или метода параметр типа является заполнителем для определенного типа, который клиент задает при создании экземпляра переменной универсального типа. Универсальный класс, например `GenericList<T>` из раздела [Общие сведения об универсальных шаблонах](../../../csharp/programming-guide/generics/introduction-to-generics.md), нельзя использовать в исходном виде, поскольку он представляет собой не фактически тип, а, скорее, заготовку типа. Чтобы использовать класс `GenericList<T>`, в коде клиента необходимо объявить сконструированный тип и создать его экземпляр, указав аргумент типа в угловых скобках. Аргумент типа для этого конкретного класса может иметь любой тип, распознаваемый компилятором. Можно создать любое число экземпляров сконструированного типа, каждый из которых будет использовать разные аргументы типа, как показано ниже:  
  
 [!code-csharp[csProgGuideGenerics#7](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-type-parameters_1.cs)]  
  
 В каждом из этих экземпляров `GenericList<T>` каждое вхождение `T` в классе во время выполнения будет заменяться аргументом типа. Посредством такой замены в этом случае создается три отдельных типобезопасных эффективных объекта, использующих одно определение класса. Дополнительные сведения о том, как в среде CLR реализуется эта замена, см. в разделе [Универсальные типы во время выполнения](../../../csharp/programming-guide/generics/generics-in-the-run-time.md).  
  
## <a name="type-parameter-naming-guidelines"></a>Правила именования параметра типа  
  
-   **Присваивайте** параметрам универсального типа описательные имена, кроме случаев, когда достаточно одной буквы и описательное имя не имеет практической ценности.  
  
     [!code-csharp[csProgGuideGenerics#8](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-type-parameters_2.cs)]  
  
-   **Используйте** имя параметра типа T для типов, содержащих только однобуквенный параметр типа.  
  
     [!code-csharp[csProgGuideGenerics#9](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-type-parameters_3.cs)]  
  
-   **Используйте** префикс "T" для описательных имен параметров типа.  
  
     [!code-csharp[csProgGuideGenerics#10](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-type-parameters_4.cs)]  
  
-   **Указывайте** ограничения, связанные с параметром типа, в его имени. Например, параметр с ограничением `ISession` может называться `TSession`.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Collections.Generic>  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Универсальные шаблоны](../../../csharp/programming-guide/generics/index.md)  
 [Различия между шаблонами языка C++ и универсальными шаблонами языка C#](../../../csharp/programming-guide/generics/differences-between-cpp-templates-and-csharp-generics.md)
