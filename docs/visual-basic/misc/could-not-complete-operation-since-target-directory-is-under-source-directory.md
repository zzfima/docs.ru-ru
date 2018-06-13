---
title: 'Невозможно завершить операцию: конечный каталог находится внутри исходного'
ms.date: 07/20/2015
f1_keywords:
- vbrIO_CyclicOperation
ms.assetid: 850d3a24-5d51-4ac8-a912-630efcd75278
ms.openlocfilehash: 68217023a980891200c18b5536ef902574d36257
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33638516"
---
# <a name="could-not-complete-operation-since-target-directory-is-under-source-directory"></a>Невозможно завершить операцию: конечный каталог находится внутри исходного
Циклическая операция не удалась. Циклические операции являются бесконечными циклами и поэтому не могут завершиться. Например, объект A может попытаться наследоваться от объекта B, который в свою очередь наследуется от объекта A.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   При наследовании убедитесь в отсутствии циклических ссылок.  
  
## <a name="see-also"></a>См. также  
 [Типы ошибок](../../visual-basic/programming-guide/language-features/error-types.md)  
 [Общие сведения об отладке: точки останова](http://msdn.microsoft.com/library/752a02c2-0ac7-4c8b-aa1b-4b2b3b21152e)
