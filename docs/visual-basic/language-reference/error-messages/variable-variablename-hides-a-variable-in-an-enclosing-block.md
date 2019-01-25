---
title: Переменная &#39; &lt;variablename&gt; &#39; скрывает переменную во внешнем блоке
ms.date: 07/20/2015
f1_keywords:
- vbc30616
- bc30616
helpviewer_keywords:
- BC30616
ms.assetid: e7658ebc-da45-451b-a409-a0f8915f0beb
ms.openlocfilehash: 23ec659535b71ee9af189f5c4fec0dec2bb1cd8f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54719434"
---
# <a name="variable-39ltvariablenamegt39-hides-a-variable-in-an-enclosing-block"></a>Переменная &#39; &lt;variablename&gt; &#39; скрывает переменную во внешнем блоке
Содержится в блоке, переменная имеет имя, совпадающее с именем другой локальной переменной.  
  
 **Идентификатор ошибки:** BC30616  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Переименуйте переменную в закрытом блоке, так как это не так же, как локальные переменные. Пример:  
  
    ```  
    Dim a, b, x As Integer  
    If a = b Then  
       Dim y As Integer = 20 ' Uniquely named block variable.  
    End If  
    ```  
  
-   Распространенной причиной этой ошибки является использование `Catch e As Exception` внутри обработчика событий. Если это так, имя `Catch` переменная блока `ex` вместо `e`.  
  
-   Другой распространенной причиной этой ошибки является попытка получить доступ к локальной переменной, объявленной в `Try` блокировать в отдельном `Catch` блока. Чтобы исправить эту ошибку, объявите переменную за пределами `Try...Catch...Finally` структуры.  
  
## <a name="see-also"></a>См. также
- [Оператор Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [Объявление переменных](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
