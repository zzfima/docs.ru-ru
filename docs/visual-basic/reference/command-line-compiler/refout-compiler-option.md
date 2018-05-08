---
title: -refout (Visual Basic)
ms.date: 03/16/2018
f1_keywords:
- /refout
helpviewer_keywords:
- refout compiler option [Visual Basic]
- /refout compiler option [Visual Basic]
- -refout compiler option [Visual Basic]
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 21cea76f31bdf2ac5fcf434ee759f874f917617b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="-refout-visual-basic"></a>-refout (Visual Basic)

Параметр **-refout** указывает путь к файлу, в который нужно выводить базовую сборку.

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]

## <a name="syntax"></a>Синтаксис

```console
-refout:filepath
```

## <a name="arguments"></a>Аргументы

 `filepath` Путь и имя файла ссылочную сборку. Как правило, он должен находиться в подпапке основной сборки. Согласно рекомендуемому соглашению (используемому в MSBuild), базовую сборку следует помещать во вложенную папку ref/ относительно основной сборки. Все папки в `filepath` должен существовать; компилятор не выполняет их. 

## <a name="remarks"></a>Примечания

Visual Basic поддерживает `-refout` переключения, начиная с версии 15,3.

Ссылочные сборки являются только метаданные сборки, которые содержат метаданные, но без реализации их кода. Они включают сведения о типе и члене для все, кроме анонимных типов. Их тела заменяются одной `throw null` инструкции. Причины для использования `throw null` тела метода (в отличие от без тела), находится PEVerify можно выполнить и передать (таким образом Проверка полноты метаданных).

Ссылочные сборки включают уровня сборки [ReferenceAssembly](xref:System.Runtime.CompilerServices.ReferenceAssemblyAttribute) атрибута. Этот атрибут может быть задан в исходном коде (в этом случае компилятору не требуется его синтезировать). Из-за этого атрибута сред выполнения не будет загружать ссылочные сборки для выполнения (но по-прежнему могут быть загружены в контекст только для отражения). Средства, которые отражают сборок необходимо убедиться, что они загрузятся ссылку как предназначенный только для отражения; в противном случае среда выполнения создает <xref:System.BadImageFormatException>.

Параметры `-refout` и [`-refonly`](refonly-compiler-option.md) являются взаимоисключающими.

## <a name="see-also"></a>См. также
[-refonly](refonly-compiler-option.md)   
[Компилятор Visual Basic с интерфейсом командной строки](index.md)  
[Примеры командных строк компиляции](sample-compilation-command-lines.md)  

