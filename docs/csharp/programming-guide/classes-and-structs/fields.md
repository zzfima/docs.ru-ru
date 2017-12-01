---
title: "Поля (Руководство по программированию в C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: fields [C#]
ms.assetid: 3cbb2f61-75f8-4cce-b4ef-f5d1b3de0db7
caps.latest.revision: "29"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: acf4ade68235a196fd6d2f3c6c71279748f3dd71
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="fields-c-programming-guide"></a>Поля (Руководство по программированию в C#)
*Поле* является переменной любого типа, которая объявлена непосредственно в [классе](../../../csharp/language-reference/keywords/class.md) или [структуре](../../../csharp/language-reference/keywords/struct.md). Поля являются *членами* содержащих их типов.  
  
 Класс или структура может иметь поля экземпляра или статические поля. Поля экземпляра относятся только к экземпляру типа. Если имеется класс T с полем экземпляра F, можно создать два объекта типа T и изменить значение F в каждом объекте, не влияя на значение в другом объекте. Напротив, статическое поле принадлежит к самому классу и является общим для всех экземпляров этого класса. Изменения, выполненные из экземпляра A, будут немедленно доступны экземплярам B и C, если они получат доступ к полю.  
  
 Как правило, следует использовать поля только для переменных, являющихся закрытыми или защищенными. Данные, которые класс представляет клиентскому коду, должны предоставляться через [методы](../../../csharp/programming-guide/classes-and-structs/methods.md), [свойства](../../../csharp/programming-guide/classes-and-structs/properties.md) и [индексаторы](../../../csharp/programming-guide/indexers/index.md). Используя эти конструкции для косвенного доступа к внутренним полям, можно предотвратить использование недопустимых входных значений. Закрытое поле, которое хранит данные, представленные открытым свойством, называется *резервным хранилищем* или *резервным полем*.  
  
 Как правило, поля хранят данные, которые должны быть доступны нескольким методам класса и храниться дольше, чем время существования любого отдельного метода. Например, класс, представляющий календарную дату, может иметь три целочисленных поля: одно для месяца, одно для числа и одно для года. Переменные, не используемые вне области одного метода, должны быть объявлены как *локальные переменные* в самом теле метода.  
  
 Поля объявляются в блоке класса путем указания уровня доступа поля, за которым следует тип поля, а затем имя поля. Пример:  
  
 [!code-csharp[csProgGuideObjects#61](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/fields_1.cs)]  
  
 Для доступа к полю в объекте добавьте точку после имени объекта, за которой следует имя поля, как в `objectname.fieldname`. Пример:  
  
 [!code-csharp[csProgGuideObjects#62](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/fields_2.cs)]  
  
 Полю можно присвоить начальное значение с помощью оператора присваивания при объявлении поля. Чтобы автоматически назначить поле `day`, например полю `"Monday"`, нужно объявить `day`, как в следующем примере:  
  
 [!code-csharp[csProgGuideObjects#63](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/fields_3.cs)]  
  
 Поля инициализируются непосредственно перед вызовом конструктора для экземпляра объекта. Если конструктор присваивает значение поля, он заменит значения, присвоенные при объявлении поля. Дополнительные сведения см. в разделе [Использование конструкторов](../../../csharp/programming-guide/classes-and-structs/using-constructors.md).  
  
> [!NOTE]
>  Инициализатор поля не может ссылаться на другие поля экземпляров.  
  
 Поля могут быть помечены как [открытый](../../../csharp/language-reference/keywords/public.md), [закрытый](../../../csharp/language-reference/keywords/private.md), [защищенных](../../../csharp/language-reference/keywords/protected.md), [внутренней](../../../csharp/language-reference/keywords/internal.md), [защищенные внутренние](../../../csharp/language-reference/keywords/protected-internal.md) или [private protected](../../../csharp/language-reference/keywords/private-protected.md). Эти модификаторы доступа определяют, каким образом пользователи класса смогут получать доступ к полю. Дополнительные сведения см. в разделе [Модификаторы доступа](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).  
  
 При необходимости можно объявить поле статическим ([static](../../../csharp/language-reference/keywords/static.md)). Это делает поле доступным для вызывающих объектов в любое время, даже если экземпляр класса не существует. Дополнительные сведения см. в разделе [Статические классы и члены статических классов](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).  
  
 Поле может быть объявлено доступным только для чтения ([readonly](../../../csharp/language-reference/keywords/readonly.md)). Полю только для чтения можно присвоить значение только во время инициализации или в конструкторе. Поле `static``readonly` очень похоже на константу, за исключением того, что компилятор C# не имеет доступа к значению статического поля только для чтения во время компиляции, но только во время выполнения. Дополнительные сведения см. в разделе [Константы](../../../csharp/programming-guide/classes-and-structs/constants.md).  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Классы и структуры](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [Использование конструкторов](../../../csharp/programming-guide/classes-and-structs/using-constructors.md)  
 [Наследование](../../../csharp/programming-guide/classes-and-structs/inheritance.md)  
 [Модификаторы доступа](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)  
 [Абстрактные и запечатанные классы и члены классов](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md)
