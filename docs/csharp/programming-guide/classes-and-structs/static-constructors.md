---
title: "Статические конструкторы (Руководство по программированию в C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- static constructors [C#]
- constructors [C#], static
ms.assetid: 151ec95e-3c4d-4ed7-885d-95b7a3be2e7d
caps.latest.revision: "23"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: ee5448095cf06c2473c94bae542c02557918271a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="static-constructors-c-programming-guide"></a>Статические конструкторы (Руководство по программированию в C#)
Статический конструктор используется для инициализации любых [статических](../../../csharp/language-reference/keywords/static.md) данных или для выполнения определенного действия, которое требуется выполнить только один раз. Он вызывается автоматически перед созданием первого экземпляра или ссылкой на какие-либо статические члены.  
  
 [!code-csharp[csProgGuideObjects#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/static-constructors_1.cs)]  
  
 Статические конструкторы обладают следующими свойствами.  
  
-   Статический конструктор не принимает модификаторы доступа и не имеет параметров.  
  
-   Статический конструктор вызывается автоматически для инициализации [класса](../../../csharp/language-reference/keywords/class.md) перед созданием первого экземпляра типа или ссылкой на какие-либо статические члены.  
  
-   Статический конструктор нельзя вызывать напрямую.  
  
-   Пользователь не управляет временем, в течение которого статический конструктор выполняется в программе.  
  
-   Типичным использованием статических конструкторов является случай, когда класс использует файл журнала и конструктор применяется для добавления записей в этот файл.  
  
-   Статические конструкторы также полезны при создании классов-оболочек для неуправляемого кода, когда конструктор может вызвать метод `LoadLibrary`.  
  
-   Если статический конструктор инициирует исключение, среда выполнения не вызывает его во второй раз, и тип остается неинициализированным на время существования домена приложения, в котором выполняется программа.  
  
## <a name="example"></a>Пример  
 В этом примере класс `Bus` имеет статический конструктор. При создании первого экземпляра класса `Bus` (`bus1`) для инициализации класса вызывается статический конструктор. В выходных данных этого примера можно увидеть, что статический конструктор выполняется только один раз, несмотря на то, что создается два экземпляра класса `Bus`. Кроме того, этот конструктор вызывается до выполнения конструктора экземпляра.  
  
 [!code-csharp[csProgGuideObjects#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/static-constructors_2.cs)]  
  
## <a name="see-also"></a>См. также  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Классы и структуры](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [Конструкторы](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
 [Статические классы и члены статических классов](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)  
 [Методы завершения](../../../csharp/programming-guide/classes-and-structs/destructors.md)
