---
title: Идентификаторы Source Line, File и Path (F#)
description: 'Узнайте, как использовать встроенные значения идентификатора языка F #, которые позволяют получить доступ к номер строки источника, каталог и имя файла в коде.'
ms.date: 05/16/2016
ms.openlocfilehash: 76b705fec0d951b12655edbe69e7c9212f50779d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="source-line-file-and-path-identifiers"></a>Идентификаторы Source Line, File и Path

Идентификаторы `__LINE__`, `__SOURCE_DIRECTORY__` и `__SOURCE_FILE__` являются встроенными значениями, которые позволяют получить доступ к исходной строке номер, каталог и имя файла в коде.


## <a name="syntax"></a>Синтаксис

```fsharp
__LINE__
__SOURCE_DIRECTORY__
__SOURCE_FILE__
```

## <a name="remarks"></a>Примечания
Каждый из этих значений имеет тип `string`.

В следующей таблице перечислены строку исходного кода, файлов и путь идентификаторы, доступные в языке F #. Эти идентификаторы не являются макросы препроцессора; они являются встроенными значениями, распознаваемым компилятором.

|Предопределенный идентификатор|Описание|
|---------------------|-----------|
|`__LINE__`|Вычисляет значение текущей строки, учитывая `#line` директивы.|
|`__SOURCE_DIRECTORY__`|Находит текущий полный путь к исходному каталогу, учитывая `#line` директивы.|
|`__SOURCE_FILE__`|Находит текущее имя исходного файла и пути, учитывая `#line` директивы.|
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
[Директивы компилятора](compiler-directives.md)

[Справочник по языку F#](index.md)
