---
title: Практическое руководство. Объявление структуры (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], structures
- structure statements [Visual Basic]
- statements [Visual Basic], structure
- structures [Visual Basic], declaring
ms.assetid: d5e98381-eb81-47d4-af83-48cc534a2572
ms.openlocfilehash: a52daddaa8701ccca9bd9b5b4a48535a6ffa19ed
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59343562"
---
# <a name="how-to-declare-a-structure-visual-basic"></a>Практическое руководство. Объявление структуры (Visual Basic)
Начать объявление структуры [оператор Structure](../../../../visual-basic/language-reference/statements/structure-statement.md), и завершается с `End Structure` инструкции. Между этими двумя операторами должен быть объявлен по крайней мере *элемент*. Элементы могут быть любого типа данных, но по крайней мере один должен быть не являющаяся общей переменная или непользовательским событий.  
  
 Вы не можете инициализировать любого из элементов структуры в объявлении структуры. Если объявить переменную типа структуры, присваиваются значения в элементы, доступ к ним через переменную.  
  
 Описание различий между структуры и классы, см. в разделе [структуры и классы](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md).  
  
 Для демонстрационных целей рассмотрим ситуацию, место для отслеживания имя сотрудника, телефон и заработной платы. Структура позволяет сделать это в одной переменной.  
  
### <a name="to-declare-a-structure"></a>Объявление структуры  
  
1. Создайте начальный и конечный инструкции для структуры.  
  
     Можно указать уровень доступа структуры с помощью [открытый](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), или [частного](../../../../visual-basic/language-reference/modifiers/private.md) ключевое слово, или можно разрешить его по умолчанию `Public`.  
  
    ```  
    Private Structure employee  
    End Structure  
    ```  
  
2. Добавьте элементы в тексте структуры.  
  
     Структуры должны иметь хотя бы один элемент. Необходимо объявить каждый элемент и указать уровень доступа для него. Если вы используете [оператор Dim](../../../../visual-basic/language-reference/statements/dim-statement.md) без любые ключевые слова, доступность по умолчанию `Public`.  
  
    ```  
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
  
     `salary` Поле в предыдущем примере является `Private`, который означает, что он недоступен вне структуры, даже от содержащего класса. Тем не менее `giveRaise` процедура `Public`, поэтому он может вызываться из вне структуры. Аналогичным образом, вы можете отправить `salaryReviewTime` событие вне структуры.  
  
     Кроме переменных `Sub` процедуры и события, можно также определить константы, `Function` процедуры и свойства в структуре. Можно указать не более одного свойства как *свойство по умолчанию*, предоставляющего по крайней мере один аргумент. Можно обработать событие с [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) `Sub` процедуры. Дополнительные сведения см. в разделе [Как Объявление и вызов свойства по умолчанию в Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md).  
  
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
