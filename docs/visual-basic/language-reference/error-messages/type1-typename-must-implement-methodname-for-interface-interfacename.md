---
title: <type1>"<typename>«должен реализовывать»<methodname>«для интерфейса»<interfacename>"
ms.date: 07/20/2015
f1_keywords:
- vbc30149
- bc30149
helpviewer_keywords:
- BC30149
ms.assetid: 29d1b7f4-dca7-478c-bbe7-c657f342c183
ms.openlocfilehash: b8bcb16798284a09608ba6942226ef07c6859d4f
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58824209"
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
