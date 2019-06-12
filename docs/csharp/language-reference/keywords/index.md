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
ms.openlocfilehash: 19126eb8bb78643ca1b91a0ddf537033d19cc698
ms.sourcegitcommit: 34593b4d0be779699d38a9949d6aec11561657ec
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/11/2019
ms.locfileid: "66833227"
---
# <a name="c-keywords"></a>Ключевые слова C#

Ключевые слова — это предварительно определенные зарезервированные идентификаторы, которые имеют специальные значения для компилятора. Их нельзя использовать как идентификаторы в программах без префикса `@`. Например, допустимым идентификатором является `@if`, но не `if`, поскольку `if` является ключевым словом.  
  
 В первой таблице этой статьи перечислены ключевые слова, которые нельзя использовать как идентификаторы в любой части программы C#. Во второй таблице этой статьи перечислены контекстные ключевые слова C#. Контекстные ключевые слова имеют особое значение только в определенном контексте программы, а за пределами этого контекста могут использоваться в качестве идентификаторов. Как правило, новые ключевые слова добавляются в язык C# в качестве контекстных ключевых слов, чтобы не нарушать работу программ, созданных в предыдущих версиях.  
  
|||||  
|---|---|---|---|  
|[abstract](abstract.md)|[as](as.md)|[base](base.md)|[bool](bool.md)|  
|[break](break.md)|[byte](byte.md)|[case](switch.md)|[catch](try-catch.md)|  
|[char](char.md)|[checked](checked.md)|[class](class.md)|[const](const.md)|  
|[continue](continue.md)|[decimal](decimal.md)|[default](default.md)|[delegate](delegate.md)|  
|[do](do.md)|[double](double.md)|[else](if-else.md)|[enum](enum.md)|  
|[event](event.md)|[explicit](explicit.md)|[extern](extern.md)|[false](false-literal.md)|  
|[finally](try-finally.md)|[fixed](fixed-statement.md)|[float](float.md)|[for](for.md)|  
|[foreach](foreach-in.md)|[goto](goto.md)|[if](if-else.md)|[implicit](implicit.md)|  
|[in](in.md)|[int](int.md)|[interface](interface.md)|[internal](internal.md)|
|[is](is.md)|[lock](lock-statement.md)|[long](long.md)|[namespace](namespace.md)|
|[new](new.md)|[null](null.md)|[object](object.md)|[operator](operator.md)|
|[out](out.md)|[override](override.md)|[params](params.md)|[private](private.md)|
|[protected](protected.md)|[public](public.md)|[readonly](readonly.md)|[ref](ref.md)|
|[return](return.md)|[sbyte](sbyte.md)|[sealed](sealed.md)|[short](short.md)||
[sizeof](sizeof.md)|[stackalloc](../operators/stackalloc.md)|[static](static.md)|[string](string.md)|
|[struct](struct.md)|[switch](switch.md)|[this](this.md)|[throw](throw.md)|
|[true](true-literal.md)|[try](try-catch.md)|[typeof](typeof.md)|[uint](uint.md)|
|[ulong](ulong.md)|[unchecked](unchecked.md)|[unsafe](unsafe.md)|[ushort](ushort.md)|
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
|[let](let-clause.md)|[nameof](nameof.md)|[on](on.md)|
|[orderby](orderby-clause.md)|[partial (тип)](partial-type.md)|[partial (метод)](partial-method.md)|
|[remove](remove.md)|[select](select-clause.md)|[set](set.md)|
|[value](value.md)|[var](var.md)|[when (условие фильтра)](when.md)|
|[where (ограничение универсального типа)](where-generic-type-constraint.md)|[where (предложение запроса)](where-clause.md)|[yield](yield.md)|
  
## <a name="see-also"></a>См. также

- [справочник по C#](../index.md)
