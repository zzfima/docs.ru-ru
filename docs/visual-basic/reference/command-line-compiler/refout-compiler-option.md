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
# <a name="-refout-visual-basic"></a><span data-ttu-id="0a188-102">-RefOut (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0a188-102">-refout (Visual Basic)</span></span>

<span data-ttu-id="0a188-103">Параметр **-refout** указывает путь к файлу, в который нужно выводить базовую сборку.</span><span class="sxs-lookup"><span data-stu-id="0a188-103">The **-refout** option specifies a file path where the reference assembly should be output.</span></span>

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]

## <a name="syntax"></a><span data-ttu-id="0a188-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0a188-104">Syntax</span></span>

```console
-refout:filepath
```

## <a name="arguments"></a><span data-ttu-id="0a188-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="0a188-105">Arguments</span></span>

`filepath`  
<span data-ttu-id="0a188-106">Путь и имя файла ссылочной сборки.</span><span class="sxs-lookup"><span data-stu-id="0a188-106">The path and filename of the reference assembly.</span></span> <span data-ttu-id="0a188-107">Обычно он находится во вложенной папке основной сборки.</span><span class="sxs-lookup"><span data-stu-id="0a188-107">It should generally be in a sub-folder of the primary assembly.</span></span> <span data-ttu-id="0a188-108">Согласно рекомендуемому соглашению (используемому в MSBuild), базовую сборку следует помещать во вложенную папку ref/ относительно основной сборки.</span><span class="sxs-lookup"><span data-stu-id="0a188-108">The recommended convention (used by MSBuild) is to place the reference assembly in a "ref/" sub-folder relative to the primary assembly.</span></span> <span data-ttu-id="0a188-109">Все папки в `filepath` должны существовать; компилятор не создает их.</span><span class="sxs-lookup"><span data-stu-id="0a188-109">All folders in `filepath` must exist; the compiler does not create them.</span></span>

## <a name="remarks"></a><span data-ttu-id="0a188-110">Заметки</span><span class="sxs-lookup"><span data-stu-id="0a188-110">Remarks</span></span>

<span data-ttu-id="0a188-111">Visual Basic поддерживает параметр `-refout`, начиная с версии 15,3.</span><span class="sxs-lookup"><span data-stu-id="0a188-111">Visual Basic supports the `-refout` switch starting with version 15.3.</span></span>

<span data-ttu-id="0a188-112">Ссылочные сборки — это особый тип сборки, который содержит только минимальный объем метаданных, необходимых для представления поверхности общедоступного API библиотеки.</span><span class="sxs-lookup"><span data-stu-id="0a188-112">Reference assemblies are a special type of assembly that contain only the minimum amount of metadata required to represent the library's public API surface.</span></span> <span data-ttu-id="0a188-113">Они включают объявления для всех элементов, которые важны при ссылке на сборку в средствах сборки, но исключают все реализации членов и объявления закрытых членов, не имеющих наблюдаемого влияния на их контракт API.</span><span class="sxs-lookup"><span data-stu-id="0a188-113">They include declarations for all members that are significant when referencing an assembly in build tools, but exclude all member implementations and declarations of private members that have no observable impact on their API contract.</span></span> <span data-ttu-id="0a188-114">Дополнительные сведения см. в разделе Справочник по [сборкам](../../../standard/assembly/reference-assemblies.md) в .NET.</span><span class="sxs-lookup"><span data-stu-id="0a188-114">For more information, see [Reference assemblies](../../../standard/assembly/reference-assemblies.md) in .NET Guide.</span></span>

<span data-ttu-id="0a188-115">Параметры `-refout` и [`-refonly`](refonly-compiler-option.md) являются взаимоисключающими.</span><span class="sxs-lookup"><span data-stu-id="0a188-115">The `-refout` and [`-refonly`](refonly-compiler-option.md) options are mutually exclusive.</span></span>

## <a name="see-also"></a><span data-ttu-id="0a188-116">См. также</span><span class="sxs-lookup"><span data-stu-id="0a188-116">See also</span></span>

- [<span data-ttu-id="0a188-117">/refonly</span><span class="sxs-lookup"><span data-stu-id="0a188-117">-refonly</span></span>](refonly-compiler-option.md)
- [<span data-ttu-id="0a188-118">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="0a188-118">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="0a188-119">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="0a188-119">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
