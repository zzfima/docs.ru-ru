---
title: -refonly (Visual Basic)
ms.date: 03/16/2018
f1_keywords:
- -refonly
helpviewer_keywords:
- /refonly compiler option [Visual Basic]
- -refonly compiler option [Visual Basic]
- refonly compiler option [Visual Basic]
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e8f6c15084ac9b1a07aef8a0311edfcc4a93337c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="-refonly-visual-basic"></a>-refonly (Visual Basic)

**- Refonly** параметр указывает, что основные выходные файлы для компиляции должна быть ссылочную сборку, а не реализации сборки. Параметр `-refonly` автоматически отключает вывод файлов PDB, так как базовые сборки не могут выполняться.

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]

## <a name="syntax"></a>Синтаксис

```console
-refonly
```

## <a name="remarks"></a>Примечания

Visual Basic поддерживает `-refout` переключения, начиная с версии 15,3.

Ссылочные сборки являются только метаданные сборки, которые содержат метаданные, но без реализации их кода. Они включают сведения о типе и члене для все, кроме анонимных типов. Тело `throw null` используется для того, чтобы могло выполняться средство PEVerify для проверки полноты метаданных, что было бы невозможно при отсутствии тела.

Ссылочные сборки включают уровня сборки [ReferenceAssembly](xref:System.Runtime.CompilerServices.ReferenceAssemblyAttribute) атрибута. Этот атрибут может быть задан в исходном коде (в этом случае компилятору не требуется его синтезировать). Из-за этого атрибута не смогут загрузить ссылочные сборки для выполнения среды выполнения (но по-прежнему могут быть загружены в контекст только для отражения). Средства, которые отражают сборок необходимо убедиться, что они загрузятся ссылку как предназначенный только для отражения; в противном случае среда выполнения создает <xref:System.BadImageFormatException>.

Параметры `-refonly` и [`-refout`](refout-compiler-option.md) являются взаимоисключающими.

## <a name="see-also"></a>См. также
[-refout](refout-compiler-option.md)   
[Компилятор Visual Basic с интерфейсом командной строки](index.md)  
[Примеры командных строк компиляции](sample-compilation-command-lines.md)   
