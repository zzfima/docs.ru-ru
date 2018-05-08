---
title: Практическое руководство. Управление областью действия переменной (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], scope
- declared elements [Visual Basic], scope
- visibility [Visual Basic], declared elements
- variables [Visual Basic], visibility
- scope [Visual Basic], declared elements
- scope [Visual Basic], variables
- scope [Visual Basic], Visual Basic
- declared elements [Visual Basic], visibility
- visibility [Visual Basic], variables
ms.assetid: 44b7f62a-cb5c-4d50-bce9-60ae68f87072
ms.openlocfilehash: 6e8d1178398711226b88fee7e6defd5162b91fcb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-control-the-scope-of-a-variable-visual-basic"></a>Практическое руководство. Управление областью действия переменной (Visual Basic)
Как правило, переменная находится в *область*, или доступна для ссылки во всей области, в котором она объявлена. В некоторых случаях переменная *уровень доступа* может повлиять на ее область действия.  
  
 Дополнительные сведения см. в разделе [области в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).  
  
## <a name="scope-at-block-or-procedure-level"></a>Область действия на уровне блока или процедуры  
  
#### <a name="to-make-a-variable-visible-only-within-a-block"></a>Чтобы сделать переменную видимой только внутри блока  
  
-   Место [оператор Dim](../../../../visual-basic/language-reference/statements/dim-statement.md) для переменной между начальными и конечными операторами объявления блока, например между `For` и `Next` инструкции `For` цикла.  
  
     Можно ссылаться только из переменной в блоке.  
  
#### <a name="to-make-a-variable-visible-only-within-a-procedure"></a>Чтобы сделать переменную видимой только внутри процедуры  
  
-   Место `Dim` инструкции для переменной внутри процедуры, но вне любого блока (такие как `With`... `End With` блок).  
  
     Можно ссылаться только из переменной внутри процедуры, в том числе внутри любого блока, содержащегося в процедуре.  
  
## <a name="scope-at-module-or-namespace-level"></a>Область действия на уровне пространства имен или модуля  
 Для удобства один термин *уровне модуля* одинаково применимо для модулей, классов и структур. Уровень доступа переменной уровня модуля определяет его области. Эту область также влияет на пространство имен, содержащее модуля, класса или структуры.  
  
#### <a name="to-make-a-variable-visible-throughout-a-module-class-or-structure"></a>Чтобы сделать переменную видимой во всей модуля, класса или структуры  
  
1.  Место `Dim` инструкции для переменной внутри модуля, класса или структуры, но вне любой процедуры.  
  
2.  Включить [закрытый](../../../../visual-basic/language-reference/modifiers/private.md) ключевое слово в `Dim` инструкции.  
  
3.  Можно ссылаться на значение переменной из любого места внутри модуля, класса или структуры, но не из за его пределами.  
  
#### <a name="to-make-a-variable-visible-throughout-a-namespace"></a>Чтобы сделать переменную видимой внутри пространства имен  
  
1.  Место `Dim` инструкции для переменной внутри модуля, класса или структуры, но вне любой процедуры.  
  
2.  Включить [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) или [открытый](../../../../visual-basic/language-reference/modifiers/public.md) ключевое слово в `Dim` инструкции.  
  
3.  Можно ссылаться на переменную в любом месте в пределах пространства имен, содержащего модуля, класса или структуры.  
  
## <a name="example"></a>Пример  
 В следующем примере объявляется переменная на уровне модуля и ограничивает видимость для кода в модуле.  
  
```  
Module demonstrateScope  
    Private strMsg As String  
    Sub initializePrivateVariable()  
        strMsg = "This variable cannot be used outside this module."  
    End Sub  
    Sub usePrivateVariable()  
        MsgBox(strMsg)  
    End Sub  
End Module  
```  
  
 В предыдущем примере все процедуры, определенные в модуле `demonstrateScope` могут ссылаться на `String` переменной `strMsg`. Когда `usePrivateVariable` при вызове процедуры, она отображает содержимое переменной строки `strMsg` в диалоговом окне.  
  
 Учитывая следующие изменения в предыдущем примере строковая переменная `strMsg` можно ссылаться из кода в любом месте в пространстве имен ее объявления.  
  
```  
Public strMsg As String  
```  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 Чем короче область переменной, тем меньше возможностей, которыми обладает пользователь случайной ссылки на нее вместо другой переменной с тем же именем. Также можно свести к минимуму проблемы с соответствием ссылки.  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
 Чем уже область действия переменной, тем меньше вероятность того, что вредоносный код может использовать неправильной его использовать.  
  
## <a name="see-also"></a>См. также  
 [Область в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)  
 [Время существования в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)  
 [Уровни доступа в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [Переменные](../../../../visual-basic/programming-guide/language-features/variables/index.md)  
 [Объявление переменных](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [Оператор Dim](../../../../visual-basic/language-reference/statements/dim-statement.md)
