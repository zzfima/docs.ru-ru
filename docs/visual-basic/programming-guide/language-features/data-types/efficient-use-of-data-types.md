---
title: "Эффективное использование типов данных (Visual Basic) | Документы Microsoft"
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
- performance, data type efficiency
- data types [Visual Basic], weak typing
- AscW function, preferred to Asc
- data types [Visual Basic], using efficiently
- optimization, data types
- data types [Visual Basic], strong typing
- strong typing
- typing, strong
- data types [Visual Basic], optimizing
- ChrW function, preferred to Chr
ms.assetid: 28f5e4ba-ec24-4f37-b90a-e8ee822f778a
caps.latest.revision: 16
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: b81a1c81d970beee32925c3f2fe6ca3bcad79151
ms.lasthandoff: 03/13/2017

---
# <a name="efficient-use-of-data-types-visual-basic"></a>Эффективное использование типов данных (Visual Basic)
Необъявленные переменные и переменные без типа данных назначаются `Object` тип данных. Это упрощает написание программ, но может замедлять их выполнение.  
  
## <a name="strong-typing"></a>Строгая типизация  
 Задание типов данных для всех переменных называется *строгой типизации*. Использование строгой типизации имеет несколько преимуществ:  
  
-   Он обеспечивает поддержку IntelliSense для переменных. Это позволяет видеть их свойства и другие члены, при вводе в коде.  
  
-   Он использует преимущества проверки типа компилятора. Благодаря этому обнаруживаются операторы, которые могут вызвать сбой во время выполнения из-за ошибок, таких как переполнение. Обнаруживаются также вызовы методов для объектов, которые не поддерживают их.  
  
-   Обеспечивается более быстрое выполнение кода.  
  
## <a name="most-efficient-data-types"></a>Наиболее эффективные типы данных  
 Для переменных, которые никогда не содержат дроби целочисленные типы данных более эффективны, чем Нецелочисленные типы. В [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], `Integer` и `UInteger` являются наиболее эффективными типами.  
  
 Для дробных чисел `Double` является наиболее эффективный тип данных, поскольку процессоры на современных платформах выполняют операции с плавающей запятой с двойной точностью. Однако операции с `Double` не так же быстро, как и в случае целочисленные типы, такие как `Integer`.  
  
## <a name="specifying-data-type"></a>Указание типа данных  
 Используйте [оператора Dim](../../../../visual-basic/language-reference/statements/dim-statement.md) для объявления переменной определенного типа. Одновременно можно указать уровень доступа с помощью [открытый](../../../../visual-basic/language-reference/modifiers/public.md), [защищенные](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), или [частного](../../../../visual-basic/language-reference/modifiers/private.md) ключевое слово, как показано в следующем примере.  
  
```  
Private x As Double  
Protected s As String  
```  
  
## <a name="character-conversion"></a>Преобразование символов  
 `AscW` И `ChrW` функции выполняются в Юникоде. Их следует использовать `Asc` и `Chr`, которые должны преобразовывать в Юникод и из него.  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.Strings.Asc%2A></xref:Microsoft.VisualBasic.Strings.Asc%2A>   
 <xref:Microsoft.VisualBasic.Strings.AscW%2A></xref:Microsoft.VisualBasic.Strings.AscW%2A>   
 <xref:Microsoft.VisualBasic.Strings.Chr%2A></xref:Microsoft.VisualBasic.Strings.Chr%2A>   
 <xref:Microsoft.VisualBasic.Strings.ChrW%2A></xref:Microsoft.VisualBasic.Strings.ChrW%2A>   
 [Типы данных](../../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [Числовые типы данных](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)   
 [Объявление переменных](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)   
 [Использование технологии IntelliSense](https://docs.microsoft.com/visualstudio/ide/using-intellisense)
