---
title: "Оператор Error | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.error"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Error - ключевое слово"
  - "Error - оператор"
  - "Error - оператор, синтаксис"
  - "ошибки [Visual Basic], имитация"
  - "ошибки во время выполнения, коды"
ms.assetid: 85cd5c59-5224-4f02-aaf5-fcfefab17a29
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 10
---
# Оператор Error
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Имитирует возникновение ошибки  
  
## Синтаксис  
  
```  
Error errornumber  
```  
  
## Части  
 `errornumber`  
 Обязательный.  Любой допустимый номер ошибки.  
  
## Заметки  
 Оператор `Error` поддерживается для совместимости с предыдущими версиями.  В новом коде, особенно при создании объектов, для создания ошибок во время выполнения следует использовать метод `Raise` объекта `Err`.  
  
 Если параметр `errornumber` определен, оператор `Error` вызывает обработчик ошибок, предварительно присвоив свойствам объекта `Err` следующие значения по умолчанию:  
  
|Свойство.|Значение|  
|---------------|--------------|  
|`Number`|Значение, заданное в виде аргумента оператора `Error`.  Любой допустимый номер ошибки.|  
|`Source`|Имя текущего проекта Visual Basic.|  
|`Description`|Строковое значение, соответствующее возвращаемому значению функции `Error` для указанного значения равно `Number`, если эта строка существует.  Если строка не существует, `Description` содержит строку нулевой длины \(""\).|  
|`HelpFile`|Полностью указанные диск, путь и имя файла для соответствующего файла справки Visual Basic.|  
|`HelpContext`|Соответствующий контекстный идентификатор файла справки Visual Basic, соответствующий свойству `Number`.|  
|`LastDLLError`|Нуль.|  
  
 Если обработчик ошибок отсутствует или отключен, из свойств объекта `Err` создается выводимое на экран сообщение об ошибке.  
  
> [!NOTE]
>  Некоторые хост\-приложения Visual Basic не могут создавать объекты.  См. документацию по хост\-приложению, чтобы узнать, может ли оно создавать классы и объекты.  
  
## Пример  
 В этом примере оператор `Error` используется для создания ошибки номер 11.  
  
```  
On Error Resume Next   ' Defer error handling.  
Error 11   ' Simulate the "Division by zero" error.  
```  
  
## Требования  
 **Пространство имен:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **Сборка:** библиотека времени выполнения Visual Basic \(в Microsoft.VisualBasic.dll\)  
  
## См. также  
 <xref:Microsoft.VisualBasic.ErrObject.Clear%2A>   
 <xref:Microsoft.VisualBasic.Information.Err%2A>   
 <xref:Microsoft.VisualBasic.ErrObject.Raise%2A>   
 [Оператор On Error](../../../visual-basic/language-reference/statements/on-error-statement.md)   
 [Оператор Resume](../../../visual-basic/language-reference/statements/resume-statement.md)   
 [Сообщения об ошибках](../../../visual-basic/language-reference/error-messages/index.md)