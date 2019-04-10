---
title: Операнд оператора AddressOf должен быть именем метода (без скобок)
ms.date: 07/20/2015
f1_keywords:
- vbc30577
- bc30577
helpviewer_keywords:
- BC30577
ms.assetid: c2c55640-5c61-4e66-97a4-4322020c6001
ms.openlocfilehash: b8c67c2390df91c6a4af66e020365544e6bf369b
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59323828"
---
# <a name="addressof-operand-must-be-the-name-of-a-method-without-parentheses"></a>Операнд оператора AddressOf должен быть именем метода (без скобок)
Оператор `AddressOf` создает экземпляр делегата процедуры, ссылающийся на конкретную процедуру. Синтаксис выглядит следующим образом.  
  
 `AddressOf` `procedurename`  
  
 Вы поставили скобки вокруг аргумента `AddressOf`, которые не нужны.  
  
 **Идентификатор ошибки:** BC30577  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1. Удалите круглые скобки вокруг аргумента `AddressOf`.  
  
2. Убедитесь, что аргумент является имя метода.  
  
## <a name="see-also"></a>См. также

- [Оператор AddressOf](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [Делегаты](../../../visual-basic/programming-guide/language-features/delegates/index.md)
