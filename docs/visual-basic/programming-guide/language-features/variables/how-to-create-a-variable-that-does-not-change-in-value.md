---
title: Практическое руководство. Создание переменной, которая не изменяет значение (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], read-only
- variables [Visual Basic], constant value
ms.assetid: 86b59266-25df-4635-ae15-9b59c411d036
ms.openlocfilehash: 7180e5141572d219ed02c57103e9d4b80cde536e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59342938"
---
# <a name="how-to-create-a-variable-that-does-not-change-in-value-visual-basic"></a>Практическое руководство. Создание переменной, которая не изменяет значение (Visual Basic)
Понятие переменной, которая не изменяет его значение может показаться противоречивым. Но существуют ситуации, когда константа не представляется возможным, и полезно иметь переменную с фиксированным значением. В этом случае можно определить переменную-член с [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md) ключевое слово.  
  
 Нельзя использовать [оператор Const](../../../../visual-basic/language-reference/statements/const-statement.md) объявить переменную и присвоить значение константы в следующих случаях:  
  
-   `Const` Оператор не принимает тип данных, который вы хотите использовать  
  
-   Вы не знаете значение во время компиляции  
  
-   Не удается вычислить постоянное значение во время компиляции  
  
### <a name="to-create-a-variable-that-does-not-change-in-value"></a>Для создание переменной, которая не изменяет значение  
  
1. На уровне модуля, объявите переменную-член с [оператор Dim](../../../../visual-basic/language-reference/statements/dim-statement.md)и включают [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md) ключевое слово.  
  
    ```  
    Dim ReadOnly timeStarted  
    ```  
  
     Можно указать `ReadOnly` только на переменную-член. Это означает, что необходимо определить переменную уровня модуля, вне любой процедуры.  
  
2. Если вы можете вычислить значение в одной инструкции во время компиляции, используйте предложение инициализации в `Dim` инструкции. Выполните [как](../../../../visual-basic/language-reference/statements/as-clause.md) предложение со знака равенства (`=`), за которым следует выражение. Убедитесь, что компилятор может вычислить это выражение с постоянным значением.  
  
    ```  
    Dim ReadOnly timeStarted As Date = Now  
    ```  
  
     Можно присвоить значение `ReadOnly` переменной только один раз. После этого код не может когда-либо измените его значение.  
  
     Если вы не знаете значение во время компиляции, или не удается вычислить во время компиляции в одной инструкции, вы по-прежнему можно назначить во время выполнения в конструкторе. Чтобы сделать это, необходимо объявить `ReadOnly` переменных на уровне класса или структуры. В конструкторе для этого класса или структуры вычисления фиксированное значение переменной и назначьте его переменной перед возвратом из конструктора.  
  
## <a name="see-also"></a>См. также

- [WriteOnly](../../../../visual-basic/language-reference/modifiers/writeonly.md)
- [Оператор Const](../../../../visual-basic/language-reference/statements/const-statement.md)
