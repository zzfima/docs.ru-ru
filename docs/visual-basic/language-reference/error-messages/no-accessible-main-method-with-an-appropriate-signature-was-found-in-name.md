---
title: "Ни один из доступных &#39; Main &#39; найден метод с соответствующей сигнатурой в &#39; &lt;имя&gt;&#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30737
- vbc30737
helpviewer_keywords: BC30737
ms.assetid: 3f40bacd-3fac-4741-b204-852f693d4340
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3f45dc17304c3c9d62b65760f2c1b5d461812a66
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="no-accessible-39main39-method-with-an-appropriate-signature-was-found-in-39ltnamegt39"></a>Ни один из доступных &#39; Main &#39; найден метод с соответствующей сигнатурой в &#39; &lt;имя&gt;&#39;
Приложения командной строки должны иметь `Sub Main` определен. `Main`должен быть объявлен как `Public Shared` , если оно определено в классе или как `Public` , если определено в модуле.  
  
 Дополнительные сведения о `Main`, в разделе [NIB: Visual Basic версии из Hello, World](http://msdn.microsoft.com/en-us/9d030b60-e148-4366-a462-69532f02294c).  
  
 **Идентификатор ошибки:** BC30737  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Определение `Public Sub Main` процедуры для вашего проекта. Он объявляется как `Shared` только в том случае, если она определяется внутри класса.  
  
## <a name="see-also"></a>См. также  
 [NIB: версия Visual Basic Hello World](http://msdn.microsoft.com/en-us/9d030b60-e148-4366-a462-69532f02294c)  
 [Структура программы Visual Basic](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)  
 [Процедуры](../../../visual-basic/programming-guide/language-features/procedures/index.md)
