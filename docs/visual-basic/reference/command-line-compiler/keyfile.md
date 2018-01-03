---
title: /keyfile
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /keyfile compiler option [Visual Basic]
- keyfile compiler option [Visual Basic]
- -keyfile compiler option [Visual Basic]
ms.assetid: ffa82a4b-517a-4c6c-9889-5bae7b534bb8
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e0be7d230f16750395aaceb3c94539546716b8fd
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="keyfile"></a><span data-ttu-id="4421a-102">/keyfile</span><span class="sxs-lookup"><span data-stu-id="4421a-102">/keyfile</span></span>
<span data-ttu-id="4421a-103">Указывает файл, содержащий ключ или пару ключей, чтобы задать для сборки строгое имя.</span><span class="sxs-lookup"><span data-stu-id="4421a-103">Specifies a file containing a key or key pair to give an assembly a strong name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4421a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4421a-104">Syntax</span></span>  
  
```  
/keyfile:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="4421a-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="4421a-105">Arguments</span></span>  
 `file`  
 <span data-ttu-id="4421a-106">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="4421a-106">Required.</span></span> <span data-ttu-id="4421a-107">Файл, содержащий ключ.</span><span class="sxs-lookup"><span data-stu-id="4421a-107">File that contains the key.</span></span> <span data-ttu-id="4421a-108">Если имя файла содержит пробелы, заключите имя в кавычки (» «).</span><span class="sxs-lookup"><span data-stu-id="4421a-108">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4421a-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="4421a-109">Remarks</span></span>  
 <span data-ttu-id="4421a-110">Компилятор вставляет открытый ключ в манифест сборки, а затем подписывает окончательную сборку закрытым ключом.</span><span class="sxs-lookup"><span data-stu-id="4421a-110">The compiler inserts the public key into the assembly manifest and then signs the final assembly with the private key.</span></span> <span data-ttu-id="4421a-111">Чтобы создать файл ключа, введите `sn -k file` из командной строки.</span><span class="sxs-lookup"><span data-stu-id="4421a-111">To generate a key file, type `sn -k file` at the command line.</span></span> <span data-ttu-id="4421a-112">Дополнительные сведения см. в разделе [Sn.exe (средство строгих имен)][Sn.exe (средство строгих имен)](../../../framework/tools/sn-exe-strong-name-tool.md)).</span><span class="sxs-lookup"><span data-stu-id="4421a-112">For more information, see [Sn.exe (Strong Name Tool)][Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)).</span></span>  
  
 <span data-ttu-id="4421a-113">Если компиляция выполняется с `/target:module`, имя файла ключа сохраняется в модуле и включается в сборку, которая создается при компиляции с параметром [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).</span><span class="sxs-lookup"><span data-stu-id="4421a-113">If you compile with `/target:module`, the name of the key file is held in the module and incorporated into the assembly that is created when you compile an assembly with [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).</span></span>  
  
 <span data-ttu-id="4421a-114">Также можно передать сведения о шифровании компилятору с помощью параметра [/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md).</span><span class="sxs-lookup"><span data-stu-id="4421a-114">You can also pass your encryption information to the compiler with [/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md).</span></span> <span data-ttu-id="4421a-115">Если необходимо использовать частично подписанную сборку, применяйте параметр [/delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md).</span><span class="sxs-lookup"><span data-stu-id="4421a-115">Use [/delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md) if you want a partially signed assembly.</span></span>  
  
 <span data-ttu-id="4421a-116">Этот параметр можно также указать в качестве настраиваемого атрибута (<xref:System.Reflection.AssemblyKeyFileAttribute>) в исходном коде любого модуля промежуточного языка корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="4421a-116">You can also specify this option as a custom attribute (<xref:System.Reflection.AssemblyKeyFileAttribute>) in the source code for any Microsoft intermediate language module.</span></span>  
  
 <span data-ttu-id="4421a-117">В случае оба `/keyfile` и [/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) указаны (в командной строке или с помощью настраиваемого атрибута) в одной компиляции, компилятор сначала пытается контейнера ключей.</span><span class="sxs-lookup"><span data-stu-id="4421a-117">In case both `/keyfile` and [/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) are specified (either by command-line option or by custom attribute) in the same compilation, the compiler first tries the key container.</span></span> <span data-ttu-id="4421a-118">В случае успеха сборка подписывается данными контейнера ключей.</span><span class="sxs-lookup"><span data-stu-id="4421a-118">If that succeeds, then the assembly is signed with the information in the key container.</span></span> <span data-ttu-id="4421a-119">Если контейнер ключей не обнаружен, функция пытается найти файл, заданный параметром `/keyfile`.</span><span class="sxs-lookup"><span data-stu-id="4421a-119">If the compiler does not find the key container, it tries the file specified with `/keyfile`.</span></span> <span data-ttu-id="4421a-120">Если он завершается успешно, сборка подписывается данными из файла ключей и сведения о ключах устанавливается в контейнер ключей (аналогично `sn -i`) таким образом, при следующей компиляции контейнер ключей будет недопустимым.</span><span class="sxs-lookup"><span data-stu-id="4421a-120">If this succeeds, the assembly is signed with the information in the key file, and the key information is installed in the key container (similar to `sn -i`) so that on the next compilation, the key container will be valid.</span></span>  
  
 <span data-ttu-id="4421a-121">Обратите внимание, что файл ключей может содержать только открытый ключ.</span><span class="sxs-lookup"><span data-stu-id="4421a-121">Note that a key file might contain only the public key.</span></span>  
  
 <span data-ttu-id="4421a-122">В разделе [Создание и использование сборок](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) Дополнительные сведения о подписи сборки.</span><span class="sxs-lookup"><span data-stu-id="4421a-122">See [Creating and Using Strong-Named Assemblies](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) for more information on signing an assembly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4421a-123">`/keyfile` Параметр не доступен в [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] среде разработки; он доступен только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="4421a-123">The `/keyfile` option is not available from within the [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4421a-124">Пример</span><span class="sxs-lookup"><span data-stu-id="4421a-124">Example</span></span>  
 <span data-ttu-id="4421a-125">Следующий код компилирует исходный файл `Input.vb` и задает файл ключа.</span><span class="sxs-lookup"><span data-stu-id="4421a-125">The following code compiles source file `Input.vb` and specifies a key file.</span></span>  
  
```  
vbc /keyfile:myfile.sn input.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="4421a-126">См. также</span><span class="sxs-lookup"><span data-stu-id="4421a-126">See Also</span></span>  
 [<span data-ttu-id="4421a-127">Сборки и глобальный кэш сборок</span><span class="sxs-lookup"><span data-stu-id="4421a-127">Assemblies and the Global Assembly Cache</span></span>](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [<span data-ttu-id="4421a-128">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="4421a-128">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="4421a-129">/ Reference (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4421a-129">/reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)  
 [<span data-ttu-id="4421a-130">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="4421a-130">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
