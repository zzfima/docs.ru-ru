---
title: "-delaysign (параметры компилятора C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /delaysign
helpviewer_keywords:
- -delaysign compiler option [C#]
- delaysign compiler option [C#]
- /delaysign compiler option [C#]
ms.assetid: bcb058eb-2933-4e7f-b356-5c941db4de75
caps.latest.revision: "16"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 74cd4caaa134f881297134867018346c323deeab
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="-delaysign-c-compiler-options"></a><span data-ttu-id="22617-102">-delaysign (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="22617-102">-delaysign (C# Compiler Options)</span></span>
<span data-ttu-id="22617-103">Этот параметр указывает компилятору зарезервировать пространство в выходном файле, чтобы впоследствии добавить в него цифровую подпись.</span><span class="sxs-lookup"><span data-stu-id="22617-103">This option causes the compiler to reserve space in the output file so that a digital signature can be added later.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22617-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="22617-104">Syntax</span></span>  
  
```console  
-delaysign[ + | - ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="22617-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="22617-105">Arguments</span></span>  
 <span data-ttu-id="22617-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="22617-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="22617-107">Если требуется полностью подписанная сборка, используйте параметр **-delaysign-**.</span><span class="sxs-lookup"><span data-stu-id="22617-107">Use **-delaysign-** if you want a fully signed assembly.</span></span> <span data-ttu-id="22617-108">Если нужно лишь поместить в сборку открытый ключ, используйте параметр **-delaysign+**.</span><span class="sxs-lookup"><span data-stu-id="22617-108">Use **-delaysign+** if you only want to place the public key in the assembly.</span></span> <span data-ttu-id="22617-109">Значение по умолчанию — **-delaysign-**.</span><span class="sxs-lookup"><span data-stu-id="22617-109">The default is **-delaysign-**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="22617-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="22617-110">Remarks</span></span>  
 <span data-ttu-id="22617-111">Параметр **-delaysign** не оказывает никакого влияния, за исключением применения с [-keyfile](../../../csharp/language-reference/compiler-options/keyfile-compiler-option.md) или [-keycontainer](../../../csharp/language-reference/compiler-options/keycontainer-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="22617-111">The **-delaysign** option has no effect unless used with [/keyfile](../../../csharp/language-reference/compiler-options/keyfile-compiler-option.md) or [/keycontainer](../../../csharp/language-reference/compiler-options/keycontainer-compiler-option.md).</span></span>  
  
 <span data-ttu-id="22617-112">При запросе полностью подписанной сборки компилятор хэширует файл, содержащий манифест (метаданные сборки), и подписывает хэш закрытым ключом.</span><span class="sxs-lookup"><span data-stu-id="22617-112">When you request a fully signed assembly, the compiler hashes the file that contains the manifest (assembly metadata) and signs that hash with the private key.</span></span> <span data-ttu-id="22617-113">Итоговая цифровая подпись хранится в файле, содержащем манифест.</span><span class="sxs-lookup"><span data-stu-id="22617-113">The resulting digital signature is stored in the file that contains the manifest.</span></span> <span data-ttu-id="22617-114">При использовании отложенной подписи компилятор не вычисляет и не сохраняет подпись, а резервирует место в файле для добавления подписи в сборку в будущем.</span><span class="sxs-lookup"><span data-stu-id="22617-114">When an assembly is delay signed, the compiler does not compute and store the signature, but reserves space in the file so the signature can be added later.</span></span>  
  
 <span data-ttu-id="22617-115">Например, чтобы поместить сборку в глобальный кэш для тестирования, используйте параметр **-delaysign+**.</span><span class="sxs-lookup"><span data-stu-id="22617-115">For example, using **-delaysign+** allows a tester to put the assembly in the global cache.</span></span> <span data-ttu-id="22617-116">После тестирования можно полностью подписать сборку, поместив в нее закрытый ключ с помощью [компоновщика сборок](../../../framework/tools/al-exe-assembly-linker.md).</span><span class="sxs-lookup"><span data-stu-id="22617-116">After testing, you can fully sign the assembly by placing the private key in the assembly using the [Assembly Linker](../../../framework/tools/al-exe-assembly-linker.md) utility.</span></span>  
  
 <span data-ttu-id="22617-117">Дополнительные сведения см. в разделах [Создание и использование сборок со строгими именами](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) и [Отложенная подпись сборки](../../../framework/app-domains/delay-sign-assembly.md).</span><span class="sxs-lookup"><span data-stu-id="22617-117">For more information, see [Creating and Using Strong-Named Assemblies](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) and [Delay Signing an Assembly](../../../framework/app-domains/delay-sign-assembly.md).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="22617-118">Установка данного параметра компилятора в среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="22617-118">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="22617-119">Откройте страницу **свойств** для проекта.</span><span class="sxs-lookup"><span data-stu-id="22617-119">Open the **Properties** page for the project.</span></span>  
  
2.  <span data-ttu-id="22617-120">Измените свойство **Только отложенная подпись**.</span><span class="sxs-lookup"><span data-stu-id="22617-120">Modify the **Delay sign only** property.</span></span>  
  
 <span data-ttu-id="22617-121">Сведения об установке этого параметра компилятора программными средствами см. в разделе <xref:VSLangProj80.ProjectProperties3.DelaySign%2A>.</span><span class="sxs-lookup"><span data-stu-id="22617-121">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.DelaySign%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22617-122">См. также</span><span class="sxs-lookup"><span data-stu-id="22617-122">See Also</span></span>  
 [<span data-ttu-id="22617-123">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="22617-123">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="22617-124">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="22617-124">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
