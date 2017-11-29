---
title: "Разделяемые методы (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.PartialMethod
- PartialMethod
helpviewer_keywords:
- custom logic into code [Visual Basic]
- partial methods [Visual Basic]
- partial [Visual Basic], methods [Visual Basic]
- methods [Visual Basic], partial methods
- inserting custom logic into code
ms.assetid: 74b3368b-b348-44a0-a326-7d7dc646f4e9
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8ebedd6f8173e3c349240d24ddaf16e4841f67a4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="partial-methods-visual-basic"></a>Разделяемые методы (Visual Basic)
Разделяемые методы позволяют разработчикам использовать пользовательскую логику в код. Обычно код является частью класса автоматически созданный конструктором. Разделяемые методы определяются в разделяемый класс, созданный генератор кода, и обычно используются для предоставления уведомления, что что-то был изменен. Они позволяют разработчику указать пользовательское поведение в ответ на изменение.  
  
 Конструктор генератора кода определяет только сигнатуру метода и один или несколько вызовов метода. Разработчики могут затем предоставить реализации метода, если они хотят настроить поведение созданного кода. При реализации не указаны, вызовы метода удаляются компилятором, что потери производительности.  
  
## <a name="declaration"></a>Объявление  
 Созданный код помечает определение разделяемого метода, поместив ключевое слово `Partial` в начале строки сигнатуры.  
  
```vb  
Partial Private Sub QuantityChanged()  
End Sub  
```  
  
 Определение должно удовлетворять следующим условиям:  
  
-   Метод должен быть `Sub`, а не `Function`.  
  
-   Тело метода должно быть пустым.  
  
-   Модификатор доступа должны иметь `Private`.  
  
## <a name="implementation"></a>Реализация  
 Реализация состоит заполнения тела разделяемого метода. Реализация обычно находится в отдельном разделяемом классе из определения и записывается разработчиком, который требуется расширить созданный код.  
  
```vb  
Private Sub QuantityChanged()  
'    Code for executing the desired action.  
End Sub  
```  
  
 Предыдущий пример точно дублирует подпись в объявлении, но возможны также другие варианты. В частности, другие модификаторы можно добавить, например `Overloads` или `Overrides`. Только один `Overrides` модификатор разрешен. Дополнительные сведения о метод модификаторы см [оператор Sub](../../../../visual-basic/language-reference/statements/sub-statement.md).  
  
## <a name="use"></a>Применение  
 Вызовите разделяемый метод, как и любой другой `Sub` процедуры. Если метод был реализован, вычисляются аргументы и выполняется тело метода. Однако следует помните, что реализация разделяемого метода является необязательным. Если метод не реализован, его вызов не оказывает влияния и не вычисляются выражения, передаваемые как аргументы в метод.  
  
## <a name="example"></a>Пример  
 В файле с именем Product.Designer.vb, определить `Product` классом, имеющим `Quantity` свойство.  
  
 [!code-vb[VbVbalrPartialMeths#4](./codesnippet/VisualBasic/partial-methods_1.vb)]  
  
 В файле с именем Product.vb предоставить реализацию `QuantityChanged`.  
  
 [!code-vb[VbVbalrPartialMeths#5](./codesnippet/VisualBasic/partial-methods_2.vb)]  
  
 Наконец, в методе Main проекта объявите `Product` экземпляра и укажите начальное значение для его `Quantity` свойство.  
  
 [!code-vb[VbVbalrPartialMeths#6](./codesnippet/VisualBasic/partial-methods_3.vb)]  
  
 Появится окно сообщения, будет отображено следующее сообщение:  
  
 `Quantity was changed to 100`  
  
## <a name="see-also"></a>См. также  
 [Оператор Sub](../../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Подпрограммы](./sub-procedures.md)  
 [Необязательные параметры](./optional-parameters.md)  
 [Partial](../../../../visual-basic/language-reference/modifiers/partial.md)  
 [Создание кода в LINQ to SQL](https://msdn.microsoft.com/library/bb399400)  
 [Добавление бизнес-логики с помощью разделяемых методов](https://msdn.microsoft.com/library/bb546176)
