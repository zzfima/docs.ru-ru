---
title: "Типы методов для обработки в Visual Basic | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- strings [Visual Basic], manipulating [Visual Basic]
- string manipulation
ms.assetid: 905055cd-7f50-48fb-9eed-b0995af1dc1f
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 349cfdb3e31225f6aeba90ac29aa1c66e37c7e11
ms.lasthandoff: 03/13/2017

---
# <a name="types-of-string-manipulation-methods-in-visual-basic"></a>Типы методов для работы со строками в Visual Basic
Существует несколько способов анализа и работы со строками. Некоторые методы являются частью [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] язык и другие принадлежат `String` класса.  
  
## <a name="visual-basic-language-and-the-net-framework"></a>Язык Visual Basic и .NET Framework  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]методы используются как встроенные функции языка. Они могут использоваться без уточнения в коде. В следующем примере показано типичное использование [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] команды управления строками:  
  
 [!code-vb[VbVbalrStrings&#44;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_1.vb)]  
  
 В этом примере `Mid` функция выполняет прямую операцию на `aString` и присваивает это значение `bString`.  
  
 Список методов обработки для Visual Basic, в разделе [Сводка управления строками](../../../../visual-basic/language-reference/keywords/string-manipulation-summary.md).  
  
### <a name="shared-methods-and-instance-methods"></a>Общие методы и методы экземпляра  
 Строками можно управлять с помощью методов `String` класса. Существует два типа методов в `String`: *общего* методы и *экземпляр* методы.  
  
#### <a name="shared-methods"></a>Общие методы  
 Общий метод является методом, порождаемой `String` сам класс и не требует экземпляр этого класса для работы. Эти методы могут быть уточнено именем класса (`String`), а не с экземпляром `String` класса. Например:  
  
 [!code-vb[VbVbalrStrings&#45;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_2.vb)]  
  
 В предыдущем примере <xref:System.String.Copy%2A?displayProperty=fullName>является статическим методом, выражение, которое функционирует он получает и присваивает полученное значение для `bString`.</xref:System.String.Copy%2A?displayProperty=fullName>  
  
#### <a name="instance-methods"></a>Методы экземпляра  
 Методы экземпляра, напротив, вытекают из конкретного экземпляра `String` и должны уточняться именем экземпляра. Пример:  
  
 [!code-vb[VbVbalrStrings&#46;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_3.vb)]  
  
 В этом примере <xref:System.String.Substring%2A?displayProperty=fullName>является методом экземпляра `String` (то есть, `aString`).</xref:System.String.Substring%2A?displayProperty=fullName> Он выполняет операцию над `aString` и присваивает это значение `bString`.  
  
 Дополнительные сведения см. в документации для <xref:System.String>класса.</xref:System.String>  
  
## <a name="see-also"></a>См. также  
 [Знакомство со строками в Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
