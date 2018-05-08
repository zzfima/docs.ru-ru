---
title: Недопустимая инструкция внутри метода многострочного лямбда-выражения
ms.date: 07/20/2015
f1_keywords:
- vbc30024
- bc30024
helpviewer_keywords:
- BC30024
ms.assetid: 758e7a8f-429b-42c1-9a78-778e5b480e04
ms.openlocfilehash: cef5beea16c8589a884b7d3533e0543454783999
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="statement-is-not-valid-inside-a-methodmultiline-lambda"></a>Оператор недопустим в теле метода/многострочного лямбда-оператора
Инструкция не является допустимым в `Sub`, `Function`, свойство `Get`, или свойство `Set` процедуры. Некоторые операторы могут размещаться на уровне модуля или класса. Другие, такие как `Option Strict`, должны быть на уровне пространства имен и перед всеми объявлениями.  
  
 **Идентификатор ошибки:** BC30024  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Удалите оператор из процедуры.  
  
## <a name="see-also"></a>См. также  
 [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)  
 [Оператор Get](../../../visual-basic/language-reference/statements/get-statement.md)  
 [Оператор Set](../../../visual-basic/language-reference/statements/set-statement.md)
