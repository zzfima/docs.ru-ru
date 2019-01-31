---
title: В <name> не найдено доступного метода Main с подходящей подписью
ms.date: 07/20/2015
f1_keywords:
- bc30737
- vbc30737
helpviewer_keywords:
- BC30737
ms.assetid: 3f40bacd-3fac-4741-b204-852f693d4340
ms.openlocfilehash: b3aa66416f0cad6a6fb29a20aa0bca5e3486a18e
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55275435"
---
# <a name="no-accessible-main-method-with-an-appropriate-signature-was-found-in-name"></a>Метод не доступен «Main» с подходящей сигнатурой найден в "\<имя >"
Приложения командной строки должны иметь `Sub Main` определен. `Main` должен быть объявлен как `Public Shared` если оно определено в классе, или как `Public` Если определен в модуле.  
  
 **Идентификатор ошибки:** BC30737  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Определение `Public Sub Main` процедуры для вашего проекта. Он объявляется как `Shared` только в том случае, если она определяется внутри класса.  
  
## <a name="see-also"></a>См. также
- [Структура программы на Visual Basic](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)
- [Процедуры](../../../visual-basic/programming-guide/language-features/procedures/index.md)
