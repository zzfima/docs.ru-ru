---
title: "Практическое руководство. Объявление параметра для процедуры (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "параметры процедуры, определение"
  - "параметры процедуры, определение типов данных для"
  - "процедуры, определение"
  - "процедуры, параметры"
  - "код Visual Basic, процедуры"
ms.assetid: 7962808d-407e-4e84-984e-43e9857c53c9
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Практическое руководство. Объявление параметра для процедуры (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

*Параметр* позволяет вызывающему коду передать значение в вызываемую процедуру при ее вызове.  Каждый параметр процедуры объявляется таким же способом, каким объявляется переменная: следует указать имя и тип данных параметра.  Также можно задать способ передачи и указать, является ли параметр необязательным.  
  
 Дополнительные сведения см. в разделе [Параметры и аргументы процедуры](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md).  
  
### Определение параметра процедуры  
  
1.  В объявлении процедуры добавьте имя параметра в список параметров процедуры, отделив его от других параметров запятыми.  
  
2.  Выберите тип данных параметра.  
  
3.  Укажите имя параметра и используйте предложение `As` для указания типа данных.  
  
4.  Определите механизм передачи параметра.  Обычно необходимо передавать параметр по значению, если не требуется, чтобы процедура смогла изменить его значение в коде вызова.  
  
5.  Перед именем параметра укажите [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) или [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), чтобы задать механизм передачи.  Дополнительные сведения см. в разделе [Различия между передачей аргумента по значению и по ссылке](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md).  
  
6.  Если аргумент является необязательным, сначала укажите перед механизмом передачи [Optional](../../../../visual-basic/language-reference/modifiers/optional.md), а затем добавьте в тип данных параметр со знаком равенства \(`=`\) и значение по умолчанию.  
  
     В следующем примере определяется структура процедуры `Sub` с тремя параметрами.  Первые два параметра являются обязательными, а третий — необязательным.  Объявления параметров в списке параметров разделяются запятыми.  
  
     [!code-vb[VbVbcnProcedures#33](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/how-to-define-a-parameter-for-a-procedure_1.vb)]  
  
     Первый параметр принимает объект  `customer` , `updateCustomer` может непосредственно обновлять переменную, передаваемую в `c`, так как аргумент передается [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md).  Процедура не может изменить значения последних двух аргументов, поскольку они передаются [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).  
  
     Если вызывающий код не предоставляет значение параметра  `level` , [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] устанавливает его значение по умолчанию \(0\).  
  
     Если переключатель проверки типов \([Оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)\) имеет значение `Off`, предложение `As` необязательно при определении параметров.  Однако, если любой из параметров использует предложение `As`, для других также необходимо его использование.  Если переключатель проверки типов имеет значение `On`, предложение `As` является обязательным для каждого определения параметра.  
  
     Задание типов данных для всех элементов программирования называется *строгая типизация*.  При установке `Option Strict On`, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] выполняет строгую типизацию.  Настоятельно рекомендуется делать это по следующим причинам:  
  
    -   Это позволяет IntelliSense поддерживать переменные и параметры.  Это позволяет видеть их свойства и другие члены при их вводе в код.  
  
    -   Это позволяет компилятору выполнять проверку типов.  Благодаря этому обнаруживаются операторы, которые не выполняются в ходе работы программы из\-за таких ошибок, например как переполнение.  Также обнаруживаются вызовы методов для объекта, который их не поддерживает.  
  
    -   Обеспечивается более быстрое выполнение кода.  Одной из причин, вызывающих такой эффект, является то, что если не указать тип данных для элемента программирования, компилятор [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] присваивает ему тип `Object`.  Скомпилированному коду может потребоваться прямое и обратное преобразование `Object` и других типов данных, что приводит к снижению производительности.  
  
## См. также  
 [Процедуры](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Подпрограммы](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md)   
 [Процедуры Function](../../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)   
 [Практическое руководство. Передача аргументов в процедуру](../../../../visual-basic/programming-guide/language-features/procedures/how-to-pass-arguments-to-a-procedure.md)   
 [Передача аргументов по значению и по ссылке](../../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)   
 [Рекурсивные процедуры](../../../../visual-basic/programming-guide/language-features/procedures/recursive-procedures.md)   
 [Перегрузка процедур](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)   
 [Объекты и классы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)   
 [Объектно\-ориентированное программирование](../Topic/Object-Oriented%20Programming%20\(C%23%20and%20Visual%20Basic\).md)