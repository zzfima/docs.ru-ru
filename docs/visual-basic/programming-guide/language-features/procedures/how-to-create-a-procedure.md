---
title: "Практическое руководство. Создание процедуры (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- Visual Basic code, reusing
- procedure declarations
- procedures [Visual Basic], about procedures
ms.assetid: 4f779247-0b50-47e8-9e5c-ab5cf39ac0d2
caps.latest.revision: "27"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 56a44918b7a1426d215cee0ff2981f5763432a48
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-procedure-visual-basic"></a>Практическое руководство. Создание процедуры (Visual Basic)
Заключите процедуру между начальной оператор объявления (`Sub` или `Function`) и конечный оператор объявления (`End Sub` или `End Function`). Код процедуры содержится между этими операторами.  
  
 Процедура не может содержать другую процедуру, поэтому его начала и конца инструкции должны быть вне любых других процедур.  
  
 Если у вас есть код, который выполняет ту же задачу в разных местах, можно написать задачу один раз как процедуру и вызвать его из различных мест в коде.  
  
### <a name="to-create-a-procedure-that-does-not-return-a-value"></a>Чтобы создать процедуру, которая не возвращает значение  
  
1.  Вне любых других процедур используйте `Sub` инструкции, за которой следует `End Sub` инструкции.  
  
2.  В `Sub` инструкции, выполните `Sub` ключевого слова with имя процедуры, а затем список параметров в круглых скобках.  
  
3.  Поместите операторы кода процедуры между `Sub` и `End Sub` инструкции.  
  
### <a name="to-create-a-procedure-that-returns-a-value"></a>Создание процедуры, возвращающей значение  
  
1.  Вне любых других процедур используйте `Function` инструкции, за которой следует `End Function` инструкции.  
  
2.  В `Function` инструкции, выполните `Function` ключевого слова with имя процедуры, а затем список параметров в круглых скобках, а затем `As` предложение, указывающие тип данных возвращаемого значения.  
  
3.  Поместите операторы кода процедуры между `Function` и `End Function` инструкции.  
  
4.  Используйте `Return` инструкцию, чтобы возвращать значение вызывающему коду.  
  
### <a name="to-connect-your-new-procedure-with-the-old-repetitive-blocks-of-code"></a>Для подключения новой процедуры со старыми повторяющимися блоками кода  
  
1.  Убедитесь, что определение новой процедуры в том месте, где старый код не имеет доступа к нему.  
  
2.  В блок кода, старого, повторяющихся, замените операторы, которые выполняют повторяющихся задач с помощью одной инструкции, которая вызывает `Sub` или `Function` процедуры.  
  
3.  Если процедура является `Function` , возвращающий значение, убедитесь, что вызывающий оператор выполняет действие с возвращаемым значением, например для сохранения его в переменной, иначе значение будет потеряно.  
  
## <a name="example"></a>Пример  
 Следующие `Function` процедуры рассчитывается длинной стороны, гипотенуза прямоугольного треугольника, заданы значения для двух других сторон.  
  
 [!code-vb[VbVbcnProcedures#1](./codesnippet/VisualBasic/how-to-create-a-procedure_1.vb)]  
  
## <a name="see-also"></a>См. также  
 [Процедуры](./index.md)  
 [Подпрограммы](./sub-procedures.md)  
 [Процедуры функций](./function-procedures.md)  
 [Процедуры свойств](./property-procedures.md)  
 [Процедуры операторов](./operator-procedures.md)  
 [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)  
 [Рекурсивные процедуры](./recursive-procedures.md)  
 [Перегрузка процедур](./procedure-overloading.md)  
 [Объекты и классы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [Объектно-ориентированное программирование](http://msdn.microsoft.com/library/1cf6e655-3f30-45f1-9a5d-4a88ca24a1c2)
