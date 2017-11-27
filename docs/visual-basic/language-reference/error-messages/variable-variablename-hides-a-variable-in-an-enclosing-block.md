---
title: "Переменная &#39; &lt;variablename&gt;&#39; скрывает переменную во внешнем блоке"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30616
- bc30616
helpviewer_keywords: BC30616
ms.assetid: e7658ebc-da45-451b-a409-a0f8915f0beb
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2af570cd002b4be4e15a7c03b0ffc2ff84ba3982
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="variable-39ltvariablenamegt39-hides-a-variable-in-an-enclosing-block"></a>Переменная &#39; &lt;variablename&gt;&#39; скрывает переменную во внешнем блоке
Переменная, заключенном в блоке имеет имя, совпадающее с именем другой локальной переменной.  
  
 **Идентификатор ошибки:** BC30616  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Переименуйте переменную, содержащуюся в блоке, чтобы это не то же, что локальные переменные. Например:  
  
    ```  
    Dim a, b, x As Integer  
    If a = b Then  
       Dim y As Integer = 20 ' Uniquely named block variable.  
    End If  
    ```  
  
-   Распространенной причиной этой ошибки является использование класса `Catch e As Exception` внутри обработчика событий. Если это так, имя `Catch` переменная блока `ex` вместо `e`.  
  
-   Другой распространенной причиной этой ошибки может быть попытка доступа к локальной переменной, объявленной в `Try` блок в отдельном `Catch` блока. Чтобы исправить эту ошибку, объявите переменную за пределами `Try...Catch...Finally` структуры.  
  
## <a name="see-also"></a>См. также  
 [Оператор Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [Объявление переменных](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
