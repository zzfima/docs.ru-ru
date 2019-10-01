---
title: <type1>'<typename>«должен реализовывать»<membername>«для интерфейса»<interfacename>'
ms.date: 07/20/2015
f1_keywords:
- vbc30154
- bc30154
helpviewer_keywords:
- BC30154
ms.assetid: 259afdfa-3608-4760-adcb-88ec0da5020d
ms.openlocfilehash: a824b66eaad964049ced5cae5eb2cc370d00ba7f
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71696895"
---
# <a name="type1typename-must-implement-membername-for-interface-interfacename"></a>\<type1 > "\<typename >" должен реализовывать "\<membername >" для интерфейса "\<interfacename >"
"\<typename >" должен реализовывать "\<membername >" для интерфейса "\<interfacename >". Реализация свойства должна иметь соответствующие описатели "ReadOnly"/"WriteOnly".  
  
 Класс или структура объявляет о необходимости реализации интерфейса, но не реализует процедуру, свойство или событие, определенные интерфейсом. Каждый член интерфейса должен быть реализован.  
  
 **Идентификатор ошибки:** BC30154  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1. Объявите член с таким же именем и сигнатурой, как определено в интерфейсе. Не забудьте включить как минимум инструкцию `End Function`, `End Sub` или `End Property`.  
  
2. Добавьте предложение `Implements` в конец оператора `Function`, `Sub`, `Property` или `Event`. Пример:  
  
    ```vb  
    Public Event ItHappened() Implements IBaseInterface.ItHappened  
    ```  
  
3. При реализации свойства убедитесь, что `ReadOnly` или `WriteOnly` используется так же, как и в определении интерфейса.  
  
4. При реализации свойства объявите процедуры `Get` и `Set` соответственно.  
  
## <a name="see-also"></a>См. также

- [Оператор Implements](../../../visual-basic/language-reference/statements/implements-statement.md)
- [Интерфейсы](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
