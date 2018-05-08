---
title: Типы методов для работы со строками в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], manipulating [Visual Basic]
- string manipulation
ms.assetid: 905055cd-7f50-48fb-9eed-b0995af1dc1f
ms.openlocfilehash: 11903e067c064f129ecd2df80244edb6741c73be
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="types-of-string-manipulation-methods-in-visual-basic"></a>Типы методов для работы со строками в Visual Basic
Существует несколько способов для анализа и работы со строками. Некоторые методы являются частью языка Visual Basic, а другие принадлежат `String` класса.  
  
## <a name="visual-basic-language-and-the-net-framework"></a>Язык Visual Basic и .NET Framework  
 Методы Visual Basic используются как встроенные функции языка. Они могут использоваться без уточнения в коде. В следующем примере показано типичное использование команды управления строками Visual Basic:  
  
 [!code-vb[VbVbalrStrings#44](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_1.vb)]  
  
 В этом примере `Mid` функция выполняет операцию прямой на `aString` и присваивает это значение `bString`.  
  
 Список методов Visual Basic для обработки см. в разделе [Сводка управления строками](../../../../visual-basic/language-reference/keywords/string-manipulation-summary.md).  
  
### <a name="shared-methods-and-instance-methods"></a>Общие методы и методы экземпляра  
 Строки также можно работать с методами `String` класса. Существует два типа методов в `String`: *общего* методы и *экземпляр* методы.  
  
#### <a name="shared-methods"></a>Общие методы  
 Общий метод является методом, основанная на `String` сам класс и не требует экземпляр этого класса для работы. Эти методы могут быть дополнены имя класса (`String`), а не с помощью экземпляра `String` класса. Пример:  
  
 [!code-vb[VbVbalrStrings#45](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_2.vb)]  
  
 В приведенном выше примере <xref:System.String.Copy%2A?displayProperty=nameWithType> метод является статическим методом, который функционирует после выражения он получает и присваивает результирующее значение `bString`.  
  
#### <a name="instance-methods"></a>Методы экземпляра  
 Методы экземпляра, в отличие от этого, возникающих из-за определенный экземпляр `String` и должны быть дополнены именем экземпляра. Пример:  
  
 [!code-vb[VbVbalrStrings#46](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_3.vb)]  
  
 В этом примере <xref:System.String.Substring%2A?displayProperty=nameWithType> метод является методом экземпляра `String` (то есть, `aString`). Он выполняет операцию над `aString` и присваивает это значение `bString`.  
  
 Дополнительные сведения см. в документации для <xref:System.String> класса.  
  
## <a name="see-also"></a>См. также  
 [Знакомство со строками в Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
