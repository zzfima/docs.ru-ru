---
title: Передача аргументов по позиции и по имени
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
ms.openlocfilehash: b6588335f7634cc87a9fc14cbfc4ba80baad1abb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401439"
---
# <a name="passing-arguments-by-position-and-by-name-visual-basic"></a>Передача аргументов по позиции и по имени (Visual Basic)

Когда вы `Sub` вызываете или `Function` процедуру, вы можете пройти аргументы *по позиции* - в порядке, в котором они появляются в определении процедуры - или вы можете передать их по *имени,* без учета позиции.

Когда вы передаете аргумент по имени, вы указываете заявленное имя`:=`аргумента с последующим двоеточием и равным знаком (), за которым следует значение аргумента. Вы можете предоставить именованные аргументы в любом порядке.

Например, следующая `Sub` процедура требует трех аргументов:

[!code-vb[SampleProcedure](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#1)]

Когда вы называете эту процедуру, вы можете предоставить аргументы по позиции, по имени, или с помощью смеси обоих.

## <a name="passing-arguments-by-position"></a>Прохождение Аргументы по позиции

Вы можете `Display` назвать метод с его аргументами, передаваемыми по позиции и делимитировамыми запятыми, как показано в следующем примере:

[!code-vb[ByPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#2)]

Если вы не опускаете факультативный аргумент в позиционном списке аргументов, вы должны занять его место с запятой. Следующий пример `Display` называет метод `age` без аргумента:

[!code-vb[ByPositionWithOptionalArgument](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#3)]

## <a name="passing-arguments-by-name"></a>Передача Аргументов по имени

Кроме того, вы `Display` можете позвонить с аргументами, передаваемыми по имени, также делегированными запятыми, как показано в следующем примере:

[!code-vb[ByName](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#4)]

Передача аргументов по имени таким образом особенно полезна, когда вы называете процедуру, которая имеет более одного факультативного аргумента. Если вы поставляете аргументы по имени, вам не придется использовать последовательные запятые для обозначения недостающих позиционных аргументов. Передача аргументов по имени также облегчает отслеживание того, какие аргументы вы проходите, а какие вы опускаете.

## <a name="mixing-arguments-by-position-and-by-name"></a>Смешивание аргументов по позиции и имени

Аргументы можно предоставить как по позиции, так и по имени в одном вызове процедуры, как показано в следующем примере:

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#5)]

В предыдущем примере для удержания места опущенного `age` аргумента не требуется дополнительная запятая, так как `birth` она передается по имени.

В версиях Visual Basic до 15.5, когда вы поставляете аргументы по смеси позиции и имени, позиционные аргументы должны быть на первом месте. Как только вы поставите аргумент по имени, все оставшиеся аргументы должны быть переданы по имени.  Например, следующий вызов `Display` метода отображает ошибку компилятора [BC30241: Именованный аргумент ожидаемый.](../../../misc/bc30241.md)

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#6)]

Начиная с Visual Basic 15.5, позиционные аргументы могут следовать названным аргументам, если окончание позиционных аргументов находятся в правильном положении. Если компилируется в соответствии с Visual `Display` Basic 15.5, предыдущий вызов метода успешно компилируется и больше не генерирует ошибку компилятора [BC30241.](../../../misc/bc30241.md)

Эта способность смешивать и сочетать названные и позиционные аргументы в любом порядке особенно полезна, когда вы хотите использовать названный аргумент, чтобы сделать ваш код более читаемым. Например, следующий `Person` конструктор класса требует двух `Person`аргументов типа, `Nothing`оба из которых могут быть.

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#7)]

Использование смешанных именованных и позиционных аргументов помогает сделать `mother` цель `Nothing`кода ясным, когда значение `father` и аргументы:

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#8)]

Чтобы следовать позиционным аргументам с названными аргументами, необходимо\*добавить следующий элемент в файл Visual Basic Project (.vbproj):

```xml
<PropertyGroup>
  <LangVersion>15.5</LangVersion>
</PropertyGroup>
```

Для получения дополнительной информации [см.](../../../language-reference/configure-language-version.md)

## <a name="restrictions-on-supplying-arguments-by-name"></a>Ограничения на поставку аргументов по имени

Вы не можете передавать аргументы по имени, чтобы избежать ввода необходимых аргументов. Вы можете пропустить только факультативные аргументы.

Вы не можете передать параметр по имени. Это происходит потому, что при вызове процедуры вы поставляете неопределенное количество аргументов, разделенных запятой, для массива параметров, и компилятор не может связать более одного аргумента с одним именем.

## <a name="see-also"></a>См. также раздел

- [Процедуры](./index.md)
- [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)
- [Практическое руководство. Передача аргументов в процедуру](./how-to-pass-arguments-to-a-procedure.md)
- [Передача аргументов по значению и по ссылке](./passing-arguments-by-value-and-by-reference.md)
- [Дополнительные параметры](./optional-parameters.md)
- [Массивы параметров](./parameter-arrays.md)
- [Дополнительные](../../../../visual-basic/language-reference/modifiers/optional.md)
- [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md)
