---
title: Оператор Error
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
ms.openlocfilehash: 668ffbc7b8db73a706c5771bb0734a77f8fc0206
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351238"
---
# <a name="error-statement"></a>Оператор Error
Имитирует возникновение ошибки.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
Error errornumber  
```  
  
## <a name="parts"></a>Части  
 `errornumber`  
 Обязательно. Может быть любым допустимым номером ошибки.  
  
## <a name="remarks"></a>Примечания  
 Оператор `Error` поддерживается для обеспечения обратной совместимости. В новом коде, особенно при создании объектов, используйте метод `Raise` объекта `Err` для создания ошибок времени выполнения.  
  
 Если определено `errornumber`, инструкция `Error` вызывает обработчик ошибок после присвоения свойству объекта `Err` следующих значений по умолчанию:  
  
|Свойство|значения|  
|--------------|-----------|  
|`Number`|Значение, заданное в качестве аргумента для `Error` инструкции. Может быть любым допустимым номером ошибки.|  
|`Source`|Имя текущего проекта Visual Basic.|  
|`Description`|Строковое выражение, соответствующее возвращаемому значению функции `Error` для указанного `Number`, если эта строка существует. Если строка не существует, `Description` содержит строку нулевой длины ("").|  
|`HelpFile`|Полный диск, путь и имя файла подходящего файла справки Visual Basic.|  
|`HelpContext`|Соответствующий идентификатор контекста файла справки Visual Basic для ошибки, соответствующей свойству `Number`.|  
|`LastDLLError`|Нуль.|  
  
 Если обработчик ошибок не существует или не включен, сообщение об ошибке создается и отображается в свойствах объекта `Err`.  
  
> [!NOTE]
> Некоторые приложения Visual Basic узла не могут создавать объекты. Чтобы определить, может ли он создавать классы и объекты, см. документацию по ведущему приложению.  
  
## <a name="example"></a>Пример  
 В этом примере используется оператор `Error` для создания номера ошибки 11.  
  
```vb  
On Error Resume Next   ' Defer error handling.  
Error 11   ' Simulate the "Division by zero" error.  
```  
  
## <a name="requirements"></a>Требования  
 **Пространство имен:** [Microsoft. VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **Сборка:** Библиотека времени выполнения Visual Basic (в Microsoft. VisualBasic. dll)  
  
## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.ErrObject.Clear%2A>
- <xref:Microsoft.VisualBasic.Information.Err%2A>
- <xref:Microsoft.VisualBasic.ErrObject.Raise%2A>
- [Оператор On Error](../../../visual-basic/language-reference/statements/on-error-statement.md)
- [Оператор Resume](../../../visual-basic/language-reference/statements/resume-statement.md)
- [Сообщения об ошибках](../../../visual-basic/language-reference/error-messages/index.md)
