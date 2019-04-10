---
title: <type1>"<typename>«должен реализовывать»<membername>«для интерфейса»<interfacename>"
ms.date: 07/20/2015
f1_keywords:
- vbc30154
- bc30154
helpviewer_keywords:
- BC30154
ms.assetid: 259afdfa-3608-4760-adcb-88ec0da5020d
ms.openlocfilehash: 86b0d46e0e27b2fd8d1fccb37f4a3c45e95f5f63
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59295332"
---
# <a name="type1typename-must-implement-membername-for-interface-interfacename"></a>\<тип1 > "\<typename >" должен реализовывать "\<имя_члена >" для интерфейса "\<имя_интерфейса >"
"\<typename >" должен реализовывать "\<имя_члена >" для интерфейса "\<имя_интерфейса >". Реализация свойства должен иметь совпадающие «ReadOnly» или «WriteOnly» спецификаторы.  
  
 Класс или структура объявляет о реализации интерфейса, но не реализует процедуру, свойства или события, определенные в интерфейсе. Каждый член интерфейса должен быть реализован.  
  
 **Идентификатор ошибки:** BC30154  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1. Объявите член с тем же именем и подписью, как определено в интерфейсе. Не забудьте включить по крайней мере `End Function`, `End Sub`, или `End Property` инструкции.  
  
2. Добавить `Implements` предложение в конец `Function`, `Sub`, `Property`, или `Event` инструкции. Пример:  
  
    ```  
    Public Event ItHappened() Implements IBaseInterface.ItHappened  
    ```  
  
3. При реализации свойства, убедитесь, что `ReadOnly` или `WriteOnly` используется таким же образом, как и в определении интерфейса.  
  
4. При реализации свойства объявить `Get` и `Set` процедуры, соответствующим образом.  
  
## <a name="see-also"></a>См. также

- [Оператор Implements](../../../visual-basic/language-reference/statements/implements-statement.md)
- [интерфейсов,](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
