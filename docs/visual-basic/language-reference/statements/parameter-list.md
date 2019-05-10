---
title: Список параметров (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- parameters [Visual Basic], Visual Basic
- parameters [Visual Basic], lists
- parameter lists [Visual Basic]
- Visual Basic code, parameter lists
- arguments [Visual Basic], Visual Basic
- procedures [Visual Basic], parameter lists
ms.assetid: 5d737319-0c34-4df9-a23d-188fc840becd
ms.openlocfilehash: e58d80896d11b4154c7197d4cdaf73a536fdd5e7
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64583546"
---
# <a name="parameter-list-visual-basic"></a>Список параметров (Visual Basic)
Задает параметры, ожидаемые процедурой, если он вызван. Несколько параметров разделяются запятыми. Ниже приведен синтаксис для одного параметра.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
[ <attributelist> ] [ Optional ] [{ ByVal | ByRef }] [ ParamArray ]   
parametername[( )] [ As parametertype ] [ = defaultvalue ]  
```  
  
## <a name="parts"></a>Части  
 `attributelist`  
 Необязательный параметр. Список атрибутов, которые применяются к данному параметру. Необходимо заключить [список атрибутов](../../../visual-basic/language-reference/statements/attribute-list.md) в угловые скобки (»`<`«и»`>`«).  
  
 `Optional`  
 Необязательный параметр. Указывает, что этот параметр не является обязательным, при вызове процедуры.  
  
 `ByVal`  
 Необязательный параметр. Указывает, что процедура не может заменить или переназначить основной соответствующего аргумента в вызывающем коде элемент переменной.  
  
 `ByRef`  
 Необязательный параметр. Указывает, что процедура может изменить элемент базовой переменной в вызывающем коде так же, вызывающем коде.  
  
 `ParamArray`  
 Необязательный параметр. Указывает, что последний параметр в списке параметров необязательный массив элементов указанного типа данных. Это позволяет передать произвольное число аргументов в процедуру.  
  
 `parametername`  
 Обязательный. Имя локальной переменной, представляющей параметр.  
  
 `parametertype`  
 Обязателен, если `Option Strict` является `On`. Тип данных локальной переменной, представляющей параметр.  
  
 `defaultvalue`  
 Требуется для `Optional` параметров. Любая константа или константное выражение, результатом которого является тип данных параметра. Если тип является `Object`, или класс, интерфейс, массив или структура, значение по умолчанию может быть только `Nothing`.  
  
## <a name="remarks"></a>Примечания  
 Параметры заключаются в круглые скобки и разделенные запятыми. Параметр может быть объявлен с любой тип данных. Если вы не укажете `parametertype`, по умолчанию используется `Object`.  
  
 Когда вызывающий код вызывает процедуру, он передает *аргумент* для каждого обязательного параметра. Дополнительные сведения см. в разделе [различия между параметрами и аргументами](../../../visual-basic/programming-guide/language-features/procedures/differences-between-parameters-and-arguments.md).  
  
 Аргумент, который передает вызывающий код в каждый параметр является указателем на базовый элемент в вызывающем коде. Если этот элемент является *неизменяемым* (константой, литерал, перечисление или выражение), в отношении любого кода изменить его невозможно. Если это *переменной* элемент (объявленной переменной, поля, свойства, элемент массива или элемента структуры), вызывающий код может изменить его. Дополнительные сведения см. в разделе [различия между изменяемые и неизменяемые аргументы](../../../visual-basic/programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md).  
  
 Если элемент переменной передается `ByRef`, процедура может изменять его также. Дополнительные сведения см. в разделе [различия между передачей аргумента по значению и по ссылке](../../../visual-basic/programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md).  
  
## <a name="rules"></a>Правила  
  
- **Круглые скобки.** Если указать список параметров, его необходимо заключить в круглые скобки. Если нет параметров, можно по-прежнему использовать скобки, ограничивающие пустой список. Это повышает удобочитаемость кода, указывая, что элемент является процедурой.  
  
- **Необязательные параметры.** Если вы используете `Optional` модификатор параметра, все последующие параметры в списке также должен быть необязательным и объявляться с помощью `Optional` модификатор.  
  
     Каждое объявление необязательного параметра необходимо указать `defaultvalue` предложение.  
  
     Дополнительные сведения см. в разделе [необязательные параметры](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md).  
  
- **Массивы параметров.** Необходимо указать `ByVal` для `ParamArray` параметра.  
  
     Нельзя использовать оба `Optional` и `ParamArray` в тот же список параметров.  
  
     Дополнительные сведения см. в разделе [массивы параметров](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).  
  
- **Механизм передачи.** Этот механизм по умолчанию для каждого аргумента – `ByVal`, означающее процедура не может изменить элемент базовой переменной. Тем не менее если элемент является ссылочным типом, процедура может изменить содержимое или члены базового объекта, несмотря на то, что он не может заменить или переназначить сам объект.  
  
- **Имена параметров.** Если тип данных параметра является массивом, выполните `parametername` немедленно в круглые скобки. Дополнительные сведения об именах параметров см. в разделе [имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
## <a name="example"></a>Пример  
 В следующем примере показан `Function` процедуру, которая определяет два параметра.  
  
 [!code-vb[VbVbalrStatements#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#2)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Runtime.InteropServices.DllImportAttribute>
- [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)
- [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)
- [Оператор Structure](../../../visual-basic/language-reference/statements/structure-statement.md)
- [Оператор Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [Обзор атрибутов](../../../visual-basic/programming-guide/concepts/attributes/index.md)
- [Практическое руководство. Разбиение и объединение инструкций в коде](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
