---
title: Практическое руководство. Создание процедуры (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- Visual Basic code, reusing
- procedure declarations
- procedures [Visual Basic], about procedures
ms.assetid: 4f779247-0b50-47e8-9e5c-ab5cf39ac0d2
ms.openlocfilehash: 56099d334a03e85b816cf48983cbbead0784ef5b
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59320396"
---
# <a name="how-to-create-a-procedure-visual-basic"></a>Практическое руководство. Создание процедуры (Visual Basic)
Заключите процедуру между начальной оператор объявления (`Sub` или `Function`) и окончания оператор объявления (`End Sub` или `End Function`). Код процедуры находится в диапазоне от этих инструкций.  
  
 Процедура не может содержать другую процедуру, поэтому его начала и конца инструкции должны быть вне любых других процедур.  
  
 Если у вас есть код, который выполняет ту же задачу в разных местах, можно написать задачу один раз как процедуру и затем вызывать из различных мест в коде.  
  
### <a name="to-create-a-procedure-that-does-not-return-a-value"></a>Чтобы создать процедуру, которая не возвращает значение  
  
1. Вне любых других процедур используйте `Sub` , применив инструкцию `End Sub` инструкции.  
  
2. В `Sub` инструкции, следуйте `Sub` ключевое слово с именем процедуры, затем список параметров в круглых скобках.  
  
3. Поместите операторы кода процедуры между `Sub` и `End Sub` инструкций.  
  
### <a name="to-create-a-procedure-that-returns-a-value"></a>Создание процедуры, возвращающей значение  
  
1. Вне любых других процедур используйте `Function` , применив инструкцию `End Function` инструкции.  
  
2. В `Function` инструкции, следуйте `Function` ключевое слово с именем процедуры, затем список параметров в скобки, а затем `As` предложение, указывающие тип данных возвращаемого значения.  
  
3. Поместите операторы кода процедуры между `Function` и `End Function` инструкций.  
  
4. Используйте `Return` инструкция возвращает значение вызывающему коду.  
  
### <a name="to-connect-your-new-procedure-with-the-old-repetitive-blocks-of-code"></a>Для подключения новой процедуры с помощью старого, повторяющихся блоков кода  
  
1. Убедитесь, что определение новой процедуры в том месте, где старый код имеет доступ к нему.  
  
2. В блок кода старые, повторяющихся, замените операторы, которые выполняют повторяющихся задач с помощью одного оператора, который вызывает `Sub` или `Function` процедуры.  
  
3. Если процедура является `Function` , возвращает значение, убедитесь, что вызывающий оператор выполняет действие с возвращаемым значением, например сохраняет его в переменной, в противном случае значение будет потеряно.  
  
## <a name="example"></a>Пример  
 Следующие `Function` процедура вычисляет самая длинная сторона гипотенузы прямоугольного треугольника, значения для двух других сторон.  
  
 [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]  
  
## <a name="see-also"></a>См. также

- [Процедуры](./index.md)
- [Подпрограммы](./sub-procedures.md)
- [Процедуры функций](./function-procedures.md)
- [Процедуры свойств](./property-procedures.md)
- [Процедуры операторов](./operator-procedures.md)
- [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)
- [Рекурсивные процедуры](./recursive-procedures.md)
- [Перегрузка процедур](./procedure-overloading.md)
- [Объекты и классы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [Объектно ориентированного программирования (Visual Basic)](../../concepts/object-oriented-programming.md)
