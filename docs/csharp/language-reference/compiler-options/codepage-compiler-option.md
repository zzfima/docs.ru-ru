---
title: "-codepage (параметры компилятора C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /codepage
helpviewer_keywords:
- /codepage compiler option [C#]
- codepage compiler option [C#]
- -codepage compiler option [C#]
ms.assetid: 75942989-b69a-4308-90a0-840c73d2c478
caps.latest.revision: "15"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: c1181ef98ac5f335c9737771eda2b3bd9227cc9f
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="-codepage-c-compiler-options"></a><span data-ttu-id="39f2b-102">-codepage (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="39f2b-102">-codepage (C# Compiler Options)</span></span>
<span data-ttu-id="39f2b-103">Этот параметр задает кодовую страницу, используемую во время компиляции, если требуемая страница не является текущей кодовой страницей системы по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="39f2b-103">This option specifies which codepage to use during compilation if the required page is not the current default codepage for the system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39f2b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="39f2b-104">Syntax</span></span>  
  
```console  
-codepage:id  
```  
  
## <a name="arguments"></a><span data-ttu-id="39f2b-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="39f2b-105">Arguments</span></span>  
 `id`  
 <span data-ttu-id="39f2b-106">Идентификатор кодовой страницы, используемой для всех файлов исходного кода при компиляции.</span><span class="sxs-lookup"><span data-stu-id="39f2b-106">The id of the code page to use for all source code files in the compilation.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="39f2b-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="39f2b-107">Remarks</span></span>  
 <span data-ttu-id="39f2b-108">При компиляции одного или нескольких файлов исходного кода, не использующих кодовую страницу по умолчанию, с помощью параметра **-codepage** можно указать нужную кодовую страницу.</span><span class="sxs-lookup"><span data-stu-id="39f2b-108">If you compile one or more source code files that were not created to use the default code page on your computer, you can use the **-codepage** option to specify which code page should be used.</span></span> <span data-ttu-id="39f2b-109">Параметр **-codepage** применяется ко всем файлам исходного кода, включенным в компиляцию.</span><span class="sxs-lookup"><span data-stu-id="39f2b-109">**-codepage** applies to all source code files in your compilation.</span></span>  
  
 <span data-ttu-id="39f2b-110">Если файлы исходного кода были созданы с помощью кодовой страницы, активной на компьютере, либо с помощью кодовой страницы UNICODE или UTF-8, использовать параметр **-codepage** не требуется.</span><span class="sxs-lookup"><span data-stu-id="39f2b-110">If the source code files were created with the same codepage that is in effect on your computer or if the source code files were created with UNICODE or UTF-8, you need not use **-codepage**.</span></span>  
  
 <span data-ttu-id="39f2b-111">Сведения о том, как найти кодовые страницы, которые поддерживаются в системе, см. на странице, посвященной функции [GetCPInfo](https://msdn.microsoft.com/library/dd318078(VS.85).aspx).</span><span class="sxs-lookup"><span data-stu-id="39f2b-111">See [GetCPInfo](https://msdn.microsoft.com/library/dd318078(VS.85).aspx) for information on how to find which code pages are supported on your system.</span></span>  
  
 <span data-ttu-id="39f2b-112">Этот параметр компилятора недоступен в Visual Studio и не может быть изменен программным способом.</span><span class="sxs-lookup"><span data-stu-id="39f2b-112">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39f2b-113">См. также</span><span class="sxs-lookup"><span data-stu-id="39f2b-113">See Also</span></span>  
 [<span data-ttu-id="39f2b-114">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="39f2b-114">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="39f2b-115">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="39f2b-115">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
