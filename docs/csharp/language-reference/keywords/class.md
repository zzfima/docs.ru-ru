---
title: "класс (Справочник по C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "class_CSharpKeyword"
  - "class"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "class - ключевое слово [C#]"
ms.assetid: b95d8815-de18-4c3f-a8cc-a0a53bdf8690
caps.latest.revision: 30
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 30
---
# класс (Справочник по C#)
Классы объявляются с помощью ключевого слова `class`, как показано в следующем примере.  
  
```  
  
      class TestClass  
{  
    // Methods, properties, fields, events, delegates   
    // and nested classes go here.  
}  
```  
  
## Заметки  
 Только разрешено единичное наследование в C\-\#.  Другими словами, класс может наследовать реализацию только от одного базового класса.  Однако класс может реализовать несколько интерфейсов.  В приведенной ниже таблице приведены примеры наследования класса и реализации интерфейса.  
  
|Наследование|Пример|  
|------------------|------------|  
|None|`class ClassA { }`|  
|Single|`class DerivedClass: BaseClass { }`|  
|Отсутствует, реализует два интерфейса|`class ImplClass: IFace1, IFace2 { }`|  
|Одиночное, реализует один интерфейс|`class ImplDerivedClass: BaseClass, IFace1 { }`|  
  
 Классы, объявляемому непосредственно в пространстве имен, не вложенные в другие классы, могут быть [открытый](../../../csharp/language-reference/keywords/public.md) или [внутренний](../../../csharp/language-reference/keywords/internal.md).  Класс `internal` по умолчанию.  
  
 Члены класса, включая вложенные классы, могут быть `protected internal`, [открытый](../../../csharp/language-reference/keywords/public.md), [защищенный](../../../csharp/language-reference/keywords/protected.md), [внутренний](../../../csharp/language-reference/keywords/internal.md) или [закрытый](../../../csharp/language-reference/keywords/private.md).  Элементы [закрытый](../../../csharp/language-reference/keywords/private.md) по умолчанию.  
  
 Для получения дополнительной информации см. [Модификаторы доступа](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).  
  
 Можно объявить универсальные классы, имеющие параметры типа.  Дополнительные сведения см. в разделе [Универсальные классы](../../../csharp/programming-guide/generics/generic-classes.md).  
  
 Класс может содержать объявления следующих членов.  
  
-   [Конструкторы](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
  
-   [Деструкторы](../../../csharp/programming-guide/classes-and-structs/destructors.md)  
  
-   [Константы](../../../csharp/programming-guide/classes-and-structs/constants.md)  
  
-   [Поля](../../../csharp/programming-guide/classes-and-structs/fields.md)  
  
-   [Методы](../../../csharp/programming-guide/classes-and-structs/methods.md)  
  
-   [Свойства](../../../csharp/programming-guide/classes-and-structs/properties.md)  
  
-   [Indexers](../../../csharp/programming-guide/indexers/index.md)  
  
-   [Операторы](../../../csharp/programming-guide/statements-expressions-operators/operators.md)  
  
-   [События](../../../csharp/programming-guide/events/index.md)  
  
-   [Делегаты](../../../csharp/programming-guide/delegates/index.md)  
  
-   [Классы](../../../csharp/programming-guide/classes-and-structs/classes.md)  
  
-   [Интерфейсы](../../../csharp/programming-guide/interfaces/index.md)  
  
-   [Структуры](../../../csharp/programming-guide/classes-and-structs/structs.md)  
  
## Пример  
 В следующем примере показано объявление полей, конструкторов и методов классов.  В нем также демонстрируется создание объекта и печать данных экземпляра.  В этом примере объявляются два класса — класс `Child`, который содержит два закрытых поля \(`name` и `age`\) и два открытых метода.  Второй класс, `StringTest`, используется для хранения `Main`.  
  
 [!code-cs[csrefKeywordsTypes#5](../../../csharp/language-reference/keywords/codesnippet/csharp/class_1.cs)]  
  
## Комментарии  
 Обратите внимание, что в предыдущем примере доступ к закрытым полям \(`name` и `age`\) возможен только с помощью открытых методов класса `Child`.  Например, имя ребенка нельзя напечатать из метода `Main` с помощью следующего оператора.  
  
```  
Console.Write(child1.name);   // Error  
```  
  
 Получить доступ к закрытым членам класса `Child`из метода `Main` можно было бы лишь тогда, если бы `Main` был членом класса.  
  
 Типы, объявленные внутри класса без модификатора доступа не имеют по умолчанию значение `private`, поэтому элементы данных в этом примере по\-прежнему будет `private`, если ключевое слово было удалено.  
  
 И наконец, обратите внимание, что созданное для объекта с помощью конструктора по умолчанию \(`child3`\) поле "Возраст" по умолчанию было инициализировано с помощью нулевого значения.  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова C\#](../../../csharp/language-reference/keywords/index.md)   
 [Ссылочные типы](../../../csharp/language-reference/keywords/reference-types.md)