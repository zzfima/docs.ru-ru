---
title: "Не удается выпустить сборку: &lt;сообщение об ошибке&gt; | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30145
- bc30145
dev_langs:
- VB
helpviewer_keywords:
- BC30145
ms.assetid: 2e7eb2b9-eda6-4bdb-95cc-72c7f0be7528
caps.latest.revision: 11
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
ms.openlocfilehash: d15981a1a2fb31ba377066fa421f5a9979d47a12
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="unable-to-emit-assembly-lterror-messagegt"></a><span data-ttu-id="bdef4-102">Не удается выпустить сборку: &lt;сообщение об ошибке&gt;</span><span class="sxs-lookup"><span data-stu-id="bdef4-102">Unable to emit assembly: &lt;error message&gt;</span></span>
<span data-ttu-id="bdef4-103">Компилятор [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] вызывает компоновщик сборок (Al.exe, который также называется Alink) для создания сборки с манифестом, при этом компоновщик сообщает об ошибке на этапе предварительного выпуска процедуры создания сборки.</span><span class="sxs-lookup"><span data-stu-id="bdef4-103">The [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler calls the Assembly Linker (Al.exe, also known as Alink) to generate an assembly with a manifest, with the linker reporting an error in the emission stage of creating the assembly.</span></span>  
  
 <span data-ttu-id="bdef4-104">**Идентификатор ошибки:** BC30145</span><span class="sxs-lookup"><span data-stu-id="bdef4-104">**Error ID:** BC30145</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="bdef4-105">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="bdef4-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="bdef4-106">Просмотрите сообщение об ошибке и обратитесь к разделу [Al.exe ошибки и предупреждения средства](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b) для пояснения и рекомендации.</span><span class="sxs-lookup"><span data-stu-id="bdef4-106">Examine the quoted error message and consult the topic [Al.exe Tool Errors and Warnings](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b) for further explanation and advice.</span></span>  
  
2.  <span data-ttu-id="bdef4-107">Попробуйте подписать сборку вручную, используя [компоновщик сборок (Al.exe)](https://msdn.microsoft.com/library/c405shex) или [Sn.exe (средство строгих имен)](https://msdn.microsoft.com/library/k5b5tt23).</span><span class="sxs-lookup"><span data-stu-id="bdef4-107">Try signing the assembly manually, using either the [Al.exe (Assembly Linker)](https://msdn.microsoft.com/library/c405shex) or the [Sn.exe (Strong Name Tool)](https://msdn.microsoft.com/library/k5b5tt23).</span></span>  
  
3.  <span data-ttu-id="bdef4-108">Если ошибка не устранена, соберите сведения об условиях ее возникновения и уведомите службу технической поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="bdef4-108">If the error persists, gather information about the circumstances and notify Microsoft Product Support Services.</span></span>  
  
### <a name="to-sign-the-assembly-manually"></a><span data-ttu-id="bdef4-109">Подпись сборки вручную</span><span class="sxs-lookup"><span data-stu-id="bdef4-109">To sign the assembly manually</span></span>  
  
1.  <span data-ttu-id="bdef4-110">Используйте [Sn.exe (средство строгих имен)](https://msdn.microsoft.com/library/k5b5tt23) для создания файла пары открытого и закрытого ключей.</span><span class="sxs-lookup"><span data-stu-id="bdef4-110">Use the [Sn.exe (Strong Name Tool)](https://msdn.microsoft.com/library/k5b5tt23) to create a public/private key pair file.</span></span>  
  
     <span data-ttu-id="bdef4-111">Этот файл имеет расширение .SNK.</span><span class="sxs-lookup"><span data-stu-id="bdef4-111">This file has a .snk extension.</span></span>  
  
2.  <span data-ttu-id="bdef4-112">Удалите из проекта ссылку COM, вызывающую ошибку.</span><span class="sxs-lookup"><span data-stu-id="bdef4-112">Delete the COM reference that is generating the error from your project.</span></span>  
  
3.  <span data-ttu-id="bdef4-113">Из Windows **запустить** наведите указатель мыши на **программы**, пункты **Microsoft Visual Studio 2008**, пункты **средств Visual Studio**и нажмите кнопку **Командная строка Visual Studio 2008**.</span><span class="sxs-lookup"><span data-stu-id="bdef4-113">From the Windows **Start** menu, point to **Programs**, point to **Microsoft Visual Studio 2008**, point to **Visual Studio Tools**, and then click **Visual Studio 2008 Command Prompt**.</span></span>  
  
4.  <span data-ttu-id="bdef4-114">Перейдите в каталог, куда хотите поместить программу-оболочку сборки.</span><span class="sxs-lookup"><span data-stu-id="bdef4-114">Move to the directory where you want to place your assembly wrapper.</span></span>  
  
5.  <span data-ttu-id="bdef4-115">Введите следующий код.</span><span class="sxs-lookup"><span data-stu-id="bdef4-115">Type the following code.</span></span>  
  
    ```  
    tlbimp <path to COM reference file> /out:<output assembly name> /keyfile:<path to .snk file>  
    ```  
  
     <span data-ttu-id="bdef4-116">Ниже приведен пример кода, который вы можете ввести.</span><span class="sxs-lookup"><span data-stu-id="bdef4-116">An example of the code you might enter would be the following.</span></span>  
  
    ```  
    tlbimp c:\windows\system32\msi.dll /out:Interop.WindowsInstaller.dll /keyfile:"c:\documents and settings\mykey.snk"  
    ```  
  
     <span data-ttu-id="bdef4-117">Используйте двойные кавычки ("), если путь или файл содержат пробелы.</span><span class="sxs-lookup"><span data-stu-id="bdef4-117">Use double quotation marks (") if a path or file contains spaces.</span></span>  
  
6.  <span data-ttu-id="bdef4-118">В [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] добавьте в созданный файл ссылку на сборку .NET.</span><span class="sxs-lookup"><span data-stu-id="bdef4-118">In [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)], add a .NET Assembly reference to the file you just created.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdef4-119">См. также</span><span class="sxs-lookup"><span data-stu-id="bdef4-119">See Also</span></span>  
 <span data-ttu-id="bdef4-120">[Al.exe (компоновщик сборок)](https://msdn.microsoft.com/library/c405shex) </span><span class="sxs-lookup"><span data-stu-id="bdef4-120">[Al.exe (Assembly Linker)](https://msdn.microsoft.com/library/c405shex) </span></span>  
<span data-ttu-id="bdef4-121"> [Ошибки и предупреждения программы Al.exe](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b) </span><span class="sxs-lookup"><span data-stu-id="bdef4-121"> [Al.exe Tool Errors and Warnings](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b) </span></span>  
<span data-ttu-id="bdef4-122"> [Sn.exe (средство строгих имен)](https://msdn.microsoft.com/library/k5b5tt23) </span><span class="sxs-lookup"><span data-stu-id="bdef4-122"> [Sn.exe (Strong Name Tool)](https://msdn.microsoft.com/library/k5b5tt23) </span></span>  
<span data-ttu-id="bdef4-123"> [Практическое руководство. Создание пары открытого и закрытого ключей](http://msdn.microsoft.com/library/05026813-f3bd-4d7c-9e0b-fc588eb3d114) </span><span class="sxs-lookup"><span data-stu-id="bdef4-123"> [How to: Create a Public-Private Key Pair](http://msdn.microsoft.com/library/05026813-f3bd-4d7c-9e0b-fc588eb3d114) </span></span>  
<span data-ttu-id="bdef4-124"> [Обращайтесь к нам](https://docs.microsoft.com/visualstudio/ide/talk-to-us)</span><span class="sxs-lookup"><span data-stu-id="bdef4-124"> [Talk to Us](https://docs.microsoft.com/visualstudio/ide/talk-to-us)</span></span>
