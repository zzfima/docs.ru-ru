---
title: Повышение типа (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- declared elements [Visual Basic], scope
- visibility [Visual Basic], declared elements
- Partial keyword [Visual Basic], unexpected results with type promotion
- scope [Visual Basic], declared elements
- scope [Visual Basic], Visual Basic
- type promotion
- declared elements [Visual Basic], visibility
ms.assetid: 035eeb15-e4c5-4288-ab3c-6bd5d22f7051
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ddb0d61f0f1c94e8e28493d0c62afe1e09503804
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="type-promotion-visual-basic"></a>Повышение типа (Visual Basic)
При объявлении элемента программирования в модуле Visual Basic повышает уровень его области до пространства имен, содержащего модуль. Это называется *введите рекламной акции*.  
  
 В следующем примере показано определение схемы модуля и двух членов этого модуля.  
  
 [!code-vb[VbVbalrDeclaredElements#1](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_1.vb)]  
  
 В пределах `projModule`программирования элементы, объявленные на уровне модуля, продвигаются в `projNamespace`. В приведенном выше примере `basicEnum` и `innerClass` отправит запрос, но `numberSub` — нет, поскольку он не объявлен как на уровне модуля.  
  
## <a name="effect-of-type-promotion"></a>Эффект повышения типа  
 Повышение типа действует, уточняющей строки не должны включать имя модуля. Следующий пример вызывает две процедуры в предыдущем примере.  
  
 [!code-vb[VbVbalrDeclaredElements#2](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_2.vb)]  
  
 В предыдущем примере первый вызов использует квалификации завершения строки. Однако это не требуется из-за повышения типов. Во втором вызове также доступ к членам модуля без включения `projModule` в строки квалификации.  
  
## <a name="defeat-of-type-promotion"></a>Отмена повышения типа  
 Если пространство имен уже имеется член с тем же именем члена модуля, повышение типа для члена модуля отменяется. В следующем примере показано каркасное определение перечисления и модуль в том же пространстве имен.  
  
 [!code-vb[VbVbalrDeclaredElements#3](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_3.vb)]  
  
 В предыдущем примере, Visual Basic не может повысить уровень класса `abc` для `thisNameSpace` , так как уже существует перечисление с тем же именем на уровне пространства имен. Чтобы получить доступ к `abcSub`, необходимо использовать полной строки `thisNamespace.thisModule.abc.abcSub`. Однако для класса `xyz` по-прежнему повышается, и имеет доступ к `xyzSub` с более короткие строки квалификации `thisNamespace.xyz.xyzSub`.  
  
### <a name="defeat-of-type-promotion-for-partial-types"></a>Отмена повышения типа для разделяемых типов  
 Если класс или структуру в модуле использует [частичного](../../../../visual-basic/language-reference/modifiers/partial.md) ключевое слово, повышение типа автоматически отменяется для этого класса или структуры, независимо от того, имеется ли пространство имен содержит член с тем же именем. Другие элементы в модуль, по-прежнему возможно повышение типа.  
  
 **Последствия.** Отмена повышения типа частичного определения может привести к непредсказуемым результатам и даже ошибкам компилятора. В следующем примере каркас разделяемые определения класса, один из которых находится внутри модуля.  
  
 [!code-vb[VbVbalrDeclaredElements#4](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_4.vb)]  
  
 В предыдущем примере разработчик может ожидать, что компилятор слияние двух частично выполненных определений `sampleClass`. Однако компилятор не учитывает продвижение частичное определение внутри `sampleModule`. В результате он попытается скомпилировать два отдельных и различных класса, и именованные `sampleClass` , но с другой квалификации пути.  
  
 Компилятор объединяет частичные определения, только если их полные пути идентичны.  
  
## <a name="recommendations"></a>Рекомендации  
 Следующие рекомендации представляют хорошим стилем программирования.  
  
-   **Уникальные имена.** Если у вас есть полный контроль над именованием элементов программирования, рекомендуется всегда использовать уникальные имена everywhere. Идентичные имена требуют дополнительного уточнения и могут сделать код труднее читаться. Они также могут привести к непредсказуемым результатам и неявных ошибок.  
  
-   **Полное имя пространства имен.** При работе с модулями и другие элементы в одном пространстве имен безопаснее использовать полное определение для всех элементов программирования. Если повышение типа для члена модуля отменяется, не полностью уточнить этот член может случайно доступ к другому элементу программирования.  
  
## <a name="see-also"></a>См. также  
 [Оператор Module](../../../../visual-basic/language-reference/statements/module-statement.md)  
 [Оператор Namespace](../../../../visual-basic/language-reference/statements/namespace-statement.md)  
 [Partial](../../../../visual-basic/language-reference/modifiers/partial.md)  
 [Область в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)  
 [Практическое руководство. Управление областью действия переменной](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-scope-of-a-variable.md)  
 [Ссылки на объявленные элементы](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
