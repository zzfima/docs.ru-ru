---
title: /keycontainer
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- -keycontainer compiler option [Visual Basic]
- keycontainer compiler option [Visual Basic]
- /keycontainer compiler option [Visual Basic]
ms.assetid: 6a9bc861-1752-4db1-9f64-b5252f0482cc
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3f7c5ffa255ba9ac2f062ea52eb3471659e0192b
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/09/2017
---
# <a name="keycontainer"></a><span data-ttu-id="d0652-102">/keycontainer</span><span class="sxs-lookup"><span data-stu-id="d0652-102">/keycontainer</span></span>
<span data-ttu-id="d0652-103">Указывает имя контейнера для пары ключей, чтобы задать для сборки строгое имя.</span><span class="sxs-lookup"><span data-stu-id="d0652-103">Specifies a key container name for a key pair to give an assembly a strong name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0652-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d0652-104">Syntax</span></span>  
  
```  
/keycontainer:container  
```  
  
## <a name="arguments"></a><span data-ttu-id="d0652-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="d0652-105">Arguments</span></span>  
  
|<span data-ttu-id="d0652-106">Термин</span><span class="sxs-lookup"><span data-stu-id="d0652-106">Term</span></span>|<span data-ttu-id="d0652-107">Определение</span><span class="sxs-lookup"><span data-stu-id="d0652-107">Definition</span></span>|  
|---|---|  
|`container`|<span data-ttu-id="d0652-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="d0652-108">Required.</span></span> <span data-ttu-id="d0652-109">Файл контейнера, содержащий ключ.</span><span class="sxs-lookup"><span data-stu-id="d0652-109">Container file that contains the key.</span></span> <span data-ttu-id="d0652-110">Заключите имя файла в кавычки ("»), если имя содержит пробелы.</span><span class="sxs-lookup"><span data-stu-id="d0652-110">Enclose the file name in quotation marks ("") if the name contains a space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d0652-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="d0652-111">Remarks</span></span>  
 <span data-ttu-id="d0652-112">Компилятор создает совместно используемый компонент путем вставки открытого ключа в манифест сборки и подписывая окончательную сборку закрытым ключом.</span><span class="sxs-lookup"><span data-stu-id="d0652-112">The compiler creates the sharable component by inserting a public key into the assembly manifest and by signing the final assembly with the private key.</span></span> <span data-ttu-id="d0652-113">Чтобы создать файл ключа, введите `sn -k``file` из командной строки.</span><span class="sxs-lookup"><span data-stu-id="d0652-113">To generate a key file, type `sn -k``file` at the command line.</span></span> <span data-ttu-id="d0652-114">`-i` Параметр устанавливает пару ключей в контейнер.</span><span class="sxs-lookup"><span data-stu-id="d0652-114">The `-i` option installs the key pair into a container.</span></span> <span data-ttu-id="d0652-115">Дополнительные сведения см. на странице [Sn.exe (Strong Name Tool)](https://msdn.microsoft.com/library/k5b5tt23) (Sn.exe: средство строгих имен).</span><span class="sxs-lookup"><span data-stu-id="d0652-115">For more information, see [Sn.exe (Strong Name Tool)](https://msdn.microsoft.com/library/k5b5tt23).</span></span>  
  
 <span data-ttu-id="d0652-116">Если компиляция выполняется с `/target:module`, имя файла ключа сохраняется в модуле и включается в сборку, которая создается при компиляции с параметром [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).</span><span class="sxs-lookup"><span data-stu-id="d0652-116">If you compile with `/target:module`, the name of the key file is held in the module and incorporated into the assembly that is created when you compile an assembly with [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).</span></span>  
  
 <span data-ttu-id="d0652-117">Этот параметр можно также указать в исходном коде любого модуля MSIL в качестве настраиваемого атрибута (<xref:System.Reflection.AssemblyKeyNameAttribute>).</span><span class="sxs-lookup"><span data-stu-id="d0652-117">You can also specify this option as a custom attribute (<xref:System.Reflection.AssemblyKeyNameAttribute>) in the source code for any Microsoft intermediate language (MSIL) module.</span></span>  
  
 <span data-ttu-id="d0652-118">Также можно передать сведения о шифровании компилятору с помощью параметра [/keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md).</span><span class="sxs-lookup"><span data-stu-id="d0652-118">You can also pass your encryption information to the compiler with [/keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md).</span></span> <span data-ttu-id="d0652-119">Если необходимо использовать частично подписанную сборку, применяйте параметр [/delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md).</span><span class="sxs-lookup"><span data-stu-id="d0652-119">Use [/delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md) if you want a partially signed assembly.</span></span>  
  
 <span data-ttu-id="d0652-120">В разделе [Создание и использование сборок](../../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md) Дополнительные сведения о подписи сборки.</span><span class="sxs-lookup"><span data-stu-id="d0652-120">See [Creating and Using Strong-Named Assemblies](../../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md) for more information on signing an assembly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d0652-121">`/keycontainer` Параметр недоступен в среде разработки Visual Studio; она доступна только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="d0652-121">The `/keycontainer` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d0652-122">Пример</span><span class="sxs-lookup"><span data-stu-id="d0652-122">Example</span></span>  
 <span data-ttu-id="d0652-123">Следующий код компилирует исходный файл `Input.vb` и указывает контейнер ключей.</span><span class="sxs-lookup"><span data-stu-id="d0652-123">The following code compiles source file `Input.vb` and specifies a key container.</span></span>  
  
```  
vbc /keycontainer:key1 input.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="d0652-124">См. также</span><span class="sxs-lookup"><span data-stu-id="d0652-124">See Also</span></span>  
 [<span data-ttu-id="d0652-125">Сборки и глобальный кэш сборок</span><span class="sxs-lookup"><span data-stu-id="d0652-125">Assemblies and the Global Assembly Cache</span></span>](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [<span data-ttu-id="d0652-126">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="d0652-126">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="d0652-127">/keyfile</span><span class="sxs-lookup"><span data-stu-id="d0652-127">/keyfile</span></span>](../../../visual-basic/reference/command-line-compiler/keyfile.md)  
 [<span data-ttu-id="d0652-128">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="d0652-128">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
