---
title: Sub или Function не определена (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID35
ms.assetid: 661fdb90-ee7d-40ce-b30b-5e7267bd957a
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6237ca26b06bdffa06499607e634b3222725c189
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="sub-or-function-not-defined-visual-basic"></a>Sub или Function не определена (Visual Basic)
Объект `Sub` или `Function` должен быть определен для вызываться. Возможные причины этой ошибки:  
  
-   Ошибка в написании имени процедуры.  
  
-   Попытка вызова процедуры из другого проекта без явного добавления ссылки на этот проект в **ссылки** диалоговое окно.  
  
-   Задание процедуры, которая не видна в вызывающую процедуру.  
  
-   Объявление процедуры библиотеки динамической компоновки (DLL) для Windows или Macintosh ресурс кода подпрограмму, которая не находится в указанный ресурс библиотеки или кода.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Проверьте правильность написания имени процедуры.  
  
2.  Найдите имя проекта, содержащего процедуру, которую требуется вызывать в **ссылки** диалоговое окно. Если он не отображается, нажмите кнопку **Обзор** кнопку, чтобы найти его. Установите флажок слева от имени проекта и нажмите кнопку **ОК**.  
  
3.  Проверьте имя подпрограммы.  
  
## <a name="see-also"></a>См. также  
 [Типы ошибок](../../../visual-basic/programming-guide/language-features/error-types.md)  
 [Управление ссылками в проекте](/visualstudio/ide/managing-references-in-a-project)  
 [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)
