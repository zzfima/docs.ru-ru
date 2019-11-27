---
title: Практическое руководство. Объявление структуры
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], structures
- structure statements [Visual Basic]
- statements [Visual Basic], structure
- structures [Visual Basic], declaring
ms.assetid: d5e98381-eb81-47d4-af83-48cc534a2572
ms.openlocfilehash: 41d2d03064dea703909218de56feb863526c220b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349999"
---
# <a name="how-to-declare-a-structure-visual-basic"></a>Практическое руководство. Объявление структуры (Visual Basic)
Объявление структуры начинается с [оператора Structure](../../../../visual-basic/language-reference/statements/structure-statement.md)и завершается с помощью оператора `End Structure`. Между этими двумя операторами необходимо объявить хотя бы один *элемент*. Элементы могут иметь любой тип данных, но хотя бы один из них должен быть либо необщей переменной, либо нестандартным, ненастраиваемым событием.  
  
 Нельзя инициализировать какие либо элементы структуры в объявлении структуры. При объявлении переменной, имеющей тип структуры, необходимо назначить значения элементам, обращаясь к ним через переменную.  
  
 Обсуждение различий между структурами и классами см. в разделе [структуры и классы](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md).  
  
 В демонстрационных целях рассмотрим ситуацию, когда необходимо отследить имя сотрудника, телефонное расширение и заработную плату. Структура позволяет сделать это в одной переменной.  
  
### <a name="to-declare-a-structure"></a>Объявление структуры  
  
1. Создайте начальную и конечную инструкции для структуры.  
  
     Уровень доступа структуры можно указать с помощью ключевого слова [Public](../../../../visual-basic/language-reference/modifiers/public.md), [protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md)или [Private](../../../../visual-basic/language-reference/modifiers/private.md) . также можно разрешить `Public`по умолчанию.  
  
    ```vb  
    Private Structure employee  
    End Structure  
    ```  
  
2. Добавьте элементы в текст структуры.  
  
     Структура должна содержать по крайней мере один элемент. Необходимо объявить каждый элемент и указать для него уровень доступа. Если вы используете [инструкцию Dim](../../../../visual-basic/language-reference/statements/dim-statement.md) без ключевых слов, для специальных возможностей по умолчанию используется значение `Public`.  
  
    ```vb  
    Private Structure employee  
        Public givenName As String  
        Public familyName As String  
        Public phoneExtension As Long  
        Private salary As Decimal  
        Public Sub giveRaise(raise As Double)  
            salary *= raise  
        End Sub  
        Public Event salaryReviewTime()  
    End Structure  
    ```  
  
     Поле `salary` в предыдущем примере имеет `Private`, что означает, что оно недоступно за пределами структуры, даже из содержащего класса. Однако процедура `giveRaise` `Public`, поэтому ее можно вызывать вне структуры. Аналогичным образом можно вызвать событие `salaryReviewTime` за пределами структуры.  
  
     В дополнение к переменным, `Sub` процедурам и событиям можно также определить константы, `Function` процедуры и свойства в структуре. Можно назначить не более одного свойства в качестве *свойства по умолчанию*при условии, что оно принимает по крайней мере один аргумент. Можно выполнить обработку события с помощью [общей](../../../../visual-basic/language-reference/modifiers/shared.md) процедуры`Sub`. Дополнительные сведения см. в разделе [инструкции. объявление и вызов свойства по умолчанию в Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md).  
  
## <a name="see-also"></a>См. также

- [Типы данных](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [Простые типы данных](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [Составные типы данных](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [Структуры](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Устранение неполадок, связанных с типами данных](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Переменные структуры](../../../../visual-basic/programming-guide/language-features/data-types/structure-variables.md)
- [Структуры и другие элементы программирования](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)
- [Структуры и классы](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)
- [Тип данных, определенный пользователем](../../../../visual-basic/language-reference/data-types/user-defined-data-type.md)
