---
title: "Функция &#39; &lt;имя_процедуры&gt;&#39; &#39; t возвращает значение во всех путях кода"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc42105
- vbc42105
helpviewer_keywords: BC42105
ms.assetid: b6929bf4-a365-4a70-8dc9-6b0fc09e1468
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5244d97a79f2450f44fe05f63510369914375912
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="function-39ltprocedurenamegt39-doesn39t-return-a-value-on-all-code-paths"></a>Функция &#39; &lt;имя_процедуры&gt;&#39; &#39; t возвращает значение во всех путях кода
Функция "\<procedurename >" не возвращает значение во всех путях кода. Отсутствует оператор «Return»?  
  
 Объект `Function` процедура имеет по крайней мере один возможный путь во всем коде, который не возвращает значение.  
  
 Может возвращать значение из `Function` процедура в любой из следующих способов:  
  
-   Включите значение в [оператор Return](../../../visual-basic/language-reference/statements/return-statement.md).  
  
-   Присвойте значение `Function` процедуры имя, а затем выполнить `Exit Function` инструкции.  
  
-   Присвойте значение `Function` процедуры имя, а затем выполнить `End Function` инструкции.  
  
 Если управление передается `Exit Function` или `End Function` и не назначенные любое значение в имени процедуры, процедура возвращает значение по умолчанию типа возвращаемых данных. Дополнительные сведения см. в разделе «Поведение» в [Function, инструкция](../../../visual-basic/language-reference/statements/function-statement.md).  
  
 По умолчанию данное сообщение является предупреждением. Дополнительные сведения о скрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Настройка предупреждений в Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Идентификатор ошибки:** BC42105  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Проверьте логику потока управления и убедитесь, что можно присвоить значение перед каждым оператором, вызывающим возврат.  
  
     Проще гарантировать, что каждый возврата из процедуры возвращает значение, если всегда использовать `Return` инструкции. После этого, последней инструкцией перед `End Function` должно быть `Return` инструкции.  
  
## <a name="see-also"></a>См. также  
 [Процедуры функций](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)  
 [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)  
 [Страница "Компиляция" в конструкторе проектов (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)
