---
title: Идентификаторы Source Line, File и Path
description: Узнайте, как воспользоваться встроенным F# значений идентификаторов, которые дадут возможность доступа к источнику строка номером, каталогу и имя файла в коде.
ms.date: 05/16/2016
ms.openlocfilehash: 3f2048aed9ef75037b43cd091a749e3d6bbaf9a3
ms.sourcegitcommit: 5e05f983e63d5bbd8c0b246d02c6e4f23d2fc1db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2019
ms.locfileid: "67152055"
---
# <a name="source-line-file-and-path-identifiers"></a>Идентификаторы Source Line, File и Path

Идентификаторы `__LINE__`, `__SOURCE_DIRECTORY__` и `__SOURCE_FILE__` собой встроенные значения, которые позволяют получить доступ к исходной строке номер, каталог и имя файла в коде.

## <a name="syntax"></a>Синтаксис

```fsharp
__LINE__
__SOURCE_DIRECTORY__
__SOURCE_FILE__
```

## <a name="remarks"></a>Примечания

Каждое из этих значений имеет тип `string`.

В следующей таблице перечислены идентификаторы источника line, file и path, доступные в F#. Эти идентификаторы не макросы препроцессора; они являются встроенные значения, которые распознаются компилятором.

|Предопределенный идентификатор|Описание|
|---------------------|-----------|
|`__LINE__`|Вычисляет значение текущей строки, учитывая `#line` директивы.|
|`__SOURCE_DIRECTORY__`|Находит текущий полный путь к исходному каталогу, учитывая `#line` директивы.|
|`__SOURCE_FILE__`|Принимает значение текущее имя исходного файла без пути, учитывая `#line` директивы.|

Дополнительные сведения о `#line` директив, см. в разделе [директивы компилятора](compiler-directives.md).

## <a name="example"></a>Пример

В следующем примере кода показано использование этих значений.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet7401.fs)]

Результат

```
Line: 4
Source Directory: C:\Users\username\Documents\Visual Studio 2017\Projects\SourceInfo\SourceInfo
Source File: Program.fs
```

## <a name="see-also"></a>См. также

- [Директивы компилятора](compiler-directives.md)
- [Справочник по языку F#](index.md)
