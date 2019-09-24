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
ms.openlocfilehash: 2cf4c788ec421c1e74ef7198496a92149e049752
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216719"
---
# <a name="how-to-create-a-procedure-visual-basic"></a>Практическое руководство. Создание процедуры (Visual Basic)

Процедура заключается в заключении между операторами начального объявления (`Sub` или `Function`) и завершающим оператором объявления`End Sub` ( `End Function`или). Весь код процедуры находится между этими операторами.

 Процедура не может содержать другую процедуру, поэтому ее начальные и конечные операторы должны находиться за пределами любой другой процедуры.

 Если у вас есть код, выполняющий одну и ту же задачу в разных местах, можно написать задачу один раз как процедуру, а затем вызвать ее из различных мест в коде.

### <a name="to-create-a-procedure-that-does-not-return-a-value"></a>Создание процедуры, которая не возвращает значение

1. За пределами любой другой процедуры `Sub` используйте оператор, за которым `End Sub` следует оператор.

2. `Sub` В инструкции `Sub` используйте ключевое слово с именем процедуры, а затем список параметров в круглых скобках.

3. Поместите операторы кода процедуры между `Sub` операторами и. `End Sub`

### <a name="to-create-a-procedure-that-returns-a-value"></a>Создание процедуры, возвращающей значение

1. За пределами любой другой процедуры `Function` используйте оператор, за которым `End Function` следует оператор.

2. В инструкции используйте ключевое слово с именем процедуры, затем список параметров в круглых скобках, а затем `As` предложение, указывающее тип данных возвращаемого значения. `Function` `Function`

3. Поместите операторы кода процедуры между `Function` операторами и. `End Function`

4. `Return` Используйте оператор, чтобы вернуть значение в вызывающий код.

### <a name="to-connect-your-new-procedure-with-the-old-repetitive-blocks-of-code"></a>Подключение новой процедуры к старым и повторяющимся блокам кода

1. Убедитесь, что вы определили новую процедуру в том месте, где старый код имеет к ней доступ.

2. В старом и повторяющемся блоке кода замените инструкции, выполняющие повторяющуюся задачу, на одну инструкцию, которая вызывает `Sub` процедуру `Function` или.

3. Если процедура `Function` возвращает значение, убедитесь, что вызывающая инструкция выполняет действие с возвращаемым значением, например, сохраняя его в переменной, или, в противном случае, значение будет потеряно.

## <a name="example"></a>Пример

 Следующая `Function` процедура вычисляет самую длинную сторону (гипотенузу) правого треугольника, учитывая значения двух других сторон:

 [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]

## <a name="see-also"></a>См. также

- [Процедуры](index.md)
- [Подпрограммы](sub-procedures.md)
- [Процедуры функций](function-procedures.md)
- [Процедуры свойств](property-procedures.md)
- [Процедуры операторов](operator-procedures.md)
- [Параметры и аргументы процедуры](procedure-parameters-and-arguments.md)
- [Рекурсивные процедуры](recursive-procedures.md)
- [Перегрузка процедур](procedure-overloading.md)
- [Объекты и классы](../objects-and-classes/index.md)
- [Object-Oriented Programming (Visual Basic)](../../concepts/object-oriented-programming.md) (Объектно-ориентированное программирование на языке Visual Basic)
