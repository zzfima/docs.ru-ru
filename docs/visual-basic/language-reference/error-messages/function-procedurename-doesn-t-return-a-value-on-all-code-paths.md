---
title: Функция &#39; &lt;имя_процедуры&gt; &#39; &#39;t возвращает значение во всех путях кода
ms.date: 07/20/2015
f1_keywords:
- bc42105
- vbc42105
helpviewer_keywords:
- BC42105
ms.assetid: b6929bf4-a365-4a70-8dc9-6b0fc09e1468
ms.openlocfilehash: 4c18c6229eb170e8a688aaa2734ae8fbfa081061
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="function-39ltprocedurenamegt39-doesn39t-return-a-value-on-all-code-paths"></a>Функция &#39; &lt;имя_процедуры&gt; &#39; &#39;t возвращает значение во всех путях кода
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
