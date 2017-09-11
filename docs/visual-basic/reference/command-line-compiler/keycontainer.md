---
title: "/ keycontainer | Документы Microsoft"
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
- -keycontainer compiler option [Visual Basic]
- keycontainer compiler option [Visual Basic]
- /keycontainer compiler option [Visual Basic]
ms.assetid: 6a9bc861-1752-4db1-9f64-b5252f0482cc
caps.latest.revision: 16
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
ms.openlocfilehash: a783ef85e6ff2b7c6f889f809291ca8c275e709a
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="keycontainer"></a><span data-ttu-id="fea2b-102">/keycontainer</span><span class="sxs-lookup"><span data-stu-id="fea2b-102">/keycontainer</span></span>
<span data-ttu-id="fea2b-103">Указывает имя контейнера для пары ключей, чтобы задать для сборки строгое имя.</span><span class="sxs-lookup"><span data-stu-id="fea2b-103">Specifies a key container name for a key pair to give an assembly a strong name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fea2b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fea2b-104">Syntax</span></span>  
  
```  
/keycontainer:container  
```  
  
## <a name="arguments"></a><span data-ttu-id="fea2b-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="fea2b-105">Arguments</span></span>  
  
|<span data-ttu-id="fea2b-106">Термин</span><span class="sxs-lookup"><span data-stu-id="fea2b-106">Term</span></span>|<span data-ttu-id="fea2b-107">Определение</span><span class="sxs-lookup"><span data-stu-id="fea2b-107">Definition</span></span>|  
|---|---|  
|`container`|<span data-ttu-id="fea2b-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="fea2b-108">Required.</span></span> <span data-ttu-id="fea2b-109">Файл контейнера, содержащий ключ.</span><span class="sxs-lookup"><span data-stu-id="fea2b-109">Container file that contains the key.</span></span> <span data-ttu-id="fea2b-110">Заключите имя файла в кавычки ("»), если имя содержит пробелы.</span><span class="sxs-lookup"><span data-stu-id="fea2b-110">Enclose the file name in quotation marks ("") if the name contains a space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fea2b-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="fea2b-111">Remarks</span></span>  
 <span data-ttu-id="fea2b-112">Компилятор создает совместно используемый компонент, вставляя в манифест сборки открытый ключ и подписывая окончательную сборку закрытым ключом.</span><span class="sxs-lookup"><span data-stu-id="fea2b-112">The compiler creates the sharable component by inserting a public key into the assembly manifest and by signing the final assembly with the private key.</span></span> <span data-ttu-id="fea2b-113">Чтобы создать файл ключа, введите `sn -k``file` в командной строке.</span><span class="sxs-lookup"><span data-stu-id="fea2b-113">To generate a key file, type `sn -k``file` at the command line.</span></span> <span data-ttu-id="fea2b-114">`-i` Параметр устанавливает пару ключей в контейнер.</span><span class="sxs-lookup"><span data-stu-id="fea2b-114">The `-i` option installs the key pair into a container.</span></span> <span data-ttu-id="fea2b-115">Дополнительные сведения см. на странице [Sn.exe (Strong Name Tool)](https://msdn.microsoft.com/library/k5b5tt23) (Sn.exe: средство строгих имен).</span><span class="sxs-lookup"><span data-stu-id="fea2b-115">For more information, see [Sn.exe (Strong Name Tool)](https://msdn.microsoft.com/library/k5b5tt23).</span></span>  
  
 <span data-ttu-id="fea2b-116">Если компиляция выполняется с `/target:module`, имя файла ключа сохраняется в модуле и включается в сборку, созданный при компиляции с параметром [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).</span><span class="sxs-lookup"><span data-stu-id="fea2b-116">If you compile with `/target:module`, the name of the key file is held in the module and incorporated into the assembly that is created when you compile an assembly with [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).</span></span>  
  
 <span data-ttu-id="fea2b-117">Можно также указать этот параметр в качестве настраиваемого атрибута (<xref:System.Reflection.AssemblyKeyNameAttribute>) в исходном коде любого модуля промежуточного языка (MSIL) Microsoft.</xref:System.Reflection.AssemblyKeyNameAttribute></span><span class="sxs-lookup"><span data-stu-id="fea2b-117">You can also specify this option as a custom attribute (<xref:System.Reflection.AssemblyKeyNameAttribute>) in the source code for any Microsoft intermediate language (MSIL) module.</span></span>  
  
 <span data-ttu-id="fea2b-118">Сведения о шифровании можно также передать компилятору с [/keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md).</span><span class="sxs-lookup"><span data-stu-id="fea2b-118">You can also pass your encryption information to the compiler with [/keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md).</span></span> <span data-ttu-id="fea2b-119">Используйте [/delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md) Если частично подписанной сборки.</span><span class="sxs-lookup"><span data-stu-id="fea2b-119">Use [/delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md) if you want a partially signed assembly.</span></span>  
  
 <span data-ttu-id="fea2b-120">В разделе [Создание и использование сборок](https://msdn.microsoft.com/library/xwb8f617) Дополнительные сведения о подписи сборки.</span><span class="sxs-lookup"><span data-stu-id="fea2b-120">See [Creating and Using Strong-Named Assemblies](https://msdn.microsoft.com/library/xwb8f617) for more information on signing an assembly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fea2b-121">`/keycontainer` Параметр недоступен из среды разработки Visual Studio; она доступна только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="fea2b-121">The `/keycontainer` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fea2b-122">Пример</span><span class="sxs-lookup"><span data-stu-id="fea2b-122">Example</span></span>  
 <span data-ttu-id="fea2b-123">Следующий код компилирует исходный файл `Input.vb` и указывает контейнер ключей.</span><span class="sxs-lookup"><span data-stu-id="fea2b-123">The following code compiles source file `Input.vb` and specifies a key container.</span></span>  
  
```  
vbc /keycontainer:key1 input.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="fea2b-124">См. также</span><span class="sxs-lookup"><span data-stu-id="fea2b-124">See Also</span></span>  
 <span data-ttu-id="fea2b-125">[Сборки и глобальный кэш сборок](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span><span class="sxs-lookup"><span data-stu-id="fea2b-125">[Assemblies and the Global Assembly Cache](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span></span>  
<span data-ttu-id="fea2b-126"> [Компилятор командной строки Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="fea2b-126"> [Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="fea2b-127"> [/ keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md) </span><span class="sxs-lookup"><span data-stu-id="fea2b-127"> [/keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md) </span></span>  
<span data-ttu-id="fea2b-128"> [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="fea2b-128"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>
