---
title: -RefOut (Visual Basic)
ms.date: 03/16/2018
f1_keywords:
- /refout
helpviewer_keywords:
- refout compiler option [Visual Basic]
- /refout compiler option [Visual Basic]
- -refout compiler option [Visual Basic]
ms.openlocfilehash: 552e611f222bfcc3ce12520ecdb891fd7b8b21de
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775549"
---
# <a name="-refout-visual-basic"></a>-RefOut (Visual Basic)

Параметр **-refout** указывает путь к файлу, в который нужно выводить базовую сборку.

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]

## <a name="syntax"></a>Синтаксис

```console
-refout:filepath
```

## <a name="arguments"></a>Аргументы

`filepath`  
Путь и имя файла ссылочной сборки. Обычно он находится во вложенной папке основной сборки. Согласно рекомендуемому соглашению (используемому в MSBuild), базовую сборку следует помещать во вложенную папку ref/ относительно основной сборки. Все папки в `filepath` должны существовать; компилятор не создает их.

## <a name="remarks"></a>Заметки

Visual Basic поддерживает параметр `-refout`, начиная с версии 15,3.

Ссылочные сборки — это особый тип сборки, который содержит только минимальный объем метаданных, необходимых для представления поверхности общедоступного API библиотеки. Они включают объявления для всех элементов, которые важны при ссылке на сборку в средствах сборки, но исключают все реализации членов и объявления закрытых членов, не имеющих наблюдаемого влияния на их контракт API. Дополнительные сведения см. в разделе Справочник по [сборкам](../../../standard/assembly/reference-assemblies.md) в .NET.

Параметры `-refout` и [`-refonly`](refonly-compiler-option.md) являются взаимоисключающими.

## <a name="see-also"></a>См. также

- [/refonly](refonly-compiler-option.md)
- [Компилятор Visual Basic с интерфейсом командной строки](index.md)
- [Примеры командных строк компиляции](sample-compilation-command-lines.md)
