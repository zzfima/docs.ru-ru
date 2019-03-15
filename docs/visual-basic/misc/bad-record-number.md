---
title: Неверный номер записи
ms.date: 07/20/2015
f1_keywords:
- vbrID63
ms.assetid: 1fcc33f8-822a-4de9-a6e3-228ddb5824a6
ms.openlocfilehash: c71d523406f3ffa420c36125847ab6d35a8f741c
ms.sourcegitcommit: 5c1abeec15fbddcc7dbaa729fabc1f1f29f12045
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2019
ms.locfileid: "58037099"
---
# <a name="bad-record-number"></a>Неверный номер записи
Номер записи в операторе `a FileGet`, `FilePut`, `FileGetObject`или `FilePutObject` меньше или равен нулю.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Проверьте вычисления, используемые при формировании номера записи. Проверьте правильность написания переменных, содержащих номер записи или используемых при вычислении номеров записей. Неправильно написанное имя переменной неявно объявляется и приравнивается к нулю, если вы не использовали `Option Explicit On` в модуле.  
  
## <a name="see-also"></a>См. также

- [Оператор Option Explicit](../../visual-basic/language-reference/statements/option-explicit-statement.md)
