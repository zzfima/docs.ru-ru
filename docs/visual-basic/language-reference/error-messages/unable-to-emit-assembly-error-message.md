---
title: 'Не удается выпустить сборку: <error message>'
ms.date: 08/14/2018
f1_keywords:
- vbc30145
- bc30145
helpviewer_keywords:
- BC30145
ms.assetid: 2e7eb2b9-eda6-4bdb-95cc-72c7f0be7528
ms.openlocfilehash: 5776755a57fbc2b0086b1c9b6cfbb2f2b7eb03fa
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2019
ms.locfileid: "73197272"
---
# <a name="unable-to-emit-assembly-error-message"></a><span data-ttu-id="79ae5-102">Не удалось выпустить сборку: \<сообщение об ошибке ></span><span class="sxs-lookup"><span data-stu-id="79ae5-102">Unable to emit assembly: \<error message></span></span>

<span data-ttu-id="79ae5-103">Компилятор Visual Basic вызывает компоновщик сборок (*Al. exe*, также известный как ALink) для создания сборки с манифестом, а компоновщик сообщает об ошибке на этапе эмиссии создания сборки.</span><span class="sxs-lookup"><span data-stu-id="79ae5-103">The Visual Basic compiler calls the Assembly Linker (*Al.exe*, also known as Alink) to generate an assembly with a manifest, and the linker reports an error in the emission stage of creating the assembly.</span></span>

<span data-ttu-id="79ae5-104">**Идентификатор ошибки:** BC30145</span><span class="sxs-lookup"><span data-stu-id="79ae5-104">**Error ID:** BC30145</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="79ae5-105">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="79ae5-105">To correct this error</span></span>

1. <span data-ttu-id="79ae5-106">Изучите сообщение об ошибке в кавычках и ознакомьтесь с разделом [Al. exe](../../../framework/tools/al-exe-assembly-linker.md) для получения дополнительных пояснений и советов.</span><span class="sxs-lookup"><span data-stu-id="79ae5-106">Examine the quoted error message and consult the topic [Al.exe](../../../framework/tools/al-exe-assembly-linker.md) for further explanation and advice.</span></span>

2. <span data-ttu-id="79ae5-107">Попробуйте подписать сборку вручную, используя либо [Al. exe](../../../framework/tools/al-exe-assembly-linker.md) , либо [Sn. exe (средство строгих имен)](../../../framework/tools/sn-exe-strong-name-tool.md).</span><span class="sxs-lookup"><span data-stu-id="79ae5-107">Try signing the assembly manually, using either the [Al.exe](../../../framework/tools/al-exe-assembly-linker.md) or the [Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md).</span></span>

3. <span data-ttu-id="79ae5-108">Если ошибка не устранена, соберите сведения об условиях ее возникновения и уведомите службу технической поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="79ae5-108">If the error persists, gather information about the circumstances and notify Microsoft Product Support Services.</span></span>

### <a name="to-sign-the-assembly-manually"></a><span data-ttu-id="79ae5-109">Подпись сборки вручную</span><span class="sxs-lookup"><span data-stu-id="79ae5-109">To sign the assembly manually</span></span>

1. <span data-ttu-id="79ae5-110">Используйте [Sn. exe (средство строгих имен)](../../../framework/tools/sn-exe-strong-name-tool.md)) для создания файла пары открытого и закрытого ключей.</span><span class="sxs-lookup"><span data-stu-id="79ae5-110">Use the [Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)) to create a public/private key pair file.</span></span>

   <span data-ttu-id="79ae5-111">Этот файл имеет расширение *SNK* .</span><span class="sxs-lookup"><span data-stu-id="79ae5-111">This file has an *.snk* extension.</span></span>

2. <span data-ttu-id="79ae5-112">Удалите из проекта ссылку COM, вызывающую ошибку.</span><span class="sxs-lookup"><span data-stu-id="79ae5-112">Delete the COM reference that is generating the error from your project.</span></span>

3. <span data-ttu-id="79ae5-113">Откройте [Командная строка разработчика для Visual Studio](../../../framework/tools/developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="79ae5-113">Open the [Developer Command Prompt for Visual Studio](../../../framework/tools/developer-command-prompt-for-vs.md).</span></span>

   <span data-ttu-id="79ae5-114">В Windows 10 введите **командную строку разработчика** в поле поиска на панели задач.</span><span class="sxs-lookup"><span data-stu-id="79ae5-114">In Windows 10, enter **Developer command prompt** into the search box on the task bar.</span></span> <span data-ttu-id="79ae5-115">Затем выберите **Командная строка разработчика для VS 2017** в списке результатов.</span><span class="sxs-lookup"><span data-stu-id="79ae5-115">Then, select **Developer Command Prompt for VS 2017** from the results list.</span></span>

4. <span data-ttu-id="79ae5-116">Измените каталог на каталог, в который нужно поместить обертку сборки.</span><span class="sxs-lookup"><span data-stu-id="79ae5-116">Change the directory to the directory where you want to place your assembly wrapper.</span></span>

5. <span data-ttu-id="79ae5-117">Введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="79ae5-117">Enter the following command:</span></span>

    ```cmd
    tlbimp <path to COM reference file> /out:<output assembly name> /keyfile:<path to .snk file>
    ```

   <span data-ttu-id="79ae5-118">Пример реальной команды, которую можно ввести:</span><span class="sxs-lookup"><span data-stu-id="79ae5-118">An example of the actual command you might enter is:</span></span>

    ```cmd
    tlbimp c:\windows\system32\msi.dll /out:Interop.WindowsInstaller.dll /keyfile:"c:\documents and settings\mykey.snk"
    ```

   > [!TIP]
   > <span data-ttu-id="79ae5-119">Если путь или файл содержит пробелы, используйте двойные кавычки.</span><span class="sxs-lookup"><span data-stu-id="79ae5-119">Use double quotation marks if a path or file contains spaces.</span></span>

6. <span data-ttu-id="79ae5-120">В Visual Studio добавьте ссылку на сборку .NET в только что созданный файл.</span><span class="sxs-lookup"><span data-stu-id="79ae5-120">In Visual Studio, add a .NET Assembly reference to the file you just created.</span></span>

## <a name="see-also"></a><span data-ttu-id="79ae5-121">См. также</span><span class="sxs-lookup"><span data-stu-id="79ae5-121">See also</span></span>

- [<span data-ttu-id="79ae5-122">Al. exe</span><span class="sxs-lookup"><span data-stu-id="79ae5-122">Al.exe</span></span>](../../../framework/tools/al-exe-assembly-linker.md)
- [<span data-ttu-id="79ae5-123">Sn.exe (средство строгих имен)</span><span class="sxs-lookup"><span data-stu-id="79ae5-123">Sn.exe (Strong Name Tool)</span></span>](../../../framework/tools/sn-exe-strong-name-tool.md)
- [<span data-ttu-id="79ae5-124">Практическое руководство. Создание пары открытого и закрытого ключей</span><span class="sxs-lookup"><span data-stu-id="79ae5-124">How to: Create a Public-Private Key Pair</span></span>](../../../standard/assembly/create-public-private-key-pair.md)
- [<span data-ttu-id="79ae5-125">Обращайтесь к нам</span><span class="sxs-lookup"><span data-stu-id="79ae5-125">Talk to Us</span></span>](/visualstudio/ide/feedback-options)
