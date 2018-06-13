---
title: 'Не удается создать сборку: &lt;сообщение об ошибке&gt;'
ms.date: 07/20/2015
f1_keywords:
- vbc30145
- bc30145
helpviewer_keywords:
- BC30145
ms.assetid: 2e7eb2b9-eda6-4bdb-95cc-72c7f0be7528
ms.openlocfilehash: 8f497069088ad30a3be58d02caa0a32f7f1b21b7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33595177"
---
# <a name="unable-to-emit-assembly-lterror-messagegt"></a><span data-ttu-id="50696-102">Не удается создать сборку: &lt;сообщение об ошибке&gt;</span><span class="sxs-lookup"><span data-stu-id="50696-102">Unable to emit assembly: &lt;error message&gt;</span></span>
<span data-ttu-id="50696-103">Компилятор Visual Basic вызывает компоновщик сборок (Al.exe, который также называется Alink) для создания сборки с манифестом, при этом Компоновщик сообщает об ошибке на этапе вывода создания сборки.</span><span class="sxs-lookup"><span data-stu-id="50696-103">The Visual Basic compiler calls the Assembly Linker (Al.exe, also known as Alink) to generate an assembly with a manifest, with the linker reporting an error in the emission stage of creating the assembly.</span></span>  
  
 <span data-ttu-id="50696-104">**Идентификатор ошибки:** BC30145</span><span class="sxs-lookup"><span data-stu-id="50696-104">**Error ID:** BC30145</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="50696-105">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="50696-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="50696-106">Просмотрите сообщение об ошибке и обратитесь к разделу [Al.exe](../../../framework/tools/al-exe-assembly-linker.md).</span><span class="sxs-lookup"><span data-stu-id="50696-106">Examine the quoted error message and consult the topic [Al.exe](../../../framework/tools/al-exe-assembly-linker.md).</span></span> <span data-ttu-id="50696-107">содержатся дополнительные пояснения и рекомендации.</span><span class="sxs-lookup"><span data-stu-id="50696-107">for further explanation and advice.</span></span>  
  
2.  <span data-ttu-id="50696-108">Попробуйте подписать сборку вручную, используя либо [Al.exe](../../../framework/tools/al-exe-assembly-linker.md) или [Sn.exe (средство строгих имен)](../../../framework/tools/sn-exe-strong-name-tool.md).</span><span class="sxs-lookup"><span data-stu-id="50696-108">Try signing the assembly manually, using either the [Al.exe](../../../framework/tools/al-exe-assembly-linker.md) or the [Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md).</span></span>  
  
3.  <span data-ttu-id="50696-109">Если ошибка не устранена, соберите сведения об условиях ее возникновения и уведомите службу технической поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="50696-109">If the error persists, gather information about the circumstances and notify Microsoft Product Support Services.</span></span>  
  
### <a name="to-sign-the-assembly-manually"></a><span data-ttu-id="50696-110">Подпись сборки вручную</span><span class="sxs-lookup"><span data-stu-id="50696-110">To sign the assembly manually</span></span>  
  
1.  <span data-ttu-id="50696-111">Используйте [Sn.exe (средство строгих имен)][Sn.exe (средство строгих имен)](../../../framework/tools/sn-exe-strong-name-tool.md)) для создания файла пары открытого и закрытого ключей.</span><span class="sxs-lookup"><span data-stu-id="50696-111">Use the [Sn.exe (Strong Name Tool)][Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)) to create a public/private key pair file.</span></span>  
  
     <span data-ttu-id="50696-112">Этот файл имеет расширение .SNK.</span><span class="sxs-lookup"><span data-stu-id="50696-112">This file has a .snk extension.</span></span>  
  
2.  <span data-ttu-id="50696-113">Удалите из проекта ссылку COM, вызывающую ошибку.</span><span class="sxs-lookup"><span data-stu-id="50696-113">Delete the COM reference that is generating the error from your project.</span></span>  
  
3.  <span data-ttu-id="50696-114">В окнах **запустить** последовательно выберите пункты **программы**, пункты **Microsoft Visual Studio 2008**, пункты **набора средств Visual Studio**, и Нажмите кнопку **Командная строка Visual Studio 2008**.</span><span class="sxs-lookup"><span data-stu-id="50696-114">From the Windows **Start** menu, point to **Programs**, point to **Microsoft Visual Studio 2008**, point to **Visual Studio Tools**, and then click **Visual Studio 2008 Command Prompt**.</span></span>  
  
4.  <span data-ttu-id="50696-115">Перейдите в каталог, куда хотите поместить программу-оболочку сборки.</span><span class="sxs-lookup"><span data-stu-id="50696-115">Move to the directory where you want to place your assembly wrapper.</span></span>  
  
5.  <span data-ttu-id="50696-116">Введите следующий код.</span><span class="sxs-lookup"><span data-stu-id="50696-116">Type the following code.</span></span>  
  
    ```  
    tlbimp <path to COM reference file> /out:<output assembly name> /keyfile:<path to .snk file>  
    ```  
  
     <span data-ttu-id="50696-117">Ниже приведен пример кода, который вы можете ввести.</span><span class="sxs-lookup"><span data-stu-id="50696-117">An example of the code you might enter would be the following.</span></span>  
  
    ```  
    tlbimp c:\windows\system32\msi.dll /out:Interop.WindowsInstaller.dll /keyfile:"c:\documents and settings\mykey.snk"  
    ```  
  
     <span data-ttu-id="50696-118">Используйте двойные кавычки ("), если путь или файл содержат пробелы.</span><span class="sxs-lookup"><span data-stu-id="50696-118">Use double quotation marks (") if a path or file contains spaces.</span></span>  
  
6.  <span data-ttu-id="50696-119">В Visual Studio добавьте ссылку на сборку .NET в только что созданный файл.</span><span class="sxs-lookup"><span data-stu-id="50696-119">In Visual Studio, add a .NET Assembly reference to the file you just created.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50696-120">См. также</span><span class="sxs-lookup"><span data-stu-id="50696-120">See Also</span></span>  
 
 <span data-ttu-id="50696-121">[Al.exe](../../../framework/tools/al-exe-assembly-linker.md).</span><span class="sxs-lookup"><span data-stu-id="50696-121">[Al.exe](../../../framework/tools/al-exe-assembly-linker.md).</span></span>  
 <span data-ttu-id="50696-122">[Sn.exe (средство строгих имен)] [Sn.exe (средство строгих имен)](../../../framework/tools/sn-exe-strong-name-tool.md))</span><span class="sxs-lookup"><span data-stu-id="50696-122">[Sn.exe (Strong Name Tool)][Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md))</span></span>  
 [<span data-ttu-id="50696-123">Практическое руководство. Создание пары открытого и закрытого ключей</span><span class="sxs-lookup"><span data-stu-id="50696-123">How to: Create a Public-Private Key Pair</span></span>](../../../framework/app-domains/how-to-create-a-public-private-key-pair.md)  
 [<span data-ttu-id="50696-124">Обращайтесь к нам</span><span class="sxs-lookup"><span data-stu-id="50696-124">Talk to Us</span></span>](/visualstudio/ide/talk-to-us)
