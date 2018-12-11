---
title: Передача аргументов по позиции и по имени (Visual Basic)
ms.date: 02/01/2018
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
ms.openlocfilehash: bdaa0351e288b85a3e35818c0f53ef4d772932e5
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53151318"
---
# <a name="passing-arguments-by-position-and-by-name-visual-basic"></a>Передача аргументов по позиции и по имени (Visual Basic)
При вызове `Sub` или `Function` процедуру, вы можете передавать аргументы *по позиции* — в порядке, в котором они появляются в определении процедуры, или их можно передать *по имени*, без учета.  
  
 Когда аргумент передается по имени, укажите его объявленное имя, за которым следует двоеточие и знак равенства (`:=`), а затем, если значение аргумента. Вы можете указать аргументы в любом порядке.  
  
 Например, следующая `Sub` процедура принимает три аргумента:  
  
 [!code-vb[SampleProcedure](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#1)]  
  
 При вызове этой процедуры можно указать аргументов по позиции, по имени или с помощью их комбинацией.  
  
## <a name="passing-arguments-by-position"></a>Передача аргументов по позиции  
 Вы можете вызвать `Display` метод с аргументов по позиции и разделенными запятыми, как показано в следующем примере:  
  
[!code-vb[ByPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#2)] 
  
 Если опустить необязательный аргумент в список позиционных аргументов, должен выполнять вместо него запятую. В следующем примере вызывается `Display` метод без `age` аргумент:  
  
[!code-vb[ByPositionWithOptionalArgument](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#3)] 
  
## <a name="passing-arguments-by-name"></a>Передача аргументов по имени  
 Кроме того, можно вызвать `Display` с аргументами, передаваемыми по имени, также разделенными запятыми, как показано в следующем примере:  
  
[!code-vb[ByName](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#4)] 

 Передача аргументов по имени, таким образом особенно полезна при вызове процедуры, которая имеет более чем один необязательный аргумент. Если аргументы по имени, вам не нужно использовать идущие подряд запятые позволяет опускать позиционные аргументы. Передача аргументов по имени также упрощает для отслеживания какие аргументы, передаваемые и пропуск каких из них.  
  
## <a name="mixing-arguments-by-position-and-by-name"></a>Сочетание аргументов по позиции и по имени  

Аргументов по позиции и по имени в одном вызове процедуры, можно указать, как показано в следующем примере:  
  
[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#5)] 
  
 В приведенном выше примере не лишнюю запятую необходим отмечающая пропущенный аргумент `age` аргумента, так как `birth` передается по имени.  
  
В версиях Visual Basic до версии 15.5 Если аргументы перепутаны позиции и имя, позиционные аргументы должны быть первой. Когда необходимо указать аргумент по имени, все остальные аргументы должны все передаваться по имени.  Например, следующий вызов `Display` метод отображает ошибку компилятора [BC30241: Ожидается именованный аргумент](../../../misc/bc30241.md).

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#6)] 

Начиная с Visual Basic 15.5, позиционные аргументы можно выполнить именованных аргументов, если конечный позиционные аргументы в правильном положении. При компиляции в Visual Basic 15.5, предыдущего вызова `Display` метод успешно компилируется и больше не создает ошибку компилятора [BC30241](../../../misc/bc30241.md).  

Эта возможность смешивать и сочетать именованных и позиционных аргументов в любом порядке особенно полезна в случаях, когда вы хотите использовать именованный аргумент, чтобы сделать код более удобочитаемым. Например, следующая `Person` конструктору класса требуется два аргумента типа `Person`, каждый из которых может быть `Nothing`. 

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#7)] 

С помощью смешанных именованных и позиционных аргументов, упрощает назначение кода очистки, когда значение `father` и `mother` аргументов является `Nothing`:

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#8)] 

Чтобы следовать за позиционными аргументами с помощью именованных аргументов, необходимо добавить следующий элемент в проект Visual Basic (\*.vbproj) файла:

```xml
<PropertyGroup>
  <LangVersion>15.5</LangVersion>
</PropertyGroup>
```

Дополнительные сведения см. в разделе [параметр версии языка Visual Basic](../../../language-reference/configure-language-version.md).

## <a name="restrictions-on-supplying-arguments-by-name"></a>Ограничения при передаче аргументов по имени  

Нельзя передавать аргументы по имени, не следует вводить необходимые аргументы. Можно опустить только необязательные аргументы.  
  
Невозможно передать массив параметров по имени. Это потому, что при вызове процедуры, вы предоставляете неопределенное число разделенных запятыми аргументов для массива параметров, а компилятор не может связать более одного аргумента с одним именем.  
  
## <a name="see-also"></a>См. также  
 [Процедуры](./index.md)  
 [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)  
 [Инструкции: Передача аргументов в процедуру](./how-to-pass-arguments-to-a-procedure.md)  
 [Передача аргументов по значению и по ссылке](./passing-arguments-by-value-and-by-reference.md)  
 [Необязательные параметры](./optional-parameters.md)  
 [Массивы параметров](./parameter-arrays.md)  
 [Необязательный](../../../../visual-basic/language-reference/modifiers/optional.md)  
 [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md)
