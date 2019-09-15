---
title: -keyfile
ms.date: 03/10/2018
helpviewer_keywords:
- /keyfile compiler option [Visual Basic]
- keyfile compiler option [Visual Basic]
- -keyfile compiler option [Visual Basic]
ms.assetid: ffa82a4b-517a-4c6c-9889-5bae7b534bb8
ms.openlocfilehash: 30b890cf3d523d1e33b433a1ff6109759bd9a5e3
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/13/2019
ms.locfileid: "70972331"
---
# <a name="-keyfile"></a><span data-ttu-id="6c492-102">-keyfile</span><span class="sxs-lookup"><span data-stu-id="6c492-102">-keyfile</span></span>
<span data-ttu-id="6c492-103">Указывает файл, содержащий ключ или пару ключей, чтобы задать для сборки строгое имя.</span><span class="sxs-lookup"><span data-stu-id="6c492-103">Specifies a file containing a key or key pair to give an assembly a strong name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c492-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6c492-104">Syntax</span></span>  
  
``` 
-keyfile:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="6c492-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="6c492-105">Arguments</span></span>  
 `file`  
 <span data-ttu-id="6c492-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="6c492-106">Required.</span></span> <span data-ttu-id="6c492-107">Файл, содержащий ключ.</span><span class="sxs-lookup"><span data-stu-id="6c492-107">File that contains the key.</span></span> <span data-ttu-id="6c492-108">Если имя файла содержит пробел, заключите его в кавычки ("").</span><span class="sxs-lookup"><span data-stu-id="6c492-108">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6c492-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="6c492-109">Remarks</span></span>  
 <span data-ttu-id="6c492-110">Компилятор вставляет открытый ключ в манифест сборки, а затем подписывает окончательную сборку закрытым ключом.</span><span class="sxs-lookup"><span data-stu-id="6c492-110">The compiler inserts the public key into the assembly manifest and then signs the final assembly with the private key.</span></span> <span data-ttu-id="6c492-111">Чтобы создать файл ключа, в командной строке введите `sn -k file`.</span><span class="sxs-lookup"><span data-stu-id="6c492-111">To generate a key file, type `sn -k file` at the command line.</span></span> <span data-ttu-id="6c492-112">Дополнительные сведения см. в разделе [Sn. exe (средство строгих имен)](../../../framework/tools/sn-exe-strong-name-tool.md).</span><span class="sxs-lookup"><span data-stu-id="6c492-112">For more information, see [Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)).</span></span>  
  
 <span data-ttu-id="6c492-113">При компиляции с `-target:module`параметром имя файла ключа сохраняется в модуле и включается в сборку, созданную при компиляции сборки с помощью [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).</span><span class="sxs-lookup"><span data-stu-id="6c492-113">If you compile with `-target:module`, the name of the key file is held in the module and incorporated into the assembly that is created when you compile an assembly with [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).</span></span>  
  
 <span data-ttu-id="6c492-114">Также можно передать сведения о шифровании компилятору с помощью параметра [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md).</span><span class="sxs-lookup"><span data-stu-id="6c492-114">You can also pass your encryption information to the compiler with [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md).</span></span> <span data-ttu-id="6c492-115">Если требуется использовать частично подписанную сборку, применяйте параметр [-delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md).</span><span class="sxs-lookup"><span data-stu-id="6c492-115">Use [-delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md) if you want a partially signed assembly.</span></span>  
  
 <span data-ttu-id="6c492-116">Этот параметр можно также указать в исходном коде любого модуля промежуточного языка Майкрософт в качестве настраиваемого атрибута (<xref:System.Reflection.AssemblyKeyFileAttribute>).</span><span class="sxs-lookup"><span data-stu-id="6c492-116">You can also specify this option as a custom attribute (<xref:System.Reflection.AssemblyKeyFileAttribute>) in the source code for any Microsoft intermediate language module.</span></span>  
  
 <span data-ttu-id="6c492-117">В случае, `-keyfile` если в той же компиляции заданы оба параметра и [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) (либо параметр командной строки, либо настраиваемый атрибут), компилятор сначала пытается попытаться контейнер ключей.</span><span class="sxs-lookup"><span data-stu-id="6c492-117">In case both `-keyfile` and [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) are specified (either by command-line option or by custom attribute) in the same compilation, the compiler first tries the key container.</span></span> <span data-ttu-id="6c492-118">В случае успеха сборка подписывается данными контейнера ключей.</span><span class="sxs-lookup"><span data-stu-id="6c492-118">If that succeeds, then the assembly is signed with the information in the key container.</span></span> <span data-ttu-id="6c492-119">Если компилятор не находит контейнер ключей, он пытается выполнить файл, указанный в параметре `-keyfile`.</span><span class="sxs-lookup"><span data-stu-id="6c492-119">If the compiler does not find the key container, it tries the file specified with `-keyfile`.</span></span> <span data-ttu-id="6c492-120">В случае успешности сборка подписывается данными из файла ключа, а сведения о ключах устанавливаются в контейнер ключей (аналогично `sn -i`), поэтому при следующей компиляции контейнер ключей будет действительным.</span><span class="sxs-lookup"><span data-stu-id="6c492-120">If this succeeds, the assembly is signed with the information in the key file, and the key information is installed in the key container (similar to `sn -i`) so that on the next compilation, the key container will be valid.</span></span>  
  
 <span data-ttu-id="6c492-121">Обратите внимание, что файл ключей может содержать только открытый ключ.</span><span class="sxs-lookup"><span data-stu-id="6c492-121">Note that a key file might contain only the public key.</span></span>  
  
 <span data-ttu-id="6c492-122">Дополнительные сведения о подписывании сборки см. в разделе [Создание и использование сборок со строгими именами](../../../standard/assembly/create-use-strong-named.md) .</span><span class="sxs-lookup"><span data-stu-id="6c492-122">See [Creating and Using Strong-Named Assemblies](../../../standard/assembly/create-use-strong-named.md) for more information on signing an assembly.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6c492-123">Этот `-keyfile` параметр недоступен в среде разработки Visual Studio; он доступен только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="6c492-123">The `-keyfile` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6c492-124">Пример</span><span class="sxs-lookup"><span data-stu-id="6c492-124">Example</span></span>  
 <span data-ttu-id="6c492-125">Следующий код компилирует исходный файл `Input.vb` и задает файл ключа.</span><span class="sxs-lookup"><span data-stu-id="6c492-125">The following code compiles source file `Input.vb` and specifies a key file.</span></span>  
  
```console  
vbc -keyfile:myfile.sn input.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="6c492-126">См. также</span><span class="sxs-lookup"><span data-stu-id="6c492-126">See also</span></span>

- [<span data-ttu-id="6c492-127">Сборки в .NET</span><span class="sxs-lookup"><span data-stu-id="6c492-127">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
- [<span data-ttu-id="6c492-128">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="6c492-128">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="6c492-129">-Reference (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6c492-129">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)
- [<span data-ttu-id="6c492-130">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="6c492-130">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
