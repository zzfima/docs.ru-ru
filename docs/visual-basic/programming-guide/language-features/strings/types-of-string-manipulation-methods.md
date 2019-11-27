---
title: Типы методов для работы со строками
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], manipulating [Visual Basic]
- string manipulation
ms.assetid: 905055cd-7f50-48fb-9eed-b0995af1dc1f
ms.openlocfilehash: a02278abfb71efb2f31f239a89a22ad1c8ee7a18
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346275"
---
# <a name="types-of-string-manipulation-methods-in-visual-basic"></a>Типы методов для работы со строками в Visual Basic
Существует несколько различных способов анализа строк и управления ими. Некоторые методы являются частью языка Visual Basic, а другие — в классе `String`.  
  
## <a name="visual-basic-language-and-the-net-framework"></a>Язык Visual Basic и .NET Framework  
 Visual Basic методы используются в качестве встроенных функций языка. Они могут использоваться без уточнения в коде. В следующем примере показано типичное использование Visual Basic команды обработки строк:  
  
 [!code-vb[VbVbalrStrings#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#44)]  
  
 В этом примере функция `Mid` выполняет прямую операцию над `aString` и присваивает значение `bString`.  
  
 Список методов обработки строк Visual Basic см. в разделе [Сводка манипулирования строками](../../../../visual-basic/language-reference/keywords/string-manipulation-summary.md).  
  
### <a name="shared-methods-and-instance-methods"></a>Общие методы и методы экземпляров  
 Можно также управлять строками с помощью методов класса `String`. В `String`есть два типа методов: *Общие* методы и методы *экземпляра* .  
  
#### <a name="shared-methods"></a>Общие методы  
 Общий метод — это метод, который является производным от класса `String` и не требует работы экземпляра этого класса. Эти методы можно уточнять именем класса (`String`), а не экземпляром класса `String`. Пример.  
  
 [!code-vb[VbVbalrStrings#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#45)]  
  
 В предыдущем примере метод <xref:System.String.Copy%2A?displayProperty=nameWithType> является статическим методом, который действует на заданное выражение и присваивает результирующее значение `bString`.  
  
#### <a name="instance-methods"></a>Методы экземпляра  
 Методы экземпляра, напротив, имеют определенный экземпляр `String` и должны уточняться именем экземпляра. Пример.  
  
 [!code-vb[VbVbalrStrings#46](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#46)]  
  
 В этом примере метод <xref:System.String.Substring%2A?displayProperty=nameWithType> является методом экземпляра `String` (то есть `aString`). Он выполняет операцию с `aString` и присваивает этому значению `bString`.  
  
 Дополнительные сведения см. в документации по классу <xref:System.String>.  
  
## <a name="see-also"></a>См. также

- [Знакомство со строками в Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
