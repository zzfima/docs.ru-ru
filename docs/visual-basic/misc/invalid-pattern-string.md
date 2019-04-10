---
title: Недопустимая строка шаблона
ms.date: 07/20/2015
ms.assetid: ec1aecdb-5339-4a93-be71-eec56b1d7438
ms.openlocfilehash: 7390b9b32eea248969813b52f8d9799798718de0
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59298686"
---
# <a name="invalid-pattern-string"></a>Недопустимая строка шаблона
Строка шаблона, указанная в операции поиска `Like` , является недопустимой.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1. Просмотрите допустимые символы для выражений списка.  
  
2. В диапазоне шаблона убедитесь, что знак в начале диапазона меньше знака в конце диапазона, как в `[a-z]`.  
  
3. В диапазоне шаблона убедитесь, что не отсутствуют дефисы, указанные рядом друг с другом, как в `[a--z]`.  
  
4. Завершите диапазон шаблона закрывающей скобкой.  
  
## <a name="see-also"></a>См. также

- [Оператор Like](../../visual-basic/language-reference/operators/like-operator.md)
