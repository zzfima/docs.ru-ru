---
title: "Члены (Руководство по программированию на C#) | Microsoft Docs"
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
  - "C# - язык, члены типа"
  - "типы [C#], вложенные типы"
ms.assetid: 4a30a4ab-d690-4936-9124-92ce9448665a
caps.latest.revision: 20
caps.handback.revision: 20
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Члены (Руководство по программированию на C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

В классах и структурах есть члены, представляющие их данные и поведение.  Члены класса включают все члены, объявленные в этом классе, а также все члены \(кроме конструкторов и деструкторов\), объявленные во всех классах в иерархии наследования данного класса.  Закрытые члены в базовых классах наследуются, но недоступны из производных классов.  
  
 В следующей таблице перечислены виды членов, которые могут содержаться в классе или в структуре.  
  
|Элемент|Описание|  
|-------------|--------------|  
|[Поля](../../../csharp/programming-guide/classes-and-structs/fields.md)|Поля являются переменными, объявленными в области класса.  Поле может иметь встроенный числовой тип или быть экземпляром другого класса.  Например, в классе календаря может быть поле, содержащее текущую дату.|  
|[Константы](../../../csharp/programming-guide/classes-and-structs/constants.md)|Константы — это поля или свойства, значения которых устанавливаются во время компиляции и не изменяются.|  
|[Свойства](../../../csharp/programming-guide/classes-and-structs/properties.md)|Свойства — это методы класса. Доступ к ним осуществляется так же, как если бы они были полями этого класса.  Свойство может защитить поле класса от изменений \(независимо от объекта\).|  
|[Методы](../../../csharp/programming-guide/classes-and-structs/methods.md)|Методы определяют действия, которые может выполнить класс.  Методы могут получать параметры, предоставляющие входные данные, и возвращать выходные данные посредством параметров.  Также методы могут возвращать значения напрямую, без использования параметров.|  
|[События](../../../csharp/programming-guide/events/index.md)|События предоставляют другим объектам уведомления о различных случаях, таких как нажатие кнопки или успешное выполнение метода.  События определяются и переключаются с помощью делегатов.|  
|[Операторы](../../../csharp/programming-guide/statements-expressions-operators/operators.md)|Перегруженные операторы рассматриваются как члены класса.  При перегрузке оператора его следует определить как открытый статический метод в классе.  Предопределенные операторы \(`+`, `*`, `<` и т. д.\) не считаются членами.  Для получения дополнительной информации см. [Перегружаемые операторы](../../../csharp/programming-guide/statements-expressions-operators/overloadable-operators.md).|  
|[Индексаторы](../../../csharp/programming-guide/indexers/index.md)|Индексаторы позволяют индексировать объекты аналогично массивам.|  
|[Конструкторы](../../../csharp/programming-guide/classes-and-structs/constructors.md)|Конструкторы — это методы классов, вызываемые при создании объекта заданного типа.  Зачастую они используются для инициализации данных объекта.|  
|[Деструкторы](../../../csharp/programming-guide/classes-and-structs/destructors.md)|Деструкторы очень редко используются в C\#.  Они являются методами, вызываемыми средой выполнения, когда объект нужно удалить из памяти.  Деструкторы обычно применяются для правильной обработке ресурсов, которые должны быть высвобождены.|  
|[Вложенные типы](../../../csharp/programming-guide/classes-and-structs/nested-types.md)|Вложенными типами являются типы, объявленные в другом типе.  Вложенные типы часто применяются для описания объектов, использующихся только типами, в которых эти объекты находятся.|  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Классы](../../../csharp/programming-guide/classes-and-structs/classes.md)   
 [Методы](../../../csharp/programming-guide/classes-and-structs/methods.md)   
 [Конструкторы](../../../csharp/programming-guide/classes-and-structs/constructors.md)   
 [Деструкторы](../../../csharp/programming-guide/classes-and-structs/destructors.md)   
 [Свойства](../../../csharp/programming-guide/classes-and-structs/properties.md)   
 [Поля](../../../csharp/programming-guide/classes-and-structs/fields.md)   
 [Индексаторы](../../../csharp/programming-guide/indexers/index.md)   
 [События](../../../csharp/programming-guide/events/index.md)   
 [Вложенные типы](../../../csharp/programming-guide/classes-and-structs/nested-types.md)   
 [Операторы](../../../csharp/programming-guide/statements-expressions-operators/operators.md)   
 [Перегружаемые операторы](../../../csharp/programming-guide/statements-expressions-operators/overloadable-operators.md)