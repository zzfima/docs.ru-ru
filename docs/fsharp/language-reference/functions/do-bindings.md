---
title: "Привязки do (F#)"
description: "Узнайте, как выполнить привязку F # используется для выполнения кода без определения функции или значения."
keywords: "visual f#, f#, функциональное программирование"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 4c1057a3-3aa1-4b64-b46a-25ffe33f0be9
ms.openlocfilehash: f2563d384b67c005c96c2ff487c786476d385e70
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
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

