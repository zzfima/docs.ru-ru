---
title: -RefOut (Visual Basic)
ms.date: 03/16/2018
f1_keywords:
- /refout
helpviewer_keywords:
- refout compiler option [Visual Basic]
- /refout compiler option [Visual Basic]
- -refout compiler option [Visual Basic]
ms.openlocfilehash: c11d83ff37da41faa3dc6b66a87e2c52c5f6c7ac
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582872"
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

Ссылочные сборки — это сборки только метаданных, содержащие метаданные, но не имеющие кода реализации. Они включают сведения о типах и членах для всех, кроме анонимных типов. Текст их методов заменяется одной инструкцией `throw null`. Причина использования тела метода `throw null` (в отличие от тела) заключается в том, что PEVerify может выполнять и передавать (таким образом проверяет полноту метаданных).

Ссылочные сборки включают атрибут [референцеассембли](xref:System.Runtime.CompilerServices.ReferenceAssemblyAttribute) уровня сборки. Этот атрибут может быть задан в исходном коде (в этом случае компилятору не требуется его синтезировать). Из-за этого атрибута среда выполнения отказывается загружать эталонные сборки для выполнения (но они по-прежнему могут загружаться в контексте только для отражения). Средства, отражающие сборки, должны обеспечивать загрузку эталонных сборок только отражением. в противном случае среда выполнения создает <xref:System.BadImageFormatException>.

Параметры `-refout` и [`-refonly`](refonly-compiler-option.md) являются взаимоисключающими.

## <a name="see-also"></a>См. также

- [/refonly](refonly-compiler-option.md)
- [Компилятор Visual Basic с интерфейсом командной строки](index.md)
- [Примеры командных строк компиляции](sample-compilation-command-lines.md)
