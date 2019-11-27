---
title: Практическое руководство. Создание процедуры
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- Visual Basic code, reusing
- procedure declarations
- procedures [Visual Basic], about procedures
ms.assetid: 4f779247-0b50-47e8-9e5c-ab5cf39ac0d2
ms.openlocfilehash: a831814c18f97991fca8067f1c9c8e491da1b665
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344913"
---
# <a name="how-to-create-a-procedure-visual-basic"></a>Практическое руководство. Создание процедуры (Visual Basic)

Вы заключаете процедуру между оператором начального объявления (`Sub` или `Function`) и завершающим оператором объявления (`End Sub` или `End Function`). Весь код процедуры находится между этими операторами.

 Процедура не может содержать другую процедуру, поэтому ее начальные и конечные операторы должны находиться за пределами любой другой процедуры.

 Если у вас есть код, выполняющий одну и ту же задачу в разных местах, можно написать задачу один раз как процедуру, а затем вызвать ее из различных мест в коде.

### <a name="to-create-a-procedure-that-does-not-return-a-value"></a>Создание процедуры, которая не возвращает значение

1. За пределами любой другой процедуры используйте оператор `Sub`, за которым следует инструкция `End Sub`.

2. В операторе `Sub` используйте ключевое слово `Sub` с именем процедуры, а затем список параметров в круглых скобках.

3. Поместите операторы кода процедуры между операторами `Sub` и `End Sub`.

### <a name="to-create-a-procedure-that-returns-a-value"></a>Создание процедуры, возвращающей значение

1. За пределами любой другой процедуры используйте оператор `Function`, за которым следует инструкция `End Function`.

2. В операторе `Function` используйте ключевое слово `Function` с именем процедуры, затем список параметров в круглых скобках, а затем предложение `As`, указывающее тип данных возвращаемого значения.

3. Поместите операторы кода процедуры между операторами `Function` и `End Function`.

4. Используйте оператор `Return`, чтобы вернуть значение в вызывающий код.

### <a name="to-connect-your-new-procedure-with-the-old-repetitive-blocks-of-code"></a>Подключение новой процедуры к старым и повторяющимся блокам кода

1. Убедитесь, что вы определили новую процедуру в том месте, где старый код имеет к ней доступ.

2. В старом и повторяющемся блоке кода замените инструкции, выполняющие повторяющуюся задачу, одной инструкцией, которая вызывает `Sub` или `Function` процедуру.

3. Если процедура является `Function`, возвращающей значение, убедитесь, что вызывающая инструкция выполняет действие с возвращаемым значением, например, сохранив его в переменной, или в противном случае значение будет потеряно.

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
