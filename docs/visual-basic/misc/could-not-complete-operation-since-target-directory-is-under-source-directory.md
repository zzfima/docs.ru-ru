---
title: 'Невозможно завершить операцию: конечный каталог находится внутри исходного'
ms.date: 07/20/2015
f1_keywords:
- vbrIO_CyclicOperation
ms.assetid: 850d3a24-5d51-4ac8-a912-630efcd75278
ms.openlocfilehash: fca42f91f803a6b12535badcb25cc05cc3d23f6b
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64598473"
---
# <a name="could-not-complete-operation-since-target-directory-is-under-source-directory"></a>Невозможно завершить операцию: конечный каталог находится внутри исходного
Циклическая операция не удалась. Циклические операции являются бесконечными циклами и поэтому не могут завершиться. Например, объект A может попытаться наследоваться от объекта B, который в свою очередь наследуется от объекта A.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
- При наследовании убедитесь в отсутствии циклических ссылок.  
  
## <a name="see-also"></a>См. также

- [Типы ошибок](../../visual-basic/programming-guide/language-features/error-types.md)
- [Использование точек останова в отладчике Visual Studio](/visualstudio/debugger/using-breakpoints)
