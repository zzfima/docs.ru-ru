---
title: "Циклические структуры (Visual Basic) | Документы Microsoft"
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
- control flow, loops
- For keyword [Visual Basic], loop structures
- loops
- loop structures
- statements [Visual Basic], loop
- Do statement, Do loops
- conditional statements, loop structures
ms.assetid: ecacb09b-a4c9-42be-98b2-a15d368b5db8
caps.latest.revision: 18
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
ms.openlocfilehash: c2835b9d9d22196447fb1863f6e4fa9bd11ecf0a
ms.lasthandoff: 03/13/2017

---
# <a name="loop-structures-visual-basic"></a>Циклические структуры (Visual Basic)
[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]циклические структуры позволяют выполнять одну или несколько строк кода несколько раз. Операторы в циклической структуре можно повторять, пока условие `True`, пока условие `False`, указанное число раз или один раз для каждого элемента в коллекции.  
  
 Ниже показана структура цикла, выполняет набор инструкций, пока условие не станет true.  
  
 ![Блок-схема Do... Пока цикл](../../../../visual-basic/programming-guide/language-features/control-flow/media/dountilloop.gif "DoUntilLoop")  
Выполнение набора инструкций, пока условие не станет true  
  
## <a name="while-loops"></a>Циклы while  
 The `While`... `End While` выполняет набор инструкций до тех пор, пока условие, заданное в `While` инструкция является `True`. Дополнительные сведения см. в разделе [во время... Завершить оператор While](../../../../visual-basic/language-reference/statements/while-end-while-statement.md).  
  
## <a name="do-loops"></a>Do-циклы  
 The `Do`... `Loop` позволяет проверить условие в начале или в конце структуры цикла. Можно также указать, следует ли повторять цикл, пока значение условия равно `True` или пока она не станет `True`. Дополнительные сведения см. в разделе [сделать... Цикл инструкции](../../../../visual-basic/language-reference/statements/do-loop-statement.md).  
  
## <a name="for-loops"></a>Циклы for  
 The `For`... `Next` выполняет заданное количество раз. Он использует переменная управления циклом, также называемый *счетчик*, чтобы отслеживать повторений. Укажите начальное и конечное значения для этого счетчика и при необходимости можно указать сумму, по которому будет увеличен за одно повторение к следующему. Дополнительные сведения см. в разделе [для... Следующий оператор](../../../../visual-basic/language-reference/statements/for-next-statement.md).  
  
## <a name="for-each-loops"></a>Для каждого из циклов  
 The `For Each`... `Next` выполняет набор инструкций один раз для каждого элемента в коллекции. Укажите переменную цикла, но нет определения ее начального или конечного значения. Дополнительные сведения см. в разделе [For Each... Следующий оператор](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).  
  
## <a name="see-also"></a>См. также  
 [Поток управления](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)   
 [Структуры критериев](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)   
 [Другие структуры управления](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)   
 [Вложенные структуры управления](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
