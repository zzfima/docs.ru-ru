---
title: Идентификаторы Source Line, File и Path
description: Узнайте, как использовать встроенные значения F# идентификатора, которые позволяют получить доступ к номеру строки исходного кода, каталогу и имени файла в коде.
ms.date: 05/16/2016
ms.openlocfilehash: f22c3dfb3cb106fbe45883ffd7de01feac30db00
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216748"
---
# <a name="source-line-file-and-path-identifiers"></a>Идентификаторы Source Line, File и Path

Идентификаторы `__LINE__` `__SOURCE_DIRECTORY__` и`__SOURCE_FILE__` являются встроенными значениями, которые позволяют получить доступ к номеру исходной строки, каталогу и имени файла в коде.

## <a name="syntax"></a>Синтаксис

```fsharp
__LINE__
__SOURCE_DIRECTORY__
__SOURCE_FILE__
```

## <a name="remarks"></a>Примечания

Каждое из этих значений имеет тип `string`.

В следующей таблице перечислены идентификаторы исходной строки, файла и пути, доступные в F#. Эти идентификаторы не являются макросами препроцессора; они представляют собой встроенные значения, распознаваемые компилятором.

|Предопределенный идентификатор|Описание|
|---------------------|-----------|
|`__LINE__`|Вычисляется до текущего номера строки, учитывая `#line` директивы.|
|`__SOURCE_DIRECTORY__`|Вычисляет текущий полный путь к исходному каталогу, учитывая `#line` директивы.|
|`__SOURCE_FILE__`|Вычисляет текущее имя исходного файла без пути, учитывая `#line` директивы.|

Дополнительные сведения об директиве `#line` см. в разделе [директивы компилятора](compiler-directives.md).

## <a name="example"></a>Пример

В следующем примере кода показано использование этих значений.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet7401.fs)]

Результат

```console
Line: 4
Source Directory: C:\Users\username\Documents\Visual Studio 2017\Projects\SourceInfo\SourceInfo
Source File: Program.fs
```

## <a name="see-also"></a>См. также

- [Директивы компилятора](compiler-directives.md)
- [Справочник по языку F#](index.md)
