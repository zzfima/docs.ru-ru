---
title: Структуры (Руководство по программированию на C#)
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, structs
- structs [C#]
ms.assetid: b7cf4ff2-0eb7-4e5c-93d5-b2196b4f5d89
ms.openlocfilehash: ffb5b8da6c72056620cf890f38af4e7a8116ab3e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33322992"
---
# <a name="structs-c-programming-guide"></a>Структуры (Руководство по программированию на C#)
Структуры определяются с помощью ключевого слова [struct](../../../csharp/language-reference/keywords/struct.md), например:  
  
 [!code-csharp[csProgGuideObjects#39](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/structs_1.cs)]  
  
 Структуры используют большую часть того же синтаксиса, что и классы, однако они более ограничены по сравнению с ними.  
  
-   В объявлении структуры поля не могут быть инициализированы до тех пор, пока они будут объявлены как const или static.  
  
-   Структура не может объявлять используемый по умолчанию конструктор (конструктор без параметров) или метод завершения.  
  
-   Структуры копируются при присваивании. При присваивании структуры к новой переменной выполняется копирование всех данных, а любое изменение новой копии не влияет на данные в исходной копии. Это важно помнить при работе с коллекциями типов значений, такими как Dictionary\<string, myStruct>.  
  
-   Структуры являются типами значений, а классы — ссылочными типами.  
  
-   В отличие от классов структуры можно создавать без использования оператора `new`.  
  
-   Структуры могут объявлять конструкторы, имеющие параметры.  
  
-   Структура не может наследовать от другой структуры или класса и не может быть базовой для класса. Все структуры наследуют непосредственно от `System.ValueType`, который наследует от `System.Object`.  
  
-   Структуры могут реализовывать интерфейсы.  
  
-   Структура может использоваться как тип, допускающий значение NULL, и ей можно назначить значение NULL.  
  
## <a name="related-sections"></a>Связанные разделы  
 Дополнительные сведения:  
  
-   [Использование структур](../../../csharp/programming-guide/classes-and-structs/using-structs.md)  
  
-   [Конструкторы](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
  
-   [Типы, допускающие значения NULL](../../../csharp/programming-guide/nullable-types/index.md)  
  
-   [Практическое руководство. Определение различия между передачей структуры и ссылки класса в метод](../../../csharp/programming-guide/classes-and-structs/how-to-know-the-difference-passing-a-struct-and-passing-a-class-to-a-method.md)  
  
-   [Практическое руководство. Реализация определенных пользователем преобразований между структурами](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)  
  
## <a name="see-also"></a>См. также  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Классы и структуры](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [Классы](../../../csharp/programming-guide/classes-and-structs/classes.md)
