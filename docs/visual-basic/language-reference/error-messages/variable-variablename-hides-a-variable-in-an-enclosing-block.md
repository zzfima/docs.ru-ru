---
title: Переменная <variablename> скрывает содержащуюся в блоке переменную
ms.date: 07/20/2015
f1_keywords:
- vbc30616
- bc30616
helpviewer_keywords:
- BC30616
ms.assetid: e7658ebc-da45-451b-a409-a0f8915f0beb
ms.openlocfilehash: 68ec1aac7ee8d292e2a433e0fb35039d4fb317b4
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55278503"
---
# <a name="variable-variablename-hides-a-variable-in-an-enclosing-block"></a>Переменная "\<имя_переменной >" скрывает переменную во внешнем блоке
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
