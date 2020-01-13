---
title: virtual. Справочник по C#
ms.date: 07/20/2015
f1_keywords:
- virtual_CSharpKeyword
- virtual
helpviewer_keywords:
- virtual keyword [C#]
ms.assetid: 5da9abae-bc1e-434f-8bea-3601b8dcb3b2
ms.openlocfilehash: 47b77792fd3a2b2700ec0734851fdec534361596
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712875"
---
# <a name="virtual-c-reference"></a>virtual (Справочник по C#)

Ключевое слово `virtual` используется для изменения объявлений методов, свойств, индексаторов и событий и разрешения их переопределения в производном классе. Например, этот метод может быть переопределен любым наследующим его классом:

```csharp
public virtual double Area() 
{
    return x * y;
}
```

Реализацию виртуального члена можно изменить путем [переопределения члена](override.md) в производном классе. Дополнительные сведения об использовании ключевого слова `virtual` см. в разделах [Управление версиями с помощью ключевых слов Override и New](../../programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) и [Использование ключевых слов Override и New](../../programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).

## <a name="remarks"></a>Примечания

При вызове виртуального метода тип времени выполнения объекта проверяется на переопределение члена. Вызывается переопределение члена в самом дальнем классе. Это может быть исходный член, если никакой производный класс не выполнял переопределение этого члена.

По умолчанию методы не являются виртуальными. Такой метод переопределить невозможно.

Нельзя использовать модификатор `virtual` с модификаторами `static`, `abstract`, `private`, или `override`. В следующем примере показано виртуальное свойство.

[!code-csharp[csrefKeywordsModifiers#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#26)]

Действие виртуальных свойств аналогично виртуальным методам, за исключением отличий в синтаксисе объявлений и вызовов.

- Использование модификатора `virtual` в статическом свойстве является недопустимым.

- Виртуальное наследуемое свойство может быть переопределено в производном классе путем включения объявления свойства, которое использует модификатор `override`.

## <a name="example"></a>Пример

В этом примере класс `Shape` содержит две координаты `x`, `y` и виртуальный метод `Area()`. Различные классы фигур, такие как `Circle`, `Cylinder` и `Sphere`, наследуют класс `Shape`, и для каждой фигуры вычисляется площадь поверхности. Каждый производный класс обладает собственной реализацией переопределения метода `Area()`.

Обратите внимание, что наследуемые классы `Circle`, `Sphere` и `Cylinder` используют конструкторы, которые инициализируют базовый класс, как показано в следующем объявлении.

```csharp
public Cylinder(double r, double h): base(r, h) {}
```

Следующая программа вычисляет и отображает соответствующую область для каждой фигуры путем вызова нужной реализации метода `Area()` в соответствии с объектом, связанным с методом.

[!code-csharp[csrefKeywordsModifiers#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#23)]

## <a name="c-language-specification"></a>Спецификация языка C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>См. также

- [Полиморфизм](../../programming-guide/classes-and-structs/polymorphism.md)
- [abstract](abstract.md)
- [override](override.md)
- [new (модификатор)](new-modifier.md)
