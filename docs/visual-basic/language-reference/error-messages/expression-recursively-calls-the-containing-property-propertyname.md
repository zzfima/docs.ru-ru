---
title: "Выражение рекурсивно вызывает содержащее свойство &lt;имяСвойства&gt; | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc42026"
  - "BC42026"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC42026"
ms.assetid: 4fde9db6-3bf3-48dc-8e05-981bf08969da
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 10
---
# Выражение рекурсивно вызывает содержащее свойство &lt;имяСвойства&gt;
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Оператор в процедуре `Set` определения свойства сохраняет значение в имени свойства.  
  
 Рекомендуемый подход для хранения значений свойств заключается в определении переменной `Private` в контейнере свойства и использование его в процедурах `Get` и `Set`.  Процедура `Set` затем будет хранить входящее значение в этой переменной `Private`.  
  
 Процедура `Get` действует как процедура `Function`, поэтому можно присвоить значение имени свойства и вернуть управление путем добавления оператора `End Get`.  Рекомендуемым подходом, однако, является включение переменной `Private` в качестве значения в [Оператор Return](../../../visual-basic/language-reference/statements/return-statement.md).  
  
 Процедура `Set` действует как процедура `Sub`, которая не возвращает значения.  Поэтому имя процедуры или свойства не имеет особого смысла в процедуре `Set`, и в ней нельзя хранить значения.  
  
 В следующем примере показан подход, который может вызвать эту ошибку, после чего показан рекомендуемый подход.  
  
```  
Public Class illustrateProperties  
' The code in the following property causes this error.  
    Public Property badProp() As Char  
        Get  
            Dim charValue As Char  
            ' Insert code to update charValue.  
            badProp = charValue  
        End Get  
        Set(ByVal Value As Char)  
            ' The following statement causes this error.  
            badProp = Value  
            ' The value stored in the local variable badProp  
            ' is not used by the Get procedure in this property.  
        End Set  
    End Property  
' The following code uses the recommended approach.  
    Private propValue As Char  
    Public Property goodProp() As Char  
        Get  
            ' Insert code to update propValue.  
            Return propValue  
        End Get  
        Set(ByVal Value As Char)  
            propValue = Value  
        End Set  
    End Property  
End Class  
```  
  
 По умолчанию это сообщение является предупреждающим.  Дополнительные сведения о скрытии предупреждений или обработке предупреждений в качестве ошибки содержатся в разделе [Настройка предупреждений в Visual Basic](/visual-studio/ide/configuring-warnings-in-visual-basic).  
  
 **Идентификатор ошибки:** BC42026  
  
### Чтобы исправить эту ошибку  
  
-   Перепишите определение свойства согласно рекомендуемому подходу, как показано в предыдущем примере.  
  
## См. также  
 [Процедуры свойств](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)   
 [Оператор Set](../../../visual-basic/language-reference/statements/set-statement.md)