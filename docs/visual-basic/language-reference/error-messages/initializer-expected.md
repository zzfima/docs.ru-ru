---
title: Ожидается инициализатор
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30996
- bc30996
helpviewer_keywords:
- BC30996
ms.assetid: 6e183fe0-8888-43ed-a062-01571079455f
caps.latest.revision: 6
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 46ff91ec240212571f7ec9f26e82d9d128263545
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="initializer-expected"></a>Ожидается инициализатор
Предпринята попытка объявить экземпляр класса с помощью инициализатора объекта, в котором список инициализации пуст, как показано в следующем примере.  
  
 `' Not valid.`  
  
 `' Dim aStudent As New Student With {}`  
  
 По крайней мере одно поле или свойство необходимо инициализировать в списке инициализаторов, как показано в следующем примере.  
  
 `Dim aStudent As New Student With {.year = "Senior"}`  
  
 **Идентификатор ошибки:** BC30996  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Инициализация по крайней мере одно поле или свойство в инициализаторе или не использовать инициализатор объекта.  
  
## <a name="see-also"></a>См. также  
 [Инициализаторы объектов. Именованные и анонимные типы](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)  
 [Практическое руководство. Объявление объекта с помощью инициализатора объектов](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)
