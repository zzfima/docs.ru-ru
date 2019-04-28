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
ms.openlocfilehash: 0b517bca3a9e296eb891e30df91c1d32eb357432
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61907222"
---
# <a name="efficient-use-of-data-types-visual-basic"></a>Эффективное использование типов данных (Visual Basic)
Необъявленные переменные и переменные, объявленные без типа данных назначаются `Object` тип данных. Это упрощает написание программ, но его можно привести к медленному выполнению.  
  
## <a name="strong-typing"></a>Строгая типизация  
 Задание типов данных для всех переменных называется *строгую типизацию*. Использование строгой типизации имеет несколько преимуществ:  
  
- Она включает поддержку IntelliSense для переменных. Это позволяет видеть свойства и другие члены, при вводе в коде.  
  
- Он использует преимущества проверки типа компилятора. Перехватывает инструкций, которые могут вызвать сбой во время выполнения из-за ошибок, таких как переполнение. Также он перехватывает вызовы методов с объектами, которые не поддерживают их.  
  
- Он приводит к более быстрого выполнения кода.  
  
## <a name="most-efficient-data-types"></a>Наиболее эффективный типы данных  
 Для переменных, которые никогда не содержат дроби целочисленных типов данных, более эффективны, чем нецелочисленных типов. В Visual Basic `Integer` и `UInteger` являются наиболее эффективный числовых типов.  
  
 Для дробных чисел `Double` — это наиболее эффективный тип данных, так как процессоры на современных платформах выполняют операции с плавающей запятой с двойной точностью. Тем не менее операции с `Double` не выполняются так же быстро, как и в случае с целочисленными типами, такие как `Integer`.  
  
## <a name="specifying-data-type"></a>Указание типа данных  
 Используйте [оператор Dim](../../../../visual-basic/language-reference/statements/dim-statement.md) для объявления переменной определенного типа. Одновременно можно указать уровень доступа с помощью [открытый](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), или [частного](../../../../visual-basic/language-reference/modifiers/private.md) ключевое слово, как и в Ниже приведен пример.  
  
```  
Private x As Double  
Protected s As String  
```  
  
## <a name="character-conversion"></a>Преобразование символов  
 `AscW` И `ChrW` функции выполняются в Юникоде. Их следует использовать `Asc` и `Chr`, который необходимо преобразовать в Юникод и из него.  
  
## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.Strings.Asc%2A>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- <xref:Microsoft.VisualBasic.Strings.Chr%2A>
- <xref:Microsoft.VisualBasic.Strings.ChrW%2A>
- [Типы данных](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [Числовые типы данных](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)
- [Объявление переменных](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [Использование технологии IntelliSense](/visualstudio/ide/using-intellisense)
