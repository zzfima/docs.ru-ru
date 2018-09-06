---
title: Идентификаторы Source Line, File и Path (F#)
description: 'Узнайте, как использовать встроенные идентификатор значения F #, которые позволяют получить доступ к номер строки источника, каталог и имя файла в коде.'
ms.date: 05/16/2016
ms.openlocfilehash: 14f710d1412c3420ec627dc30216ba2e89f16bcd
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43865131"
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

В следующей таблице перечислены строку исходного кода, файлов и идентификаторы путей, которые доступны в F #. Эти идентификаторы не макросы препроцессора; они являются встроенные значения, которые распознаются компилятором.

|Предопределенный идентификатор|Описание|
|---------------------|-----------|
|`__LINE__`|Вычисляет значение текущей строки, учитывая `#line` директивы.|
|`__SOURCE_DIRECTORY__`|Находит текущий полный путь к исходному каталогу, учитывая `#line` директивы.|
|`__SOURCE_FILE__`|Вычисляет текущее имя исходного файла и пути, учитывая `#line` директивы.|
Дополнительные сведения о `#line` директив, см. в разделе [директивы компилятора](compiler-directives.md).

## <a name="example"></a>Пример

В следующем примере кода показано использование этих значений.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet7401.fs)]

Результат

```
Line: 4
Source Directory: C:\Users\username\Documents\Visual Studio 2017\Projects\SourceInfo\SourceInfo
Source File: C:\Users\username\Documents\Visual Studio 2017\Projects\SourceInfo\SourceInfo\Program.fs
```

## <a name="see-also"></a>См. также

- [Директивы компилятора](compiler-directives.md)
- [Справочник по языку F#](index.md)
