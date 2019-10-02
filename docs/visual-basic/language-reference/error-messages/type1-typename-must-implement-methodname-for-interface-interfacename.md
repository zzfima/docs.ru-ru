---
title: <type1>'<typename>«должен реализовывать»<methodname>«для интерфейса»<interfacename>'
ms.date: 07/20/2015
f1_keywords:
- vbc30149
- bc30149
helpviewer_keywords:
- BC30149
ms.assetid: 29d1b7f4-dca7-478c-bbe7-c657f342c183
ms.openlocfilehash: c387b0225375f4675042bef593b23a084305b4fd
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/28/2019
ms.locfileid: "71591597"
---
# <a name="type1typename-must-implement-methodname-for-interface-interfacename"></a>\<тип1 > '\<typename >' должен реализовывать '\<имя_метода >' для интерфейса '\<имя_интерфейса >'
Класс или структура требует реализации интерфейса, но не реализует процедуру, определенную интерфейсом. Каждый член интерфейса должен быть реализован.  
  
 **Идентификатор ошибки:** BC30149  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1. Объявите процедуру с тем же именем и сигнатурой, как определено в интерфейсе. Обязательно включите по крайней мере `End Function` или `End Sub`.  
  
2. Добавьте предложение `Implements` в конец оператора `Function` или `Sub`. Пример:  
  
    ```vb  
    Public Sub DoSomething() Implements IBaseInterface.DoSomething  
    ```  
  
## <a name="see-also"></a>См. также

- [Оператор Implements](../../../visual-basic/language-reference/statements/implements-statement.md)
- [Интерфейсы](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
