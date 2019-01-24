---
title: Ни один из доступных &#39;Main&#39; в найден метод с подходящей сигнатурой &#39; &lt;имя&gt;&#39;
ms.date: 07/20/2015
f1_keywords:
- bc30737
- vbc30737
helpviewer_keywords:
- BC30737
ms.assetid: 3f40bacd-3fac-4741-b204-852f693d4340
ms.openlocfilehash: 3398195ef9d503e47ab569ff85cb2a827c4270f1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54501494"
---
# <a name="no-accessible-39main39-method-with-an-appropriate-signature-was-found-in-39ltnamegt39"></a>Ни один из доступных &#39;Main&#39; в найден метод с подходящей сигнатурой &#39; &lt;имя&gt;&#39;
Приложения командной строки должны иметь `Sub Main` определен. `Main` должен быть объявлен как `Public Shared` если оно определено в классе, или как `Public` Если определен в модуле.  
  
 **Идентификатор ошибки:** BC30737  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Определение `Public Sub Main` процедуры для вашего проекта. Он объявляется как `Shared` только в том случае, если она определяется внутри класса.  
  
## <a name="see-also"></a>См. также
- [Структура программы на Visual Basic](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)
- [Процедуры](../../../visual-basic/programming-guide/language-features/procedures/index.md)
