---
title: Перегрузка процедур
ms.date: 07/20/2015
helpviewer_keywords:
- signatures
- Overloads keyword [Visual Basic]
- hiding by signature
- Visual Basic code, procedures
- procedures [Visual Basic], signatures for
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
- parameters [Visual Basic], lists
- signatures [Visual Basic], procedure
- parameter lists [Visual Basic]
- Visual Basic code, parameter lists
- Shadows keyword [Visual Basic]
- procedure overloading
- procedures [Visual Basic], parameter lists
ms.assetid: fbc7fb18-e3b2-48b6-b554-64c00ed09d2a
ms.openlocfilehash: 41a971896fe726cbe9849fd46334910e7288afe0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352587"
---
# <a name="procedure-overloading-visual-basic"></a>Перегрузка процедур (Visual Basic)

*Перегрузка* процедуры означает определение ее в нескольких версиях с использованием того же имени, но с разными списками параметров. Целью перегрузки является определение нескольких тесно связанных версий процедуры без необходимости отличать их по имени. Это можно сделать, изменив список параметров.

## <a name="overloading-rules"></a>Перегрузка правил

При перегрузке процедуры применяются следующие правила.

- **То же имя**. Каждая перегруженная версия должна использовать одно и то же имя процедуры.

- **Другая сигнатура**. Каждая перегруженная версия должна отличаться от всех остальных перегруженных версий хотя бы в одном из следующих соблюда:

  - Число параметров

  - Порядок параметров

  - Типы данных параметров

  - Число параметров типа (для универсальной процедуры)

  - Тип возвращаемого значения (только для оператора преобразования)

  Вместе с именем процедуры предыдущие элементы называются *сигнатурой* процедуры. При вызове перегруженной процедуры компилятор использует сигнатуру для проверки того, что вызов правильно соответствует определению.

- **Элементы не являются частью сигнатуры**. Нельзя перегружать процедуру без изменения сигнатуры. В частности, невозможно перегрузить процедуру, изменив только один или несколько из следующих элементов:

  - Ключевые слова модификаторов процедур, такие как `Public`, `Shared`и `Static`

  - Имя параметра или параметра типа

  - Ограничения параметров типа (для универсальной процедуры)

  - Ключевые слова модификаторов параметров, такие как `ByRef` и `Optional`

  - Возвращает ли оно значение

  - Тип данных возвращаемого значения (за исключением оператора преобразования)

  Элементы в приведенном выше списке не являются частью сигнатуры. Хотя их нельзя использовать для различения перегруженных версий, их можно изменять в разных перегруженных версиях, которые должны различаться в соответствии с сигнатурами.

- **Аргументы с поздним**связыванием. Если предполагается передать переменную объекта с поздней привязкой в перегруженную версию, необходимо объявить соответствующий параметр как <xref:System.Object>.

## <a name="multiple-versions-of-a-procedure"></a>Несколько версий процедуры

Предположим, вы пишете `Sub` процедуру для публикации транзакции по балансу клиента и хотите иметь возможность ссылаться на клиента по имени или номеру счета. Для этого можно определить две различные процедуры `Sub`, как показано в следующем примере:

[!code-vb[VbVbcnProcedures#73](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#73)]

### <a name="overloaded-versions"></a>Перегруженные версии

Альтернативой является перегрузка имени одной процедуры. Для определения версии процедуры для каждого списка параметров можно использовать ключевое слово [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) , как показано ниже.

[!code-vb[VbVbcnProcedures#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#72)]

#### <a name="additional-overloads"></a>Дополнительные перегрузки

Если вы также хотите принять сумму транзакции в `Decimal` или `Single`, можно дополнительно перегрузить `post`, чтобы разрешить этот вариант. Если вы сделали это для каждой перегрузки в предыдущем примере, у вас будут четыре `Sub`ные процедуры с одним и тем же именем, но с четырьмя разными сигнатурами.

## <a name="advantages-of-overloading"></a>Преимущества перегрузки

Преимущество перегрузки процедуры заключается в гибкости вызова. Чтобы использовать процедуру `post`, объявленную в предыдущем примере, вызывающий код может получить идентификатор клиента как `String` или `Integer`, а затем вызвать ту же процедуру в любом случае. Это показано в приведенном ниже примере.

[!code-vb[VbVbcnProcedures#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#56)]

[!code-vb[VbVbcnProcedures#57](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#57)]

## <a name="see-also"></a>См. также

- [Процедуры](./index.md)
- [Практическое руководство. Определение различных версий процедуры](./how-to-define-multiple-versions-of-a-procedure.md)
- [Практическое руководство. Вызов перегруженной процедуры](./how-to-call-an-overloaded-procedure.md)
- [Практическое руководство. Перегрузка процедуры, которая принимает один необязательный параметр](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [Практическое руководство. Перегрузка процедуры, принимающей неопределенное число параметров](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [Вопросы, связанные с перегрузкой процедур](./considerations-in-overloading-procedures.md)
- [Разрешение перегрузки](./overload-resolution.md)
- [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md)
- [Generic Types in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
