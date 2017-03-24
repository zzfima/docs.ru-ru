---
title: "Список параметров (Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic code, procedures
- parameters, Visual Basic
- parameters, lists
- parameter lists
- Visual Basic code, parameter lists
- arguments [Visual Basic], Visual Basic
- procedures, parameter lists
ms.assetid: 5d737319-0c34-4df9-a23d-188fc840becd
caps.latest.revision: 19
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: abadaa8e035bfa4c92acc30ab633d6a7e958676c
ms.lasthandoff: 03/13/2017

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
 Необязательный. Список атрибутов, которые применяются к данному параметру. Необходимо заключить [список атрибутов](../../../visual-basic/language-reference/statements/attribute-list.md) в угловые скобки («`<`«и»`>`»).  
  
 `Optional`  
 Необязательный. Указывает, что этот параметр не требуется при вызове процедуры.  
  
 `ByVal`  
 Необязательный. Указывает, что процедура не может заменить или переназначить основной соответствующего аргумента в вызывающем коде элемент переменной.  
  
 `ByRef`  
 Необязательный. Указывает, что процедура может изменять основной элемент переменной в вызывающем коде так же, как самим вызывающим кодом.  
  
 `ParamArray`  
 Необязательный. Указывает, что последний параметр в списке параметров необязательный массив элементов заданного типа данных. Это позволяет передавать произвольное число аргументов в процедуру.  
  
 `parametername`  
 Обязательный. Имя локальной переменной, представляющей параметр.  
  
 `parametertype`  
 Обязателен, если `Option Strict` — `On`. Тип данных локальной переменной, представляющей параметр.  
  
 `defaultvalue`  
 Требуется для `Optional` параметров. Любая константа или константное выражение, результатом которого является тип данных параметра. Если тип является `Object`, или класс, интерфейс, массив или структура, значение по умолчанию может быть только `Nothing`.  
  
## <a name="remarks"></a>Примечания  
 Параметры заключаются в круглые скобки и разделенные запятыми. Параметр может быть объявлен с любой тип данных. Если вы не укажете `parametertype`, по умолчанию используется `Object`.  
  
 Если вызывающий код вызывает процедуру, он передает *аргумент* для каждого обязательного параметра. Дополнительные сведения см. в разделе [различия между параметрами и аргументами](../../../visual-basic/programming-guide/language-features/procedures/differences-between-parameters-and-arguments.md).  
  
 Аргумент, вызывающий код передает в каждый параметр является указателем на базовый элемент в вызывающем коде. Если этот элемент является *неизменяемым* (константа, литерал, перечисление или выражение), любой код изменить его невозможно. Если это *переменной* элемента (объявленная переменная, поле, свойство, элемент массива или элемент структуры), вызывающий код может изменить его. Дополнительные сведения см. в разделе [различия между изменяемые и неизменяемые аргументы](../../../visual-basic/programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md).  
  
 Если элемент переменной передается `ByRef`, процедура может изменять его тоже. Дополнительные сведения см. в разделе [различия между передачей аргумента по значению и по ссылке](../../../visual-basic/programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md).  
  
## <a name="rules"></a>Правила  
  
-   **Круглые скобки.** Если указан список параметров, необходимо заключить его в круглые скобки. Если параметры не указаны, по-прежнему можно использовать скобки, ограничивающие пустой список. Это повышает удобочитаемость кода, указывая, что элемент является процедурой.  
  
-   **Необязательные параметры.** Если вы используете `Optional` модификатора параметра, все последующие параметры в списке также должен быть необязательным и объявляться с помощью `Optional` модификатор.  
  
     Каждое объявление дополнительного параметра необходимо указать `defaultvalue` предложения.  
  
     Дополнительные сведения см. в разделе [необязательные параметры](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md).  
  
-   **Массивы параметров.** Необходимо указать `ByVal` для `ParamArray` параметр.  
  
     Нельзя одновременно указать `Optional` и `ParamArray` в такой же список параметров.  
  
     Дополнительные сведения см. в разделе [массивы параметров](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).  
  
-   **Механизм передачи.** Механизм по умолчанию для каждого аргумента является `ByVal`, означающее процедуру нельзя изменить элемент базовой переменной. Тем не менее если элемент является ссылочным типом, процедура может изменить содержимое или члены базового объекта, даже если она не может заменить или переназначить сам объект.  
  
-   **Имена параметров.** Если тип данных параметра является массивом, выполните `parametername` немедленно круглые скобки. Дополнительные сведения об именах параметра см. в разделе [имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
## <a name="example"></a>Пример  
 В следующем примере показан `Function` процедуры, определяющей два параметра.  
  
 [!code-vb[VbVbalrStatements&#2;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/parameter-list_1.vb)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Runtime.InteropServices.DllImportAttribute></xref:System.Runtime.InteropServices.DllImportAttribute>   
 [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)   
 [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)   
 [Оператор Structure](../../../visual-basic/language-reference/statements/structure-statement.md)   
 [Оператор Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md)   
 [Общие сведения об атрибутах](../../../visual-basic/programming-guide/concepts/attributes/index.md)   
 [Практическое руководство. Разбиение и объединение инструкций в коде](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
