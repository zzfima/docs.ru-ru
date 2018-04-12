---
title: Недопустимая инструкция внутри метода многострочного лямбда-выражения
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30024
- bc30024
helpviewer_keywords:
- BC30024
ms.assetid: 758e7a8f-429b-42c1-9a78-778e5b480e04
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 80673fc7a1497b4148a6505d29581c6403115558
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
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
