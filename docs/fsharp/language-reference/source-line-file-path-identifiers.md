---
title: "Идентификаторы Source Line, File и Path (F#)"
description: "Узнайте, как использовать встроенные значения идентификатора языка F #, которые позволяют получить доступ к номер строки источника, каталог и имя файла в коде."
keywords: "visual f#, f#, функциональное программирование"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 4cfe7439-275c-4d08-980b-784e240bbf29
ms.openlocfilehash: 44cc0914226c120f2b877ce3decd25caa6817eec
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
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
