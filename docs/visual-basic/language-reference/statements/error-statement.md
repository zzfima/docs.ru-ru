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
ms.openlocfilehash: 7b926214d3be7f5f57783a8599acf1bb1042f956
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69944445"
---
# <a name="error-statement"></a>Оператор Error
Имитирует возникновение ошибки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
Error errornumber  
```  
  
## <a name="parts"></a>Части  
 `errornumber`  
 Обязательный. Может быть любым допустимым номером ошибки.  
  
## <a name="remarks"></a>Примечания  
 Эта `Error` инструкция поддерживается для обеспечения обратной совместимости. В новом коде, особенно при создании объектов, используйте `Err` `Raise` метод объекта для создания ошибок времени выполнения.  
  
 Если `errornumber` определено `Error` , инструкция вызывает обработчик ошибок `Err` после того, как свойства объекта присвоены следующие значения по умолчанию:  
  
|Свойство.|Значение|  
|--------------|-----------|  
|`Number`|Значение, указанное в качестве `Error` аргумента инструкции. Может быть любым допустимым номером ошибки.|  
|`Source`|Имя текущего проекта Visual Basic.|  
|`Description`|Строковое выражение, соответствующее возвращаемому значению `Error` функции для указанного `Number`объекта, если эта строка существует. Если строка не существует, `Description` содержит строку нулевой длины ("").|  
|`HelpFile`|Полный диск, путь и имя файла подходящего файла справки Visual Basic.|  
|`HelpContext`|Соответствующий идентификатор контекста файла справки Visual Basic для ошибки, соответствующей `Number` свойству.|  
|`LastDLLError`|Нуль.|  
  
 Если обработчик ошибок не существует или не включен, сообщение об ошибке создается и отображается в `Err` свойствах объекта.  
  
> [!NOTE]
> Некоторые приложения Visual Basic узла не могут создавать объекты. Чтобы определить, может ли он создавать классы и объекты, см. документацию по ведущему приложению.  
  
## <a name="example"></a>Пример  
 В этом примере используется `Error` оператор для создания номера ошибки 11.  
  
```  
On Error Resume Next   ' Defer error handling.  
Error 11   ' Simulate the "Division by zero" error.  
```  
  
## <a name="requirements"></a>Требования  
 **Пространство имен:** [Microsoft. VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **Сборок** Visual Basic (библиотека времени выполнения, в Microsoft.VisualBasic.dll)  
  
## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.ErrObject.Clear%2A>
- <xref:Microsoft.VisualBasic.Information.Err%2A>
- <xref:Microsoft.VisualBasic.ErrObject.Raise%2A>
- [Оператор On Error](../../../visual-basic/language-reference/statements/on-error-statement.md)
- [Оператор Resume](../../../visual-basic/language-reference/statements/resume-statement.md)
- [Сообщения об ошибках](../../../visual-basic/language-reference/error-messages/index.md)
