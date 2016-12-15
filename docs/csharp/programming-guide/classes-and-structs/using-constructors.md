---
title: "Использование конструкторов (Руководство по программированию на C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "конструкторы [C#], сведения о конструкторах"
ms.assetid: 464253b2-fd5d-469a-836d-df0fdf2a43f7
caps.latest.revision: 26
caps.handback.revision: 26
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Использование конструкторов (Руководство по программированию на C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Если [класс](../../../csharp/language-reference/keywords/class.md) или [структура](../../../csharp/language-reference/keywords/struct.md) создаются, вызывают его конструктора.  Конструкторы имеют то же имя, что и класс или структура, и они обычно инициализирует элементы данных нового объекта.  
  
 В следующем примере класс `Taxi` определяется с помощью простого конструктора.  После этого с помощью оператора [new](../../../csharp/language-reference/keywords/new.md) создается экземпляр класса.  Конструктор `Taxi` вызывается оператором `new` сразу после выделения памяти для нового объекта.  
  
 [!code-cs[csProgGuideObjects#53](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_1.cs)]  
  
 Конструктор без параметров называется *конструктором по умолчанию*.  Конструкторы по умолчанию вызываются при создании экземпляров объекта с помощью оператора `new`, при этом для оператора `new` не указываются аргументы.  Для получения дополнительной информации см. [Конструкторы экземпляров](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md).  
  
 Компилятор C\# предоставляет классам без конструкторов открытый конструктор по умолчанию, чтобы обеспечить создание экземпляров класса, если класс не является [статическим](../../../csharp/language-reference/keywords/static.md).  Для получения дополнительной информации см. [Статические классы и члены статических классов](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).  
  
 Чтобы не допустить создание экземпляров класса, можно сделать конструктор закрытым:  
  
 [!code-cs[csProgGuideObjects#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_2.cs)]  
  
 Для получения дополнительной информации см. [Закрытые конструкторы](../../../csharp/programming-guide/classes-and-structs/private-constructors.md).  
  
 Конструкторы для типов [структур](../../../csharp/language-reference/keywords/struct.md) похожи на конструкторы классов, но `structs` не могут содержать явно указанный конструктор по умолчанию, поскольку такой конструктор автоматически предоставляется компилятором.  Этот конструктор инициализирует все поля в `struct` их значениями по умолчанию.  Для получения дополнительной информации см. [Таблица значений по умолчанию](../../../csharp/language-reference/keywords/default-values-table.md).  Однако конструктор по умолчанию вызывается только в том случае, если создается экземпляр `struct` при помощи оператора `new`.  Например, следующий код использует конструктор по умолчанию для <xref:System.Int32> таким образом, чтобы гарантировать инициализацию целочисленного значения.  
  
```  
int i = new int();  
Console.WriteLine(i);  
```  
  
 Однако в следующем коде возникает ошибка компилятора, поскольку оператор `new` не используется и в коде совершается попытка использовать объект, который не был инициализирован.  
  
```  
int i;  
Console.WriteLine(i);  
```  
  
 Также можно инициализировать или присваивать объекты, основанные на `structs` \(включая все встроенные числовые типы\), и затем использовать их, как показано в следующем примере.  
  
```  
int a = 44;  // Initialize the value type...  
int b;  
b = 33;      // Or assign it before using it.  
Console.WriteLine("{0}, {1}", a, b);  
```  
  
 Поэтому вызов конструктора по умолчанию для типа значения не требуется.  
  
 Классы и `structs` могут определять конструкторы, использующие параметры.  Конструкторы, использующие параметры, нужно вызывать с помощью операторов `new` или [base](../../../csharp/language-reference/keywords/base.md).  Классы и `structs` также могут определять несколько конструкторов; они не требуются для определения конструктора по умолчанию.  Например:  
  
 [!code-cs[csProgGuideObjects#54](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_3.cs)]  
  
 Этот класс можно создать с помощью любого из следующих операторов:  
  
 [!code-cs[csProgGuideObjects#55](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_4.cs)]  
  
 Конструктор может использовать ключевое слово `base` для вызова конструктора базового класса.  Например:  
  
 [!code-cs[csProgGuideObjects#56](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_5.cs)]  
  
 В этом примере конструктор базового класса вызывается перед выполнением блока конструктора.  Ключевое слово `base` можно использовать как с параметрами, так и без них.  Любые параметры конструктора можно указывать для оператора `base` или в составе выражения.  Для получения дополнительной информации см. [базовые](../../../csharp/language-reference/keywords/base.md).  
  
 Если конструктор базового класса не вызывается явным образом в производном классе при помощи ключевого слова `base`, то вызывается конструктор по умолчанию, если он существует.  Это означает, что следующие объявления конструкторов действуют одинаково:  
  
 [!code-cs[csProgGuideObjects#58](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_6.cs)]  
  
 [!code-cs[csProgGuideObjects#57](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_7.cs)]  
  
 Если в базовом классе нет конструктора по умолчанию, производный класс должен сделать явный вызов базового конструктора при помощи ключевого слова `base`.  
  
 Конструктор может вызывать в том же самом объекте другой конструктор с помощью ключевого слова [this](../../../csharp/language-reference/keywords/this.md).  Как и `base`, ключевое слово `this` можно использовать с параметрами или без параметрами, а все параметры конструктора доступны в качестве параметров `this` или в составе выражения.  Например, второй конструктор в предыдущем примере можно переписать с помощью `this`:  
  
 [!code-cs[csProgGuideObjects#59](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_8.cs)]  
  
 Использование ключевого слова `this` в предыдущем примере приводит к вызову этого конструктора:  
  
 [!code-cs[csProgGuideObjects#60](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_9.cs)]  
  
 Конструкторы могут быть отмечены модификаторами [public](../../../csharp/language-reference/keywords/public.md) \(открытый\), [private](../../../csharp/language-reference/keywords/private.md) \(закрытый\), [protected](../../../csharp/language-reference/keywords/protected.md) \(защищенный\), [internal](../../../csharp/language-reference/keywords/internal.md) \(внутренний\) или `protected` `internal` \(защищенный внутренний\).  Эти модификаторы доступа определяют порядок доступа пользователей класса к конструкторам класса.  Дополнительные сведения см. в разделе [Модификаторы доступа](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).  
  
 Конструктор можно объявить статическим при помощи ключевого слова [static](../../../csharp/language-reference/keywords/static.md).  Статические конструкторы вызываются автоматически непосредственно перед доступом к статическим полям и обычно служат для инициализации членов статического класса.  Дополнительные сведения см. в разделе [Статические конструкторы](../../../csharp/programming-guide/classes-and-structs/static-constructors.md).  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Классы и структуры](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [Конструкторы](../../../csharp/programming-guide/classes-and-structs/constructors.md)   
 [Деструкторы](../../../csharp/programming-guide/classes-and-structs/destructors.md)