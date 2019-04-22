---
title: Функция <procedurename> возвращает значение не для всех путей выполнения
ms.date: 07/20/2015
f1_keywords:
- bc42105
- vbc42105
helpviewer_keywords:
- BC42105
ms.assetid: b6929bf4-a365-4a70-8dc9-6b0fc09e1468
ms.openlocfilehash: badcfea4f24ba3858071e02ba47b8f77ab557f88
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58824836"
---
# <a name="function-procedurename-doesnt-return-a-value-on-all-code-paths"></a>Функция "\<имя_процедуры >" не возвращает значение на всех путях кода
Функция "\<имя_процедуры >" не возвращает значение на всех путях кода. Возможно, отсутствует оператор «Return»?  
  
 Объект `Function` процедура имеет по крайней мере один возможный путь во всем коде, который не возвращает значение.  
  
 Может возвращать значение из `Function` процедуры в любой из следующих способов:  
  
-   Включите значение в [оператор Return](../../../visual-basic/language-reference/statements/return-statement.md).  
  
-   Присвойте значение `Function` процедуры имя, а затем выполнить `Exit Function` инструкции.  
  
-   Присвойте значение `Function` процедуры имя, а затем выполнить `End Function` инструкции.  
  
 Если управление передается `Exit Function` или `End Function` и которые не были назначены любое значение для имени процедуры, процедура возвращает значение по умолчанию тип возвращаемых данных. Дополнительные сведения см. в разделе «Поведение» в [инструкции Function](../../../visual-basic/language-reference/statements/function-statement.md).  
  
 По умолчанию данное сообщение является предупреждением. Дополнительные сведения о скрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Идентификатор ошибки:** BC42105  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Проверьте логику потока управления и убедитесь, что можно присвоить значение перед каждой инструкции, которая вызывает возврат.  
  
     Проще гарантировать, что каждое возвращение из процедуры возвращает значение, если всегда использовать `Return` инструкции. После этого, последней инструкцией перед `End Function` должно быть `Return` инструкции.  
  
## <a name="see-also"></a>См. также

- [Процедуры функций](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)
- [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)
- [Страница "Компиляция" в конструкторе проектов (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)
