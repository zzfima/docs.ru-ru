---
title: Оператор Throw (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Throw
helpviewer_keywords:
- structured exception handling, throw statements
- try-catch exception handling, throw statements
- throw statement [Visual Basic], about throw statements
- throwing exceptions, throw statement
- exception handling, throw statement
- On Error statement [Visual Basic], throwing exceptions
- throwing exceptions
- exception handling, unstructured
- throw statement [Visual Basic]
ms.assetid: a6e07406-5c8a-4498-87a2-8339f3651d62
ms.openlocfilehash: cfa53b3585846da25711739fb7af4bde21746b29
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33602857"
---
# <a name="throw-statement-visual-basic"></a>Оператор Throw (Visual Basic)
Вызывает исключение в процедуре.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
Throw [ expression ]  
```  
  
## <a name="part"></a>Отделение  
 `expression`  
 Сведения о к созданию исключения. Необязательно, если в `Catch` инструкции, в противном случае необходимо.  
  
## <a name="remarks"></a>Примечания  
 `Throw` Оператор создает исключение, которое можно обработать с помощью кода структурированной обработки исключений (`Try`... `Catch`... `Finally`) или неструктурированных код обработки исключений (`On Error GoTo`). Можно использовать `Throw` инструкции для перехвата ошибок в коде, так как Visual Basic перемещается вверх по стеку вызовов, пока не найдет соответствующий код обработки исключений.  
  
 Объект `Throw` оператор без выражения может использоваться только в `Catch` инструкции, исключение обрабатываемое в данный момент повторно создает инструкцию случай `Catch` инструкции.  
  
 `Throw` Инструкция сбрасывает стек вызовов для `expression` исключения. Если `expression` не указано, стек вызовов останется без изменений. Можно получить доступ к стек вызовов для исключения через <xref:System.Exception.StackTrace%2A> свойство.  
  
## <a name="example"></a>Пример  
 В следующем коде используется `Throw` инструкции для создания исключения:  
  
 [!code-vb[VbVbalrStatements#84](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/throw-statement_1.vb)]  
  
## <a name="requirements"></a>Требования  
 **Пространство имен:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **Модуль:** `Interaction`  
  
 **Сборка:** Visual Basic Runtime Library (Microsoft.VisualBasic.dll)  
  
## <a name="see-also"></a>См. также  
 [Оператор Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [Оператор On Error](../../../visual-basic/language-reference/statements/on-error-statement.md)
