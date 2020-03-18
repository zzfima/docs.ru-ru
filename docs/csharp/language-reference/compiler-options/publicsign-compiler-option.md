---
title: -publicsign (параметры компилятора C#)
ms.date: 05/15/2018
f1_keywords:
- /publicsign
helpviewer_keywords:
- -publicsign compiler option [C#]
- publicsign compiler option [C#]
- /publicsign compiler option [C#]
ms.openlocfilehash: de7d9c98b0f279b52bc93711c5b986a2b2e57215
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "61662534"
---
# <a name="-publicsign-c-compiler-options"></a><span data-ttu-id="f34d3-102">-publicsign (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="f34d3-102">-publicsign (C# Compiler Options)</span></span>

<span data-ttu-id="f34d3-103">Этот параметр указывает компилятору на необходимость применения открытого ключа, но фактически не подписывает сборку.</span><span class="sxs-lookup"><span data-stu-id="f34d3-103">This option causes the compiler to apply a public key but does not actually sign the assembly.</span></span> <span data-ttu-id="f34d3-104">Кроме того, параметр **-publicsign** задает в сборке бит, который сообщает среде выполнения, что файл подписан.</span><span class="sxs-lookup"><span data-stu-id="f34d3-104">The **-publicsign** option also sets a bit in the assembly that tells the runtime that the file is actually signed.</span></span>

## <a name="syntax"></a><span data-ttu-id="f34d3-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f34d3-105">Syntax</span></span>

```console
-publicsign
```

## <a name="arguments"></a><span data-ttu-id="f34d3-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="f34d3-106">Arguments</span></span>

<span data-ttu-id="f34d3-107">Нет.</span><span class="sxs-lookup"><span data-stu-id="f34d3-107">None.</span></span>

## <a name="remarks"></a><span data-ttu-id="f34d3-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="f34d3-108">Remarks</span></span>

<span data-ttu-id="f34d3-109">С параметром **-publicsign** необходимо использовать параметр [-keyfile](keyfile-compiler-option.md) или [-keycontainer](keycontainer-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="f34d3-109">The **-publicsign** option requires the use of the [-keyfile](keyfile-compiler-option.md) or [-keycontainer](keycontainer-compiler-option.md).</span></span> <span data-ttu-id="f34d3-110">Каждый из параметров **keyfile** и **keycontainer** определяет открытый ключ.</span><span class="sxs-lookup"><span data-stu-id="f34d3-110">The **keyfile** or **keycontainer** options specify the public key.</span></span>

<span data-ttu-id="f34d3-111">Параметры **-publicsign** и **-delaysign** — взаимоисключающие.</span><span class="sxs-lookup"><span data-stu-id="f34d3-111">The **-publicsign** and **-delaysign** options are mutually exclusive.</span></span>

<span data-ttu-id="f34d3-112">При таком подписывании в сборку добавляется открытый ключ. Кроме того, в сборке устанавливается флаг "подписано", хотя фактически сборка не подписывается закрытым ключом. Такой подход иногда называют "фиктивным подписыванием" или "подписыванием OSS".</span><span class="sxs-lookup"><span data-stu-id="f34d3-112">Sometimes called "fake sign" or "OSS sign", public signing includes the public key in an output assembly and sets the "signed" flag, but doesn't actually sign the assembly with a private key.</span></span> <span data-ttu-id="f34d3-113">Он полезен на проектах с открытым исходным кодом: людям нужно создавать сборки, которые будут совместимы с выпущенными "полностью подписанными" сборками, но у них нет доступа к закрытому ключу, который использовался для подписывания сборок.</span><span class="sxs-lookup"><span data-stu-id="f34d3-113">This is useful for open source projects where people want to build assemblies which are compatible with the released "fully signed" assemblies, but don't have access to the private key used to sign the assemblies.</span></span> <span data-ttu-id="f34d3-114">Так как потребителям практически никогда не нужно проверять, полностью ли подписана сборка, создаваемые сообществами сборки можно использовать практические во всех случаях, в которых может использоваться полностью подписанная сборка.</span><span class="sxs-lookup"><span data-stu-id="f34d3-114">Since almost no consumers actually need to check if the assembly is fully signed, these publicly built assemblies are useable in almost every scenario where the fully signed one would be used.</span></span>

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="f34d3-115">Установка данного параметра компилятора в среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f34d3-115">To set this compiler option in the Visual Studio development environment</span></span>

1. <span data-ttu-id="f34d3-116">Откройте страницу **свойств** для проекта.</span><span class="sxs-lookup"><span data-stu-id="f34d3-116">Open the **Properties** page for the project.</span></span>
1. <span data-ttu-id="f34d3-117">Измените свойство **Только отложенная подпись**.</span><span class="sxs-lookup"><span data-stu-id="f34d3-117">Modify the **Delay sign only** property.</span></span>

## <a name="see-also"></a><span data-ttu-id="f34d3-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f34d3-118">See also</span></span>

- [<span data-ttu-id="f34d3-119">-delaysign (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="f34d3-119">C# Compiler -delaysign option</span></span>](delaysign-compiler-option.md)
- [<span data-ttu-id="f34d3-120">-keyfile (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="f34d3-120">C# Compiler -keyfile option</span></span>](keyfile-compiler-option.md)
- [<span data-ttu-id="f34d3-121">-keycontainer (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="f34d3-121">C# Compiler -keycontainer option</span></span>](keycontainer-compiler-option.md)
- [<span data-ttu-id="f34d3-122">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="f34d3-122">C# Compiler Options</span></span>](index.md)
- [<span data-ttu-id="f34d3-123">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="f34d3-123">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
