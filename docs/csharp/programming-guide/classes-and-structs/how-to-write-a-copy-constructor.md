---
title: Практическое руководство. Создание конструктора копий (руководство по программированию на C#)
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- C# Language, copy constructor
- copy constructor [C#]
ms.assetid: fba899b5-fc41-428e-a745-3ebdbf37990a
ms.openlocfilehash: bdc352566052f4cec1686176131e9b1e1b768794
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2019
ms.locfileid: "69596601"
---
# <a name="how-to-write-a-copy-constructor-c-programming-guide"></a>Практическое руководство. Создание конструктора копий (руководство по программированию на C#)
В C# не предусмотрен конструктор копии для объектов, однако его можно написать самостоятельно.  
  
## <a name="example"></a>Пример  
 В следующем примере [класс](../../language-reference/keywords/class.md) `Person` определяет конструктор копии, который использует экземпляр `Person`в качестве аргумента. Значения свойств аргумента присваиваются свойствам нового экземпляра `Person`. Код содержит дополнительный конструктор копии, который отправляет свойства `Name` и `Age` экземпляра, который необходимо скопировать конструктору экземпляра класса.  
  
 [!code-csharp[csProgGuideObjects#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#16)]  
  
## <a name="see-also"></a>См. также

- <xref:System.ICloneable>
- [Руководство по программированию на C#](../index.md)
- [Классы и структуры](./index.md)
- [Конструкторы](./constructors.md)
- [Методы завершения](./destructors.md)
