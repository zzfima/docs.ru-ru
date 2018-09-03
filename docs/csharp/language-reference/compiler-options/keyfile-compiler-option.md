---
title: -keyfile (параметры компилятора C#)
ms.date: 07/20/2015
f1_keywords:
- /keyfile
helpviewer_keywords:
- /keyfile compiler option [C#]
- -keyfile compiler option [C#]
- keyfile compiler option [C#]
ms.assetid: 0815f9de-ace4-4e98-b4c6-13c55dea40c2
ms.openlocfilehash: 5e5ef095fbb982b0d37d7f44d4d57f27c20a72c1
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2018
ms.locfileid: "43400087"
---
# <a name="-keyfile-c-compiler-options"></a><span data-ttu-id="be989-102">-keyfile (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="be989-102">-keyfile (C# Compiler Options)</span></span>
<span data-ttu-id="be989-103">Задает имя файла, содержащего криптографический ключ.</span><span class="sxs-lookup"><span data-stu-id="be989-103">Specifies the filename containing the cryptographic key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be989-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="be989-104">Syntax</span></span>  
  
```console  
-keyfile:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="be989-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="be989-105">Arguments</span></span>  
  
|<span data-ttu-id="be989-106">Термин</span><span class="sxs-lookup"><span data-stu-id="be989-106">Term</span></span>|<span data-ttu-id="be989-107">Определение</span><span class="sxs-lookup"><span data-stu-id="be989-107">Definition</span></span>|  
|----------|----------------|  
|`file`|<span data-ttu-id="be989-108">Имя файла, содержащего ключ строгого имени.</span><span class="sxs-lookup"><span data-stu-id="be989-108">The name of the file containing the strong name key.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="be989-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="be989-109">Remarks</span></span>  
 <span data-ttu-id="be989-110">При использовании этого параметра компилятор вставляет открытый ключ из указанного файла в манифест сборки и затем подписывает окончательную сборку закрытым ключом.</span><span class="sxs-lookup"><span data-stu-id="be989-110">When this option is used, the compiler inserts the public key from the specified file into the assembly manifest and then signs the final assembly with the private key.</span></span> <span data-ttu-id="be989-111">Чтобы создать файл ключа, введите в командной строке sn -k `file`.</span><span class="sxs-lookup"><span data-stu-id="be989-111">To generate a key file, type sn -k `file` at the command line.</span></span>  
  
 <span data-ttu-id="be989-112">При компиляции с параметром **-target:module** имя файла ключа сохраняется в модуле и включается в сборку, создаваемую при компиляции с параметром [-addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="be989-112">If you compile with **-target:module**, the name of the key file is held in the module and incorporated into the assembly that is created when you compile an assembly with [-addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md).</span></span>  
  
 <span data-ttu-id="be989-113">Также можно передать сведения о шифровании компилятору с помощью параметра [-keycontainer](../../../csharp/language-reference/compiler-options/keycontainer-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="be989-113">You can also pass your encryption information to the compiler with [-keycontainer](../../../csharp/language-reference/compiler-options/keycontainer-compiler-option.md).</span></span> <span data-ttu-id="be989-114">Если требуется использовать частично подписанную сборку, применяйте параметр [-delaysign](../../../csharp/language-reference/compiler-options/delaysign-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="be989-114">Use [-delaysign](../../../csharp/language-reference/compiler-options/delaysign-compiler-option.md) if you want a partially signed assembly.</span></span>  
  
 <span data-ttu-id="be989-115">Если для одной процедуры компиляции одновременно заданы параметры -keyfile и -keycontainer (в командной строке или с помощью пользовательских атрибутов), то сначала будет предпринята попытка использовать контейнер ключей.</span><span class="sxs-lookup"><span data-stu-id="be989-115">In case both -keyfile and -keycontainer are specified (either by command line option or by custom attribute) in the same compilation, the compiler will first try the key container.</span></span> <span data-ttu-id="be989-116">В случае успеха сборка подписывается данными контейнера ключей.</span><span class="sxs-lookup"><span data-stu-id="be989-116">If that succeeds, then the assembly is signed with the information in the key container.</span></span> <span data-ttu-id="be989-117">Если компилятору не удалось обнаружить контейнер ключей, будет предпринята попытка использовать файл, заданный параметром -keyfile.</span><span class="sxs-lookup"><span data-stu-id="be989-117">If the compiler does not find the key container, it will try the file specified with -keyfile.</span></span> <span data-ttu-id="be989-118">В случае успеха сборка подписывается данными из файла ключей, и эти данные о ключах будут помещены в контейнер ключей (аналогично команде sn -i); таким образом, при следующей компиляции контейнер ключей будет действителен.</span><span class="sxs-lookup"><span data-stu-id="be989-118">If that succeeds, the assembly is signed with the information in the key file and the key information will be installed in the key container (similar to sn -i) so that on the next compilation, the key container will be valid.</span></span>  
  
 <span data-ttu-id="be989-119">Обратите внимание, что файл ключей может содержать только открытый ключ.</span><span class="sxs-lookup"><span data-stu-id="be989-119">Note that a key file might contain only the public key.</span></span>  
  
 <span data-ttu-id="be989-120">Дополнительные сведения см. в разделах [Создание и использование сборок со строгими именами](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) и [Отложенная подпись сборки](../../../framework/app-domains/delay-sign-assembly.md).</span><span class="sxs-lookup"><span data-stu-id="be989-120">For more information, see [Creating and Using Strong-Named Assemblies](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) and [Delay Signing an Assembly](../../../framework/app-domains/delay-sign-assembly.md).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="be989-121">Установка данного параметра компилятора в среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="be989-121">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="be989-122">Откройте страницу **свойств** для проекта.</span><span class="sxs-lookup"><span data-stu-id="be989-122">Open the **Properties** page for the project.</span></span>  
  
2.  <span data-ttu-id="be989-123">Выберите страницу свойств **Подпись**.</span><span class="sxs-lookup"><span data-stu-id="be989-123">Click the **Signing** property page.</span></span>  
  
3.  <span data-ttu-id="be989-124">Измените свойство **Выберите файл ключа строгого имени**.</span><span class="sxs-lookup"><span data-stu-id="be989-124">Modify the **Choose a strong name key file** property.</span></span>  
  
 <span data-ttu-id="be989-125">Программный доступ к этому параметру компилятора возможен с помощью свойства <xref:VSLangProj.ProjectProperties.AssemblyOriginatorKeyFile%2A>.</span><span class="sxs-lookup"><span data-stu-id="be989-125">You can programmatically access this compiler option with <xref:VSLangProj.ProjectProperties.AssemblyOriginatorKeyFile%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be989-126">См. также</span><span class="sxs-lookup"><span data-stu-id="be989-126">See Also</span></span>

- [<span data-ttu-id="be989-127">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="be989-127">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
- [<span data-ttu-id="be989-128">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="be989-128">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
