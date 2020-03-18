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
ms.openlocfilehash: bf271cc6b6887e930911071d4603b51daed55e61
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "70970258"
---
# <a name="-keyfile-c-compiler-options"></a><span data-ttu-id="a6726-102">-keyfile (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="a6726-102">-keyfile (C# Compiler Options)</span></span>
<span data-ttu-id="a6726-103">Задает имя файла, содержащего криптографический ключ.</span><span class="sxs-lookup"><span data-stu-id="a6726-103">Specifies the filename containing the cryptographic key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6726-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a6726-104">Syntax</span></span>  
  
```console  
-keyfile:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="a6726-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="a6726-105">Arguments</span></span>  
  
|<span data-ttu-id="a6726-106">Термин</span><span class="sxs-lookup"><span data-stu-id="a6726-106">Term</span></span>|<span data-ttu-id="a6726-107">Определение</span><span class="sxs-lookup"><span data-stu-id="a6726-107">Definition</span></span>|  
|----------|----------------|  
|`file`|<span data-ttu-id="a6726-108">Имя файла, содержащего ключ строгого имени.</span><span class="sxs-lookup"><span data-stu-id="a6726-108">The name of the file containing the strong name key.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a6726-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="a6726-109">Remarks</span></span>  
 <span data-ttu-id="a6726-110">При использовании этого параметра компилятор вставляет открытый ключ из указанного файла в манифест сборки и затем подписывает окончательную сборку закрытым ключом.</span><span class="sxs-lookup"><span data-stu-id="a6726-110">When this option is used, the compiler inserts the public key from the specified file into the assembly manifest and then signs the final assembly with the private key.</span></span> <span data-ttu-id="a6726-111">Чтобы создать файл ключа, введите в командной строке sn -k `file`.</span><span class="sxs-lookup"><span data-stu-id="a6726-111">To generate a key file, type sn -k `file` at the command line.</span></span>  
  
 <span data-ttu-id="a6726-112">При компиляции с параметром **-target:module** имя файла ключа сохраняется в модуле и включается в сборку, создаваемую при компиляции с параметром [-addmodule](./addmodule-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="a6726-112">If you compile with **-target:module**, the name of the key file is held in the module and incorporated into the assembly that is created when you compile an assembly with [-addmodule](./addmodule-compiler-option.md).</span></span>  
  
 <span data-ttu-id="a6726-113">Также можно передать сведения о шифровании компилятору с помощью параметра [-keycontainer](./keycontainer-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="a6726-113">You can also pass your encryption information to the compiler with [-keycontainer](./keycontainer-compiler-option.md).</span></span> <span data-ttu-id="a6726-114">Если требуется использовать частично подписанную сборку, применяйте параметр [-delaysign](./delaysign-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="a6726-114">Use [-delaysign](./delaysign-compiler-option.md) if you want a partially signed assembly.</span></span>  
  
 <span data-ttu-id="a6726-115">Если для одной процедуры компиляции одновременно заданы параметры -keyfile и -keycontainer (в командной строке или с помощью пользовательских атрибутов), то сначала будет предпринята попытка использовать контейнер ключей.</span><span class="sxs-lookup"><span data-stu-id="a6726-115">In case both -keyfile and -keycontainer are specified (either by command line option or by custom attribute) in the same compilation, the compiler will first try the key container.</span></span> <span data-ttu-id="a6726-116">В случае успеха сборка подписывается данными контейнера ключей.</span><span class="sxs-lookup"><span data-stu-id="a6726-116">If that succeeds, then the assembly is signed with the information in the key container.</span></span> <span data-ttu-id="a6726-117">Если компилятору не удалось обнаружить контейнер ключей, будет предпринята попытка использовать файл, заданный параметром -keyfile.</span><span class="sxs-lookup"><span data-stu-id="a6726-117">If the compiler does not find the key container, it will try the file specified with -keyfile.</span></span> <span data-ttu-id="a6726-118">В случае успеха сборка подписывается данными из файла ключей, и эти данные о ключах будут помещены в контейнер ключей (аналогично команде sn -i); таким образом, при следующей компиляции контейнер ключей будет действителен.</span><span class="sxs-lookup"><span data-stu-id="a6726-118">If that succeeds, the assembly is signed with the information in the key file and the key information will be installed in the key container (similar to sn -i) so that on the next compilation, the key container will be valid.</span></span>  
  
 <span data-ttu-id="a6726-119">Обратите внимание, что файл ключей может содержать только открытый ключ.</span><span class="sxs-lookup"><span data-stu-id="a6726-119">Note that a key file might contain only the public key.</span></span>  
  
 <span data-ttu-id="a6726-120">Дополнительные сведения см. в разделах [Создание и использование сборок со строгими именами](../../../standard/assembly/create-use-strong-named.md) и [Отложенная подпись сборки](../../../standard/assembly/delay-sign.md).</span><span class="sxs-lookup"><span data-stu-id="a6726-120">For more information, see [Creating and Using Strong-Named Assemblies](../../../standard/assembly/create-use-strong-named.md) and [Delay Signing an Assembly](../../../standard/assembly/delay-sign.md).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="a6726-121">Установка данного параметра компилятора в среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a6726-121">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="a6726-122">Откройте страницу **свойств** для проекта.</span><span class="sxs-lookup"><span data-stu-id="a6726-122">Open the **Properties** page for the project.</span></span>  
  
2. <span data-ttu-id="a6726-123">Выберите страницу свойств **Подпись**.</span><span class="sxs-lookup"><span data-stu-id="a6726-123">Click the **Signing** property page.</span></span>  
  
3. <span data-ttu-id="a6726-124">Измените свойство **Выберите файл ключа строгого имени**.</span><span class="sxs-lookup"><span data-stu-id="a6726-124">Modify the **Choose a strong name key file** property.</span></span>  
  
 <span data-ttu-id="a6726-125">Программный доступ к этому параметру компилятора возможен с помощью свойства <xref:VSLangProj.ProjectProperties.AssemblyOriginatorKeyFile%2A>.</span><span class="sxs-lookup"><span data-stu-id="a6726-125">You can programmatically access this compiler option with <xref:VSLangProj.ProjectProperties.AssemblyOriginatorKeyFile%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6726-126">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="a6726-126">See also</span></span>

- [<span data-ttu-id="a6726-127">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="a6726-127">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="a6726-128">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="a6726-128">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
