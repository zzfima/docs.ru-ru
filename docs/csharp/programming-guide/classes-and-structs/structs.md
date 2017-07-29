---
title: "Структуры (Руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- C# language, structs
- structs [C#]
ms.assetid: b7cf4ff2-0eb7-4e5c-93d5-b2196b4f5d89
caps.latest.revision: 31
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: ce12f402c0748ea6729c82e3f188c0a58f63d628
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="structs-c-programming-guide"></a>Структуры (Руководство по программированию на C#)
Структуры определяются с помощью ключевого слова [struct](../../../csharp/language-reference/keywords/struct.md), например:  
  
 [!code-cs[csProgGuideObjects#39](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/structs_1.cs)]  
  
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

