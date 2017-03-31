---
title: "abstract (справочник по C#) | Документы Майкрософт"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- abstract
- abstract_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- abstract keyword [C#]
ms.assetid: b0797770-c1f3-4b4d-9441-b9122602a6bb
caps.latest.revision: 24
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
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: acb9c5748addd75f741e97688fca707910b042a0
ms.lasthandoff: 03/13/2017

---
# <a name="abstract-c-reference"></a>abstract (Справочник по C#)
Модификатор `abstract` указывает, что изменяемый элемент имеет отсутствующую или неполную реализацию. Модификатор abstract можно использовать с классами, методами, свойствами, индексаторами и событиями. Модификатор `abstract` в определении класса позволяет указать, что класс может быть только базовым классом для других классов. Члены, помеченные как абстрактные или включенные в абстрактный класс, должны быть реализованы классами, производными от абстрактного класса.  
  
## <a name="example"></a>Пример  
 В этом примере класс `Square` должен обеспечивать реализацию `Area`, поскольку является производным от класса `ShapesClass`:  
  
 [!code-cs[csrefKeywordsModifiers#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/abstract_1.cs)]  
  
 Абстрактные классы предоставляют следующие возможности:  
  
-   Создавать экземпляры абстрактного класса нельзя.  
  
-   Абстрактный класс может содержать абстрактные методы и методы доступа.  
  
-   Изменить абстрактный класс с модификатором [sealed](../../../csharp/language-reference/keywords/sealed.md) нельзя, поскольку два этих модификатора имеют взаимоисключающие значения. Модификатор `sealed` запрещает наследование класса, в то время как модификатор `abstract` указывает, что класс обязан иметь производные классы.  
  
-   Неабстрактный класс, производный от абстрактного класса, должен включать фактические реализации всех наследуемых абстрактных методов и методов доступа.  
  
 Модификатор `abstract` в объявлении метода или свойства позволяет указать, что этот метод или свойство не содержат реализации.  
  
 Абстрактные методы предоставляют следующие возможности:  
  
-   Абстрактный метод неявно представляет собой виртуальный метод.  
  
-   Объявления абстрактных методов допускаются только в абстрактных классах.  
  
-   Поскольку объявление абстрактного метода не предоставляет фактической реализации, тело метода отсутствует, а объявление метода заканчивается точкой с запятой, и фигурных скобок ({ }) после подписи нет. Пример:  
  
    ```  
    public abstract void MyMethod();  
    ```  
  
     Реализация предоставляется методом переопределения [override](../../../csharp/language-reference/keywords/override.md), который является членом неабстрактного класса.  
  
-   В объявлении абстрактного метода нельзя использовать [статические](../../../csharp/language-reference/keywords/static.md) или [виртуальные](../../../csharp/language-reference/keywords/virtual.md) модификаторы.  
  
 Действие абстрактных свойств аналогично абстрактным методам, за исключением отличий в синтаксисе объявлений и вызовов.  
  
-   Использование модификатора `abstract` в статическом свойстве является недопустимым.  
  
-   Абстрактное наследуемое свойство можно переопределить в производном классе, включив объявление свойства, которое использует модификатор [override](../../../csharp/language-reference/keywords/override.md).  
  
 Дополнительные сведения об абстрактных классах см. в разделе [Абстрактные и запечатанные классы и члены классов](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md).  
  
 Абстрактный класс должен предоставлять реализацию для всех членов интерфейса.  
  
 Абстрактный класс, реализующий интерфейс, может сопоставлять методы интерфейса с абстрактными методами. Например:  
  
 [!code-cs[csrefKeywordsModifiers#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/abstract_2.cs)]  
  
## <a name="example"></a>Пример  
 В следующем примере класс `DerivedClass` является производным от абстрактного класса `BaseClass`. Абстрактный класс содержит абстрактный метод, `AbstractMethod`, и два абстрактных свойства, `X` и `Y`.  
  
 [!code-cs[csrefKeywordsModifiers#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/abstract_3.cs)]  
  
 В предыдущем примере при попытке создать экземпляр абстрактного класса с помощью оператора вида:  
  
```  
BaseClass bc = new BaseClass();   // Error  
```  
  
 выдается сообщение об ошибке, указывающее, что компилятор не может создать экземпляр абстрактного класса BaseClass.  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Модификаторы](../../../csharp/language-reference/keywords/modifiers.md)   
 [virtual](../../../csharp/language-reference/keywords/virtual.md)   
 [override](../../../csharp/language-reference/keywords/override.md)   
 [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)
