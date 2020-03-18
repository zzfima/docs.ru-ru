---
title: -delaysign (параметры компилятора C#)
ms.date: 05/15/2018
f1_keywords:
- /delaysign
helpviewer_keywords:
- -delaysign compiler option [C#]
- delaysign compiler option [C#]
- /delaysign compiler option [C#]
ms.assetid: bcb058eb-2933-4e7f-b356-5c941db4de75
ms.openlocfilehash: 9fdc02c22d9d8c8a709155e43a17ebf0d86dfd69
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "70970445"
---
# <a name="-delaysign-c-compiler-options"></a><span data-ttu-id="245fb-102">-delaysign (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="245fb-102">-delaysign (C# Compiler Options)</span></span>

<span data-ttu-id="245fb-103">Этот параметр указывает компилятору зарезервировать пространство в выходном файле, чтобы впоследствии добавить в него цифровую подпись.</span><span class="sxs-lookup"><span data-stu-id="245fb-103">This option causes the compiler to reserve space in the output file so that a digital signature can be added later.</span></span>

## <a name="syntax"></a><span data-ttu-id="245fb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="245fb-104">Syntax</span></span>

```console
-delaysign[ + | - ]
```

## <a name="arguments"></a><span data-ttu-id="245fb-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="245fb-105">Arguments</span></span>

<span data-ttu-id="245fb-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="245fb-106">`+` &#124; `-`</span></span>

<span data-ttu-id="245fb-107">Если требуется полностью подписанная сборка, используйте параметр **-delaysign-** .</span><span class="sxs-lookup"><span data-stu-id="245fb-107">Use **-delaysign-** if you want a fully signed assembly.</span></span> <span data-ttu-id="245fb-108">Если нужно лишь поместить в сборку открытый ключ, используйте параметр **-delaysign+** .</span><span class="sxs-lookup"><span data-stu-id="245fb-108">Use **-delaysign+** if you only want to place the public key in the assembly.</span></span> <span data-ttu-id="245fb-109">Значение по умолчанию — **-delaysign-** .</span><span class="sxs-lookup"><span data-stu-id="245fb-109">The default is **-delaysign-**.</span></span>

## <a name="remarks"></a><span data-ttu-id="245fb-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="245fb-110">Remarks</span></span>

<span data-ttu-id="245fb-111">Параметр **-delaysign** никак не действует, если не использовать его с [-keyfile](./keyfile-compiler-option.md) или [-keycontainer](./keycontainer-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="245fb-111">The **-delaysign** option has no effect unless used with [-keyfile](./keyfile-compiler-option.md) or [-keycontainer](./keycontainer-compiler-option.md).</span></span>

<span data-ttu-id="245fb-112">Параметры **-delaysign** и **-publicsign** — взаимоисключающие.</span><span class="sxs-lookup"><span data-stu-id="245fb-112">The **-delaysign** and **-publicsign** options are mutually exclusive.</span></span>

<span data-ttu-id="245fb-113">При запросе полностью подписанной сборки компилятор хэширует файл, содержащий манифест (метаданные сборки), и подписывает хэш закрытым ключом.</span><span class="sxs-lookup"><span data-stu-id="245fb-113">When you request a fully signed assembly, the compiler hashes the file that contains the manifest (assembly metadata) and signs that hash with the private key.</span></span> <span data-ttu-id="245fb-114">Эта операция предназначена для создания итоговой цифровой подписи, которая хранится в файле, содержащем манифест.</span><span class="sxs-lookup"><span data-stu-id="245fb-114">That operation creates a digital signature which is stored in the file that contains the manifest.</span></span> <span data-ttu-id="245fb-115">При использовании отложенной подписи компилятор не вычисляет и не сохраняет подпись, а резервирует место в файле для добавления подписи в сборку в будущем.</span><span class="sxs-lookup"><span data-stu-id="245fb-115">When an assembly is delay signed, the compiler does not compute and store the signature, but reserves space in the file so the signature can be added later.</span></span>

<span data-ttu-id="245fb-116">Например, чтобы поместить сборку в глобальный кэш для тестирования, используйте параметр **-delaysign+** .</span><span class="sxs-lookup"><span data-stu-id="245fb-116">For example, using **-delaysign+** allows a tester to put the assembly in the global cache.</span></span> <span data-ttu-id="245fb-117">После тестирования можно полностью подписать сборку, поместив в нее закрытый ключ с помощью [компоновщика сборок](../../../framework/tools/al-exe-assembly-linker.md).</span><span class="sxs-lookup"><span data-stu-id="245fb-117">After testing, you can fully sign the assembly by placing the private key in the assembly using the [Assembly Linker](../../../framework/tools/al-exe-assembly-linker.md) utility.</span></span>

<span data-ttu-id="245fb-118">Дополнительные сведения см. в разделах [Создание и использование сборок со строгими именами](../../../standard/assembly/create-use-strong-named.md) и [Отложенная подпись сборки](../../../standard/assembly/delay-sign.md).</span><span class="sxs-lookup"><span data-stu-id="245fb-118">For more information, see [Creating and Using Strong-Named Assemblies](../../../standard/assembly/create-use-strong-named.md) and [Delay Signing an Assembly](../../../standard/assembly/delay-sign.md).</span></span>

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="245fb-119">Установка данного параметра компилятора в среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="245fb-119">To set this compiler option in the Visual Studio development environment</span></span>

1. <span data-ttu-id="245fb-120">Откройте страницу **свойств** для проекта.</span><span class="sxs-lookup"><span data-stu-id="245fb-120">Open the **Properties** page for the project.</span></span>
1. <span data-ttu-id="245fb-121">Измените свойство **Только отложенная подпись**.</span><span class="sxs-lookup"><span data-stu-id="245fb-121">Modify the **Delay sign only** property.</span></span>

<span data-ttu-id="245fb-122">Сведения об установке этого параметра компилятора программными средствами см. в разделе <xref:VSLangProj80.ProjectProperties3.DelaySign%2A>.</span><span class="sxs-lookup"><span data-stu-id="245fb-122">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.DelaySign%2A>.</span></span>

## <a name="see-also"></a><span data-ttu-id="245fb-123">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="245fb-123">See also</span></span>

- [<span data-ttu-id="245fb-124">Параметр -publicsign в C#</span><span class="sxs-lookup"><span data-stu-id="245fb-124">C# -publicsign option</span></span>](publicsign-compiler-option.md)
- [<span data-ttu-id="245fb-125">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="245fb-125">C# Compiler Options</span></span>](index.md)
- [<span data-ttu-id="245fb-126">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="245fb-126">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
