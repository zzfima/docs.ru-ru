---
title: "Свойство &#39;&#39;&lt;имя_свойства&gt;&#39;&#39; возвращает значение не для всех ветвей кода | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc42107"
  - "vbc42107"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC42107"
ms.assetid: 06800966-9c3b-4844-9f13-83ac95607d32
caps.latest.revision: 7
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 7
---
# Свойство &#39;&#39;&lt;имя_свойства&gt;&#39;&#39; возвращает значение не для всех ветвей кода
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Свойство "\<имя\_свойства\>" возвращает значение не для всех ветвей кода.Во время выполнения может произойти исключение, связанное с пустой ссылкой.  
  
 В свойстве процедуры `Get` имеется хотя бы один возможный путь в коде, по которому не возвращается значение.  
  
 Значение можно вернуть из свойства процедуры `Get` любым из следующих способов:  
  
-   Присвойте значение имени свойства, а затем выполните оператор `Exit Property`.  
  
-   Присвойте значение имени свойства, а затем выполните оператор `End Get`.  
  
-   Включите значение в оператор [Оператор Return](../../../visual-basic/language-reference/statements/return-statement.md).  
  
 Если управление передается в процедуру `Exit Property` или `End Get`, и имени свойства не присвоено никакого значения, тогда процедура `Get` возвращает используемое по умолчанию значение для типа данных свойства.  Дополнительные сведения см. в разделе "Поведение" раздела [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md).  
  
 По умолчанию это сообщение является предупреждающим.  Дополнительные сведения о скрытии предупреждений и их обработке как ошибок см. в разделе [Настройка предупреждений в Visual Basic](/visual-studio/ide/configuring-warnings-in-visual-basic).  
  
 **Идентификатор ошибки:** BC42107  
  
### Чтобы исправить эту ошибку  
  
-   Проверьте логику потока управления и убедитесь, что значение присваивается перед каждым оператором, вызывающим возврат.  
  
     Если всегда используется оператор `Return`, то проще обеспечить возврат значения при каждом возврате из процедуры.  В этом случае последним оператором перед `End Get` должен быть оператор `Return`.  
  
## См. также  
 [Процедуры свойств](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)   
 [Оператор Get](../../../visual-basic/language-reference/statements/get-statement.md)