---
title: -refonly (Visual Basic)
ms.date: 03/16/2018
f1_keywords:
- -refonly
helpviewer_keywords:
- /refonly compiler option [Visual Basic]
- -refonly compiler option [Visual Basic]
- refonly compiler option [Visual Basic]
ms.openlocfilehash: 8e64989ac1410b51991027ffcb33e8dae0c0284b
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775570"
---
# <a name="-refonly-visual-basic"></a>-refonly (Visual Basic)

Параметр **-refonly** указывает, что основные выходные данные компиляции должны быть ссылочной сборкой, а не сборкой реализации. Параметр `-refonly` автоматически отключает вывод файлов PDB, так как базовые сборки не могут выполняться.

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]

## <a name="syntax"></a>Синтаксис

```console
-refonly
```

## <a name="remarks"></a>Заметки

Visual Basic поддерживает параметр `-refonly`, начиная с версии 15,3.

Ссылочные сборки — это особый тип сборки, который содержит только минимальный объем метаданных, необходимых для представления поверхности общедоступного API библиотеки. Они включают объявления для всех элементов, которые важны при ссылке на сборку в средствах сборки, но исключают все реализации членов и объявления закрытых членов, не имеющих наблюдаемого влияния на их контракт API. Дополнительные сведения см. в разделе Справочник по [сборкам](../../../standard/assembly/reference-assemblies.md) в .NET.

Параметры `-refonly` и [`-refout`](refout-compiler-option.md) являются взаимоисключающими.

## <a name="see-also"></a>См. также

- [/refout](refout-compiler-option.md)
- [Компилятор Visual Basic с интерфейсом командной строки](index.md)
- [Примеры командных строк компиляции](sample-compilation-command-lines.md)
