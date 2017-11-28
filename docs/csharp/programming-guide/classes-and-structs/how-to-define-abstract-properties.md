---
title: "Практическое руководство. Определение абстрактных свойств (Руководство по программированию в C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- properties [C#], abstract
- abstract properties [C#]
ms.assetid: 672a90eb-47b9-4ae0-9914-af53852fddcb
caps.latest.revision: "13"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: cd8a42c1040180c19bc58627ab0c6a21ace77773
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-define-abstract-properties-c-programming-guide"></a>Практическое руководство. Определение абстрактных свойств (Руководство по программированию в C#)
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
  
 [!code-csharp[csProgGuideInheritance#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-define-abstract-properties_1.cs)]  
  
-   Модификаторы свойства помещаются в само объявление свойства. Например:  
  
    ```  
    public abstract double Area  
    ```  
  
-   При объявлении абстрактного свойства, такого как `Area` в этом примере, вы просто указываете используемые методы доступа, но не реализуете их. В этом примере используется только метод доступа [get](../../../csharp/language-reference/keywords/get.md), поэтому свойство будет доступно только для чтения.  
  
## <a name="example"></a>Пример  
 В следующем коде представлены три подкласса класса `Shape` и демонстрируется, как они переопределяют свойство `Area` для получения его собственной реализации.  
  
 [!code-csharp[csProgGuideInheritance#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-define-abstract-properties_2.cs)]  
  
## <a name="example"></a>Пример  
 В следующем коде показана тестовая программа, которая создает несколько производных от `Shape` объектов и печатает их области.  
  
 [!code-csharp[csProgGuideInheritance#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-define-abstract-properties_3.cs)]  
  
## <a name="see-also"></a>См. также  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Классы и структуры](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [Абстрактные и запечатанные классы и члены классов](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md)  
 [Свойства](../../../csharp/programming-guide/classes-and-structs/properties.md)  
 [Практическое руководство. Создание и использование сборок с помощью командной строки](http://msdn.microsoft.com/library/70f65026-3687-4e9c-ab79-c18b97dd8be4)
