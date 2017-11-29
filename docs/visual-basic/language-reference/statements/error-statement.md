---
title: "Оператор Error"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.error
helpviewer_keywords:
- Error statement [Visual Basic], syntax
- Error statement [Visual Basic]
- Error keyword [Visual Basic]
- run-time errors [Visual Basic], codes
- errors [Visual Basic], simulating
ms.assetid: 85cd5c59-5224-4f02-aaf5-fcfefab17a29
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3cd3245fd3e9e62b1b6443e9787c97808a0d179d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="error-statement"></a>Оператор Error
Имитирует возникновение ошибки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
Error errornumber  
```  
  
## <a name="parts"></a>Части  
 `errornumber`  
 Обязательный. Может быть любой допустимый номер ошибки.  
  
## <a name="remarks"></a>Примечания  
 `Error` Инструкция поддерживается для обратной совместимости. В новом коде, особенно при создании объектов, используйте `Err` объекта `Raise` метод для создания ошибки во время выполнения.  
  
 Если `errornumber` определен, `Error` инструкция вызывает обработчик ошибок после свойства `Err` объекта назначаются следующие значения по умолчанию:  
  
|Свойство|Значение|  
|--------------|-----------|  
|`Number`|Значение, указанное в качестве аргумента `Error` инструкции. Может быть любой допустимый номер ошибки.|  
|`Source`|Имя текущего проекта Visual Basic.|  
|`Description`|Строковое выражение, соответствующее значение, возвращаемое `Error` функции для указанного `Number`, если эта строка существует. Если строка не существует, `Description` содержит строку нулевой длины (»»).|  
|`HelpFile`|Полное имя диска, путь и имя соответствующего файла справки Visual Basic.|  
|`HelpContext`|Соответствующий Visual Basic файла справки идентификатор контекста для ошибки, соответствующий `Number` свойство.|  
|`LastDLLError`|Ноль.|  
  
 Если обработчик ошибок отсутствует или отключен, сообщение об ошибке создаются и отображаются из `Err` свойства объекта.  
  
> [!NOTE]
>  Некоторые хост-приложения Visual Basic нельзя создавать объекты. В документации ведущего приложения для определения возможности создания классов и объектов.  
  
## <a name="example"></a>Пример  
 В этом примере используется `Error` инструкции для создания ошибки номер 11.  
  
```  
On Error Resume Next   ' Defer error handling.  
Error 11   ' Simulate the "Division by zero" error.  
```  
  
## <a name="requirements"></a>Требования  
 **Пространство имен:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **Сборка:** Visual Basic Runtime Library (Microsoft.VisualBasic.dll)  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.ErrObject.Clear%2A>  
 <xref:Microsoft.VisualBasic.Information.Err%2A>  
 <xref:Microsoft.VisualBasic.ErrObject.Raise%2A>  
 [Оператор On Error](../../../visual-basic/language-reference/statements/on-error-statement.md)  
 [Оператор Resume](../../../visual-basic/language-reference/statements/resume-statement.md)  
 [Сообщения об ошибках](../../../visual-basic/language-reference/error-messages/index.md)
