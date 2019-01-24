---
title: Как выполнить Управление областью действия переменной (Visual Basic)
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
ms.openlocfilehash: 656bfa6fa9b3445d91cd8ac39b83bccf3e44758e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54521417"
---
# <a name="how-to-control-the-scope-of-a-variable-visual-basic"></a>Как выполнить Управление областью действия переменной (Visual Basic)
Как правило, переменная находится в *область*, или доступна для ссылки на протяжении всего региона, в котором она объявлена. В некоторых случаях переменная элемента *уровень доступа* может влиять на ее область действия.  
  
 Для получения дополнительной информации см. [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).  
  
## <a name="scope-at-block-or-procedure-level"></a>Область действия на уровне блока или процедуры  
  
#### <a name="to-make-a-variable-visible-only-within-a-block"></a>Чтобы сделать переменную видимой только внутри блока  
  
-   Место [оператор Dim](../../../../visual-basic/language-reference/statements/dim-statement.md) для переменной между начальными и конечными операторы объявления блока, например между `For` и `Next` констатация `For` цикла.  
  
     Можно ссылаться только из переменной в блоке.  
  
#### <a name="to-make-a-variable-visible-only-within-a-procedure"></a>Чтобы сделать переменную видимой только внутри процедуры  
  
-   Место `Dim` инструкцию для переменной внутри процедуры, но вне любого блока (такие как `With`... `End With` блок).  
  
     Можно ссылаться только из переменной внутри процедуры, в том числе внутри любого блока, содержащегося в процедуре.  
  
## <a name="scope-at-module-or-namespace-level"></a>Область на модуль или пространство имен  
 Для удобства один термин *уровне модуля* применяется одинаково для модулей, классов и структур. Уровень доступа к переменной уровня модуля определяет ее область действия. Эту область также влияет на пространство имен, содержащее модуля, класса или структуры.  
  
#### <a name="to-make-a-variable-visible-throughout-a-module-class-or-structure"></a>Чтобы сделать переменную видимой во всей модуля, класса или структуры  
  
1.  Место `Dim` инструкцию для переменной внутри модуля, класса или структуры, но вне любой процедуры.  
  
2.  Включить [частного](../../../../visual-basic/language-reference/modifiers/private.md) ключевое слово в `Dim` инструкции.  
  
3.  Можно ссылаться на значение переменной из любого места внутри модуля, класса или структуры, но не из за его пределами.  
  
#### <a name="to-make-a-variable-visible-throughout-a-namespace"></a>Чтобы сделать переменную видимой во всей пространства имен  
  
1.  Место `Dim` инструкцию для переменной внутри модуля, класса или структуры, но вне любой процедуры.  
  
2.  Включить [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) или [открытый](../../../../visual-basic/language-reference/modifiers/public.md) ключевое слово в `Dim` инструкции.  
  
3.  В переменную можно ссылаться из любого места в пространство имен, содержащее модуля, класса или структуры.  
  
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
  
 В приведенном выше примере все процедуры, определенные в модуле `demonstrateScope` могут ссылаться на `String` переменной `strMsg`. Когда `usePrivateVariable` процедура вызывается, он отображает содержимое переменной строки `strMsg` в диалоговом окне.  
  
 Со следующими изменениями в предыдущем примере строковая переменная `strMsg` можно обращаться к любым кодом в ее объявлении пространства имен.  
  
```  
Public strMsg As String  
```  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 Чем короче область переменной, тем меньше возможностей, которыми обладает пользователь случайно обращения к нему вместо другую переменную с тем же именем. Также можно свести к минимуму проблемы с соответствием ссылки.  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
 Более узкой областью действия переменной, тем меньше вероятность того, что вредоносный код может использовать неправильной его использовать.  
  
## <a name="see-also"></a>См. также
- [Область, в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
- [Время существования в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [Уровни доступа в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [Переменные](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [Объявление переменных](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [Оператор Dim](../../../../visual-basic/language-reference/statements/dim-statement.md)
