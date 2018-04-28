---
title: Привязки do (F#)
description: 'Узнайте, как выполнить привязку F # используется для выполнения кода без определения функции или значения.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 4c63da0c5e2f4130d59f9efa6bc54a55e5fe9fd8
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="do-bindings"></a>Привязки do

Объект `do` привязка используется для выполнения кода без определения функции или значения. Кроме того, привязки "Выполнить" можно использовать в классах см [ `do` привязок в классах](../members/do-bindings-in-classes.md).


## <a name="syntax"></a>Синтаксис

```fsharp
[ attributes ]
[ do ]expression
```

## <a name="remarks"></a>Примечания
Используйте `do` привязки, если требуется выполнить код независимо от определения функции или значения. Выражение в `do` привязки должен возвращать `unit`. Код верхнего уровня `do` привязки выполняется при инициализации модуля. Ключевое слово `do` является необязательным.

Атрибуты могут быть применены к верхнего уровня `do` привязки. Например, если программа использует COM-взаимодействия, может потребоваться применить `STAThread` атрибута в программу. Это можно сделать с помощью атрибута `do` привязки, как показано в следующем коде.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet201.fs)]
    
## <a name="see-also"></a>См. также
[Справочник по языку F#](../index.md)

[Функции](index.md)

