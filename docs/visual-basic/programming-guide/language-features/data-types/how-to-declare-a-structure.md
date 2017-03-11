---
title: "Практическое руководство. Объявление структуры (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "объявления, структуры"
  - "операторы [Visual Basic], структура"
  - "structure - операторы"
  - "структуры, объявление"
ms.assetid: d5e98381-eb81-47d4-af83-48cc534a2572
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# Практическое руководство. Объявление структуры (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Объявление структуры начинается [Оператор Structure](../../../../visual-basic/language-reference/statements/structure-statement.md) и завершается оператором `End` `Structure`.  Между этими двумя операторами должен быть объявлен хотя бы один *элемент*.  Элементы могут иметь любой тип данных, но хотя бы один должен не быть общей переменной, либо не быть общим или непользовательским событием.  
  
 Невозможна инициализация каких\-либо элементов структуры в объявлении структуры.  Если объявлено, что переменная имеет тип структуры, элементам присваиваются значения путем доступа к ним через переменную.  
  
 Обсуждение различий между структурами и классами содержатся в разделе [Структуры и классы](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md).  
  
 Для демонстрационных целей рассмотрим ситуацию, в которой необходимо отследить информацию об имени сотрудника, добавочном номере телефона и зарплате.  Структура позволяет сделать это в одной переменной.  
  
### Объявление структуры  
  
1.  Создайте начальные и конечные инструкции для структуры.  
  
     Можно указать уровень доступа для структуры с помощью [Public](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md) или [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) [Private](../../../../visual-basic/language-reference/modifiers/private.md), или можно оставить ее по умолчанию `Public`.  
  
    ```  
    Private Structure employee  
    End Structure  
    ```  
  
2.  Добавьте элементы в тело структуры.  
  
     Структура должна иметь по крайней мере один элемент.  Необходимо объявить каждый элемент и указать уровень доступа для него.  При использовании [Оператор Dim](../../../../visual-basic/language-reference/statements/dim-statement.md) без любых ключевых слов, доступность по умолчанию `Public`.  
  
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
  
     Поле `salary` в предыдущем примере является `Private`, это значит, что оно является недоступным за пределами структуры даже из содержащего класса.  Однако процедура `giveRaise` является `Public`, поэтому она может быть вызвана за пределами структуры.  Аналогично за пределами структуры можно вызывать событие `salaryReviewTime`.  
  
     В дополнение к переменным, процедурам `Sub` и событиям в структуре можно также определить константы, процедуры `Function` и свойства.  Можно назначить не более одного *свойства по умолчанию*, предоставляющего по крайней мере один аргумент.  Обработка события возможна с помощью процедуры [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) `Sub`.  Дополнительные сведения см. в разделе [Практическое руководство. Объявление и вызов свойства по умолчанию в Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md).  
  
## См. также  
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