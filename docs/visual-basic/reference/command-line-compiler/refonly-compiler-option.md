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
# <a name="-refonly-visual-basic"></a><span data-ttu-id="65d23-102">-refonly (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="65d23-102">-refonly (Visual Basic)</span></span>

<span data-ttu-id="65d23-103">Параметр **-refonly** указывает, что основные выходные данные компиляции должны быть ссылочной сборкой, а не сборкой реализации.</span><span class="sxs-lookup"><span data-stu-id="65d23-103">The **-refonly** option indicates that the primary output of the compilation should be a reference assembly instead of an implementation assembly.</span></span> <span data-ttu-id="65d23-104">Параметр `-refonly` автоматически отключает вывод файлов PDB, так как базовые сборки не могут выполняться.</span><span class="sxs-lookup"><span data-stu-id="65d23-104">The `-refonly` parameter silently disables outputting PDBs, as reference assemblies cannot be executed.</span></span>

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]

## <a name="syntax"></a><span data-ttu-id="65d23-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="65d23-105">Syntax</span></span>

```console
-refonly
```

## <a name="remarks"></a><span data-ttu-id="65d23-106">Заметки</span><span class="sxs-lookup"><span data-stu-id="65d23-106">Remarks</span></span>

<span data-ttu-id="65d23-107">Visual Basic поддерживает параметр `-refonly`, начиная с версии 15,3.</span><span class="sxs-lookup"><span data-stu-id="65d23-107">Visual Basic supports the `-refonly` switch starting with version 15.3.</span></span>

<span data-ttu-id="65d23-108">Ссылочные сборки — это особый тип сборки, который содержит только минимальный объем метаданных, необходимых для представления поверхности общедоступного API библиотеки.</span><span class="sxs-lookup"><span data-stu-id="65d23-108">Reference assemblies are a special type of assembly that contain only the minimum amount of metadata required to represent the library's public API surface.</span></span> <span data-ttu-id="65d23-109">Они включают объявления для всех элементов, которые важны при ссылке на сборку в средствах сборки, но исключают все реализации членов и объявления закрытых членов, не имеющих наблюдаемого влияния на их контракт API.</span><span class="sxs-lookup"><span data-stu-id="65d23-109">They include declarations for all members that are significant when referencing an assembly in build tools, but exclude all member implementations and declarations of private members that have no observable impact on their API contract.</span></span> <span data-ttu-id="65d23-110">Дополнительные сведения см. в разделе Справочник по [сборкам](../../../standard/assembly/reference-assemblies.md) в .NET.</span><span class="sxs-lookup"><span data-stu-id="65d23-110">For more information, see [Reference assemblies](../../../standard/assembly/reference-assemblies.md) in .NET Guide.</span></span>

<span data-ttu-id="65d23-111">Параметры `-refonly` и [`-refout`](refout-compiler-option.md) являются взаимоисключающими.</span><span class="sxs-lookup"><span data-stu-id="65d23-111">The `-refonly` and [`-refout`](refout-compiler-option.md) options are mutually exclusive.</span></span>

## <a name="see-also"></a><span data-ttu-id="65d23-112">См. также</span><span class="sxs-lookup"><span data-stu-id="65d23-112">See also</span></span>

- [<span data-ttu-id="65d23-113">/refout</span><span class="sxs-lookup"><span data-stu-id="65d23-113">-refout</span></span>](refout-compiler-option.md)
- [<span data-ttu-id="65d23-114">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="65d23-114">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="65d23-115">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="65d23-115">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
