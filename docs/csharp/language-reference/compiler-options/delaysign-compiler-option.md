---
title: "-delaysign (параметры компилятора C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /delaysign
dev_langs:
- CSharp
helpviewer_keywords:
- -delaysign compiler option [C#]
- delaysign compiler option [C#]
- /delaysign compiler option [C#]
ms.assetid: bcb058eb-2933-4e7f-b356-5c941db4de75
caps.latest.revision: 16
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: ce4c9fbb14081764985f3b02988dff9ee272c451
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="delaysign-c-compiler-options"></a><span data-ttu-id="87d9f-102">/delaysign (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="87d9f-102">/delaysign (C# Compiler Options)</span></span>
<span data-ttu-id="87d9f-103">Этот параметр указывает компилятору зарезервировать пространство в выходном файле, чтобы впоследствии добавить в него цифровую подпись.</span><span class="sxs-lookup"><span data-stu-id="87d9f-103">This option causes the compiler to reserve space in the output file so that a digital signature can be added later.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87d9f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="87d9f-104">Syntax</span></span>  
  
```console  
/delaysign[ + | - ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="87d9f-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="87d9f-105">Arguments</span></span>  
 <span data-ttu-id="87d9f-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="87d9f-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="87d9f-107">Если требуется полностью подписанная сборка, используйте **/delaysign-**.</span><span class="sxs-lookup"><span data-stu-id="87d9f-107">Use **/delaysign-** if you want a fully signed assembly.</span></span> <span data-ttu-id="87d9f-108">Если необходимо только поместить в сборку открытый ключ, используйте параметр **/delaysign+**.</span><span class="sxs-lookup"><span data-stu-id="87d9f-108">Use **/delaysign+** if you only want to place the public key in the assembly.</span></span> <span data-ttu-id="87d9f-109">Значение по умолчанию — **/delaysign-**.</span><span class="sxs-lookup"><span data-stu-id="87d9f-109">The default is **/delaysign-**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="87d9f-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="87d9f-110">Remarks</span></span>  
 <span data-ttu-id="87d9f-111">Параметр **/delaysign** не оказывает никакого влияния, за исключением применения с [/keyfile](../../../csharp/language-reference/compiler-options/keyfile-compiler-option.md) или [/keycontainer](../../../csharp/language-reference/compiler-options/keycontainer-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="87d9f-111">The **/delaysign** option has no effect unless used with [/keyfile](../../../csharp/language-reference/compiler-options/keyfile-compiler-option.md) or [/keycontainer](../../../csharp/language-reference/compiler-options/keycontainer-compiler-option.md).</span></span>  
  
 <span data-ttu-id="87d9f-112">При запросе полностью подписанной сборки компилятор хэширует файл, содержащий манифест (метаданные сборки), и подписывает хэш закрытым ключом.</span><span class="sxs-lookup"><span data-stu-id="87d9f-112">When you request a fully signed assembly, the compiler hashes the file that contains the manifest (assembly metadata) and signs that hash with the private key.</span></span> <span data-ttu-id="87d9f-113">Итоговая цифровая подпись хранится в файле, содержащем манифест.</span><span class="sxs-lookup"><span data-stu-id="87d9f-113">The resulting digital signature is stored in the file that contains the manifest.</span></span> <span data-ttu-id="87d9f-114">При использовании отложенной подписи компилятор не вычисляет и не сохраняет подпись, а резервирует место в файле для добавления подписи в сборку в будущем.</span><span class="sxs-lookup"><span data-stu-id="87d9f-114">When an assembly is delay signed, the compiler does not compute and store the signature, but reserves space in the file so the signature can be added later.</span></span>  
  
 <span data-ttu-id="87d9f-115">Например, чтобы поместить сборку в глобальный кэш для тестирования, используйте параметр **/delaysign+**.</span><span class="sxs-lookup"><span data-stu-id="87d9f-115">For example, using **/delaysign+** allows a tester to put the assembly in the global cache.</span></span> <span data-ttu-id="87d9f-116">После тестирования можно полностью подписать сборку, поместив в нее закрытый ключ с помощью [компоновщика сборок](https://msdn.microsoft.com/library/c405shex).</span><span class="sxs-lookup"><span data-stu-id="87d9f-116">After testing, you can fully sign the assembly by placing the private key in the assembly using the [Assembly Linker](https://msdn.microsoft.com/library/c405shex) utility.</span></span>  
  
 <span data-ttu-id="87d9f-117">Дополнительные сведения см. в разделах [Создание и использование сборок со строгими именами](https://msdn.microsoft.com/library/xwb8f617) и [Отложенная подпись сборки](../../../framework/app-domains/delay-sign-assembly.md).</span><span class="sxs-lookup"><span data-stu-id="87d9f-117">For more information, see [Creating and Using Strong-Named Assemblies](https://msdn.microsoft.com/library/xwb8f617) and [Delay Signing an Assembly](../../../framework/app-domains/delay-sign-assembly.md).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="87d9f-118">Установка данного параметра компилятора в среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="87d9f-118">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="87d9f-119">Откройте страницу **свойств** для проекта.</span><span class="sxs-lookup"><span data-stu-id="87d9f-119">Open the **Properties** page for the project.</span></span>  
  
2.  <span data-ttu-id="87d9f-120">Измените свойство **Только отложенная подпись**.</span><span class="sxs-lookup"><span data-stu-id="87d9f-120">Modify the **Delay sign only** property.</span></span>  
  
 <span data-ttu-id="87d9f-121">Сведения об установке этого параметра компилятора программными средствами см. в разделе <xref:VSLangProj80.ProjectProperties3.DelaySign%2A>.</span><span class="sxs-lookup"><span data-stu-id="87d9f-121">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.DelaySign%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87d9f-122">См. также</span><span class="sxs-lookup"><span data-stu-id="87d9f-122">See Also</span></span>  
 <span data-ttu-id="87d9f-123">[Параметры компилятора C#](../../../csharp/language-reference/compiler-options/index.md) </span><span class="sxs-lookup"><span data-stu-id="87d9f-123">[C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md) </span></span>  
 [<span data-ttu-id="87d9f-124">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="87d9f-124">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)

