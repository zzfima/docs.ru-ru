---
title: Разделяемые методы (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: a974a68010fe80a07e83ac31e109bbf1c2b955e2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54568781"
---
# <a name="partial-methods-visual-basic"></a>Разделяемые методы (Visual Basic)
Разделяемые методы позволяют разработчикам использовать пользовательскую логику в код. Как правило код входит в созданном конструктором класса. Разделяемые методы определяются в разделяемый класс, созданный генератором кода, и они часто используются для предоставления уведомления, что что-то было изменено. Они позволяют разработчику указать пользовательское поведение в ответ на изменение.  
  
 Конструктор генератора кода определяет только сигнатуру метода и один или несколько вызовов метода. Разработчики могут затем предоставить реализации метода, если они хотят настроить поведение сформированного кода. При реализации не указаны, вызовы метода удаляются компилятором, что потери производительности.  
  
## <a name="declaration"></a>Объявление  
 Созданный код помечает определение разделяемого метода, поместив ключевое слово `Partial` в начале строки подписи.  
  
```vb  
Partial Private Sub QuantityChanged()  
End Sub  
```  
  
 Определение должно удовлетворять следующим условиям:  
  
-   Этот метод должен быть `Sub`, а не `Function`.  
  
-   Тело метода должно быть пустым.  
  
-   Модификатор доступа должен быть `Private`.  
  
## <a name="implementation"></a>Реализация  
 Реализация состоит заполнения тела разделяемого метода. Реализация обычно находится в отдельном разделяемом классе из определения и записывается разработчиком, который хочет расширить созданный код.  
  
```vb  
Private Sub QuantityChanged()  
'    Code for executing the desired action.  
End Sub  
```  
  
 Предыдущий пример точно дублирует подпись в объявлении, но возможны вариации. В частности, другие модификаторы могут добавляться, такие как `Overloads` или `Overrides`. Только один `Overrides` модификатор может применяться. Дополнительные сведения о модификаторах метода, см. в разделе [оператор Sub](../../../../visual-basic/language-reference/statements/sub-statement.md).  
  
## <a name="use"></a>Использовать  
 Вызовите разделяемый метод, как и любой другой `Sub` процедуры. Если метод был реализован, вычисляются аргументы и выполняется тело метода. Однако следует помните, что реализация разделяемого метода не является обязательным. Если метод не реализован, его вызов не влияет, и выражения, которые передаются как аргументы метода не вычисляются.  
  
## <a name="example"></a>Пример  
 В файле с именем Product.Designer.vb, определить `Product` классом, имеющим `Quantity` свойство.  
  
 [!code-vb[VbVbalrPartialMeths#4](./codesnippet/VisualBasic/partial-methods_1.vb)]  
  
 В файле с именем Product.vb, обеспечить реализацию для `QuantityChanged`.  
  
 [!code-vb[VbVbalrPartialMeths#5](./codesnippet/VisualBasic/partial-methods_2.vb)]  
  
 Наконец, в методе Main проекта, объявите `Product` экземпляра и укажите начальное значение для его `Quantity` свойство.  
  
 [!code-vb[VbVbalrPartialMeths#6](./codesnippet/VisualBasic/partial-methods_3.vb)]  
  
 Откроется окно сообщения, отображается следующее сообщение:  
  
 `Quantity was changed to 100`  
  
## <a name="see-also"></a>См. также
- [Оператор Sub](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [Подпрограммы](./sub-procedures.md)
- [Необязательные параметры](./optional-parameters.md)
- [Partial](../../../../visual-basic/language-reference/modifiers/partial.md)
- [Создание кода в LINQ to SQL](../../../../framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md)
- [Добавление бизнес-логики с использованием разделяемых методов](../../../../framework/data/adonet/sql/linq/adding-business-logic-by-using-partial-methods.md)
