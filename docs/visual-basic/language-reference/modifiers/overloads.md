---
title: Overloads (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Overloads
- Overloads
helpviewer_keywords:
- Overloads keyword [Visual Basic]
- hiding by signature
- Shadows keyword [Visual Basic]
- signature, hiding by
ms.assetid: 0c6820b8-25b2-4664-bc59-5ca93c99c042
ms.openlocfilehash: 0d68846938aba809a7a3a6f7d27f185bb90a39cb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58819337"
---
# <a name="overloads-visual-basic"></a>Overloads (Visual Basic)
Указывает, что свойство или процедура повторно определяет одно или несколько существующих свойств или процедур с таким же именем.  
  
## <a name="remarks"></a>Примечания  
 *Перегрузка* — это предоставление нескольких определений для указанного имени свойства или процедуры в той же области. Повторное объявление свойства или процедуры с другой сигнатурой иногда называют *скрытием за сигнатурой*.  
  
## <a name="rules"></a>Правила  
  
-   **Контекст объявления.** `Overloads` можно использовать только в операторе объявления свойства или процедуры.  
  
-   **Комбинированные модификаторы.** Нельзя указать `Overloads` вместе с [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md) в одном объявлении процедуры.  
  
-   **Обязательные различия.** *Подпись* этого объявления должна отличаться от сигнатуры каждого свойства или процедуры, которые оно переопределяет. Сигнатура включает в себя имя свойства или процедуры, а также следующие элементы:  
  
    -   число параметров;  
  
    -   порядок параметров;  
  
    -   типы данных параметров;  
  
    -   число параметров типа (для универсальной процедуры);  
  
    -   тип возвращаемого значения (только для процедуры оператора преобразования).  
  
     Все перегрузки должны иметь одно и то же имя, но каждая должна отличаться от всех остальных по одному или нескольким из предыдущих аспектов. Это позволяет компилятору определить, какую именно версию следует использовать, когда код вызывает свойство или процедуру.  
  
-   **Запрещенные различия.** Изменение одного или нескольких из следующих аспектов не является допустимым для перегрузки свойства или процедуры, поскольку они не являются частью сигнатуры:  
  
    -   наличие возвращаемого значения (для процедуры);  
  
    -   тип данных возвращаемого значения (за исключением оператора преобразования);  
  
    -   имена параметров или параметров типа;  
  
    -   ограничения для параметров типа (для универсальной процедуры);  
  
    -   ключевые слова модификаторов параметров (например, `ByRef` или `Optional`);  
  
    -   ключевые слова модификаторов свойств или процедур (например, `Public` или `Shared`).  
  
-   **Необязательный модификатор.** Модификатор `Overloads` можно не использовать при определении нескольких перегруженных свойств или процедур в одном классе. Однако при использовании `Overloads` в одном из объявлений его необходимо использовать в них всех.  
  
-   **Затенение и перегрузка.** `Overloads` Можно также использовать для затенения существующего члена или набора перегруженных членов в базовом классе. При таком использовании `Overloads` свойство или метод объявляются с таким же именем и таким же списком параметров, как и у члена базового класса, а ключевое слово `Shadows` не предоставляется.  
  
 При использовании `Overrides` компилятор неявно добавляет `Overloads`, чтобы упростить работу API-интерфейсов с библиотекой C#.  
  
 Модификатор `Overloads` можно использовать в следующих контекстах:  
  
 [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Оператор Statement](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>См. также

- [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)
- [Перегрузка процедур](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)
- [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [Процедуры операторов](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)
- [Практическое руководство. Определение оператора преобразования](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
