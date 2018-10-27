---
title: -refonly (Visual Basic)
ms.date: 03/16/2018
f1_keywords:
- -refonly
helpviewer_keywords:
- /refonly compiler option [Visual Basic]
- -refonly compiler option [Visual Basic]
- refonly compiler option [Visual Basic]
ms.openlocfilehash: b22fb9ae24a04d9fe530811bf764352199c31813
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50036064"
---
# <a name="-refonly-visual-basic"></a><span data-ttu-id="6ab7a-102">-refonly (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6ab7a-102">-refonly (Visual Basic)</span></span>

<span data-ttu-id="6ab7a-103">**- Refonly** параметр указывает, что основные выходные файлы компиляции ссылочную сборку, а не сборка реализации.</span><span class="sxs-lookup"><span data-stu-id="6ab7a-103">The **-refonly** option indicates that the primary output of the compilation should be a reference assembly instead of an implementation assembly.</span></span> <span data-ttu-id="6ab7a-104">Параметр `-refonly` автоматически отключает вывод файлов PDB, так как базовые сборки не могут выполняться.</span><span class="sxs-lookup"><span data-stu-id="6ab7a-104">The `-refonly` parameter silently disables outputting PDBs, as reference assemblies cannot be executed.</span></span>

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]

## <a name="syntax"></a><span data-ttu-id="6ab7a-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6ab7a-105">Syntax</span></span>

```console
-refonly
```

## <a name="remarks"></a><span data-ttu-id="6ab7a-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="6ab7a-106">Remarks</span></span>

<span data-ttu-id="6ab7a-107">Visual Basic поддерживает `-refout` переключения, начиная с версии 15.3.</span><span class="sxs-lookup"><span data-stu-id="6ab7a-107">Visual Basic supports the `-refout` switch starting with version 15.3.</span></span>

<span data-ttu-id="6ab7a-108">Ссылка сборки являются только метаданные, которые содержат метаданные, но без реализации их кода.</span><span class="sxs-lookup"><span data-stu-id="6ab7a-108">Reference assemblies are metadata-only assemblies that contain metadata but no implementation code.</span></span> <span data-ttu-id="6ab7a-109">Они включают сведения о типе и члене для всем, кроме анонимных типов.</span><span class="sxs-lookup"><span data-stu-id="6ab7a-109">They include type and member information for everything except anonymous types.</span></span> <span data-ttu-id="6ab7a-110">Тело `throw null` используется для того, чтобы могло выполняться средство PEVerify для проверки полноты метаданных, что было бы невозможно при отсутствии тела.</span><span class="sxs-lookup"><span data-stu-id="6ab7a-110">The reason for using `throw null` bodies (as opposed to no bodies) is so that PEVerify could run and pass (thus validating the completeness of the metadata).</span></span>

<span data-ttu-id="6ab7a-111">Базовые сборки содержат уровня сборки [ReferenceAssembly](xref:System.Runtime.CompilerServices.ReferenceAssemblyAttribute) атрибута.</span><span class="sxs-lookup"><span data-stu-id="6ab7a-111">Reference assemblies include an assembly-level [ReferenceAssembly](xref:System.Runtime.CompilerServices.ReferenceAssemblyAttribute) attribute.</span></span> <span data-ttu-id="6ab7a-112">Этот атрибут может быть задан в исходном коде (в этом случае компилятору не требуется его синтезировать).</span><span class="sxs-lookup"><span data-stu-id="6ab7a-112">This attribute may be specified in source (then the compiler won't need to synthesize it).</span></span> <span data-ttu-id="6ab7a-113">Из-за этого атрибута среды выполнения не будут загружать базовые сборки для выполнения (но по-прежнему могут быть загружены в контекст только для отражения).</span><span class="sxs-lookup"><span data-stu-id="6ab7a-113">Because of this attribute, runtimes will refuse to load reference assemblies for execution (but they can still be loaded in a reflection-only context).</span></span> <span data-ttu-id="6ab7a-114">Средства, выполняющие отражение сборок необходимо убедиться, что они загружать базовые сборки как предназначенный только для отражения; в противном случае среда выполнения создает <xref:System.BadImageFormatException>.</span><span class="sxs-lookup"><span data-stu-id="6ab7a-114">Tools that reflect on assemblies need to ensure they load reference assemblies as reflection-only; otherwise, the runtime throws a <xref:System.BadImageFormatException>.</span></span>

<span data-ttu-id="6ab7a-115">Параметры `-refonly` и [`-refout`](refout-compiler-option.md) являются взаимоисключающими.</span><span class="sxs-lookup"><span data-stu-id="6ab7a-115">The `-refonly` and [`-refout`](refout-compiler-option.md) options are mutually exclusive.</span></span>

## <a name="see-also"></a><span data-ttu-id="6ab7a-116">См. также</span><span class="sxs-lookup"><span data-stu-id="6ab7a-116">See also</span></span>
<span data-ttu-id="6ab7a-117">[-refout](refout-compiler-option.md) </span><span class="sxs-lookup"><span data-stu-id="6ab7a-117">[-refout](refout-compiler-option.md) </span></span>  
[<span data-ttu-id="6ab7a-118">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="6ab7a-118">Visual Basic Command-Line Compiler</span></span>](index.md)  
[<span data-ttu-id="6ab7a-119">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="6ab7a-119">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)   
