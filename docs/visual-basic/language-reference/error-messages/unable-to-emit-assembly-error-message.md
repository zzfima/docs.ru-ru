---
title: "Не удается создать сборку: &lt;сообщение об ошибке&gt;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30145
- bc30145
helpviewer_keywords: BC30145
ms.assetid: 2e7eb2b9-eda6-4bdb-95cc-72c7f0be7528
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9dcf3d4bec379faa5783ca17847b91f9739df598
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="unable-to-emit-assembly-lterror-messagegt"></a><span data-ttu-id="bbec7-102">Не удается создать сборку: &lt;сообщение об ошибке&gt;</span><span class="sxs-lookup"><span data-stu-id="bbec7-102">Unable to emit assembly: &lt;error message&gt;</span></span>
<span data-ttu-id="bbec7-103">Компилятор [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] вызывает компоновщик сборок (Al.exe, который также называется Alink) для создания сборки с манифестом, при этом компоновщик сообщает об ошибке на этапе предварительного выпуска процедуры создания сборки.</span><span class="sxs-lookup"><span data-stu-id="bbec7-103">The [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler calls the Assembly Linker (Al.exe, also known as Alink) to generate an assembly with a manifest, with the linker reporting an error in the emission stage of creating the assembly.</span></span>  
  
 <span data-ttu-id="bbec7-104">**Идентификатор ошибки:** BC30145</span><span class="sxs-lookup"><span data-stu-id="bbec7-104">**Error ID:** BC30145</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="bbec7-105">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="bbec7-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="bbec7-106">Изучите приведенное сообщение об ошибке и обратитесь к разделу [Ошибки и предупреждения программы Al.exe](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b) , в котором содержатся дополнительные пояснения и рекомендации.</span><span class="sxs-lookup"><span data-stu-id="bbec7-106">Examine the quoted error message and consult the topic [Al.exe Tool Errors and Warnings](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b) for further explanation and advice.</span></span>  
  
2.  <span data-ttu-id="bbec7-107">Попробуйте подписать сборку вручную, используя либо [компоновщик сборок (Al.exe)](https://msdn.microsoft.com/library/c405shex) или [Sn.exe (средство строгих имен)](https://msdn.microsoft.com/library/k5b5tt23).</span><span class="sxs-lookup"><span data-stu-id="bbec7-107">Try signing the assembly manually, using either the [Al.exe (Assembly Linker)](https://msdn.microsoft.com/library/c405shex) or the [Sn.exe (Strong Name Tool)](https://msdn.microsoft.com/library/k5b5tt23).</span></span>  
  
3.  <span data-ttu-id="bbec7-108">Если ошибка не устранена, соберите сведения об условиях ее возникновения и уведомите службу технической поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="bbec7-108">If the error persists, gather information about the circumstances and notify Microsoft Product Support Services.</span></span>  
  
### <a name="to-sign-the-assembly-manually"></a><span data-ttu-id="bbec7-109">Подпись сборки вручную</span><span class="sxs-lookup"><span data-stu-id="bbec7-109">To sign the assembly manually</span></span>  
  
1.  <span data-ttu-id="bbec7-110">Используйте [Sn.exe (средство строгих имен)](https://msdn.microsoft.com/library/k5b5tt23) для создания файла пары открытого и закрытого ключей.</span><span class="sxs-lookup"><span data-stu-id="bbec7-110">Use the [Sn.exe (Strong Name Tool)](https://msdn.microsoft.com/library/k5b5tt23) to create a public/private key pair file.</span></span>  
  
     <span data-ttu-id="bbec7-111">Этот файл имеет расширение .SNK.</span><span class="sxs-lookup"><span data-stu-id="bbec7-111">This file has a .snk extension.</span></span>  
  
2.  <span data-ttu-id="bbec7-112">Удалите из проекта ссылку COM, вызывающую ошибку.</span><span class="sxs-lookup"><span data-stu-id="bbec7-112">Delete the COM reference that is generating the error from your project.</span></span>  
  
3.  <span data-ttu-id="bbec7-113">В окнах **запустить** последовательно выберите пункты **программы**, пункты **Microsoft Visual Studio 2008**, пункты **набора средств Visual Studio**, и Нажмите кнопку **Командная строка Visual Studio 2008**.</span><span class="sxs-lookup"><span data-stu-id="bbec7-113">From the Windows **Start** menu, point to **Programs**, point to **Microsoft Visual Studio 2008**, point to **Visual Studio Tools**, and then click **Visual Studio 2008 Command Prompt**.</span></span>  
  
4.  <span data-ttu-id="bbec7-114">Перейдите в каталог, куда хотите поместить программу-оболочку сборки.</span><span class="sxs-lookup"><span data-stu-id="bbec7-114">Move to the directory where you want to place your assembly wrapper.</span></span>  
  
5.  <span data-ttu-id="bbec7-115">Введите следующий код.</span><span class="sxs-lookup"><span data-stu-id="bbec7-115">Type the following code.</span></span>  
  
    ```  
    tlbimp <path to COM reference file> /out:<output assembly name> /keyfile:<path to .snk file>  
    ```  
  
     <span data-ttu-id="bbec7-116">Ниже приведен пример кода, который вы можете ввести.</span><span class="sxs-lookup"><span data-stu-id="bbec7-116">An example of the code you might enter would be the following.</span></span>  
  
    ```  
    tlbimp c:\windows\system32\msi.dll /out:Interop.WindowsInstaller.dll /keyfile:"c:\documents and settings\mykey.snk"  
    ```  
  
     <span data-ttu-id="bbec7-117">Используйте двойные кавычки ("), если путь или файл содержат пробелы.</span><span class="sxs-lookup"><span data-stu-id="bbec7-117">Use double quotation marks (") if a path or file contains spaces.</span></span>  
  
6.  <span data-ttu-id="bbec7-118">В [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] добавьте в созданный файл ссылку на сборку .NET.</span><span class="sxs-lookup"><span data-stu-id="bbec7-118">In [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)], add a .NET Assembly reference to the file you just created.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbec7-119">См. также</span><span class="sxs-lookup"><span data-stu-id="bbec7-119">See Also</span></span>  
 [<span data-ttu-id="bbec7-120">Al.exe (компоновщик сборок)</span><span class="sxs-lookup"><span data-stu-id="bbec7-120">Al.exe (Assembly Linker)</span></span>](https://msdn.microsoft.com/library/c405shex)  
 [<span data-ttu-id="bbec7-121">Ошибки и предупреждения программы Al.exe</span><span class="sxs-lookup"><span data-stu-id="bbec7-121">Al.exe Tool Errors and Warnings</span></span>](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b)  
 [<span data-ttu-id="bbec7-122">Sn.exe (средство строгих имен)</span><span class="sxs-lookup"><span data-stu-id="bbec7-122">Sn.exe (Strong Name Tool)</span></span>](https://msdn.microsoft.com/library/k5b5tt23)  
 [<span data-ttu-id="bbec7-123">Практическое руководство. Создание пары открытого и закрытого ключей</span><span class="sxs-lookup"><span data-stu-id="bbec7-123">How to: Create a Public-Private Key Pair</span></span>](http://msdn.microsoft.com/library/05026813-f3bd-4d7c-9e0b-fc588eb3d114)  
 [<span data-ttu-id="bbec7-124">Обращайтесь к нам</span><span class="sxs-lookup"><span data-stu-id="bbec7-124">Talk to Us</span></span>](/visualstudio/ide/talk-to-us)
