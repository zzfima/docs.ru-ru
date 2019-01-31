---
title: Тип <type1><typename> должен реализовать <methodname> для интерфейса <interfacename>
ms.date: 07/20/2015
f1_keywords:
- vbc30149
- bc30149
helpviewer_keywords:
- BC30149
ms.assetid: 29d1b7f4-dca7-478c-bbe7-c657f342c183
ms.openlocfilehash: c5dd7c6889a3fb5344142ee9914f98e8922d748b
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55264442"
---
# <a name="type1typename-must-implement-methodname-for-interface-interfacename"></a>\<тип1 > "\<typename >" должен реализовывать "\<имя_метода >" для интерфейса "\<имя_интерфейса >"
Класс или структура объявляет о реализации интерфейса, но не реализует процедуры, определенные в интерфейсе. Каждый член интерфейса должен быть реализован.  
  
 **Идентификатор ошибки:** BC30149  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Объявите процедуру с тем же именем и подписью, как определено в интерфейсе. Не забудьте включить по крайней мере `End Function` или `End Sub` инструкции.  
  
2.  Добавить `Implements` предложение в конец `Function` или `Sub` инструкции. Пример:  
  
    ```  
    Public Sub DoSomething() Implements IBaseInterface.DoSomething  
    ```  
  
## <a name="see-also"></a>См. также
- [Оператор Implements](../../../visual-basic/language-reference/statements/implements-statement.md)
- [Интерфейсы](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
