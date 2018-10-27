---
title: -refout (Visual Basic)
ms.date: 03/16/2018
f1_keywords:
- /refout
helpviewer_keywords:
- refout compiler option [Visual Basic]
- /refout compiler option [Visual Basic]
- -refout compiler option [Visual Basic]
ms.openlocfilehash: 8a8068c467f9066af3153434187749fa80d254ca
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2018
ms.locfileid: "50048402"
---
# <a name="-refout-visual-basic"></a>-refout (Visual Basic)

Параметр **-refout** указывает путь к файлу, в который нужно выводить базовую сборку.

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]

## <a name="syntax"></a>Синтаксис

```console
-refout:filepath
```

## <a name="arguments"></a>Аргументы

 `filepath` Путь и имя файла базовой сборки. Обычно следует во вложенной папке основной сборки. Согласно рекомендуемому соглашению (используемому в MSBuild), базовую сборку следует помещать во вложенную папку ref/ относительно основной сборки. Все папки в `filepath` должен существовать; компилятор не создает их. 

## <a name="remarks"></a>Примечания

Visual Basic поддерживает `-refout` переключения, начиная с версии 15.3.

Ссылка сборки являются только метаданные, которые содержат метаданные, но без реализации их кода. Они включают сведения о типе и члене для всем, кроме анонимных типов. Их тела заменяются одной `throw null` инструкции. Причина использования `throw null` тел методов (в отличие от отсутствии тела) является, поэтому PEVerify можно запустить и передать (проверки полноты метаданных).

Базовые сборки содержат уровня сборки [ReferenceAssembly](xref:System.Runtime.CompilerServices.ReferenceAssemblyAttribute) атрибута. Этот атрибут может быть задан в исходном коде (в этом случае компилятору не требуется его синтезировать). Из-за этого атрибута среды выполнения не будет загружать базовые сборки для выполнения (но по-прежнему могут быть загружены в контекст только для отражения). Средства, выполняющие отражение сборок необходимо убедиться, что они загружать базовые сборки как предназначенный только для отражения; в противном случае среда выполнения создает <xref:System.BadImageFormatException>.

Параметры `-refout` и [`-refonly`](refonly-compiler-option.md) являются взаимоисключающими.

## <a name="see-also"></a>См. также
[-refonly](refonly-compiler-option.md)   
[Компилятор Visual Basic с интерфейсом командной строки](index.md)  
[Примеры командных строк компиляции](sample-compilation-command-lines.md)  

