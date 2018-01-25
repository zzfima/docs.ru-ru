---
title: "-keycontainer (параметры компилятора C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /keycontainer
helpviewer_keywords:
- /keycontainer compiler option [C#]
- keycontainer compiler option [C#]
- -keycontainer compiler option [C#]
ms.assetid: b3982b6d-2382-4f7e-bebd-ce98eaa30763
caps.latest.revision: "17"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 944a9b4dbbed76f388642d67be9518343f750de5
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="-keycontainer-c-compiler-options"></a><span data-ttu-id="a224a-102">-keycontainer (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="a224a-102">-keycontainer (C# Compiler Options)</span></span>
<span data-ttu-id="a224a-103">Задает имя контейнера криптографического ключа.</span><span class="sxs-lookup"><span data-stu-id="a224a-103">Specifies the name of the cryptographic key container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a224a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a224a-104">Syntax</span></span>  
  
```console  
-keycontainer:string  
```  
  
## <a name="arguments"></a><span data-ttu-id="a224a-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="a224a-105">Arguments</span></span>  
 `string`  
 <span data-ttu-id="a224a-106">Имя контейнера ключа строгого имени.</span><span class="sxs-lookup"><span data-stu-id="a224a-106">The name of the strong name key container.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a224a-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="a224a-107">Remarks</span></span>  
 <span data-ttu-id="a224a-108">При использовании параметра **-keycontainer** компилятор создает компонент, который можно сделать общим, вставляя в манифест сборки открытый ключ из указанного контейнера и подписывая окончательную сборку закрытым ключом.</span><span class="sxs-lookup"><span data-stu-id="a224a-108">When the **-keycontainer** option is used, the compiler creates a sharable component by inserting a public key from the specified container into the assembly manifest and signing the final assembly with the private key.</span></span> <span data-ttu-id="a224a-109">Чтобы создать файл ключа, введите в командной строке sn -k `file`.</span><span class="sxs-lookup"><span data-stu-id="a224a-109">To generate a key file, type sn -k `file` at the command line.</span></span> <span data-ttu-id="a224a-110">Параметр sn -i устанавливает пару ключей в контейнер.</span><span class="sxs-lookup"><span data-stu-id="a224a-110">sn -i installs the key pair into a container.</span></span>  
  
 <span data-ttu-id="a224a-111">При компиляции с параметром [-target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md) имя файла ключа сохраняется в модуле и включается в сборку при компиляции этого модуля с параметром [-addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="a224a-111">If you compile with [-target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md), the name of the key file is held in the module and incorporated into the assembly when you compile this module into an assembly with [-addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md).</span></span>  
  
 <span data-ttu-id="a224a-112">Этот параметр можно также указать в исходном коде любого модуля MSIL в качестве настраиваемого атрибута (<xref:System.Reflection.AssemblyKeyNameAttribute?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="a224a-112">You can also specify this option as a custom attribute (<xref:System.Reflection.AssemblyKeyNameAttribute?displayProperty=nameWithType>) in the source code for any Microsoft intermediate language (MSIL) module.</span></span>  
  
 <span data-ttu-id="a224a-113">Также можно передать сведения о шифровании компилятору с помощью параметра [-keyfile](../../../csharp/language-reference/compiler-options/keyfile-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="a224a-113">You can also pass your encryption information to the compiler with [-keyfile](../../../csharp/language-reference/compiler-options/keyfile-compiler-option.md).</span></span> <span data-ttu-id="a224a-114">Если нужно добавить в манифест сборки открытый ключ, но при этом отложить подпись сборки до завершения ее тестирования, используйте параметр [-delaysign](../../../csharp/language-reference/compiler-options/delaysign-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="a224a-114">Use [-delaysign](../../../csharp/language-reference/compiler-options/delaysign-compiler-option.md) if you want the public key added to the assembly manifest but want to delay signing the assembly until it has been tested.</span></span>  
  
 <span data-ttu-id="a224a-115">Дополнительные сведения см. в разделах [Создание и использование сборок со строгими именами](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) и [Отложенная подпись сборки](../../../framework/app-domains/delay-sign-assembly.md).</span><span class="sxs-lookup"><span data-stu-id="a224a-115">For more information, see [Creating and Using Strong-Named Assemblies](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) and [Delay Signing an Assembly](../../../framework/app-domains/delay-sign-assembly.md).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="a224a-116">Установка данного параметра компилятора в среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a224a-116">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="a224a-117">Данный параметр компилятора недоступен в среде разработки Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a224a-117">This compiler option is not available in the Visual Studio development environment.</span></span>  
  
 <span data-ttu-id="a224a-118">Программный доступ к этому параметру компилятора возможен с помощью свойства <xref:VSLangProj.ProjectProperties.AssemblyKeyContainerName%2A>.</span><span class="sxs-lookup"><span data-stu-id="a224a-118">You can programmatically access this compiler option with <xref:VSLangProj.ProjectProperties.AssemblyKeyContainerName%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a224a-119">См. также</span><span class="sxs-lookup"><span data-stu-id="a224a-119">See Also</span></span>  
 [<span data-ttu-id="a224a-120">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="a224a-120">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="a224a-121">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="a224a-121">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
