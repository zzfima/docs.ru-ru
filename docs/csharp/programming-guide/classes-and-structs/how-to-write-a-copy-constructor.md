---
title: Практическое руководство. Создание конструктора копии (Руководство по программированию в C#)
ms.date: 07/20/2015
helpviewer_keywords:
- C# Language, copy constructor
- copy constructor [C#]
ms.assetid: fba899b5-fc41-428e-a745-3ebdbf37990a
ms.openlocfilehash: d6ecfc3659dcf533db0f4e7b67fdffd620a584fd
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "48582337"
---
# <a name="how-to-write-a-copy-constructor-c-programming-guide"></a>Практическое руководство. Создание конструктора копии (Руководство по программированию в C#)
В C# не предусмотрен конструктор копии для объектов, однако его можно написать самостоятельно.  
  
## <a name="example"></a>Пример  
 В следующем примере [класс](../../../csharp/language-reference/keywords/class.md) `Person` определяет конструктор копии, который использует экземпляр `Person`в качестве аргумента. Значения свойств аргумента присваиваются свойствам нового экземпляра `Person`. Код содержит дополнительный конструктор копии, который отправляет свойства `Name` и `Age` экземпляра, который необходимо скопировать конструктору экземпляра класса.  
  
 [!code-csharp[csProgGuideObjects#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-write-a-copy-constructor_1.cs)]  
  
## <a name="see-also"></a>См. также

- <xref:System.ICloneable>  
- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
- [Классы и структуры](../../../csharp/programming-guide/classes-and-structs/index.md)  
- [Конструкторы](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
- [Методы завершения](../../../csharp/programming-guide/classes-and-structs/destructors.md)
