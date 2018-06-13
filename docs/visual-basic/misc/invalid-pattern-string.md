---
title: Недопустимая строка шаблона
ms.date: 07/20/2015
ms.assetid: ec1aecdb-5339-4a93-be71-eec56b1d7438
ms.openlocfilehash: 4905f74683989d8e1a2b041a8af4af4d7432ffab
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33635649"
---
# <a name="invalid-pattern-string"></a>Недопустимая строка шаблона
Строка шаблона, указанная в операции поиска `Like` , является недопустимой.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Просмотрите допустимые символы для выражений списка.  
  
2.  В диапазоне шаблона убедитесь, что знак в начале диапазона меньше знака в конце диапазона, как в `[a-z]`.  
  
3.  В диапазоне шаблона убедитесь, что не отсутствуют дефисы, указанные рядом друг с другом, как в `[a--z]`.  
  
4.  Завершите диапазон шаблона закрывающей скобкой.  
  
## <a name="see-also"></a>См. также  
 [Оператор Like](../../visual-basic/language-reference/operators/like-operator.md)
