---
title: Перегрузка процедур (Visual Basic)
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
ms.openlocfilehash: 6e8d1fa72c60c4fa3d2237ad24c2d1b4891a7bf2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61791876"
---
# <a name="procedure-overloading-visual-basic"></a>Перегрузка процедур (Visual Basic)
*Перегрузка* процедуры означает определение ее в нескольких версиях с помощью тем же именем, но различными списками параметров. Перегрузка предназначена для определения несколько взаимосвязанных версий процедуры без необходимости различать их по имени. Это делается путем изменения списка параметров.  
  
## <a name="overloading-rules"></a>Правила перегрузки  
 Когда вы перегрузка процедуры, применяются следующие правила:  
  
- **Тем же именем**. Каждая перегруженная версия необходимо использовать то же имя процедуры.  
  
- **Другой сигнатурой**. Каждая перегруженная версия должна отличаться от всех других перегруженных версий, по крайней мере одним из следующих параметров:  
  
    - Число параметров  
  
    - Порядок параметров  
  
    - Типы данных параметров  
  
    - Число параметров типа (для универсальной процедуры)  
  
    - Тип возвращаемого значения (только для оператора преобразования)  
  
     Вместе с именем процедуры предыдущие элементы называются *подпись* процедуры. При вызове перегруженной процедуры, компилятор использует подпись для проверки вызова на соответствие определению.  
  
- **Элементы не являются частью сигнатуры**. Нельзя перегрузить процедуру без изменения подписи. В частности не могут перегружать процедуру путем изменения только один или несколько из следующих элементов:  
  
    - Ключевые слова модификаторов процедур, таких как `Public`, `Shared`, и `Static`  
  
    - Имена параметров параметра или типа  
  
    - Ограничения параметров типа (для универсальной процедуры)  
  
    - Ключевые слова модификаторов параметров, таких как `ByRef` и `Optional`  
  
    - Оно возвращает значение  
  
    - Тип данных возвращаемого значения (за исключением оператора преобразования)  
  
     Элементы в списке выше не являются частью сигнатуры. Несмотря на то, что их нельзя использовать для различения перегруженных версий, их можно изменять для перегруженных версий, которые правильно различаются по подписям.  
  
- **С поздним связыванием аргументы**. Если вы собираетесь передать переменную объекта поздней привязкой перегруженную версию, необходимо объявить соответствующий аргумент как <xref:System.Object>.  
  
## <a name="multiple-versions-of-a-procedure"></a>Несколько версий процедуры  
 Предположим, что при написании `Sub` процедуры для публикации транзакций, применительно к балансу клиента, а хотите иметь возможность идентификации клиента по имени или по номеру счета. Чтобы решить эту проблему, можно определить двумя разными `Sub` процедуры, как показано в следующем примере:  
  
 [!code-vb[VbVbcnProcedures#73](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#73)]  
  
### <a name="overloaded-versions"></a>Перегруженные версии  
 Альтернативой является перегрузка процедуры. Можно использовать [перегружает](../../../../visual-basic/language-reference/modifiers/overloads.md) ключевое слово, чтобы определить версию процедуры для каждого списка аргументов следующим образом:  
  
 [!code-vb[VbVbcnProcedures#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#72)]  
  
#### <a name="additional-overloads"></a>Дополнительные перегрузки  
 Если вы хотите принять сумму транзакции в формате `Decimal` или `Single`, определить дополнительные перегруженные версии `post` для для этих вариантов. Если вы уже сделали это для каждой из перегрузок в предыдущем примере, имеется четыре `Sub` процедуры, с тем же именем, но с четырьмя различными сигнатурами.  
  
## <a name="advantages-of-overloading"></a>Преимущества перегрузки  
 Преимущество перегрузки процедуры заключается в гибкости вызова. Для использования `post` объявление процедуры в предыдущем примере, вызывающий код может получить идентификатор клиента как `String` или `Integer`, а затем вызвать ту же процедуру в любом случае. Это показано в приведенном ниже примере.  
  
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
- [Перегрузки](../../../../visual-basic/language-reference/modifiers/overloads.md)
- [Generic Types in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
