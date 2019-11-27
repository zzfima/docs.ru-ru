---
title: -refout
ms.date: 03/16/2018
f1_keywords:
- /refout
helpviewer_keywords:
- refout compiler option [Visual Basic]
- /refout compiler option [Visual Basic]
- -refout compiler option [Visual Basic]
ms.openlocfilehash: 3649a24a52cc6a448ea7cf4d850915adf02147fb
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348657"
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

Базовые сборки являются особым типом сборки, которая содержит только минимальный объем метаданных, необходимый для представления общедоступного API-интерфейса библиотеки. Такие сборки включают в себя объявления для всех элементов, которые важны при указании ссылки на сборку в средствах сборки, но исключают все реализации элементов, а также объявления закрытых элементов, не имеющих наблюдаемого влияния на их контракт API. Дополнительные сведения см. в разделе [Базовые сборки](../../../standard/assembly/reference-assemblies.md) в руководстве по .NET.

Параметры `-refout` и [`-refonly`](refonly-compiler-option.md) являются взаимоисключающими.

## <a name="see-also"></a>См. также

- [/refonly](refonly-compiler-option.md)
- [Компилятор Visual Basic с интерфейсом командной строки](index.md)
- [Примеры командных строк компиляции](sample-compilation-command-lines.md)
