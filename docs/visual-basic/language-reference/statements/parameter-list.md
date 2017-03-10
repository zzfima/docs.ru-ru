---
title: "Список параметров (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "аргументы [Visual Basic], Visual Basic"
  - "списки параметров"
  - "параметры, списки"
  - "параметры, Visual Basic"
  - "процедуры, списки параметров"
  - "код Visual Basic, списки параметров"
  - "код Visual Basic, процедуры"
ms.assetid: 5d737319-0c34-4df9-a23d-188fc840becd
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# Список параметров (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Задает параметры, ожидаемые процедурой при вызове.  Несколько параметров разделяются запятыми.  Ниже представлен синтаксис для одного параметра.  
  
## Синтаксис  
  
```  
[ <attributelist> ] [ Optional ] [{ ByVal | ByRef }] [ ParamArray ]   
parametername[( )] [ As parametertype ] [ = defaultvalue ]  
```  
  
## Части  
 `attributelist`  
 Необязательный.  Список атрибутов, которые применяются к данному параметру.  Необходимо заключить [Список атрибутов](../../../visual-basic/language-reference/statements/attribute-list.md) в угловые скобки \("`<`" и "`>`"\).  
  
 `Optional`  
 Необязательный.  Указывает, что этот параметр не требуется при вызове процедуры.  
  
 `ByVal`  
 Необязательный.  Указывает, что процедура не может заменить или переназначить основной элемент переменной соответствующего аргумента в коде вызова.  
  
 `ByRef`  
 Необязательный.  Указывает на то, что процедура может изменять основной элемент переменной в вызывающем коде так же, как он изменяется самим вызывающим кодом.  
  
 `ParamArray`  
 Необязательный.  Указывает, что последний параметр в списке параметров является дополнительным массивом элементов заданного типа данных.  Это позволяет передавать произвольное число аргументов в процедуру.  
  
 `parametername`  
 Обязательный.  Имя локальной переменной, представляющей параметр.  
  
 `parametertype`  
 Требуется, если для `Option Strict` установлено значение `On`.  Тип данных локальной переменной, представляющей параметр.  
  
 `defaultvalue`  
 Обязателен для `Optional` параметров.  Любая константа или константное выражение, вычисляемое значение которого имеет тип данных параметра.  Если тип — `Object`, класс, интерфейс, массив или структура, его значением по умолчанию может быть только `Nothing`.  
  
## Заметки  
 Параметры заключаются в круглые скобки и разделяются запятыми.  Параметр может быть объявлен с любым типом данных.  Если не указан `parametertype`, то по умолчанию он имеет значение `Object`.  
  
 Когда код вызова вызывает процедуру, он передает *аргумент* для каждого обязательного параметра.  Дополнительные сведения см. в разделе [Различия между параметрами и аргументами](../../../visual-basic/programming-guide/language-features/procedures/differences-between-parameters-and-arguments.md).  
  
 Аргумент, передаваемый кодом вызова для каждого параметра, является указателем на базовый элемент в коде вызова.  Если этот элемент является *неизменяемым* \(константа, литерал, перечисление или выражение\), то никакой код не сможет его изменить.  Если это элемент *изменяемый* \(объявленная переменная, поле, свойство, элемент массива или элемент структуры\), вызывающий код может изменить его.  Дополнительные сведения см. в разделе [Различия между аргументами Modifiable и Nonmodifiable](../../../visual-basic/programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md).  
  
 Если элемент переменной передается `ByRef`, в процедуре также можно его изменить.  Дополнительные сведения см. в разделе [Различия между передачей аргумента по значению и по ссылке](../../../visual-basic/programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md).  
  
## Правила  
  
-   **Круглые скобки.** Если задан список параметров, необходимо заключить его в круглые скобки.  Если нет параметров, можно по\-прежнему использовать скобки, ограничивающие пустой список.  Это повышает удобочитаемость кода, указывая, что элемент является процедурой.  
  
-   **Необязательные параметры.** Если используется модификатор `Optional` для параметра, все последующие параметры в списке должны также быть дополнительными и быть объявлены с помощью модификатора `Optional`.  
  
     Каждое объявление дополнительного параметра необходимо указать в предложении `defaultvalue`.  
  
     Дополнительные сведения см. в разделе [Необязательные параметры](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md).  
  
-   **Массивы параметров.** Необходимо указать `ByVal` для параметра `ParamArray`.  
  
     Нельзя использовать одновременно и `Optional`, и `ParamArray` в одном списке параметров.  
  
     Дополнительные сведения см. в разделе [Массивы параметров](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).  
  
-   **Способ передачи.** Способом по умолчанию для каждого аргумента является `ByVal`, что означает, что процедура не может изменять базовый элемент переменной.  Однако если элемент является ссылочным типом, процедура может изменять содержимое или члены базового объекта, даже если она не может заменить или переназначить сам объект.  
  
-   **Имена параметра** Если тип данных параметра является массивом, нужно `parametername` ограничить круглыми скобками.  Дополнительные сведения об именах параметра см. в разделе [Имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
## Пример  
 В следующем примере показана процедура `Function`, определяющая два параметра.  
  
 [!code-vb[VbVbalrStatements#2](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/parameter-list_1.vb)]  
  
## См. также  
 <xref:System.Runtime.InteropServices.DllImportAttribute>   
 [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)   
 [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)   
 [Оператор Structure](../../../visual-basic/language-reference/statements/structure-statement.md)   
 [Оператор Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md)   
 [Атрибуты](../Topic/Attributes%20\(C%23%20and%20Visual%20Basic\).md)   
 [Практическое руководство. Разбиение и объединение инструкций в коде](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)