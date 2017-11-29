---
title: "Оператор Throw (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Throw
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
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 50ada551c32b8296f0dad2ae929ca9c81a14a711
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
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
  
 **Модуль:**`Interaction`  
  
 **Сборка:** Visual Basic Runtime Library (Microsoft.VisualBasic.dll)  
  
## <a name="see-also"></a>См. также  
 [Оператор Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [Оператор On Error](../../../visual-basic/language-reference/statements/on-error-statement.md)
