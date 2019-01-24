---
title: Типы методов для работы со строками в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], manipulating [Visual Basic]
- string manipulation
ms.assetid: 905055cd-7f50-48fb-9eed-b0995af1dc1f
ms.openlocfilehash: fa579303ad268a88269f360bdf626f9590c5d6a2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54648499"
---
# <a name="types-of-string-manipulation-methods-in-visual-basic"></a>Типы методов для работы со строками в Visual Basic
Существует несколько различных способов анализа и работы со строками. Некоторые методы являются частью языка Visual Basic, а другие принадлежат `String` класса.  
  
## <a name="visual-basic-language-and-the-net-framework"></a>Язык Visual Basic и .NET Framework  
 Методы Visual Basic используются как встроенные функции языка. Они могут использоваться без уточнения в коде. В следующем примере показано типичное использование команды строками Visual Basic:  
  
 [!code-vb[VbVbalrStrings#44](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_1.vb)]  
  
 В этом примере `Mid` функция выполняет прямой операцию на `aString` и присваивает это значение `bString`.  
  
 Список методов обработки строк в Visual Basic, см. в разделе [Сводка управления строками](../../../../visual-basic/language-reference/keywords/string-manipulation-summary.md).  
  
### <a name="shared-methods-and-instance-methods"></a>Общие методы и методы экземпляра  
 Строки также можно работать с методами `String` класса. Существует два типа методов в `String`: *общего* методы и *экземпляр* методы.  
  
#### <a name="shared-methods"></a>Общие методы  
 Общий метод является методом, порождаемой `String` сам по себе класс и не требует запуска экземпляра этого класса для работы. Эти методы могут быть уточнено именем класса (`String`), а не с экземпляром `String` класса. Пример:  
  
 [!code-vb[VbVbalrStrings#45](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_2.vb)]  
  
 В приведенном выше примере <xref:System.String.Copy%2A?displayProperty=nameWithType> метод — это статический метод, который действует при выражение он предоставляется и присваивает результирующее значение `bString`.  
  
#### <a name="instance-methods"></a>Методы экземпляра  
 Методы экземпляра, напротив, возникающих из-за конкретный экземпляр `String` и должны быть дополнены именем экземпляра. Пример:  
  
 [!code-vb[VbVbalrStrings#46](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_3.vb)]  
  
 В этом примере <xref:System.String.Substring%2A?displayProperty=nameWithType> метод является методом экземпляра `String` (то есть `aString`). Он выполняет операцию над `aString` и присваивает это значение `bString`.  
  
 Дополнительные сведения см. в документации по <xref:System.String> класса.  
  
## <a name="see-also"></a>См. также
- [Знакомство со строками в Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
