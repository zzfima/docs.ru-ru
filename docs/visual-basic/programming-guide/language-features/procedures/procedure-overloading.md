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
ms.openlocfilehash: 0d1f2c4d8c88922659b3d91ed41d5e760e6e5233
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33653918"
---
# <a name="procedure-overloading-visual-basic"></a>Перегрузка процедур (Visual Basic)
*Перегрузка* процедуры означает определение ее в нескольких версиях с помощью тем же именем, но различными списками параметров. Перегрузка предназначена для определения несколько взаимосвязанных версий процедуры, не различая их по имени. Это делается путем изменения списка параметров.  
  
## <a name="overloading-rules"></a>Правила перегрузки  
 При перегрузке процедур действуют следующие правила:  
  
-   **Таким же именем**. Каждая перегруженная версия необходимо использовать то же имя процедуры.  
  
-   **Сигнатура**. Каждая перегруженная версия должна отличаться от всех остальных перегруженных версий хотя бы один из следующих параметров:  
  
    -   Число параметров  
  
    -   Порядок параметров  
  
    -   Типы данных параметров  
  
    -   Число параметров типа (для универсальной процедуры)  
  
    -   Тип возвращаемого значения (только для оператора преобразования)  
  
     Вместе с именем процедуры предыдущие элементы называются *подписи* процедуры. При вызове перегруженной процедуры компилятор использует подпись для проверки вызова на соответствие определению.  
  
-   **Элементы не являются частью сигнатуры**. Нельзя перегрузить процедуру без изменения подписи. В частности нельзя перегрузить процедуру путем изменения только один или несколько из следующих элементов:  
  
    -   Ключевые слова модификаторов процедур, таких как `Public`, `Shared`, и `Static`  
  
    -   Имена параметров для параметра или типа  
  
    -   Ограничения параметров типа (для универсальной процедуры)  
  
    -   Ключевые слова модификаторов параметров, таких как `ByRef` и `Optional`  
  
    -   Оно возвращает значение  
  
    -   Тип данных возвращаемого значения (за исключением оператора преобразования)  
  
     Элементы, перечисленные в списке не являются частью сигнатуры. Несмотря на то, что их нельзя использовать для различения перегруженных версий, можно изменять их для перегруженных версий, которые правильно различаются по подписи.  
  
-   **Позднее связывание аргументов**. Если требуется передать переменную объекта поздней привязкой перегруженную версию, необходимо объявить соответствующий аргумент как <xref:System.Object>.  
  
## <a name="multiple-versions-of-a-procedure"></a>Несколько версий процедуры  
 Предположим, что вы пишете `Sub` процедуры для учета транзакции по балансу клиента и должны быть можно ссылаться по имени или номеру учетной записи клиента. Чтобы решить эту проблему, можно определить двумя разными `Sub` процедуры, как показано в следующем примере:  
  
 [!code-vb[VbVbcnProcedures#73](./codesnippet/VisualBasic/procedure-overloading_1.vb)]  
  
### <a name="overloaded-versions"></a>Перегруженные версии  
 Альтернативой является перегрузка отдельного имени процедуры. Можно использовать [перегрузки](../../../../visual-basic/language-reference/modifiers/overloads.md) ключевое слово можно определить версии процедуры для каждого списка аргументов, как показано ниже:  
  
 [!code-vb[VbVbcnProcedures#72](./codesnippet/VisualBasic/procedure-overloading_2.vb)]  
  
#### <a name="additional-overloads"></a>Дополнительные перегрузки  
 Если вы хотите принять сумму транзакции в формате `Decimal` или `Single`, определить дополнительные перегруженные версии `post` для для этих вариантов. Если сделать это для каждой перегрузки, показанной в предыдущем примере, будет иметь четыре `Sub` процедуры с тем же именем, но с четырьмя разными сигнатурами.  
  
## <a name="advantages-of-overloading"></a>Преимущества перегрузки  
 Преимущество перегрузки процедуры заключается в гибкости вызова. Для использования `post` объявление процедуры в предыдущем примере, вызывающий код может получить идентификатор клиента как `String` или `Integer`, а затем вызвать процедуру в любом случае. Это показано в приведенном ниже примере.  
  
 [!code-vb[VbVbcnProcedures#56](./codesnippet/VisualBasic/procedure-overloading_3.vb)]  
  
 [!code-vb[VbVbcnProcedures#57](./codesnippet/VisualBasic/procedure-overloading_4.vb)]  
  
## <a name="see-also"></a>См. также  
 [Процедуры](./index.md)  
 [Практическое руководство. Определение различных версий процедуры](./how-to-define-multiple-versions-of-a-procedure.md)  
 [Практическое руководство. Вызов перегруженной процедуры](./how-to-call-an-overloaded-procedure.md)  
 [Практическое руководство. Перегрузка процедуры, которая принимает один необязательный параметр](./how-to-overload-a-procedure-that-takes-optional-parameters.md)  
 [Практическое руководство. Перегрузка процедуры, принимающей неопределенное число параметров](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)  
 [Вопросы, связанные с перегрузкой процедур](./considerations-in-overloading-procedures.md)  
 [Разрешение перегрузки](./overload-resolution.md)  
 [Перегрузки](../../../../visual-basic/language-reference/modifiers/overloads.md)  
 [Универсальные типы в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
