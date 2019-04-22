---
title: Недопустимая инструкция в методе / многострочной лямбде
ms.date: 07/20/2015
f1_keywords:
- vbc30024
- bc30024
helpviewer_keywords:
- BC30024
ms.assetid: 758e7a8f-429b-42c1-9a78-778e5b480e04
ms.openlocfilehash: 994cafc44a37d16d0f70caec560f530c6a836ec0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58841567"
---
# <a name="statement-is-not-valid-inside-a-methodmultiline-lambda"></a>Оператор недопустим в теле метода/многострочного лямбда-оператора
Инструкция не является допустимым в `Sub`, `Function`, свойство `Get`, или свойство `Set` процедуры. Некоторые инструкции можно поместить на уровне модуля или класса. Другие, такие как `Option Strict`должны быть на уровне пространства имен и должны предшествовать всем объявлениям.  
  
 **Идентификатор ошибки:** BC30024  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Удалите оператор из процедуры.  
  
## <a name="see-also"></a>См. также

- [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)
- [Оператор Get](../../../visual-basic/language-reference/statements/get-statement.md)
- [Оператор Set](../../../visual-basic/language-reference/statements/set-statement.md)
