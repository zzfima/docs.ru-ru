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
ms.openlocfilehash: 2494eac2f61f112f3ba6321ada7404f8cd618049
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58821396"
---
# <a name="throw-statement-visual-basic"></a>Оператор Throw (Visual Basic)
Возникло исключение в процедуре.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
Throw [ expression ]  
```  
  
## <a name="part"></a>Отделение  
 `expression`  
 Сведения об исключении исключение. Необязательно, если находятся в `Catch` инструкции, в противном случае необходимо.  
  
## <a name="remarks"></a>Примечания  
 `Throw` Оператор создает исключение, которое можно обработать с помощью структурированный код обработки исключений (`Try`... `Catch`... `Finally`) или неструктурированных код обработки исключений (`On Error GoTo`). Можно использовать `Throw` инструкции для перехвата ошибок в коде, поскольку Visual Basic перемещается вверх по стеку вызовов, пока не найдет соответствующий код обработки исключений.  
  
 Объект `Throw` оператор выражения не может использоваться только в `Catch` инструкции, в котором операторе case повторно вызывает исключение, обрабатываемое в данный момент `Catch` инструкции.  
  
 `Throw` Инструкция сбрасывает стек вызовов для `expression` исключение. Если `expression` не указан, стек вызовов останется без изменений. Можно получить доступ к стек вызовов для исключения через <xref:System.Exception.StackTrace%2A> свойство.  
  
## <a name="example"></a>Пример  
 В следующем коде используется `Throw` инструкции для создания исключения:  
  
 [!code-vb[VbVbalrStatements#84](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#84)]  
  
## <a name="requirements"></a>Требования  
 **Пространство имен:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **Модуль:** `Interaction`  
  
 **Сборка:** Visual Basic (библиотека времени выполнения, в Microsoft.VisualBasic.dll)  
  
## <a name="see-also"></a>См. также

- [Оператор Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [Оператор On Error](../../../visual-basic/language-reference/statements/on-error-statement.md)
