---
title: "Практическое руководство. Управление доступностью переменной (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- access levels, declared elements
- Private keyword [Visual Basic], accessing variables
- access levels, variables
- Public keyword [Visual Basic], accessing variables
- Friend keyword [Visual Basic], accessing variables
- variables [Visual Basic], access level
- declared elements [Visual Basic], access level
- Protected keyword [Visual Basic], accessing variables
ms.assetid: eaf4f073-7922-43ce-ae1e-90ff376ae947
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 004fb101661fadeaee084e1f9374ca8332ac7234
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-control-the-availability-of-a-variable-visual-basic"></a>Практическое руководство. Управление доступностью переменной (Visual Basic)
Управление доступностью переменной, указав его *уровень доступа*. Уровень доступа определяет, какой код имеет разрешение на чтение или запись в переменную.  
  
-   *Переменные-члены* (определяется на уровне модуля и вне любых процедур) по умолчанию для общего доступа, что означает любой код, который могли получить к ним могли обращаться к ним. Это можно изменить, указав модификатор доступа.  
  
-   *Локальные переменные* (определяется внутри процедуры) обычно общедоступны являются общедоступными, несмотря на то, что они доступны только код внутри процедуры. Невозможно изменить уровень доступа к локальной переменной, но можно изменить уровень доступа для процедуры, в которой он содержится.  
  
 Дополнительные сведения см. в разделе [уровни в Visual Basic доступа](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## <a name="private-and-public-access"></a>Закрытый и открытый доступ  
  
#### <a name="to-make-a-variable-accessible-only-from-within-its-module-class-or-structure"></a>Чтобы сделать переменную доступной только из модуля, класса или структуры  
  
1.  Место [оператор Dim](../../../../visual-basic/language-reference/statements/dim-statement.md) для переменной внутри модуля, класса или структуры, но вне любой процедуры.  
  
2.  Включить [закрытый](../../../../visual-basic/language-reference/modifiers/private.md) ключевое слово в `Dim` инструкции.  
  
     Может считывать или записывать значение переменной из любого места внутри модуля, класса или структуры, но не из за его пределами.  
  
#### <a name="to-make-a-variable-accessible-from-any-code-that-can-see-it"></a>Чтобы сделать переменную доступной из любого кода, который можно видеть его  
  
1.  Переменную-член, поместите `Dim` инструкции для переменной внутри модуля, класса или структуры, но вне любой процедуры.  
  
2.  Включить [открытый](../../../../visual-basic/language-reference/modifiers/public.md) ключевое слово в `Dim` инструкции.  
  
     Может считывать или записывать значение переменной из любого кода, взаимодействующего со сборкой.  
  
 -или-  
  
1.  Для локальной переменной, поместите `Dim` инструкции для переменной внутри процедуры.  
  
2.  Не включайте `Public` ключевое слово в `Dim` инструкции.  
  
     Вы могли читать или записывать значение переменной из любого места внутри процедуры, но не из за его пределами.  
  
## <a name="protected-and-friend-access"></a>Защищенные и дружественный доступ  
 Можно ограничить уровень доступа переменной его класса и всех производных классах, или его сборке. Можно также указать объединение этих ограничений, который позволяет доступ из кода любого производного класса или любого другого места в той же сборке. Укажите это объединение путем объединения `Protected` и `Friend` ключевые слова в одном объявлении.  
  
#### <a name="to-make-a-variable-accessible-only-from-within-its-class-and-any-derived-classes"></a>Чтобы сделать переменную доступной только из своего класса и его производные классы  
  
1.  Место `Dim` инструкции для переменной внутри класса, но вне любой процедуры.  
  
2.  Включить [Protected](../../../../visual-basic/language-reference/modifiers/protected.md) ключевое слово в `Dim` инструкции.  
  
     Может считывать или записывать значение переменной из любого места внутри класса, а также внутри любого класса, производного от него, но не из за пределами любого класса в иерархии наследования.  
  
#### <a name="to-make-a-variable-accessible-only-from-within-the-same-assembly"></a>Чтобы сделать переменную доступной только из той же сборки  
  
1.  Место `Dim` инструкции для переменной внутри модуля, класса или структуры, но вне любой процедуры.  
  
2.  Включить [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) ключевое слово в `Dim` инструкции.  
  
     Может считывать или записывать значение переменной из любого места внутри модуля, класса или структуры, а также из любого кода в той же сборке, но не из за пределами сборки.  
  
## <a name="example"></a>Пример  
 В следующем примере показано объявление переменных с `Public`, `Protected`, `Friend`, `Protected Friend`, и `Private` уровни доступа. Обратите внимание, что при `Dim` инструкция указывает уровень доступа, не должны включать `Dim` ключевое слово.  
  
```  
Public Class classForEverybody  
Protected Class classForMyHeirs  
Friend stringForThisProject As String  
Protected Friend stringForProjectAndHeirs As String  
Private numberForMeOnly As Integer  
```  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
 Более строгий уровень доступа к переменной, тем меньше вероятность того, что вредоносный код может использовать неправильной его использовать.  
  
## <a name="see-also"></a>См. также  
 [Уровни доступа в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [Оператор Dim](../../../../visual-basic/language-reference/statements/dim-statement.md)  
 [Public](../../../../visual-basic/language-reference/modifiers/public.md)  
 [Protected](../../../../visual-basic/language-reference/modifiers/protected.md)  
 [Friend](../../../../visual-basic/language-reference/modifiers/friend.md)  
 [Закрытые](../../../../visual-basic/language-reference/modifiers/private.md)
