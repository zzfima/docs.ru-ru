---
title: "Практическое руководство. Создание переменной, которая не изменяет значение (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- variables [Visual Basic], read-only
- variables [Visual Basic], constant value
ms.assetid: 86b59266-25df-4635-ae15-9b59c411d036
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d1475553e64fef92ec3f3bb7e1b4fbfb357dbec8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-variable-that-does-not-change-in-value-visual-basic"></a>Практическое руководство. Создание переменной, которая не изменяет значение (Visual Basic)
Понятие переменной, которая не изменяет его значение может показаться противоречивым. Но существуют ситуации, когда константа не может быть выполнено и полезно иметь переменную с фиксированным значением. В этом случае можно определить переменную-член с [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md) ключевое слово.  
  
 Нельзя использовать [оператор Const](../../../../visual-basic/language-reference/statements/const-statement.md) для объявления и присвоения постоянного значения в следующих случаях:  
  
-   `Const` Инструкция не принимает тип данных, который вы хотите использовать  
  
-   Вы не знаете значение во время компиляции  
  
-   Не удается вычислить постоянное значение во время компиляции  
  
### <a name="to-create-a-variable-that-does-not-change-in-value"></a>Создание переменной, которая не изменяет значение  
  
1.  На уровне модуля, объявите переменную-член с [оператор Dim](../../../../visual-basic/language-reference/statements/dim-statement.md)и включать [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md) ключевое слово.  
  
    ```  
    Dim ReadOnly timeStarted  
    ```  
  
     Можно указать `ReadOnly` только на переменную-член. Это означает, что необходимо определить переменную на уровне модуля, вне любой процедуры.  
  
2.  Если можно вычислить значение в одной инструкции во время компиляции, используйте предложение инициализации в `Dim` инструкции. Выполните [как](../../../../visual-basic/language-reference/statements/as-clause.md) предложение со знака равенства (`=`), за которым следует выражение. Убедитесь, что компилятор может вычислить это выражение с постоянным значением.  
  
    ```  
    Dim ReadOnly timeStarted As Date = Now  
    ```  
  
     Можно присвоить значение `ReadOnly` переменной только один раз. После этого код не может изменяться его значение.  
  
     Если вы не знаете значение во время компиляции или не может вычислить во время компиляции в одной инструкции, вы по-прежнему можно назначить во время выполнения в конструкторе. Чтобы сделать это, необходимо объявить `ReadOnly` переменных на уровне класса или структуры. В конструкторе для этого класса или структуры вычисление фиксированное значение переменной и присвоить его переменной перед возвратом из конструктора.  
  
## <a name="see-also"></a>См. также  
 [WriteOnly](../../../../visual-basic/language-reference/modifiers/writeonly.md)  
 [Оператор Const](../../../../visual-basic/language-reference/statements/const-statement.md)
