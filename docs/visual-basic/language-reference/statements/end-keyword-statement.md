---
title: "Оператор End &lt;ключевое_слово&gt; (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.EndDefinition"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "End - ключевое слово"
ms.assetid: 42d6e088-ab0f-4cda-88e8-fdce3e5fcf4f
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# Оператор End &lt;ключевое_слово&gt; (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Когда следует за дополнительным ключевым словом, завершает определение блока операторов, представленного ключевым словом.  
  
## Синтаксис  
  
```  
End AddHandler  
End Class   
End Enum   
End Event   
End Function   
End Get   
End If   
End Interface   
End Module   
End Namespace   
End Operator   
End Property   
End RaiseEvent  
End RemoveHandler  
End Select   
End Set   
End Structure   
End Sub   
End SyncLock   
End Try   
End While   
End With  
```  
  
## Части  
 `End`  
 Обязательный.  Завершает определение программного элемента.  
  
 `AddHandler`  
 Обязателен для завершения метода доступа `AddHandler`, запущенного соответствующим оператором `AddHandler` в пользовательском [Оператор Event](../../../visual-basic/language-reference/statements/event-statement.md).  
  
 `Class`  
 Обязателен для завершения определения класса, начатого соответствующим [Оператор Class](../../../visual-basic/language-reference/statements/class-statement.md).  
  
 `Enum`  
 Обязателен для завершения определения перечисления, начатого соответствующим [Оператор Enum](../../../visual-basic/language-reference/statements/enum-statement.md).  
  
 `Event`  
 Обязателен для завершения определения события `Custom`, начатого соответствующим [Оператор Event](../../../visual-basic/language-reference/statements/event-statement.md).  
  
 `Function`  
 Обязателен для завершения определения процедуры `Function`, начатого соответствующим [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md).  Если при выполнении встречается оператор `End` `Function`, то управление возвращается в вызывающий код.  
  
 `Get`  
 Обязателен для завершения определения процедуры `Property`, начатого соответствующим [Оператор Get](../../../visual-basic/language-reference/statements/get-statement.md).  Если при выполнении встречается оператор `End` `Get`, то управление возвращается оператору, выполнившему запрос значения.  
  
 `If`  
 Обязателен для завершения блока определений `If`... `Then`... `Else`, начатого соответствующим оператором `If`.  Дополнительные сведения см. в разделе [Оператор If...Then...Else](../../../visual-basic/language-reference/statements/if-then-else-statement.md).  
  
 `Interface`  
 Обязателен для завершения определения интерфейса, начатого соответствующим оператором [Оператор Interface](../../../visual-basic/language-reference/statements/interface-statement.md).  
  
 `Module`  
 Обязателен для завершения определения события, начатого соответствующим [Оператор Module](../../../visual-basic/language-reference/statements/module-statement.md).  
  
 `Namespace`  
 Обязателен для завершения определения пространства имен, начатого соответствующим оператором инструкцией [Оператор Namespace](../../../visual-basic/language-reference/statements/namespace-statement.md).  
  
 `Operator`  
 Обязателен для завершения определения оператора, начатого соответствующим [Оператор Operator](../../../visual-basic/language-reference/statements/operator-statement.md).  
  
 `Property`  
 Обязателен для завершения определения свойства, начатого соответствующим [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md).  
  
 `RaiseEvent`  
 Обязателен для завершения метода доступа `RaiseEvent`, запущенного соответствующим выражением `RaiseEvent` в пользовательском [Оператор Event](../../../visual-basic/language-reference/statements/event-statement.md).  
  
 `RemoveHandler`  
 Обязателен для завершения метода доступа `RemoveHandler`, запущенного соответствующим выражением `RemoveHandler` в пользовательском [Оператор Event](../../../visual-basic/language-reference/statements/event-statement.md).  
  
 `Select`  
 Обязателен для завершения блока определений `Select`... `Case`, начатого соответствующим оператором `Select`.  Дополнительные сведения см. в разделе [Оператор Select...Case](../../../visual-basic/language-reference/statements/select-case-statement.md).  
  
 `Set`  
 Обязателен для завершения определения процедуры `Property`, начатого соответствующим [Оператор Set](../../../visual-basic/language-reference/statements/set-statement.md).  Если при выполнении встречается оператор `End` `Set`, то управление возвращается оператору, задавшему значение свойства.  
  
 `Structure`  
 Обязателен для завершения определения структуры, начатого соответствующим [Оператор Structure](../../../visual-basic/language-reference/statements/structure-statement.md).  
  
 `Sub`  
 Обязателен для завершения определения процедуры `Sub`, начатого соответствующим [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md).  Если при выполнении встречается оператор `End` `Sub`, то управление возвращается в вызывающий код.  
  
 `SyncLock`  
 Обязателен для завершения определения блока `SyncLock`, начатого соответствующим оператором `SyncLock`.  Дополнительные сведения см. в разделе [Оператор SyncLock](../../../visual-basic/language-reference/statements/synclock-statement.md).  
  
 `Try`  
 Обязателен для завершения определения блока `Try`...`Catch`...`Finally`, начатого соответствующим оператором `Try`.  Дополнительные сведения см. в разделе [Оператор Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
 `While`  
 Обязателен для завершения определения цикла `While`, начатого соответствующим оператором `While`.  Дополнительные сведения см. в разделе [Оператор While...End While](../../../visual-basic/language-reference/statements/while-end-while-statement.md).  
  
 `With`  
 Обязателен для завершения определения блока `With`, начатого соответствующим оператором `With`.  Дополнительные сведения см. в разделе [Оператор With...End With](../../../visual-basic/language-reference/statements/with-end-with-statement.md).  
  
## Заметки  
 Оператор [Оператор End](../../../visual-basic/language-reference/statements/end-statement.md), используемый без дополнительных ключевых слов, немедленно прекращает выполнение программы.  
  
 Если предшествует знак решетки \(`#`\), ключевое слово `End` завершает блок предварительной обработки, представленный соответствующей директивой.  
  
 `#End`  
 Обязательный.  Завершает определение блока предварительной обработки.  
  
 `#ExternalSource`  
 Обязателен для завершения блока внешнего блока, начатого соответствующей [Директива \#ExternalSource](../../../visual-basic/language-reference/directives/externalsource-directive.md).  
  
 `#If`  
 Обязателен для завершения блока условной компиляции, начатого соответствующей директивой `#If`.  Дополнительные сведения см. в разделе [Директивы \#If...Then...\#Else](../../../visual-basic/language-reference/directives/if-then-else-directives.md).  
  
 `#Region`  
 Обязателен для завершения блока региона, начатого соответствующей [Директива \#Region](../../../visual-basic/language-reference/directives/region-directive.md).  
  
## Примечания для разработчиков приложений смарт\-устройств  
 Оператор `End`, используемый без дополнительных ключевых слов, не поддерживается.  
  
## См. также  
 [Оператор End](../../../visual-basic/language-reference/statements/end-statement.md)