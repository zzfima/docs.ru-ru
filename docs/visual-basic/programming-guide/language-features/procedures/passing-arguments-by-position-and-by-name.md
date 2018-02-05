---
title: "Передача аргументов по позиции и по имени (Visual Basic)"
ms.custom: 
ms.date: 02/01/2018
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- arguments [Visual Basic], passing by name
- procedures [Visual Basic], arguments
- := passing arguments
- procedure arguments
- Visual Basic code, procedures
- named arguments [Visual Basic], passing arguments
- arguments [Visual Basic], passing by position
- Function procedures [Visual Basic], passing arguments
- named parameters [Visual Basic], passing arguments
- named arguments
- passing parameters [Visual Basic], named parameter arguments
- passing parameters [Visual Basic], by position
- procedures [Visual Basic], calling
- named parameters
- Sub procedures [Visual Basic], passing arguments
- argument passing
- passing parameters [Visual Basic], by name
- argument passing [Visual Basic], by position
- arguments [Visual Basic], listing by name
ms.assetid: 1ad7358f-1da9-48da-a95b-f3c7ed41eff3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 13f5e5a8da6a899d4920a25b250ca88b2a21f559
ms.sourcegitcommit: 099aa20d9b6450d1b7452d782a55771a6ad8ff35
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2018
---
# <a name="passing-arguments-by-position-and-by-name-visual-basic"></a>Передача аргументов по позиции и по имени (Visual Basic)
При вызове `Sub` или `Function` процедуры, можно передать аргументы *по позиции* — в том порядке, в котором они отображаются в определении процедуры, или их можно передать *по имени*, без учета.  
  
 Если аргумент передается по имени, укажите его объявленное имя, за которым следует двоеточие и знак равенства (`:=`), а затем значение аргумента. Можно передать аргументы в любом порядке.  
  
 Например, следующая `Sub` процедура принимает три аргумента:  
  
 [!code-vb[SampleProcedure](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#1)]  
  
 При вызове этой процедуры можно указать аргументов по позиции, по имени или с помощью их сочетании.  
  
## <a name="passing-arguments-by-position"></a>Передача аргументов по позиции  
 Можно вызвать `Display` метод с ее аргументы, передаваемые по позиции и разделенными запятыми, как показано в следующем примере:  
  
[!code-vb[ByPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#2)] 
  
 Если необязательный аргумент в списке позиционный аргумент опущен, необходимо отметить его место запятой. В следующем примере вызывается `Display` метод без `age` аргумент:  
  
[!code-vb[ByPositionWithOptionalArgument](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#3)] 
  
## <a name="passing-arguments-by-name"></a>Передача аргументов по имени  
 Кроме того, можно вызвать метод `Display` с аргументами, передаваемыми по имени и также разделенными запятыми, как показано в следующем примере:  
  
[!code-vb[ByName](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#4)] 

 Передача аргументов по имени таким образом особенно полезна при вызове процедуры, которая имеет более чем один необязательный аргумент. Если аргументы передаются по имени, не имеют несколько запятых подряд для опускать позиционные аргументы. Передача аргументов по имени делает его более удобным для отслеживания какие аргументы заданы, а какие пропущены.  
  
## <a name="mixing-arguments-by-position-and-by-name"></a>Смешивание аргументов по позиции и по имени  

Аргументов по позиции и по имени в одном вызове процедуры, можно указать, как показано в следующем примере:  
  
[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#5)] 
  
 В приведенном выше примере дополнительная запятая, не обязательно отмечающая пропущенный аргумент `age` аргумент, поскольку `birth` передается по имени.  
  
В версиях Visual Basic до 15,5 Если аргументы перепутаны позиции и имя, это позиционные аргументы должны быть первой. После аргумента, передаваемого по имени, все остальные аргументы все передается по имени.  Например, в следующем вызове `Display` метод отображает ошибку компилятора [BC30241: ожидается аргумент с именем](../../../misc/bc30241.md).

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#6)] 

Начиная с Visual Basic 15,5 позиционные аргументы для выполнения именованные аргументы окончания позиционные аргументы находятся в правильном положении. При компиляции в Visual Basic 15,5, предыдущего вызова `Display` метод успешно компилируется и больше не создает ошибку компилятора [BC30241](../../../misc/bc30241.md).  

Эта возможность комбинировать и сопоставлять именованных и позиционных аргументов в любом порядке особенно полезен, если вы хотите использовать именованный аргумент, чтобы сделать код более удобочитаемым. Например, следующая `Person` конструктору класса требуется два аргумента типа `Person`, которые могут быть `Nothing`. 

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#7)] 

С помощью смешанного именованных и позиционных аргументов, снимите помогает сделать назначение кода, когда значение `father` и `mother` аргументов является `Nothing`:

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#8)] 

Чтобы выполнить позиционные аргументы с именованными аргументами, необходимо добавить следующий элемент в проект Visual Basic (\*.vbproj) файла:

```xml
<PropertyGroup>
  <LangVersion>15.5</LangVersion>
</PropertyGroup>
```

## <a name="restrictions-on-supplying-arguments-by-name"></a>Ограничения при передаче аргументов по имени  

Аргументы невозможно передать по имени, чтобы избежать ввода обязательных аргументов. Можно опустить только необязательные аргументы.  
  
Невозможно передать массив параметров по имени. Это так, как при вызове процедуры, необходимо указать неопределенное число разделенных запятыми аргументов для массива параметров, и компилятор не может связывать несколько аргументов с одним именем.  
  
## <a name="see-also"></a>См. также  
 [Процедуры](./index.md)  
 [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)  
 [Практическое руководство. Передача аргументов в процедуру](./how-to-pass-arguments-to-a-procedure.md)  
 [Передача аргументов по значению и по ссылке](./passing-arguments-by-value-and-by-reference.md)  
 [Необязательные параметры](./optional-parameters.md)  
 [Массивы параметров](./parameter-arrays.md)  
 [Необязательный](../../../../visual-basic/language-reference/modifiers/optional.md)  
 [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md)
