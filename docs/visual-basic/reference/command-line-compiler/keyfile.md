---
title: -keyfile
ms.date: 03/10/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /keyfile compiler option [Visual Basic]
- keyfile compiler option [Visual Basic]
- -keyfile compiler option [Visual Basic]
ms.assetid: ffa82a4b-517a-4c6c-9889-5bae7b534bb8
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 319d01e8162dbc3806b0d9ba59e90410acb1acd5
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2018
---
# <a name="-keyfile"></a><span data-ttu-id="76d38-102">-keyfile</span><span class="sxs-lookup"><span data-stu-id="76d38-102">-keyfile</span></span>
<span data-ttu-id="76d38-103">Указывает файл, содержащий ключ или пару ключей, чтобы задать для сборки строгое имя.</span><span class="sxs-lookup"><span data-stu-id="76d38-103">Specifies a file containing a key or key pair to give an assembly a strong name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76d38-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="76d38-104">Syntax</span></span>  
  
``` 
-keyfile:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="76d38-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="76d38-105">Arguments</span></span>  
 `file`  
 <span data-ttu-id="76d38-106">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="76d38-106">Required.</span></span> <span data-ttu-id="76d38-107">Файл, содержащий ключ.</span><span class="sxs-lookup"><span data-stu-id="76d38-107">File that contains the key.</span></span> <span data-ttu-id="76d38-108">Если имя файла содержит пробелы, заключите имя в кавычки (» «).</span><span class="sxs-lookup"><span data-stu-id="76d38-108">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="76d38-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="76d38-109">Remarks</span></span>  
 <span data-ttu-id="76d38-110">Компилятор вставляет открытый ключ в манифест сборки, а затем подписывает окончательную сборку закрытым ключом.</span><span class="sxs-lookup"><span data-stu-id="76d38-110">The compiler inserts the public key into the assembly manifest and then signs the final assembly with the private key.</span></span> <span data-ttu-id="76d38-111">Чтобы создать файл ключа, введите `sn -k file` из командной строки.</span><span class="sxs-lookup"><span data-stu-id="76d38-111">To generate a key file, type `sn -k file` at the command line.</span></span> <span data-ttu-id="76d38-112">Дополнительные сведения см. в разделе [Sn.exe (средство строгих имен)][Sn.exe (средство строгих имен)](../../../framework/tools/sn-exe-strong-name-tool.md)).</span><span class="sxs-lookup"><span data-stu-id="76d38-112">For more information, see [Sn.exe (Strong Name Tool)][Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)).</span></span>  
  
 <span data-ttu-id="76d38-113">Если компиляция выполняется с `-target:module`, имя файла ключа сохраняется в модуле и включается в сборку, которая создается при компиляции с параметром [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).</span><span class="sxs-lookup"><span data-stu-id="76d38-113">If you compile with `-target:module`, the name of the key file is held in the module and incorporated into the assembly that is created when you compile an assembly with [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).</span></span>  
  
 <span data-ttu-id="76d38-114">Также можно передать сведения о шифровании компилятору с помощью параметра [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md).</span><span class="sxs-lookup"><span data-stu-id="76d38-114">You can also pass your encryption information to the compiler with [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md).</span></span> <span data-ttu-id="76d38-115">Если требуется использовать частично подписанную сборку, применяйте параметр [-delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md).</span><span class="sxs-lookup"><span data-stu-id="76d38-115">Use [-delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md) if you want a partially signed assembly.</span></span>  
  
 <span data-ttu-id="76d38-116">Этот параметр можно также указать в качестве настраиваемого атрибута (<xref:System.Reflection.AssemblyKeyFileAttribute>) в исходном коде любого модуля промежуточного языка корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="76d38-116">You can also specify this option as a custom attribute (<xref:System.Reflection.AssemblyKeyFileAttribute>) in the source code for any Microsoft intermediate language module.</span></span>  
  
 <span data-ttu-id="76d38-117">В случае оба `-keyfile` и [- keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) указаны (в командной строке или с помощью настраиваемого атрибута) в одной компиляции, компилятор сначала пытается контейнера ключей.</span><span class="sxs-lookup"><span data-stu-id="76d38-117">In case both `-keyfile` and [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) are specified (either by command-line option or by custom attribute) in the same compilation, the compiler first tries the key container.</span></span> <span data-ttu-id="76d38-118">В случае успеха сборка подписывается данными контейнера ключей.</span><span class="sxs-lookup"><span data-stu-id="76d38-118">If that succeeds, then the assembly is signed with the information in the key container.</span></span> <span data-ttu-id="76d38-119">Если контейнер ключей не обнаружен, функция пытается найти файл, заданный параметром `-keyfile`.</span><span class="sxs-lookup"><span data-stu-id="76d38-119">If the compiler does not find the key container, it tries the file specified with `-keyfile`.</span></span> <span data-ttu-id="76d38-120">Если он завершается успешно, сборка подписывается данными из файла ключей и сведения о ключах устанавливается в контейнер ключей (аналогично `sn -i`) таким образом, при следующей компиляции контейнер ключей будет недопустимым.</span><span class="sxs-lookup"><span data-stu-id="76d38-120">If this succeeds, the assembly is signed with the information in the key file, and the key information is installed in the key container (similar to `sn -i`) so that on the next compilation, the key container will be valid.</span></span>  
  
 <span data-ttu-id="76d38-121">Обратите внимание, что файл ключей может содержать только открытый ключ.</span><span class="sxs-lookup"><span data-stu-id="76d38-121">Note that a key file might contain only the public key.</span></span>  
  
 <span data-ttu-id="76d38-122">В разделе [Создание и использование сборок](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) Дополнительные сведения о подписи сборки.</span><span class="sxs-lookup"><span data-stu-id="76d38-122">See [Creating and Using Strong-Named Assemblies](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) for more information on signing an assembly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="76d38-123">`-keyfile` Параметр недоступен в среде разработки Visual Studio; она доступна только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="76d38-123">The `-keyfile` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="76d38-124">Пример</span><span class="sxs-lookup"><span data-stu-id="76d38-124">Example</span></span>  
 <span data-ttu-id="76d38-125">Следующий код компилирует исходный файл `Input.vb` и задает файл ключа.</span><span class="sxs-lookup"><span data-stu-id="76d38-125">The following code compiles source file `Input.vb` and specifies a key file.</span></span>  
  
```console  
vbc -keyfile:myfile.sn input.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="76d38-126">См. также</span><span class="sxs-lookup"><span data-stu-id="76d38-126">See Also</span></span>  
 [<span data-ttu-id="76d38-127">Сборки и глобальный кэш сборок</span><span class="sxs-lookup"><span data-stu-id="76d38-127">Assemblies and the Global Assembly Cache</span></span>](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [<span data-ttu-id="76d38-128">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="76d38-128">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="76d38-129">-ссылке (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="76d38-129">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)  
 [<span data-ttu-id="76d38-130">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="76d38-130">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
