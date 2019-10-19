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
# <a name="-refout-visual-basic"></a><span data-ttu-id="ca1c7-102">-RefOut (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ca1c7-102">-refout (Visual Basic)</span></span>

<span data-ttu-id="ca1c7-103">Параметр **-refout** указывает путь к файлу, в который нужно выводить базовую сборку.</span><span class="sxs-lookup"><span data-stu-id="ca1c7-103">The **-refout** option specifies a file path where the reference assembly should be output.</span></span>

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]

## <a name="syntax"></a><span data-ttu-id="ca1c7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ca1c7-104">Syntax</span></span>

```console
-refout:filepath
```

## <a name="arguments"></a><span data-ttu-id="ca1c7-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="ca1c7-105">Arguments</span></span>

`filepath`  
<span data-ttu-id="ca1c7-106">Путь и имя файла ссылочной сборки.</span><span class="sxs-lookup"><span data-stu-id="ca1c7-106">The path and filename of the reference assembly.</span></span> <span data-ttu-id="ca1c7-107">Обычно он находится во вложенной папке основной сборки.</span><span class="sxs-lookup"><span data-stu-id="ca1c7-107">It should generally be in a sub-folder of the primary assembly.</span></span> <span data-ttu-id="ca1c7-108">Согласно рекомендуемому соглашению (используемому в MSBuild), базовую сборку следует помещать во вложенную папку ref/ относительно основной сборки.</span><span class="sxs-lookup"><span data-stu-id="ca1c7-108">The recommended convention (used by MSBuild) is to place the reference assembly in a "ref/" sub-folder relative to the primary assembly.</span></span> <span data-ttu-id="ca1c7-109">Все папки в `filepath` должны существовать; компилятор не создает их.</span><span class="sxs-lookup"><span data-stu-id="ca1c7-109">All folders in `filepath` must exist; the compiler does not create them.</span></span>

## <a name="remarks"></a><span data-ttu-id="ca1c7-110">Заметки</span><span class="sxs-lookup"><span data-stu-id="ca1c7-110">Remarks</span></span>

<span data-ttu-id="ca1c7-111">Visual Basic поддерживает параметр `-refout`, начиная с версии 15,3.</span><span class="sxs-lookup"><span data-stu-id="ca1c7-111">Visual Basic supports the `-refout` switch starting with version 15.3.</span></span>

<span data-ttu-id="ca1c7-112">Ссылочные сборки — это сборки только метаданных, содержащие метаданные, но не имеющие кода реализации.</span><span class="sxs-lookup"><span data-stu-id="ca1c7-112">Reference assemblies are metadata-only assemblies that contain metadata but no implementation code.</span></span> <span data-ttu-id="ca1c7-113">Они включают сведения о типах и членах для всех, кроме анонимных типов.</span><span class="sxs-lookup"><span data-stu-id="ca1c7-113">They include type and member information for everything except anonymous types.</span></span> <span data-ttu-id="ca1c7-114">Текст их методов заменяется одной инструкцией `throw null`.</span><span class="sxs-lookup"><span data-stu-id="ca1c7-114">Their method bodies are replaced with a single `throw null` statement.</span></span> <span data-ttu-id="ca1c7-115">Причина использования тела метода `throw null` (в отличие от тела) заключается в том, что PEVerify может выполнять и передавать (таким образом проверяет полноту метаданных).</span><span class="sxs-lookup"><span data-stu-id="ca1c7-115">The reason for using `throw null` method bodies (as opposed to no bodies) is so that PEVerify can run and pass (thus validating the completeness of the metadata).</span></span>

<span data-ttu-id="ca1c7-116">Ссылочные сборки включают атрибут [референцеассембли](xref:System.Runtime.CompilerServices.ReferenceAssemblyAttribute) уровня сборки.</span><span class="sxs-lookup"><span data-stu-id="ca1c7-116">Reference assemblies include an assembly-level [ReferenceAssembly](xref:System.Runtime.CompilerServices.ReferenceAssemblyAttribute) attribute.</span></span> <span data-ttu-id="ca1c7-117">Этот атрибут может быть задан в исходном коде (в этом случае компилятору не требуется его синтезировать).</span><span class="sxs-lookup"><span data-stu-id="ca1c7-117">This attribute may be specified in source (then the compiler won't need to synthesize it).</span></span> <span data-ttu-id="ca1c7-118">Из-за этого атрибута среда выполнения отказывается загружать эталонные сборки для выполнения (но они по-прежнему могут загружаться в контексте только для отражения).</span><span class="sxs-lookup"><span data-stu-id="ca1c7-118">Because of this attribute, runtimes refuse to load reference assemblies for execution (but they can still be loaded in a reflection-only context).</span></span> <span data-ttu-id="ca1c7-119">Средства, отражающие сборки, должны обеспечивать загрузку эталонных сборок только отражением. в противном случае среда выполнения создает <xref:System.BadImageFormatException>.</span><span class="sxs-lookup"><span data-stu-id="ca1c7-119">Tools that reflect on assemblies need to ensure they load reference assemblies as reflection-only; otherwise, the runtime throws a <xref:System.BadImageFormatException>.</span></span>

<span data-ttu-id="ca1c7-120">Параметры `-refout` и [`-refonly`](refonly-compiler-option.md) являются взаимоисключающими.</span><span class="sxs-lookup"><span data-stu-id="ca1c7-120">The `-refout` and [`-refonly`](refonly-compiler-option.md) options are mutually exclusive.</span></span>

## <a name="see-also"></a><span data-ttu-id="ca1c7-121">См. также</span><span class="sxs-lookup"><span data-stu-id="ca1c7-121">See also</span></span>

- [<span data-ttu-id="ca1c7-122">/refonly</span><span class="sxs-lookup"><span data-stu-id="ca1c7-122">-refonly</span></span>](refonly-compiler-option.md)
- [<span data-ttu-id="ca1c7-123">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="ca1c7-123">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="ca1c7-124">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="ca1c7-124">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
