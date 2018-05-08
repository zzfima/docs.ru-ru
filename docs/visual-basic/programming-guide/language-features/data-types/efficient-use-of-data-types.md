---
title: Эффективное использование типов данных (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- performance, data type efficiency
- data types [Visual Basic], weak typing
- AscW function [Visual Basic], preferred to Asc
- data types [Visual Basic], using efficiently
- optimization [Visual Basic], data types
- data types [Visual Basic], strong typing
- strong typing
- typing, strong
- data types [Visual Basic], optimizing
- ChrW function [Visual Basic], preferred to Chr
ms.assetid: 28f5e4ba-ec24-4f37-b90a-e8ee822f778a
ms.openlocfilehash: 6e71c4e2225bbcde3bb2bd20ae098f5600990051
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="efficient-use-of-data-types-visual-basic"></a>Эффективное использование типов данных (Visual Basic)
Необъявленные переменные и переменные, объявленные типами данных назначенных `Object` тип данных. Это упрощает написание программ, но может замедлять их выполняются медленнее.  
  
## <a name="strong-typing"></a>Строгая типизация  
 Задание типов данных для всех переменных называется *строгую типизацию*. Использование строгой типизации имеет несколько преимуществ.  
  
-   Она включает поддержку IntelliSense для переменных. Это позволяет видеть свойства и другие члены, вводимые в коде.  
  
-   Она использует преимущества проверки типа компилятора. Благодаря этому обнаруживаются операторы, которые могут вызвать сбой во время выполнения из-за ошибок, таких как переполнение. Он также обнаруживаются вызовы методов для объектов, которые не поддерживают.  
  
-   Это приводит к более быстрое выполнение кода.  
  
## <a name="most-efficient-data-types"></a>Наиболее эффективные типы данных  
 Для переменных, которые никогда не содержат дроби целочисленные типы данных более эффективны, чем Нецелочисленные типы. В Visual Basic `Integer` и `UInteger` являются наиболее эффективный числовых типов.  
  
 Для дробных чисел `Double` является наиболее эффективный тип данных, поскольку процессоры на современных платформах выполняют операции с плавающей запятой с двойной точностью. Тем не менее операции с `Double` не выполняются так же быстро, как и для целочисленных типов, таких как `Integer`.  
  
## <a name="specifying-data-type"></a>Указание типа данных  
 Используйте [оператор Dim](../../../../visual-basic/language-reference/statements/dim-statement.md) для объявления переменной определенного типа. Одновременно можно указать уровень доступа с помощью [открытый](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), или [закрытый](../../../../visual-basic/language-reference/modifiers/private.md) ключевое слово как Ниже приведен пример.  
  
```  
Private x As Double  
Protected s As String  
```  
  
## <a name="character-conversion"></a>Преобразование символов  
 `AscW` И `ChrW` функции выполняются в Юникоде. Их следует использовать `Asc` и `Chr`, который необходимо преобразовать в Юникод и из него.  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.Strings.Asc%2A>  
 <xref:Microsoft.VisualBasic.Strings.AscW%2A>  
 <xref:Microsoft.VisualBasic.Strings.Chr%2A>  
 <xref:Microsoft.VisualBasic.Strings.ChrW%2A>  
 [Типы данных](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [Числовые типы данных](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)  
 [Объявление переменных](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [Использование технологии IntelliSense](/visualstudio/ide/using-intellisense)
