---
title: Конец &lt;ключевое слово&gt; Statement (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.EndDefinition
helpviewer_keywords:
- End keyword [Visual Basic]
ms.assetid: 42d6e088-ab0f-4cda-88e8-fdce3e5fcf4f
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: cf0ac1221f8a85a8a43599d9c5ec210884205e5e
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
---
# <a name="end-ltkeywordgt-statement-visual-basic"></a>Конец &lt;ключевое слово&gt; Statement (Visual Basic)
Когда следует дополнительным ключевым словом, завершает определение блока операторов, представленного ключевым словом.  
  
## <a name="syntax"></a>Синтаксис  
  
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
  
## <a name="parts"></a>Части  
 `End`  
 Обязательный. Завершает определение элемента программирования.  
  
 `AddHandler`  
 Обязателен для завершения `AddHandler` начато путем сопоставления доступа `AddHandler` инструкции в пользовательском [оператор Event](../../../visual-basic/language-reference/statements/event-statement.md).  
  
 `Class`  
 Обязателен для завершения определения класса начался, сопоставляя [оператор Class](../../../visual-basic/language-reference/statements/class-statement.md).  
  
 `Enum`  
 Обязателен для завершения начался, сопоставляя определение перечисления [оператор Enum](../../../visual-basic/language-reference/statements/enum-statement.md).  
  
 `Event`  
 Обязателен для завершения `Custom` определение события начала, сопоставляя [оператор Event](../../../visual-basic/language-reference/statements/event-statement.md).  
  
 `Function`  
 Обязателен для завершения `Function` начался, соответствующего определения процедуры [Function, инструкция](../../../visual-basic/language-reference/statements/function-statement.md). Если при выполнении `End``Function` инструкции, управление возвращается в вызывающий код.  
  
 `Get`  
 Обязателен для завершения `Property` начался, соответствующего определения процедуры [оператор Get](../../../visual-basic/language-reference/statements/get-statement.md). Если при выполнении `End``Get` инструкции, управление возвращается в инструкции, запрашивающего значение свойства.  
  
 `If`  
 Обязателен для завершения `If`... `Then`... `Else` начался с соответствующим определением блока `If` инструкции. В разделе [Если... Затем... Оператор Else](../../../visual-basic/language-reference/statements/if-then-else-statement.md).  
  
 `Interface`  
 Обязателен для завершения определения интерфейса начался, сопоставляя [оператор Interface](../../../visual-basic/language-reference/statements/interface-statement.md).  
  
 `Module`  
 Требуется для завершения определения начала путем сопоставления [оператор Module](../../../visual-basic/language-reference/statements/module-statement.md).  
  
 `Namespace`  
 Обязателен для завершения определения начала путем сопоставления пространства имен [оператор Namespace](../../../visual-basic/language-reference/statements/namespace-statement.md).  
  
 `Operator`  
 Требуется для завершения определения оператора начался, сопоставляя [оператор](../../../visual-basic/language-reference/statements/operator-statement.md).  
  
 `Property`  
 Обязателен для завершения определения свойства начался, сопоставляя [оператор Property](../../../visual-basic/language-reference/statements/property-statement.md).  
  
 `RaiseEvent`  
 Обязателен для завершения `RaiseEvent` начато путем сопоставления доступа `RaiseEvent` инструкции в пользовательском [оператор Event](../../../visual-basic/language-reference/statements/event-statement.md).  
  
 `RemoveHandler`  
 Обязателен для завершения `RemoveHandler` начато путем сопоставления доступа `RemoveHandler` инструкции в пользовательском [оператор Event](../../../visual-basic/language-reference/statements/event-statement.md).  
  
 `Select`  
 Обязателен для завершения `Select`... `Case` начался с соответствующим определением блока `Select` инструкции. В разделе [выберите... Оператор выбора](../../../visual-basic/language-reference/statements/select-case-statement.md).  
  
 `Set`  
 Обязателен для завершения `Property` начался, соответствующего определения процедуры [инструкции Set](../../../visual-basic/language-reference/statements/set-statement.md). Если при выполнении `End``Set` инструкции, управление возвращается оператор, который задает значение свойства.  
  
 `Structure`  
 Требуется для завершения определения структуры начался, сопоставляя [оператор Structure](../../../visual-basic/language-reference/statements/structure-statement.md).  
  
 `Sub`  
 Обязателен для завершения `Sub` начался, соответствующего определения процедуры [оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md). Если при выполнении `End``Sub` инструкции, управление возвращается в вызывающий код.  
  
 `SyncLock`  
 Обязателен для завершения `SyncLock` начался с соответствующим определением блока `SyncLock` инструкции. В разделе [оператор SyncLock](../../../visual-basic/language-reference/statements/synclock-statement.md).  
  
 `Try`  
 Обязателен для завершения `Try`... `Catch`... `Finally` начался с соответствующим определением блока `Try` инструкции. В разделе [Try... CATCH... Оператор Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
 `While`  
 Обязателен для завершения `While` цикл определения начала путем сопоставления `While` инструкции. В разделе [во время... Завершить оператор While](../../../visual-basic/language-reference/statements/while-end-while-statement.md).  
  
 `With`  
 Обязателен для завершения `With` начался с соответствующим определением блока `With` инструкции. В разделе [с... Завершить с инструкцией](../../../visual-basic/language-reference/statements/with-end-with-statement.md).  
  
## <a name="remarks"></a>Примечания  
 [Оператор End](../../../visual-basic/language-reference/statements/end-statement.md), без дополнительных ключевых слов, немедленно прекращает выполнение.  
  
 Если предшествует знак решетки (`#`), `End` ключевое слово завершает блок предварительной обработки, представленный соответствующей директивой.  
  
 `#End`  
 Обязательный. Завершает определение блока предварительной обработки.  
  
 `#ExternalSource`  
 Обязателен для завершения блока внешнего источника, начался, сопоставляя [директива #ExternalSource](../../../visual-basic/language-reference/directives/externalsource-directive.md).  
  
 `#If`  
 Обязателен для завершения блока условной компиляции, начался, сопоставляя `#If` директивы. В разделе [#If... Then... #Else директивы](../../../visual-basic/language-reference/directives/if-then-else-directives.md).  
  
 `#Region`  
 Обязателен для завершения блока региона начался, сопоставляя [директива #Region](../../../visual-basic/language-reference/directives/region-directive.md).  
  
## <a name="smart-device-developer-notes"></a>Примечания для разработчиков интеллектуальных устройств  
 `End` Оператор, используемый без дополнительных ключевых слов, не поддерживается.  
  
## <a name="see-also"></a>См. также  
 [Оператор End](../../../visual-basic/language-reference/statements/end-statement.md)
