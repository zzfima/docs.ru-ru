---
title: Оператор Error (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.error
helpviewer_keywords:
- Error statement [Visual Basic], syntax
- Error statement [Visual Basic]
- Error keyword [Visual Basic]
- run-time errors [Visual Basic], codes
- errors [Visual Basic], simulating
ms.assetid: 85cd5c59-5224-4f02-aaf5-fcfefab17a29
ms.openlocfilehash: 8ac7cee2f9959bc75df165d00d3a0a67e1dd9af0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61982401"
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
 `Error` Инструкция поддерживается для обеспечения обратной совместимости. В новом коде, особенно в том случае, при создании объектов, используйте `Err` объекта `Raise` метод для создания ошибки времени выполнения.  
  
 Если `errornumber` определен, `Error` инструкция вызывает обработчик ошибок после свойства `Err` объекта назначаются следующие значения по умолчанию:  
  
|Свойство|Значение|  
|--------------|-----------|  
|`Number`|Значение, указанное в качестве аргумента `Error` инструкции. Может быть любой допустимый номер ошибки.|  
|`Source`|Имя текущего проекта Visual Basic.|  
|`Description`|Строковое выражение, соответствующее возвращаемое значение `Error` функция для указанного `Number`, если эта строка существует. Если строка не существует, `Description` содержит строку нулевой длины (»»).|  
|`HelpFile`|Полное имя диска, путь и имя файла, соответствующего файла справки Visual Basic.|  
|`HelpContext`|Соответствующий Visual Basic файла справки идентификатор контекста для ошибки, соответствующий `Number` свойство.|  
|`LastDLLError`|Ноль.|  
  
 Если обработчик ошибок отсутствует или отключен, сообщение об ошибке создаются и отображаются из `Err` свойства объекта.  
  
> [!NOTE]
>  Некоторые хост-приложения Visual Basic нельзя создавать объекты. См. в разделе документации ведущего приложения для определения возможности создания классов и объектов.  
  
## <a name="example"></a>Пример  
 В этом примере используется `Error` инструкции для создания ошибки номер 11.  
  
```  
On Error Resume Next   ' Defer error handling.  
Error 11   ' Simulate the "Division by zero" error.  
```  
  
## <a name="requirements"></a>Требования  
 **Пространство имен:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **Сборка:** Visual Basic (библиотека времени выполнения, в Microsoft.VisualBasic.dll)  
  
## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.ErrObject.Clear%2A>
- <xref:Microsoft.VisualBasic.Information.Err%2A>
- <xref:Microsoft.VisualBasic.ErrObject.Raise%2A>
- [Оператор On Error](../../../visual-basic/language-reference/statements/on-error-statement.md)
- [Оператор Resume](../../../visual-basic/language-reference/statements/resume-statement.md)
- [Сообщения об ошибках](../../../visual-basic/language-reference/error-messages/index.md)
