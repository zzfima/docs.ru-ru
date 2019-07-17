---
title: Ключевые слова C#
ms.date: 03/07/2017
f1_keywords:
- cs.keywords
helpviewer_keywords:
- keywords [C#]
- C# language, keywords
- Visual C#, keywords
- '@ keyword'
ms.assetid: e929b0f2-4b92-4d37-8060-23d323b098ad
ms.openlocfilehash: 8bb61767324602ae54427c50c73e029a6c7bf3b7
ms.sourcegitcommit: 4d8efe00f2e5ab42e598aff298d13b8c052d9593
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/16/2019
ms.locfileid: "68236021"
---
# <a name="c-keywords"></a>Ключевые слова C#

Ключевые слова — это предварительно определенные зарезервированные идентификаторы, которые имеют специальные значения для компилятора. Их нельзя использовать как идентификаторы в программах без префикса `@`. Например, допустимым идентификатором является `@if`, но не `if`, поскольку `if` является ключевым словом.  
  
 В первой таблице этой статьи перечислены ключевые слова, которые нельзя использовать как идентификаторы в любой части программы C#. Во второй таблице этой статьи перечислены контекстные ключевые слова C#. Контекстные ключевые слова имеют особое значение только в определенном контексте программы, а за пределами этого контекста могут использоваться в качестве идентификаторов. Как правило, новые ключевые слова добавляются в язык C# в качестве контекстных ключевых слов, чтобы не нарушать работу программ, созданных в предыдущих версиях.  
  
|||||  
|---|---|---|---|  
|[abstract](abstract.md)|[as](../operators/type-testing-and-conversion-operators.md#as-operator)|[base](base.md)|[bool](bool.md)|  
|[break](break.md)|[byte](../builtin-types/integral-numeric-types.md)|[case](switch.md)|[catch](try-catch.md)|  
|[char](char.md)|[checked](checked.md)|[class](class.md)|[const](const.md)|  
|[continue](continue.md)|[decimal](../builtin-types/floating-point-numeric-types.md)|[default](default.md)|[delegate](delegate.md)|  
|[do](do.md)|[double](../builtin-types/floating-point-numeric-types.md)|[else](if-else.md)|[enum](enum.md)|  
|[event](event.md)|[explicit](../operators/user-defined-conversion-operators.md)|[extern](extern.md)|[false](false-literal.md)|  
|[finally](try-finally.md)|[fixed](fixed-statement.md)|[float](../builtin-types/floating-point-numeric-types.md)|[for](for.md)|  
|[foreach](foreach-in.md)|[goto](goto.md)|[if](if-else.md)|[implicit](../operators/user-defined-conversion-operators.md)|  
|[in](in.md)|[int](../builtin-types/integral-numeric-types.md)|[interface](interface.md)|[internal](internal.md)|
|[is](is.md)|[lock](lock-statement.md)|[long](../builtin-types/integral-numeric-types.md)|[namespace](namespace.md)|
|[new](../operators/new-operator.md)|[null](null.md)|[object](object.md)|[operator](../operators/operator-overloading.md)|
|[out](out.md)|[override](override.md)|[params](params.md)|[private](private.md)|
|[protected](protected.md)|[public](public.md)|[readonly](readonly.md)|[ref](ref.md)|
|[return](return.md)|[sbyte](../builtin-types/integral-numeric-types.md)|[sealed](sealed.md)|[short](../builtin-types/integral-numeric-types.md)||
[sizeof](sizeof.md)|[stackalloc](../operators/stackalloc.md)|[static](static.md)|[string](string.md)|
|[struct](struct.md)|[switch](switch.md)|[this](this.md)|[throw](throw.md)|
|[true](true-literal.md)|[try](try-catch.md)|[typeof](../operators/type-testing-and-conversion-operators.md#typeof-operator)|[uint](../builtin-types/integral-numeric-types.md)|
|[ulong](../builtin-types/integral-numeric-types.md)|[unchecked](unchecked.md)|[unsafe](unsafe.md)|[ushort](../builtin-types/integral-numeric-types.md)|
|[using](using.md)|[using static](using-static.md)|[virtual](virtual.md)|[void](void.md)|
|[volatile](volatile.md)|[while](while.md)|

## <a name="contextual-keywords"></a>Контекстные ключевые слова

 Контекстное ключевое слово используется для предоставления конкретного значения в коде, но оно не является зарезервированным словом в C#. Некоторые контекстные ключевые слова, например `partial` и `where`, имеют особое значение в двух или более контекстах.  
  
||||  
|---|---|---|  
|[add](add.md)|[alias](extern-alias.md)|[ascending](ascending.md)|
|[async](async.md)|[await](await.md)|[by](by.md)|
|[descending](descending.md)|[dynamic](dynamic.md)|[equals](equals.md)|
|[from](from-clause.md)|[get](get.md)|[global](global.md)|
|[group](group-clause.md)|[into](into.md)|[join](join-clause.md)|
|[let](let-clause.md)|[nameof](../operators/nameof.md)|[on](on.md)|
|[orderby](orderby-clause.md)|[partial (тип)](partial-type.md)|[partial (метод)](partial-method.md)|
|[remove](remove.md)|[select](select-clause.md)|[set](set.md)|
|[value](value.md)|[var](var.md)|[when (условие фильтра)](when.md)|
|[where (ограничение универсального типа)](where-generic-type-constraint.md)|[where (предложение запроса)](where-clause.md)|[yield](yield.md)|
  
## <a name="see-also"></a>См. также

- [справочник по C#](../index.md)
