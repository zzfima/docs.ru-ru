---
title: -refonly (параметры компилятора C#)
ms.date: 07/08/2017
f1_keywords:
- /refonly
helpviewer_keywords:
- /refonly compiler option [C#]
- -refonly compiler option [C#]
- refonly compiler option [C#]
ms.openlocfilehash: 856b65d3b2217dbe5d53ecda00723b47247d80a4
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2019
ms.locfileid: "72773856"
---
# <a name="-refonly-c-compiler-options"></a><span data-ttu-id="64cb0-102">-refonly (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="64cb0-102">-refonly (C# Compiler Options)</span></span>

<span data-ttu-id="64cb0-103">Параметр **-refonly** указывает на то, что в качестве основных выходных данных должна быть выведена базовая сборка, а не сборка реализации.</span><span class="sxs-lookup"><span data-stu-id="64cb0-103">The **-refonly** option indicates that a reference assembly should be output instead of an implementation assembly, as the primary output.</span></span> <span data-ttu-id="64cb0-104">Параметр `-refonly` автоматически отключает вывод файлов PDB, так как базовые сборки не могут выполняться.</span><span class="sxs-lookup"><span data-stu-id="64cb0-104">The `-refonly` parameter silently disables outputting PDBs, as reference assemblies cannot be executed.</span></span> <span data-ttu-id="64cb0-105">Этот параметр соответствует свойству проекта [ProduceOnlyReferenceAssembly](/visualstudio/msbuild/common-msbuild-project-properties) в MSBuild.</span><span class="sxs-lookup"><span data-stu-id="64cb0-105">This option corresponds to the [ProduceOnlyReferenceAssembly](/visualstudio/msbuild/common-msbuild-project-properties) project property of MSBuild.</span></span>

## <a name="syntax"></a><span data-ttu-id="64cb0-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="64cb0-106">Syntax</span></span>

```console
-refonly
```

## <a name="remarks"></a><span data-ttu-id="64cb0-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="64cb0-107">Remarks</span></span>

<span data-ttu-id="64cb0-108">Базовые сборки являются особым типом сборки, которая содержит только минимальный объем метаданных, необходимый для представления общедоступного API-интерфейса библиотеки.</span><span class="sxs-lookup"><span data-stu-id="64cb0-108">Reference assemblies are a special type of assembly that contain only the minimum amount of metadata required to represent the library's public API surface.</span></span> <span data-ttu-id="64cb0-109">Такие сборки включают в себя объявления для всех элементов, которые важны при указании ссылки на сборку в средствах сборки, но исключают все реализации элементов, а также объявления закрытых элементов, не имеющих наблюдаемого влияния на их контракт API.</span><span class="sxs-lookup"><span data-stu-id="64cb0-109">They include declarations for all members that are significant when referencing an assembly in build tools, but exclude all member implementations and declarations of private members that have no observable impact on their API contract.</span></span> <span data-ttu-id="64cb0-110">Дополнительные сведения см. в разделе [Базовые сборки](../../../standard/assembly/reference-assemblies.md) в руководстве по .NET.</span><span class="sxs-lookup"><span data-stu-id="64cb0-110">For more information, see [Reference assemblies](../../../standard/assembly/reference-assemblies.md) in .NET Guide.</span></span>

<span data-ttu-id="64cb0-111">Параметры `-refonly` и [`-refout`](refout-compiler-option.md) являются взаимоисключающими.</span><span class="sxs-lookup"><span data-stu-id="64cb0-111">The `-refonly` and [`-refout`](refout-compiler-option.md) options are mutually exclusive.</span></span>

## <a name="see-also"></a><span data-ttu-id="64cb0-112">См. также</span><span class="sxs-lookup"><span data-stu-id="64cb0-112">See also</span></span>

- [<span data-ttu-id="64cb0-113">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="64cb0-113">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="64cb0-114">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="64cb0-114">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
