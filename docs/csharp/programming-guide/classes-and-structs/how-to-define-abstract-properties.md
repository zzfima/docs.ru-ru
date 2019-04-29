---
title: Практическое руководство. Определение абстрактных свойств (Руководство по программированию на C#)
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- properties [C#], abstract
- abstract properties [C#]
ms.assetid: 672a90eb-47b9-4ae0-9914-af53852fddcb
ms.openlocfilehash: 98a535f68efc50c2ff7409d8eadf52f9e7549566
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/01/2019
ms.locfileid: "57201954"
---
# <a name="how-to-define-abstract-properties-c-programming-guide"></a>Практическое руководство. Определение абстрактных свойств (Руководство по программированию на C#)
В следующем примере показано, как определять [абстрактные](../../../csharp/language-reference/keywords/abstract.md) свойства. В объявлении абстрактного свойства не предоставляется реализация методов доступа к свойству. В нем объявляется, что класс поддерживает свойства, однако реализация методов доступа к ним передается в производные классы. В следующем примере показано, как реализовать абстрактные свойства, наследуемые от базового класса.  
  
 Этот пример включает три файла, каждый из которых компилируется отдельно в сборку, на которую задаются ссылки при последующей компиляции:  
  
-   abstractshape.cs: класс `Shape`, который содержит абстрактное свойство `Area`.  
  
-   shapes.cs: подклассы класса `Shape`.  
  
-   shapetest.cs: тестовая программа для отображения областей некоторых объектов, производных от `Shape`.  
  
 Чтобы скомпилировать этот пример, используйте следующую команду:  
  
 `csc abstractshape.cs shapes.cs shapetest.cs`  
  
 При этом будет создан исполняемый файл shapetest.exe.  
  
## <a name="example"></a>Пример  
 В этом файле объявляется класс `Shape`, который содержит свойство `Area` типа `double`.  
  
 [!code-csharp[csProgGuideInheritance#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#1)]  
  
-   Модификаторы свойства помещаются в само объявление свойства. Например:  
  
    ```csharp  
    public abstract double Area  
    ```  
  
-   При объявлении абстрактного свойства, такого как `Area` в этом примере, вы просто указываете используемые методы доступа, но не реализуете их. В этом примере используется только метод доступа [get](../../../csharp/language-reference/keywords/get.md), поэтому свойство будет доступно только для чтения.  
  
## <a name="example"></a>Пример  
 В следующем коде представлены три подкласса класса `Shape` и демонстрируется, как они переопределяют свойство `Area` для получения его собственной реализации.  
  
 [!code-csharp[csProgGuideInheritance#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#2)]  
  
## <a name="example"></a>Пример  
 В следующем коде показана тестовая программа, которая создает несколько производных от `Shape` объектов и печатает их области.  
  
 [!code-csharp[csProgGuideInheritance#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#3)]  
  
## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)
- [Классы и структуры](../../../csharp/programming-guide/classes-and-structs/index.md)
- [Абстрактные и запечатанные классы и члены классов](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md)
- [Свойства](../../../csharp/programming-guide/classes-and-structs/properties.md)
- [Практическое руководство. Создание и использование сборок с помощью командной строки](../concepts/assemblies-gac/how-to-create-and-use-assemblies-using-the-command-line.md)
