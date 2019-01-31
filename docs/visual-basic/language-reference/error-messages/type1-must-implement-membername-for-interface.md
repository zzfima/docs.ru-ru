---
title: Тип <type1><typename> должен реализовать <membername> для интерфейса <interfacename>
ms.date: 07/20/2015
f1_keywords:
- vbc30154
- bc30154
helpviewer_keywords:
- BC30154
ms.assetid: 259afdfa-3608-4760-adcb-88ec0da5020d
ms.openlocfilehash: de7dd9026e08495941a89be0db11ad4c68d2a748
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55264236"
---
# <a name="type1typename-must-implement-membername-for-interface-interfacename"></a>\<тип1 > "\<typename >" должен реализовывать "\<имя_члена >" для интерфейса "\<имя_интерфейса >"
"\<typename >" должен реализовывать "\<имя_члена >" для интерфейса "\<имя_интерфейса >". Реализация свойства должен иметь совпадающие «ReadOnly» или «WriteOnly» спецификаторы.  
  
 Класс или структура объявляет о реализации интерфейса, но не реализует процедуру, свойства или события, определенные в интерфейсе. Каждый член интерфейса должен быть реализован.  
  
 **Идентификатор ошибки:** BC30154  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Объявите член с тем же именем и подписью, как определено в интерфейсе. Не забудьте включить по крайней мере `End Function`, `End Sub`, или `End Property` инструкции.  
  
2.  Добавить `Implements` предложение в конец `Function`, `Sub`, `Property`, или `Event` инструкции. Пример:  
  
    ```  
    Public Event ItHappened() Implements IBaseInterface.ItHappened  
    ```  
  
3.  При реализации свойства, убедитесь, что `ReadOnly` или `WriteOnly` используется таким же образом, как и в определении интерфейса.  
  
4.  При реализации свойства объявить `Get` и `Set` процедуры, соответствующим образом.  
  
## <a name="see-also"></a>См. также
- [Оператор Implements](../../../visual-basic/language-reference/statements/implements-statement.md)
- [Интерфейсы](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
