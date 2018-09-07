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
ms.openlocfilehash: 84fce92183228cbfa5554a3ba45770a86e83bff5
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44099054"
---
# <a name="error-statement"></a>Оператор Error
Имитирует возникновение ошибки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
Error errornumber  
```  
  
## <a name="parts"></a>Части  
 `errornumber`  
 Обязательно. Может быть любой допустимый номер ошибки.  
  
## <a name="remarks"></a>Примечания  
 `Error` Инструкция поддерживается для обеспечения обратной совместимости. В новом коде, особенно в том случае, при создании объектов, используйте `Err` объекта `Raise` метод для создания ошибки времени выполнения.  
  
 Если `errornumber` определен, `Error` инструкция вызывает обработчик ошибок после свойства `Err` объекта назначаются следующие значения по умолчанию:  
  
|Свойство.|Значение|  
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
  
 **Сборка:** библиотеки времени выполнения Visual Basic (в Microsoft.VisualBasic.dll)  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.ErrObject.Clear%2A>  
 <xref:Microsoft.VisualBasic.Information.Err%2A>  
 <xref:Microsoft.VisualBasic.ErrObject.Raise%2A>  
 [Оператор On Error](../../../visual-basic/language-reference/statements/on-error-statement.md)  
 [Оператор Resume](../../../visual-basic/language-reference/statements/resume-statement.md)  
 [Сообщения об ошибках](../../../visual-basic/language-reference/error-messages/index.md)
