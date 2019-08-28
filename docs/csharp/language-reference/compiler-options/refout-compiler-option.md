---
title: -refout (параметры компилятора C#)
ms.date: 08/08/2017
f1_keywords:
- /refout
helpviewer_keywords:
- refout compiler option [C#]
- /refout compiler option [C#]
- -refout compiler option [C#]
ms.openlocfilehash: 97cbf540527d0449387b71bb1d97df95b6a4aba4
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2019
ms.locfileid: "69602505"
---
# <a name="-refout-c-compiler-options"></a><span data-ttu-id="cfa26-102">-refout (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="cfa26-102">-refout (C# Compiler Options)</span></span>

<span data-ttu-id="cfa26-103">Параметр **-refout** указывает путь к файлу, в который нужно выводить базовую сборку.</span><span class="sxs-lookup"><span data-stu-id="cfa26-103">The **-refout** option specifies a file path where the reference assembly should be output.</span></span> <span data-ttu-id="cfa26-104">В API Emit он преобразуется в `metadataPeStream`.</span><span class="sxs-lookup"><span data-stu-id="cfa26-104">This translates to `metadataPeStream` in the Emit API.</span></span> <span data-ttu-id="cfa26-105">Этот параметр соответствует свойству проекта [ProduceReferenceAssembly](/visualstudio/msbuild/common-msbuild-project-properties) в MSBuild.</span><span class="sxs-lookup"><span data-stu-id="cfa26-105">This option corresponds to the [ProduceReferenceAssembly](/visualstudio/msbuild/common-msbuild-project-properties) project property of MSBuild.</span></span>

## <a name="syntax"></a><span data-ttu-id="cfa26-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cfa26-106">Syntax</span></span>

```console
-refout:filepath
```

## <a name="arguments"></a><span data-ttu-id="cfa26-107">Аргументы</span><span class="sxs-lookup"><span data-stu-id="cfa26-107">Arguments</span></span>

 <span data-ttu-id="cfa26-108">`filepath` — путь к файлу базовой сборки.</span><span class="sxs-lookup"><span data-stu-id="cfa26-108">`filepath` The filepath for the reference assembly.</span></span> <span data-ttu-id="cfa26-109">Обычно он совпадает с путем к файлу основной сборки.</span><span class="sxs-lookup"><span data-stu-id="cfa26-109">It should generally match that of the primary assembly.</span></span> <span data-ttu-id="cfa26-110">Согласно рекомендуемому соглашению (используемому в MSBuild), базовую сборку следует помещать во вложенную папку ref/ относительно основной сборки.</span><span class="sxs-lookup"><span data-stu-id="cfa26-110">The recommended convention (used by MSBuild) is to place the reference assembly in a "ref/" sub-folder relative to the primary assembly.</span></span>

## <a name="remarks"></a><span data-ttu-id="cfa26-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="cfa26-111">Remarks</span></span>

<span data-ttu-id="cfa26-112">Тела методов в сборках, состоящих только из метаданных, заменяются одним телом `throw null`, но такие сборки включают все члены, кроме анонимных типов.</span><span class="sxs-lookup"><span data-stu-id="cfa26-112">Metadata-only assemblies have their method bodies replaced with a single `throw null` body, but include all members except anonymous types.</span></span> <span data-ttu-id="cfa26-113">Тело `throw null` используется для того, чтобы могло выполняться средство PEVerify для проверки полноты метаданных, что было бы невозможно при отсутствии тела.</span><span class="sxs-lookup"><span data-stu-id="cfa26-113">The reason for using `throw null` bodies (as opposed to no bodies) is so that PEVerify could run and pass (thus validating the completeness of the metadata).</span></span>

<span data-ttu-id="cfa26-114">Базовые сборки содержат атрибут `ReferenceAssembly` уровня сборки.</span><span class="sxs-lookup"><span data-stu-id="cfa26-114">Reference assemblies include an assembly-level `ReferenceAssembly` attribute.</span></span> <span data-ttu-id="cfa26-115">Этот атрибут может быть задан в исходном коде (в этом случае компилятору не требуется его синтезировать).</span><span class="sxs-lookup"><span data-stu-id="cfa26-115">This attribute may be specified in source (then the compiler won't need to synthesize it).</span></span> <span data-ttu-id="cfa26-116">Из-за этого атрибута среды выполнения не будут загружать базовые сборки для выполнения (однако они могут загружаться в режиме только для отражения).</span><span class="sxs-lookup"><span data-stu-id="cfa26-116">Because of this attribute, runtimes will refuse to load reference assemblies for execution (but they can still be loaded in reflection-only mode).</span></span> <span data-ttu-id="cfa26-117">Средства, выполняющие отражение сборок, должны загружать базовые сборки как доступные только для отражения. В противном случае от среды выполнения будет получена ошибка загрузки типа.</span><span class="sxs-lookup"><span data-stu-id="cfa26-117">Tools that reflect on assemblies need to ensure they load reference assemblies as reflection-only, otherwise they will receive a typeload error from the runtime.</span></span>

<span data-ttu-id="cfa26-118">Базовые сборки удаляют метаданные (закрытые члены) из сборок, содержащих только метаданные.</span><span class="sxs-lookup"><span data-stu-id="cfa26-118">Reference assemblies further remove metadata (private members) from metadata-only assemblies:</span></span>

- <span data-ttu-id="cfa26-119">Базовая сборка содержит ссылки только на необходимые компоненты в слое доступа API.</span><span class="sxs-lookup"><span data-stu-id="cfa26-119">A reference assembly only has references for what it needs in the API surface.</span></span> <span data-ttu-id="cfa26-120">Реальная сборка может иметь дополнительные ссылки, связанные с конкретной реализацией.</span><span class="sxs-lookup"><span data-stu-id="cfa26-120">The real assembly may have additional references related to specific implementations.</span></span> <span data-ttu-id="cfa26-121">Например, базовая сборка для `class C { private void M() { dynamic d = 1; ... } }` не ссылается на типы, требуемые для `dynamic`.</span><span class="sxs-lookup"><span data-stu-id="cfa26-121">For instance, the reference assembly for `class C { private void M() { dynamic d = 1; ... } }` does not reference any types required for `dynamic`.</span></span>
- <span data-ttu-id="cfa26-122">Закрытые функции-члены (методы, свойства и события) удаляются в случае, если их удаление не скажется заметно на компиляции.</span><span class="sxs-lookup"><span data-stu-id="cfa26-122">Private function-members (methods, properties, and events) are removed in cases where their removal doesn't observably impact compilation.</span></span> <span data-ttu-id="cfa26-123">Если нет атрибутов <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>, то же самое выполняется для внутренних функций-членов.</span><span class="sxs-lookup"><span data-stu-id="cfa26-123">If there are no <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attributes, do the same for internal function-members.</span></span>
- <span data-ttu-id="cfa26-124">Однако в базовых сборках сохраняются все типы (включая закрытые и вложенные).</span><span class="sxs-lookup"><span data-stu-id="cfa26-124">But all types (including private or nested types) are kept in reference assemblies.</span></span> <span data-ttu-id="cfa26-125">Сохраняются все атрибуты (даже внутренние).</span><span class="sxs-lookup"><span data-stu-id="cfa26-125">All attributes are kept (even internal ones).</span></span>
- <span data-ttu-id="cfa26-126">Сохраняются все виртуальные методы.</span><span class="sxs-lookup"><span data-stu-id="cfa26-126">All virtual methods are kept.</span></span> <span data-ttu-id="cfa26-127">Сохраняются явные реализации интерфейса.</span><span class="sxs-lookup"><span data-stu-id="cfa26-127">Explicit interface implementations are kept.</span></span> <span data-ttu-id="cfa26-128">Явно реализованные свойства и события сохраняются, так как их методы доступа являются виртуальными (и, следовательно, сохраняются).</span><span class="sxs-lookup"><span data-stu-id="cfa26-128">Explicitly implemented properties and events are kept, as their accessors are virtual (and are therefore kept).</span></span>
- <span data-ttu-id="cfa26-129">Сохраняются все поля структуры.</span><span class="sxs-lookup"><span data-stu-id="cfa26-129">All fields of a struct are kept.</span></span> <span data-ttu-id="cfa26-130">(Возможно, это будет изменено в версиях после C# 7.1.)</span><span class="sxs-lookup"><span data-stu-id="cfa26-130">(This is a candidate for post-C#-7.1 refinement)</span></span>

<span data-ttu-id="cfa26-131">Параметры `-refout` и [`-refonly`](refonly-compiler-option.md) являются взаимоисключающими.</span><span class="sxs-lookup"><span data-stu-id="cfa26-131">The `-refout` and [`-refonly`](refonly-compiler-option.md) options are mutually exclusive.</span></span>

## <a name="see-also"></a><span data-ttu-id="cfa26-132">См. также</span><span class="sxs-lookup"><span data-stu-id="cfa26-132">See also</span></span>

- [<span data-ttu-id="cfa26-133">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="cfa26-133">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="cfa26-134">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="cfa26-134">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
