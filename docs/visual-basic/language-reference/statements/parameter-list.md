---
title: "Список параметров (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic code, procedures
- parameters [Visual Basic], Visual Basic
- parameters [Visual Basic], lists
- parameter lists [Visual Basic]
- Visual Basic code, parameter lists
- arguments [Visual Basic], Visual Basic
- procedures [Visual Basic], parameter lists
ms.assetid: 5d737319-0c34-4df9-a23d-188fc840becd
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2c7190b618aa98c91b826ca7c065660d3b19c31a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="parameter-list-visual-basic"></a>Список параметров (Visual Basic)
Задает параметры, ожидаемые процедурой при вызове. Несколько параметров разделяются запятыми. Ниже приведен синтаксис для одного параметра.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
[ <attributelist> ] [ Optional ] [{ ByVal | ByRef }] [ ParamArray ]   
parametername[( )] [ As parametertype ] [ = defaultvalue ]  
```  
  
## <a name="parts"></a>Части  
 `attributelist`  
 Необязательно. Список атрибутов, которые применяются к данному параметру. Необходимо заключить [список атрибутов](../../../visual-basic/language-reference/statements/attribute-list.md) в угловые скобки («`<`«и»`>`»).  
  
 `Optional`  
 Необязательно. Указывает, что этот параметр не требуется при вызове процедуры.  
  
 `ByVal`  
 Необязательно. Указывает, что процедура не может заменить или переназначить элемент переменной, представляющей соответствующий аргумент в вызывающем коде.  
  
 `ByRef`  
 Необязательно. Указывает, что процедура может изменить элемент базовой переменной в вызывающем коде так же, как в вызывающем коде можно.  
  
 `ParamArray`  
 Необязательно. Указывает, что последний параметр в списке параметров необязательный массив элементов заданного типа данных. Это позволяет передать произвольное число аргументов в процедуру вызывающий код.  
  
 `parametername`  
 Обязательный. Имя локальной переменной, представляющей параметр.  
  
 `parametertype`  
 Обязателен, если `Option Strict` — `On`. Тип данных локальной переменной, представляющей параметр.  
  
 `defaultvalue`  
 Требуется для `Optional` параметров. Любая константа или константное выражение, результатом которого является тип данных параметра. Если тип является `Object`, или класс, интерфейс, массив или структура, значение по умолчанию можно только `Nothing`.  
  
## <a name="remarks"></a>Примечания  
 Параметры заключаются в круглые скобки и разделены запятыми. Параметр может быть объявлен с любым типом данных. Если вы не укажете `parametertype`, то по умолчанию используется `Object`.  
  
 Если вызывающий код вызывает процедуру, то он передает *аргумент* для каждого обязательного параметра. Дополнительные сведения см. в разделе [различия между параметрами и аргументами](../../../visual-basic/programming-guide/language-features/procedures/differences-between-parameters-and-arguments.md).  
  
 Аргумент, который передает вызывающий код в каждый параметр является указателем на базовый элемент в вызывающем коде. Если этот элемент является *неизменяемым* (константа, литерал, перечисление или выражение), для любого кода изменить его невозможно. Если это *переменной* элемент (объявленная переменная, поле, свойство, элемент массива или элемент структуры), вызывающий код может изменить его. Дополнительные сведения см. в разделе [различия между изменяемые и неизменяемые аргументы](../../../visual-basic/programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md).  
  
 Если элемент переменной передается `ByRef`, процедура он также меняется. Дополнительные сведения см. в разделе [различия между передачей аргумента по значению и по ссылке](../../../visual-basic/programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md).  
  
## <a name="rules"></a>Правила  
  
-   **Круглые скобки.** Если указан список параметров, его необходимо заключить в круглые скобки. Если параметры не указаны, можно по-прежнему использовать скобки, ограничивающие пустой список. Это повышает удобочитаемость кода, указывая, что элемент является процедурой.  
  
-   **Необязательные параметры.** Если вы используете `Optional` модификатор параметра, все последующие параметры в списке также должен быть необязательным и быть объявлены с помощью `Optional` модификатор.  
  
     Каждое объявление необязательного параметра необходимо указать `defaultvalue` предложения.  
  
     Дополнительные сведения см. в разделе [необязательные параметры](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md).  
  
-   **Массивы параметров.** Необходимо указать `ByVal` для `ParamArray` параметра.  
  
     Нельзя одновременно указать `Optional` и `ParamArray` в том же списке параметров.  
  
     Дополнительные сведения см. в разделе [массивы параметров](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).  
  
-   **Механизм передачи.** По умолчанию механизм для каждого аргумента является `ByVal`, означающее процедуру нельзя изменить элемент базовой переменной. Тем не менее если элемент является ссылочным типом, процедура может изменить содержимое или члены базового объекта, даже в том случае, если оно не может заменить или переназначить сам объект.  
  
-   **Имена параметров.** Если тип данных параметра является массивом, выполните `parametername` немедленно круглые скобки. Дополнительные сведения об именах параметров см. в разделе [имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
## <a name="example"></a>Пример  
 В следующем примере показан `Function` процедуру, которая определяет два параметра.  
  
 [!code-vb[VbVbalrStatements#2](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/parameter-list_1.vb)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Runtime.InteropServices.DllImportAttribute>  
 [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)  
 [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)  
 [Оператор Structure](../../../visual-basic/language-reference/statements/structure-statement.md)  
 [Оператор Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [Обзор атрибутов](../../../visual-basic/programming-guide/concepts/attributes/index.md)  
 [Практическое руководство. Разбиение и объединение инструкций в коде](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
