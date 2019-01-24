---
title: Как выполнить Сокрытие наследуемой переменной (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- qualification [Visual Basic], of element names
- element names [Visual Basic], qualification
- references [Visual Basic], declared elements
- declaration statements [Visual Basic], declared elements
- referencing declared elements [Visual Basic]
- declared elements [Visual Basic], referencing
- declared elements [Visual Basic], about declared elements
- variables [Visual Basic], hiding inherited
ms.assetid: 765728d9-7351-4a30-999d-b5f34f024412
ms.openlocfilehash: 6cf45b12bebc254a0d96516ab262d7aae3d70746
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54691259"
---
# <a name="how-to-hide-an-inherited-variable-visual-basic"></a>Как выполнить Сокрытие наследуемой переменной (Visual Basic)
Производный класс наследует все определения базового класса. Если вы хотите определить переменную с тем же именем, что элемент базового класса, можно скрыть, или *тени*, этот элемент базового класса при определении переменной в производном классе. После этого код в производном классе получает доступ к переменной, если явно не обходится скрывающий механизм.  
  
 Другой причиной может потребоваться сокрытие наследуемой переменной является защита версии базового класса. Базовый класс может претерпеть изменения, изменяющей элемента, к которому вы наследуете. В этом случае `Shadows` модификатор заставляет ссылки из производного класса разрешаться в переменную, а не в элемент базового класса.  
  
### <a name="to-hide-an-inherited-variable"></a>Чтобы скрыть наследуемой переменной  
  
1.  Убедитесь, что переменная, которую вы хотите скрыть объявлен на уровне класса (вне любых процедур). В противном случае не нужно скрыть его.  
  
2.  Внутри производного класса, напишите [оператор Dim](../../../../visual-basic/language-reference/statements/dim-statement.md) объявляющий переменную. Использование тем же именем, что и наследуемой переменной.  
  
3.  Включить [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) ключевое слово в объявлении.  
  
     Когда код в производном классе ссылается на имя переменной, компилятор разрешает ссылку на переменную.  
  
     В следующем примере показано переобъявлять наследуемой переменной.  
  
    ```  
    Public Class shadowBaseClass  
        Public shadowString As String = "This is the base class string."  
    End Class  
    Public Class shadowDerivedClass  
        Inherits shadowBaseClass  
        Public Shadows shadowString As String = "This is the derived class string."  
        Public Sub showStrings()  
            Dim s As String = "Unqualified shadowString: " & shadowString &  
                vbCrLf & "MyBase.shadowString: " & MyBase.shadowString  
            MsgBox(s)  
        End Sub  
    End Class  
    ```  
  
     В предыдущем примере объявляется переменной `shadowString` в базовом классе, скрывается в производном классе. Процедура `showStrings` в производном классе отображает версию затенения строки при имя `shadowString` не обработаны квалификатором. Затем он отобразит затененная версия при `shadowString` квалифицируется `MyBase` ключевое слово.  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 Затенение представляет несколько версий переменной с тем же именем. Если оператор кода ссылается на имя переменной, версии, к которому компилятор разрешает ссылку зависит от факторов, таких как расположение оператор кода, а также наличие уточняющей строки. Это может увеличить риск ссылки на неправильную версию затененной переменной. Можно снизить этот риск путем полного все ссылки на переменную тенью.  
  
## <a name="see-also"></a>См. также
- [Ссылки на объявленные элементы](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Сокрытие в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [Различия между затемнением и переопределением](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)
- [Практическое руководство. Сокрытие переменной с тем же именем, что и ваша переменная](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)
- [Практическое руководство. Доступ к переменной, скрытой производным классом](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)
- [Переопределения](../../../../visual-basic/language-reference/modifiers/overrides.md)
- [Me, My, MyBase и MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [Основы наследования](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
