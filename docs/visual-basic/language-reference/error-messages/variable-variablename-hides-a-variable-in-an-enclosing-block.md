---
title: Переменная <variablename> скрывает содержащуюся в блоке переменную
ms.date: 07/20/2015
f1_keywords:
- vbc30616
- bc30616
helpviewer_keywords:
- BC30616
ms.assetid: e7658ebc-da45-451b-a409-a0f8915f0beb
ms.openlocfilehash: 4312abef83728f432e2f6a492e5acad3450719b1
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592066"
---
# <a name="variable-variablename-hides-a-variable-in-an-enclosing-block"></a>Переменная "\<variablename >" скрывает переменную во внешнем блоке
Переменная, заключенная в блок, имеет то же имя, что и другая локальная переменная.  
  
 **Идентификатор ошибки:** BC30616  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
- Переименуйте переменную во вложенном блоке так, чтобы она не совпадала с другими локальными переменными. Пример:  
  
    ```vb  
    Dim a, b, x As Integer  
    If a = b Then  
       Dim y As Integer = 20 ' Uniquely named block variable.  
    End If  
    ```  
  
- Распространенной причиной этой ошибки является использование `Catch e As Exception` внутри обработчика событий. Если это так, присвойте переменной блока `Catch` `ex`, а не `e`.  
  
- Другой распространенный источник этой ошибки — попытка доступа к локальной переменной, объявленной в блоке `Try`, в отдельном блоке `Catch`. Чтобы исправить это, объявите переменную вне структуры `Try...Catch...Finally`.  
  
## <a name="see-also"></a>См. также

- [Оператор Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [Объявление переменных](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
