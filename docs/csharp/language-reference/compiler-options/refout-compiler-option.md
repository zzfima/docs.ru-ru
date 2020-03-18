---
title: -refout (параметры компилятора C#)
ms.date: 08/08/2017
f1_keywords:
- /refout
helpviewer_keywords:
- refout compiler option [C#]
- /refout compiler option [C#]
- -refout compiler option [C#]
ms.openlocfilehash: f48316a1e6f657e3bd0190d269dfe0e875a833d9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "72771758"
---
# <a name="-refout-c-compiler-options"></a><span data-ttu-id="1e523-102">-refout (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="1e523-102">-refout (C# Compiler Options)</span></span>

<span data-ttu-id="1e523-103">Параметр **-refout** указывает путь к файлу, в который нужно выводить базовую сборку.</span><span class="sxs-lookup"><span data-stu-id="1e523-103">The **-refout** option specifies a file path where the reference assembly should be output.</span></span> <span data-ttu-id="1e523-104">В API Emit он преобразуется в `metadataPeStream`.</span><span class="sxs-lookup"><span data-stu-id="1e523-104">This translates to `metadataPeStream` in the Emit API.</span></span> <span data-ttu-id="1e523-105">Этот параметр соответствует свойству проекта [ProduceReferenceAssembly](/visualstudio/msbuild/common-msbuild-project-properties) в MSBuild.</span><span class="sxs-lookup"><span data-stu-id="1e523-105">This option corresponds to the [ProduceReferenceAssembly](/visualstudio/msbuild/common-msbuild-project-properties) project property of MSBuild.</span></span>

## <a name="syntax"></a><span data-ttu-id="1e523-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1e523-106">Syntax</span></span>

```console
-refout:filepath
```

## <a name="arguments"></a><span data-ttu-id="1e523-107">Аргументы</span><span class="sxs-lookup"><span data-stu-id="1e523-107">Arguments</span></span>

 <span data-ttu-id="1e523-108">`filepath` — путь к файлу базовой сборки.</span><span class="sxs-lookup"><span data-stu-id="1e523-108">`filepath` The filepath for the reference assembly.</span></span> <span data-ttu-id="1e523-109">Обычно он совпадает с путем к файлу основной сборки.</span><span class="sxs-lookup"><span data-stu-id="1e523-109">It should generally match that of the primary assembly.</span></span> <span data-ttu-id="1e523-110">Согласно рекомендуемому соглашению (используемому в MSBuild), базовую сборку следует помещать во вложенную папку ref/ относительно основной сборки.</span><span class="sxs-lookup"><span data-stu-id="1e523-110">The recommended convention (used by MSBuild) is to place the reference assembly in a "ref/" sub-folder relative to the primary assembly.</span></span>

## <a name="remarks"></a><span data-ttu-id="1e523-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="1e523-111">Remarks</span></span>

<span data-ttu-id="1e523-112">Базовые сборки являются особым типом сборки, которая содержит только минимальный объем метаданных, необходимый для представления общедоступного API-интерфейса библиотеки.</span><span class="sxs-lookup"><span data-stu-id="1e523-112">Reference assemblies are a special type of assembly that contain only the minimum amount of metadata required to represent the library's public API surface.</span></span> <span data-ttu-id="1e523-113">Такие сборки включают в себя объявления для всех элементов, которые важны при указании ссылки на сборку в средствах сборки, но исключают все реализации элементов, а также объявления закрытых элементов, не имеющих наблюдаемого влияния на их контракт API.</span><span class="sxs-lookup"><span data-stu-id="1e523-113">They include declarations for all members that are significant when referencing an assembly in build tools, but exclude all member implementations and declarations of private members that have no observable impact on their API contract.</span></span> <span data-ttu-id="1e523-114">Дополнительные сведения см. в разделе [Базовые сборки](../../../standard/assembly/reference-assemblies.md) в руководстве по .NET.</span><span class="sxs-lookup"><span data-stu-id="1e523-114">For more information, see [Reference assemblies](../../../standard/assembly/reference-assemblies.md) in .NET Guide.</span></span>

<span data-ttu-id="1e523-115">Параметры `-refout` и [`-refonly`](refonly-compiler-option.md) являются взаимоисключающими.</span><span class="sxs-lookup"><span data-stu-id="1e523-115">The `-refout` and [`-refonly`](refonly-compiler-option.md) options are mutually exclusive.</span></span>

## <a name="see-also"></a><span data-ttu-id="1e523-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="1e523-116">See also</span></span>

- [<span data-ttu-id="1e523-117">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="1e523-117">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="1e523-118">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="1e523-118">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
