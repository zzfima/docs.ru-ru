---
title: 'Не удается выпустить сборку: <error message>'
ms.date: 08/14/2018
f1_keywords:
- vbc30145
- bc30145
helpviewer_keywords:
- BC30145
ms.assetid: 2e7eb2b9-eda6-4bdb-95cc-72c7f0be7528
ms.openlocfilehash: 012284aa42dfa29ad1a5e4ec4a4df5eaacbd4fb7
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "65642277"
---
# <a name="unable-to-emit-assembly-error-message"></a><span data-ttu-id="aedbd-102">Не удается выпустить сборку: \<сообщение об ошибке ></span><span class="sxs-lookup"><span data-stu-id="aedbd-102">Unable to emit assembly: \<error message></span></span>

<span data-ttu-id="aedbd-103">Компилятор Visual Basic вызывает компоновщик сборок (*Al.exe*, которая также называется Alink) для создания сборки с манифестом и компоновщик сообщает об ошибке на этапе вывода создания сборки.</span><span class="sxs-lookup"><span data-stu-id="aedbd-103">The Visual Basic compiler calls the Assembly Linker (*Al.exe*, also known as Alink) to generate an assembly with a manifest, and the linker reports an error in the emission stage of creating the assembly.</span></span>

<span data-ttu-id="aedbd-104">**Идентификатор ошибки:** BC30145</span><span class="sxs-lookup"><span data-stu-id="aedbd-104">**Error ID:** BC30145</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="aedbd-105">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="aedbd-105">To correct this error</span></span>

1. <span data-ttu-id="aedbd-106">Изучите приведенное сообщение об ошибке и обратитесь к разделу [Al.exe](../../../framework/tools/al-exe-assembly-linker.md) для пояснения и рекомендации.</span><span class="sxs-lookup"><span data-stu-id="aedbd-106">Examine the quoted error message and consult the topic [Al.exe](../../../framework/tools/al-exe-assembly-linker.md) for further explanation and advice.</span></span>

2. <span data-ttu-id="aedbd-107">Попробуйте подписать сборку вручную, воспользовавшись [Al.exe](../../../framework/tools/al-exe-assembly-linker.md) или [Sn.exe (средство строгих имен)](../../../framework/tools/sn-exe-strong-name-tool.md).</span><span class="sxs-lookup"><span data-stu-id="aedbd-107">Try signing the assembly manually, using either the [Al.exe](../../../framework/tools/al-exe-assembly-linker.md) or the [Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md).</span></span>

3. <span data-ttu-id="aedbd-108">Если ошибка не устранена, соберите сведения об условиях ее возникновения и уведомите службу технической поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="aedbd-108">If the error persists, gather information about the circumstances and notify Microsoft Product Support Services.</span></span>

### <a name="to-sign-the-assembly-manually"></a><span data-ttu-id="aedbd-109">Подпись сборки вручную</span><span class="sxs-lookup"><span data-stu-id="aedbd-109">To sign the assembly manually</span></span>

1. <span data-ttu-id="aedbd-110">Используйте [Sn.exe (средство строгих имен)](../../../framework/tools/sn-exe-strong-name-tool.md)) для создания файла пары открытого и закрытого ключей.</span><span class="sxs-lookup"><span data-stu-id="aedbd-110">Use the [Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)) to create a public/private key pair file.</span></span>

   <span data-ttu-id="aedbd-111">Этот файл содержит *.snk* расширения.</span><span class="sxs-lookup"><span data-stu-id="aedbd-111">This file has an *.snk* extension.</span></span>

2. <span data-ttu-id="aedbd-112">Удалите из проекта ссылку COM, вызывающую ошибку.</span><span class="sxs-lookup"><span data-stu-id="aedbd-112">Delete the COM reference that is generating the error from your project.</span></span>

3. <span data-ttu-id="aedbd-113">Откройте [Командная строка разработчика для Visual Studio](../../../framework/tools/developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="aedbd-113">Open the [Developer Command Prompt for Visual Studio](../../../framework/tools/developer-command-prompt-for-vs.md).</span></span>

   <span data-ttu-id="aedbd-114">В Windows 10, введите **Командная строка разработчика** в поле поиска на панели задач.</span><span class="sxs-lookup"><span data-stu-id="aedbd-114">In Windows 10, enter **Developer command prompt** into the search box on the task bar.</span></span> <span data-ttu-id="aedbd-115">Выберите **Командная строка разработчика для VS 2017** из списка результатов.</span><span class="sxs-lookup"><span data-stu-id="aedbd-115">Then, select **Developer Command Prompt for VS 2017** from the results list.</span></span>

4. <span data-ttu-id="aedbd-116">Перейдите в каталог в каталог, где вы хотите поместить программу-оболочку сборки.</span><span class="sxs-lookup"><span data-stu-id="aedbd-116">Change the directory to the directory where you want to place your assembly wrapper.</span></span>

5. <span data-ttu-id="aedbd-117">Введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="aedbd-117">Enter the following command:</span></span>

    ```cmd
    tlbimp <path to COM reference file> /out:<output assembly name> /keyfile:<path to .snk file>
    ```

   <span data-ttu-id="aedbd-118">Примером фактического команду, которую можно ввести является:</span><span class="sxs-lookup"><span data-stu-id="aedbd-118">An example of the actual command you might enter is:</span></span>

    ```cmd
    tlbimp c:\windows\system32\msi.dll /out:Interop.WindowsInstaller.dll /keyfile:"c:\documents and settings\mykey.snk"
    ```

   > [!TIP]
   > <span data-ttu-id="aedbd-119">Используйте двойные кавычки, если путь или файл содержит пробелы.</span><span class="sxs-lookup"><span data-stu-id="aedbd-119">Use double quotation marks if a path or file contains spaces.</span></span>

6. <span data-ttu-id="aedbd-120">В Visual Studio добавьте ссылку на сборку .NET к файлу, который вы только что создали.</span><span class="sxs-lookup"><span data-stu-id="aedbd-120">In Visual Studio, add a .NET Assembly reference to the file you just created.</span></span>

## <a name="see-also"></a><span data-ttu-id="aedbd-121">См. также</span><span class="sxs-lookup"><span data-stu-id="aedbd-121">See also</span></span>

- [<span data-ttu-id="aedbd-122">Al.exe</span><span class="sxs-lookup"><span data-stu-id="aedbd-122">Al.exe</span></span>](../../../framework/tools/al-exe-assembly-linker.md)
- [<span data-ttu-id="aedbd-123">Sn.exe (средство строгих имен)</span><span class="sxs-lookup"><span data-stu-id="aedbd-123">Sn.exe (Strong Name Tool)</span></span>](../../../framework/tools/sn-exe-strong-name-tool.md)
- [<span data-ttu-id="aedbd-124">Практическое руководство. Создание пары открытого и закрытого ключей</span><span class="sxs-lookup"><span data-stu-id="aedbd-124">How to: Create a Public-Private Key Pair</span></span>](../../../framework/app-domains/how-to-create-a-public-private-key-pair.md)
- [<span data-ttu-id="aedbd-125">Обращайтесь к нам</span><span class="sxs-lookup"><span data-stu-id="aedbd-125">Talk to Us</span></span>](/visualstudio/ide/talk-to-us)
