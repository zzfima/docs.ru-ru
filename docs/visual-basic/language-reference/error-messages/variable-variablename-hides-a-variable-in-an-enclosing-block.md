---
title: Переменная &#39; &lt;variablename&gt; &#39; скрывает переменную во внешнем блоке
ms.date: 07/20/2015
f1_keywords:
- vbc30616
- bc30616
helpviewer_keywords:
- BC30616
ms.assetid: e7658ebc-da45-451b-a409-a0f8915f0beb
ms.openlocfilehash: 58e09caeb477d6b1df7f3be17e0a8ee05be3551e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33595096"
---
# <a name="variable-39ltvariablenamegt39-hides-a-variable-in-an-enclosing-block"></a>Переменная &#39; &lt;variablename&gt; &#39; скрывает переменную во внешнем блоке
Переменная, заключенном в блоке имеет имя, совпадающее с именем другой локальной переменной.  
  
 **Идентификатор ошибки:** BC30616  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Переименуйте переменную, содержащуюся в блоке, чтобы это не то же, что локальные переменные. Пример:  
  
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
