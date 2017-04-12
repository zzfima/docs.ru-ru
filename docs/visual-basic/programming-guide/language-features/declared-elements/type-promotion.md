---
title: "Введите повышение (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- declared elements, scope
- visibility, declared elements
- Partial keyword, unexpected results with type promotion
- scope, declared elements
- scope, Visual Basic
- type promotion
- declared elements, visibility
ms.assetid: 035eeb15-e4c5-4288-ab3c-6bd5d22f7051
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: d732e765fc28eaedc0deab477dbf9955a40e97c9
ms.lasthandoff: 03/13/2017

---
# <a name="type-promotion-visual-basic"></a>Повышение типа (Visual Basic)
При объявлении элемента программирования в модуле, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] повышает уровень его области до пространства имен, содержащего модуль. Это называется *введите повышения*.  
  
 В следующем примере показано определение схемы модуля и двух членов этого модуля.  
  
 [!code-vb[VbVbalrDeclaredElements&#1;](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_1.vb)]  
  
 В `projModule`, программирования элементы, объявленные на уровне модуля, продвигаются в `projNamespace`. В предыдущем примере `basicEnum` и `innerClass` повышаются, но `numberSub` — нет, поскольку он не объявлен на уровне модуля.  
  
## <a name="effect-of-type-promotion"></a>Эффект повышения типа  
 Эффект повышения типа является то, что уточняющую строку не нужно включать имя модуля. Следующий пример вызывает две процедуры в предыдущем примере.  
  
 [!code-vb[VbVbalrDeclaredElements&#2;](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_2.vb)]  
  
 В предыдущем примере для первого вызова используются полные квалификационные строки. Однако это не требуется из-за повышения типов. Во втором вызове также доступ к членам модуля без включения `projModule` в строки квалификации.  
  
## <a name="defeat-of-type-promotion"></a>Отмена повышения типа  
 Если пространство имен уже содержит член с тем же именем члена модуля, повышение типа для члена модуля отменяется. Следующий пример показывает определение схемы перечисления и модуль в том же пространстве имен.  
  
 [!code-vb[VbVbalrDeclaredElements&#3;](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_3.vb)]  
  
 В предыдущем примере [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] не удается повысить уровень класса `abc` для `thisNameSpace` , поскольку уже существует перечисление с тем же именем на уровне пространства имен. Чтобы получить доступ к `abcSub`, необходимо использовать полное имя пространства имен строка `thisNamespace.thisModule.abc.abcSub`. Тем не менее, класс `xyz` по-прежнему повышается, и можно получить доступ к `xyzSub` с короткой строки квалификации `thisNamespace.xyz.xyzSub`.  
  
### <a name="defeat-of-type-promotion-for-partial-types"></a>Отмена повышения типа для разделяемых типов  
 Если класс или структуру в модуле использует [частичного](../../../../visual-basic/language-reference/modifiers/partial.md) ключевое слово, повышение типа является невозможным для этого класса или структуры, ли пространство имен содержит член с тем же именем. Других элементов в модуле повышение типа по-прежнему возможно.  
  
 **Последствия.** Отмена повышения типа частичного определения может привести к непредсказуемым результатам и даже ошибкам компилятора. Следующий пример показывает каркас определения разделяемого класса, один из которых находится внутри модуля.  
  
 [!code-vb[VbVbalrDeclaredElements&#4;](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_4.vb)]  
  
 В предыдущем примере разработчик может ожидать, что компилятор слияние двух частично выполненных определений `sampleClass`. Тем не менее, компилятор не учитывает частичное определение внутри акции `sampleModule`. В результате он попытается скомпилировать два отдельных и различных класса, обе с именем `sampleClass` , но с разными квалификационными путями.  
  
 Компилятор объединяет частичные определения, только если их полные пути идентичны.  
  
## <a name="recommendations"></a>Рекомендации  
 Следующие рекомендации представляют рекомендаций программирования.  
  
-   **Уникальные имена.** Если у вас есть полный контроль над именованием элементов программирования, рекомендуется всегда использовать уникальные имена везде. Одинаковые имена требуют дополнительного уточнения и могут сделать код трудным для чтения. Они также может привести к непредсказуемым результатам и опасным ошибкам.  
  
-   **Полное имя пространства имен.** При работе с модулями и другими элементами в одном пространстве имен безопаснее использовать полное определение для всех элементов программирования. Если повышение типа для члена модуля отменяется, а не полностью соответствуют этому элементу, может случайно доступ к другому элементу программирования.  
  
## <a name="see-also"></a>См. также  
 [Оператор Module](../../../../visual-basic/language-reference/statements/module-statement.md)   
 [Оператор Namespace](../../../../visual-basic/language-reference/statements/namespace-statement.md)   
 [Частичное](../../../../visual-basic/language-reference/modifiers/partial.md)   
 [Область видимости в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)   
 [Практическое руководство: управление областью действия переменной](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-scope-of-a-variable.md)   
 [Ссылки на объявленные элементы](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
