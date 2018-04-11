---
title: Неверный номер записи
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID63
ms.assetid: 1fcc33f8-822a-4de9-a6e3-228ddb5824a6
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: be04987353498775ec7dcef50b6acc1e6b4ec149
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="bad-record-number"></a>Неверный номер записи
Номер записи в операторе `a FileGet`, `FilePut`, `FileGetObject`или `FilePutObject` меньше или равен нулю.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Проверьте вычисления, используемые при формировании номера записи. Проверьте правильность написания переменных, содержащих номер записи или используемых при вычислении номеров записей. Неправильно написанное имя переменной неявно объявляется и приравнивается к нулю, если вы не использовали `Option Explicit On` в модуле.  
  
## <a name="see-also"></a>См. также  
 [Оператор Option Explicit](../../visual-basic/language-reference/statements/option-explicit-statement.md)
