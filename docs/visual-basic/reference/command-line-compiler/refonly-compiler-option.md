---
title: -refonly
ms.date: 03/16/2018
f1_keywords:
- -refonly
helpviewer_keywords:
- /refonly compiler option [Visual Basic]
- -refonly compiler option [Visual Basic]
- refonly compiler option [Visual Basic]
ms.openlocfilehash: b906178abf8d159083d95e41448596d512e857de
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348579"
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

Базовые сборки являются особым типом сборки, которая содержит только минимальный объем метаданных, необходимый для представления общедоступного API-интерфейса библиотеки. Такие сборки включают в себя объявления для всех элементов, которые важны при указании ссылки на сборку в средствах сборки, но исключают все реализации элементов, а также объявления закрытых элементов, не имеющих наблюдаемого влияния на их контракт API. Дополнительные сведения см. в разделе [Базовые сборки](../../../standard/assembly/reference-assemblies.md) в руководстве по .NET.

Параметры `-refonly` и [`-refout`](refout-compiler-option.md) являются взаимоисключающими.

## <a name="see-also"></a>См. также

- [/refout](refout-compiler-option.md)
- [Компилятор Visual Basic с интерфейсом командной строки](index.md)
- [Примеры командных строк компиляции](sample-compilation-command-lines.md)
