---
title: "/ keyfile | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- /keyfile compiler option [Visual Basic]
- keyfile compiler option [Visual Basic]
- -keyfile compiler option [Visual Basic]
ms.assetid: ffa82a4b-517a-4c6c-9889-5bae7b534bb8
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: ec63fd990b8524bbc212a33714ec8380a8c99f32
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="keyfile"></a><span data-ttu-id="3f9c3-102">/keyfile</span><span class="sxs-lookup"><span data-stu-id="3f9c3-102">/keyfile</span></span>
<span data-ttu-id="3f9c3-103">Указывает файл, содержащий ключ или пару ключей, чтобы задать для сборки строгое имя.</span><span class="sxs-lookup"><span data-stu-id="3f9c3-103">Specifies a file containing a key or key pair to give an assembly a strong name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f9c3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3f9c3-104">Syntax</span></span>  
  
```  
/keyfile:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="3f9c3-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="3f9c3-105">Arguments</span></span>  
 `file`  
 <span data-ttu-id="3f9c3-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="3f9c3-106">Required.</span></span> <span data-ttu-id="3f9c3-107">Файл, содержащий ключ.</span><span class="sxs-lookup"><span data-stu-id="3f9c3-107">File that contains the key.</span></span> <span data-ttu-id="3f9c3-108">Если имя файла содержит пробел, заключите имя в кавычки (» «).</span><span class="sxs-lookup"><span data-stu-id="3f9c3-108">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3f9c3-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="3f9c3-109">Remarks</span></span>  
 <span data-ttu-id="3f9c3-110">Компилятор вставляет открытый ключ в манифест сборки и затем подписывает окончательную сборку закрытым ключом.</span><span class="sxs-lookup"><span data-stu-id="3f9c3-110">The compiler inserts the public key into the assembly manifest and then signs the final assembly with the private key.</span></span> <span data-ttu-id="3f9c3-111">Чтобы создать файл ключа, введите `sn -k file` в командной строке.</span><span class="sxs-lookup"><span data-stu-id="3f9c3-111">To generate a key file, type `sn -k file` at the command line.</span></span> <span data-ttu-id="3f9c3-112">Дополнительные сведения см. на странице [Sn.exe (Strong Name Tool)](https://msdn.microsoft.com/library/k5b5tt23) (Sn.exe: средство строгих имен).</span><span class="sxs-lookup"><span data-stu-id="3f9c3-112">For more information, see [Sn.exe (Strong Name Tool)](https://msdn.microsoft.com/library/k5b5tt23).</span></span>  
  
 <span data-ttu-id="3f9c3-113">Если компиляция выполняется с `/target:module`, имя файла ключа сохраняется в модуле и включается в сборку, созданный при компиляции с параметром [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).</span><span class="sxs-lookup"><span data-stu-id="3f9c3-113">If you compile with `/target:module`, the name of the key file is held in the module and incorporated into the assembly that is created when you compile an assembly with [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).</span></span>  
  
 <span data-ttu-id="3f9c3-114">Сведения о шифровании можно также передать компилятору с [/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md).</span><span class="sxs-lookup"><span data-stu-id="3f9c3-114">You can also pass your encryption information to the compiler with [/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md).</span></span> <span data-ttu-id="3f9c3-115">Используйте [/delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md) Если частично подписанной сборки.</span><span class="sxs-lookup"><span data-stu-id="3f9c3-115">Use [/delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md) if you want a partially signed assembly.</span></span>  
  
 <span data-ttu-id="3f9c3-116">Можно также указать этот параметр в качестве настраиваемого атрибута (<xref:System.Reflection.AssemblyKeyFileAttribute>) в исходном коде любого модуля промежуточного языка корпорации Майкрософт.</xref:System.Reflection.AssemblyKeyFileAttribute></span><span class="sxs-lookup"><span data-stu-id="3f9c3-116">You can also specify this option as a custom attribute (<xref:System.Reflection.AssemblyKeyFileAttribute>) in the source code for any Microsoft intermediate language module.</span></span>  
  
 <span data-ttu-id="3f9c3-117">В случае оба `/keyfile` и [/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) указаны (в командной строке или с помощью настраиваемого атрибута) в одной компиляции, компилятор сначала пытается использовать контейнер ключей.</span><span class="sxs-lookup"><span data-stu-id="3f9c3-117">In case both `/keyfile` and [/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) are specified (either by command-line option or by custom attribute) in the same compilation, the compiler first tries the key container.</span></span> <span data-ttu-id="3f9c3-118">В случае успеха сборка подписывается данными контейнера ключей.</span><span class="sxs-lookup"><span data-stu-id="3f9c3-118">If that succeeds, then the assembly is signed with the information in the key container.</span></span> <span data-ttu-id="3f9c3-119">Если компилятору не удается найти контейнер ключей, клиент пытается использовать файл, заданный параметром `/keyfile`.</span><span class="sxs-lookup"><span data-stu-id="3f9c3-119">If the compiler does not find the key container, it tries the file specified with `/keyfile`.</span></span> <span data-ttu-id="3f9c3-120">Если это завершается успешно, сборка подписывается данными из файла ключа и данные ключа устанавливается в контейнер ключей (аналогично `sn -i`) таким образом, при следующей компиляции контейнер ключей будет допустимым.</span><span class="sxs-lookup"><span data-stu-id="3f9c3-120">If this succeeds, the assembly is signed with the information in the key file, and the key information is installed in the key container (similar to `sn -i`) so that on the next compilation, the key container will be valid.</span></span>  
  
 <span data-ttu-id="3f9c3-121">Обратите внимание, что файл ключей может содержать только открытый ключ.</span><span class="sxs-lookup"><span data-stu-id="3f9c3-121">Note that a key file might contain only the public key.</span></span>  
  
 <span data-ttu-id="3f9c3-122">В разделе [Создание и использование сборок](https://msdn.microsoft.com/library/xwb8f617) Дополнительные сведения о подписи сборки.</span><span class="sxs-lookup"><span data-stu-id="3f9c3-122">See [Creating and Using Strong-Named Assemblies](https://msdn.microsoft.com/library/xwb8f617) for more information on signing an assembly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3f9c3-123">`/keyfile` Параметр не доступен в [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] среде разработки; он доступен только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="3f9c3-123">The `/keyfile` option is not available from within the [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3f9c3-124">Пример</span><span class="sxs-lookup"><span data-stu-id="3f9c3-124">Example</span></span>  
 <span data-ttu-id="3f9c3-125">Следующий код компилирует исходный файл `Input.vb` и задает файл ключа.</span><span class="sxs-lookup"><span data-stu-id="3f9c3-125">The following code compiles source file `Input.vb` and specifies a key file.</span></span>  
  
```  
vbc /keyfile:myfile.sn input.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="3f9c3-126">См. также</span><span class="sxs-lookup"><span data-stu-id="3f9c3-126">See Also</span></span>  
 <span data-ttu-id="3f9c3-127">[Сборки и глобальный кэш сборок](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span><span class="sxs-lookup"><span data-stu-id="3f9c3-127">[Assemblies and the Global Assembly Cache](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span></span>  
<span data-ttu-id="3f9c3-128"> [Компилятор командной строки Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="3f9c3-128"> [Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="3f9c3-129"> [/ Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) </span><span class="sxs-lookup"><span data-stu-id="3f9c3-129"> [/reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) </span></span>  
<span data-ttu-id="3f9c3-130"> [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="3f9c3-130"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>
