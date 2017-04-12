---
title: "Функция &quot;&lt;procedurename&gt;&quot; возвращает значение не для всех путей кода | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc42105
- vbc42105
dev_langs:
- VB
helpviewer_keywords:
- BC42105
ms.assetid: b6929bf4-a365-4a70-8dc9-6b0fc09e1468
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 288fdf7c4845b20283681d9eb3504ac314f1ddd2
ms.lasthandoff: 03/13/2017

---
# <a name="function-39ltprocedurenamegt39-doesn39t-return-a-value-on-all-code-paths"></a>Функция "&lt;procedurename&gt;" возвращает значение не для всех путей кода
Функция "\<procedurename настроек" возвращает значение не для всех ветвей кода. Отсутствует оператор «Return»?  
  
 A `Function` процедура имеет хотя бы один возможный путь во всем коде, который не возвращает значение.  
  
 Может возвращать значение из `Function` процедура в любой из следующих способов:  
  
-   Включите значение в [оператор Return](../../../visual-basic/language-reference/statements/return-statement.md).  
  
-   Присвойте значение `Function` процедуры имя, а затем выполнить `Exit Function` инструкции.  
  
-   Присвойте значение `Function` процедуры имя, а затем выполнить `End Function` инструкции.  
  
 Если управление передается `Exit Function` или `End Function` и не были назначены любое значение имени процедуры, процедура возвращает значение по умолчанию типа возвращаемых данных. Дополнительные сведения см. в разделе «Поведение» в [инструкции Function](../../../visual-basic/language-reference/statements/function-statement.md).  
  
 По умолчанию данное сообщение является предупреждением. Дополнительные сведения о скрытии предупреждений или обработке предупреждений как ошибок см. в разделе [в Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Идентификатор ошибки:** BC42105  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Проверьте логику потока управления и убедитесь, что можно присвоить значение перед каждым оператором, вызывающим возврат.  
  
     Проще гарантировать, что каждое возвращение из процедуры возвращает значение, если всегда использовать `Return` инструкции. После этого, последним оператором перед `End Function` должно быть `Return` инструкции.  
  
## <a name="see-also"></a>См. также  
 [Процедуры функций](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)   
 [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)   
 [Страница "Компиляция" в конструкторе проектов (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic)
