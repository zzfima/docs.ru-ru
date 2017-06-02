---
title: "virtual (справочник по C#) | Документы Майкрософт"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- virtual_CSharpKeyword
- virtual
dev_langs:
- CSharp
helpviewer_keywords:
- virtual keyword [C#]
ms.assetid: 5da9abae-bc1e-434f-8bea-3601b8dcb3b2
caps.latest.revision: 26
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: e2268fcc3888bf4b3a30f5855a31bfafcbd3ca49
ms.contentlocale: ru-ru
ms.lasthandoff: 03/13/2017

---
# <a name="virtual-c-reference"></a>virtual (Справочник по C#)
Ключевое слово `virtual` используется для изменения объявлений методов, свойств, индексаторов и событий и разрешения их переопределения в производном классе. Например, этот метод может быть переопределен любым наследующим его классом:  
  
```  
public virtual double Area()   
{  
    return x * y;  
}  
```  
  
 Реализацию виртуального члена можно изменить путем [переопределения члена](../../../csharp/language-reference/keywords/override.md) в производном классе. Дополнительные сведения об использовании ключевого слова `virtual` см. в разделах [Управление версиями с помощью ключевых слов Override и New](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) и [Использование ключевых слов Override и New](../../../csharp/programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).  
  
## <a name="remarks"></a>Примечания  
 При вызове виртуального метода тип времени выполнения объекта проверяется на переопределение члена. Вызывается переопределение члена в самом дальнем классе. Это может быть исходный член, если никакой производный класс не выполнял переопределение этого члена.  
  
 По умолчанию методы не являются виртуальными. Такой метод переопределить невозможно.  
  
 Модификатор `virtual` нельзя использовать с модификаторами `static`, `abstract, private` или `override`. В следующем примере показано виртуальное свойство.  
  
 [!code-cs[csrefKeywordsModifiers#26](../../../csharp/language-reference/keywords/codesnippet/CSharp/virtual_1.cs)]  
  
 Действие виртуальных свойств аналогично абстрактным методам, за исключением отличий в синтаксисе объявлений и вызовов.  
  
-   Использование модификатора `virtual` в статическом свойстве является недопустимым.  
  
-   Виртуальное наследуемое свойство может быть переопределено в производном классе путем включения объявления свойства, которое использует модификатор `override`.  
  
## <a name="example"></a>Пример  
 В этом примере класс `Shape` содержит две координаты `x`, `y` и виртуальный метод `Area()`. Различные классы фигур, такие как `Circle`, `Cylinder` и `Sphere`, наследуют класс `Shape`, и для каждой фигуры вычисляется площадь поверхности. Каждый производный класс обладает собственной реализацией переопределения метода `Area()`.  
  
 Обратите внимание, что наследуемые классы `Circle`, `Sphere` и `Cylinder` используют конструкторы, которые инициализируют базовый класс, как показано в следующем объявлении.  
  
```  
public Cylinder(double r, double h): base(r, h) {}  
```  
  
 Следующая программа вычисляет и отображает соответствующую область для каждой фигуры путем вызова нужной реализации метода `Area()` в соответствии с объектом, связанным с методом.  
  
 [!code-cs[csrefKeywordsModifiers#23](../../../csharp/language-reference/keywords/codesnippet/CSharp/virtual_2.cs)]  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Модификаторы](../../../csharp/language-reference/keywords/modifiers.md)   
 [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)   
 [Полиморфизм](../../../csharp/programming-guide/classes-and-structs/polymorphism.md)   
 [abstract](../../../csharp/language-reference/keywords/abstract.md)   
 [override](../../../csharp/language-reference/keywords/override.md)   
 [new](../../../csharp/language-reference/keywords/new.md)
