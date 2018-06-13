---
title: Практическое руководство. Объявление структуры (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], structures
- structure statements [Visual Basic]
- statements [Visual Basic], structure
- structures [Visual Basic], declaring
ms.assetid: d5e98381-eb81-47d4-af83-48cc534a2572
ms.openlocfilehash: 6128addd60609bfc88a1409648fb320bc7089974
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33650031"
---
# <a name="how-to-declare-a-structure-visual-basic"></a>Практическое руководство. Объявление структуры (Visual Basic)
Объявление структуры с начинается [оператор Structure](../../../../visual-basic/language-reference/statements/structure-statement.md), и завершается оператором `End` `Structure` инструкции. Между этими двумя операторами необходимо объявить по крайней мере один *элемент*. Элементы могут иметь любой тип данных, но по крайней мере один должен быть не общей переменной или непользовательским событий.  
  
 Не удалось инициализировать любого из элементов структуры в объявлении структуры. При объявлении переменной с типом структуры, можно присвоить значения элементы путем доступа к ним через переменную.  
  
 Описание различий между структур и классов см. в разделе [структуры и классы](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md).  
  
 Для простоты примера рассмотрим ситуацию, место для отслеживания имя, телефон и заработной платы сотрудника. Структура позволяет сделать это в одной переменной.  
  
### <a name="to-declare-a-structure"></a>Объявление структуры  
  
1.  Создайте начальный и конечный инструкции для структуры.  
  
     Можно указать уровень доступа для структуры с помощью [открытый](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), или [закрытый](../../../../visual-basic/language-reference/modifiers/private.md) ключевое слово, или можно оставить значение по умолчанию `Public`.  
  
    ```  
    Private Structure employee  
    End Structure  
    ```  
  
2.  Добавьте элементы в тело структуры.  
  
     Структуры должны иметь хотя бы один элемент. Необходимо объявить каждый элемент и указать уровень доступа для него. Если вы используете [оператор Dim](../../../../visual-basic/language-reference/statements/dim-statement.md) без любых ключевых слов, доступность по умолчанию `Public`.  
  
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
  
     `salary` Поле в предыдущем примере является `Private`, это означает, что он недоступным за пределами структуры даже из содержащего класса. Тем не менее `giveRaise` процедура `Public`, поэтому он может быть вызвана за пределами структуры. Аналогичным образом, чтобы увеличить `salaryReviewTime` событие вне структуры.  
  
     В дополнение к переменным `Sub` процедуры, а также события можно также определить константы, `Function` процедуры и свойства в структуре. Можно назначить только одно свойство как *свойство по умолчанию*, если оно может принимать хотя бы один аргумент. Можно обработать событие с [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) `Sub` процедуры. Дополнительные сведения см. в разделе [как: объявление и вызов свойства по умолчанию в Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md).  
  
## <a name="see-also"></a>См. также  
 [Типы данных](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [Простые типы данных](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)  
 [Составные типы данных](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)  
 [Типы значений и ссылочные типы](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [Структуры](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [Устранение неполадок, связанных с типами данных](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [Переменные структуры](../../../../visual-basic/programming-guide/language-features/data-types/structure-variables.md)  
 [Структуры и другие элементы программирования](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)  
 [Структуры и классы](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)  
 [Тип данных, определенный пользователем](../../../../visual-basic/language-reference/data-types/user-defined-data-type.md)
