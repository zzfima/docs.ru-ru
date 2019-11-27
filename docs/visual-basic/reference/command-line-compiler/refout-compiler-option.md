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
# <a name="-refout-visual-basic"></a><span data-ttu-id="a8165-102">-RefOut (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a8165-102">-refout (Visual Basic)</span></span>

<span data-ttu-id="a8165-103">Параметр **-refout** указывает путь к файлу, в который нужно выводить базовую сборку.</span><span class="sxs-lookup"><span data-stu-id="a8165-103">The **-refout** option specifies a file path where the reference assembly should be output.</span></span>

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]

## <a name="syntax"></a><span data-ttu-id="a8165-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a8165-104">Syntax</span></span>

```console
-refout:filepath
```

## <a name="arguments"></a><span data-ttu-id="a8165-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="a8165-105">Arguments</span></span>

`filepath`  
<span data-ttu-id="a8165-106">Путь и имя файла ссылочной сборки.</span><span class="sxs-lookup"><span data-stu-id="a8165-106">The path and filename of the reference assembly.</span></span> <span data-ttu-id="a8165-107">Обычно он находится во вложенной папке основной сборки.</span><span class="sxs-lookup"><span data-stu-id="a8165-107">It should generally be in a sub-folder of the primary assembly.</span></span> <span data-ttu-id="a8165-108">Согласно рекомендуемому соглашению (используемому в MSBuild), базовую сборку следует помещать во вложенную папку ref/ относительно основной сборки.</span><span class="sxs-lookup"><span data-stu-id="a8165-108">The recommended convention (used by MSBuild) is to place the reference assembly in a "ref/" sub-folder relative to the primary assembly.</span></span> <span data-ttu-id="a8165-109">Все папки в `filepath` должны существовать; компилятор не создает их.</span><span class="sxs-lookup"><span data-stu-id="a8165-109">All folders in `filepath` must exist; the compiler does not create them.</span></span>

## <a name="remarks"></a><span data-ttu-id="a8165-110">Заметки</span><span class="sxs-lookup"><span data-stu-id="a8165-110">Remarks</span></span>

<span data-ttu-id="a8165-111">Visual Basic поддерживает параметр `-refout`, начиная с версии 15,3.</span><span class="sxs-lookup"><span data-stu-id="a8165-111">Visual Basic supports the `-refout` switch starting with version 15.3.</span></span>

<span data-ttu-id="a8165-112">Базовые сборки являются особым типом сборки, которая содержит только минимальный объем метаданных, необходимый для представления общедоступного API-интерфейса библиотеки.</span><span class="sxs-lookup"><span data-stu-id="a8165-112">Reference assemblies are a special type of assembly that contain only the minimum amount of metadata required to represent the library's public API surface.</span></span> <span data-ttu-id="a8165-113">Такие сборки включают в себя объявления для всех элементов, которые важны при указании ссылки на сборку в средствах сборки, но исключают все реализации элементов, а также объявления закрытых элементов, не имеющих наблюдаемого влияния на их контракт API.</span><span class="sxs-lookup"><span data-stu-id="a8165-113">They include declarations for all members that are significant when referencing an assembly in build tools, but exclude all member implementations and declarations of private members that have no observable impact on their API contract.</span></span> <span data-ttu-id="a8165-114">Дополнительные сведения см. в разделе [Базовые сборки](../../../standard/assembly/reference-assemblies.md) в руководстве по .NET.</span><span class="sxs-lookup"><span data-stu-id="a8165-114">For more information, see [Reference assemblies](../../../standard/assembly/reference-assemblies.md) in .NET Guide.</span></span>

<span data-ttu-id="a8165-115">Параметры `-refout` и [`-refonly`](refonly-compiler-option.md) являются взаимоисключающими.</span><span class="sxs-lookup"><span data-stu-id="a8165-115">The `-refout` and [`-refonly`](refonly-compiler-option.md) options are mutually exclusive.</span></span>

## <a name="see-also"></a><span data-ttu-id="a8165-116">См. также</span><span class="sxs-lookup"><span data-stu-id="a8165-116">See also</span></span>

- [<span data-ttu-id="a8165-117">/refonly</span><span class="sxs-lookup"><span data-stu-id="a8165-117">-refonly</span></span>](refonly-compiler-option.md)
- [<span data-ttu-id="a8165-118">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="a8165-118">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="a8165-119">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="a8165-119">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
