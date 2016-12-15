---
title: "Поля (Руководство по программированию в C#) | Microsoft Docs"
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
  - "поля [C#]"
ms.assetid: 3cbb2f61-75f8-4cce-b4ef-f5d1b3de0db7
caps.latest.revision: 29
caps.handback.revision: 29
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Поля (Руководство по программированию в C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Переменная *field* имеет любой тип, непосредственно объявленный в [классе](../../../csharp/language-reference/keywords/class.md) или [структуре](../../../csharp/language-reference/keywords/struct.md).  Поля являются *членами* содержащихся в них типов.  
  
 Класс или структура могут иметь поля экземпляра или статические поля, либо поля обоих типов.  Поля экземпляра определяются экземпляром типа.  Если имеется класс T и поле экземпляра F, можно создать два объекта типа T и изменить значение поля F в каждом объекте, не изменяя значение в другом объекте.  В противоположность этому, статическое поле относится к самому классу, и является общим для всех экземпляров этого класса.  Изменения, выполненные из экземпляра А, будут немедленно видны экземплярам В и С, если они обращаются к полю.  
  
 Как правило, используются поля только для переменных, имеющих доступность private или protected.  Данные, которые класс представляют клиентскому коду, должны обеспечиваться [методами](../../../csharp/programming-guide/classes-and-structs/methods.md), [свойствами](../../../csharp/programming-guide/classes-and-structs/properties.md) и [индексаторами](../../../csharp/programming-guide/indexers/index.md).  Используя эти конструкции для косвенного доступа к внутренним полям, можно защититься от недопустимых входных значений.  Закрытое поле, которое хранит данные, представленные открытым свойством, называется *резервным хранилищем* или *резервным полем*.  
  
 Поля обычно хранят данные, которые должны быть доступными нескольким методам класса и должны храниться дольше, чем время существования любого отдельного метода.  Например, в классе, представляющем календарную дату, может быть три целочисленных поля: одно для месяца, одно для числа, одно для года.  Переменные, не используемые вне области одного метода, должны быть объявлены как *локальные переменные* внутри самого тела метода.  
  
 Поля объявляются в блоке класса путем указания уровня доступа поля, за которым следует тип поля и имя поля.  Примеры.  
  
 [!code-cs[csProgGuideObjects#61](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/fields_1.cs)]  
  
 Для доступа к члену объекта нужно добавить точку после имени объекта и указать имя поля: `objectname.fieldname`.  Примеры.  
  
 [!code-cs[csProgGuideObjects#62](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/fields_2.cs)]  
  
 Полю можно назначить первоначальное значение, используя оператор присвоения при объявлении поля.  Например, чтобы автоматически присвоить полю `day` значение `"Monday"`, можно объявить поле `day` как указано в следующем примере:  
  
 [!code-cs[csProgGuideObjects#63](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/fields_3.cs)]  
  
 Поля инициализируются непосредственно перед вызовом конструктора для экземпляра объекта.  Если конструктор присваивает полю значение, оно заменит значения, присвоенные при объявлении поля.  Дополнительные сведения см. в разделе [Использование конструкторов](../../../csharp/programming-guide/classes-and-structs/using-constructors.md).  
  
> [!NOTE]
>  Инициализатор поля не может ссылаться на другие поля экземпляров.  
  
 Поля могут быть отмечены модификаторами [public](../../../csharp/language-reference/keywords/public.md), [private](../../../csharp/language-reference/keywords/private.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md) или `protected internal`.  Эти модификаторы доступа определяют порядок доступа к полю для пользователей класса.  Дополнительные сведения см. в разделе [Модификаторы доступа](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).  
  
 Также при необходимости поле может быть объявлено с модификатором [static](../../../csharp/language-reference/keywords/static.md).  При этом поле становится доступным для вызова в любое время, даже экземпляр класса отсутствует.  Дополнительные сведения см. в разделе [Статические классы и члены статических классов](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).  
  
 Также при необходимости поле может быть объявлено с модификатором [readonly](../../../csharp/language-reference/keywords/readonly.md).  Полю с этим модификатором \(то есть полю, доступному только для чтения\) значения могут быть присвоены только при инициализации или в конструкторе.  Поле с модификаторами `static` `readonly` \(статическое, доступное только для чтения\) очень похоже на константу, за исключением того, что компилятор C\# не имеет доступа к значению такого поля при компиляции: доступ возможен только во время выполнения.  Дополнительные сведения см. в разделе [Константы](../../../csharp/programming-guide/classes-and-structs/constants.md).  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Классы и структуры](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [Использование конструкторов](../../../csharp/programming-guide/classes-and-structs/using-constructors.md)   
 [Наследование](../../../csharp/programming-guide/classes-and-structs/inheritance.md)   
 [Модификаторы доступа](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)   
 [Абстрактные и запечатанные классы и члены классов](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md)