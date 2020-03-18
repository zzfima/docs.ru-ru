---
title: -codepage (параметры компилятора C#)
ms.date: 07/20/2015
f1_keywords:
- /codepage
helpviewer_keywords:
- /codepage compiler option [C#]
- codepage compiler option [C#]
- -codepage compiler option [C#]
ms.assetid: 75942989-b69a-4308-90a0-840c73d2c478
ms.openlocfilehash: 3352e7fc446ace391540360a3b6b36d604ca5f13
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79173761"
---
# <a name="-codepage-c-compiler-options"></a><span data-ttu-id="9f7f3-102">-codepage (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="9f7f3-102">-codepage (C# Compiler Options)</span></span>
<span data-ttu-id="9f7f3-103">Этот параметр задает кодовую страницу, используемую во время компиляции, если требуемая страница не является текущей кодовой страницей системы по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9f7f3-103">This option specifies which codepage to use during compilation if the required page is not the current default codepage for the system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f7f3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9f7f3-104">Syntax</span></span>  
  
```console  
-codepage:id  
```  
  
## <a name="arguments"></a><span data-ttu-id="9f7f3-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="9f7f3-105">Arguments</span></span>  
 `id`  
 <span data-ttu-id="9f7f3-106">Идентификатор кодовой страницы, используемой для всех файлов исходного кода при компиляции.</span><span class="sxs-lookup"><span data-stu-id="9f7f3-106">The id of the code page to use for all source code files in the compilation.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9f7f3-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="9f7f3-107">Remarks</span></span>  
 <span data-ttu-id="9f7f3-108">Во-первых, компилятор будет пытаться интерпретировать все исходные файлы в кодировке UTF-8.</span><span class="sxs-lookup"><span data-stu-id="9f7f3-108">The compiler will first attempt to interpret all source files as UTF-8.</span></span> <span data-ttu-id="9f7f3-109">Если кодировка файлов исходного кода отличается от UTF-8 и использует символы, отличные от 7-разрядных символов ASCII, используйте параметр **-codepage**, чтобы указать нужную кодовую страницу.</span><span class="sxs-lookup"><span data-stu-id="9f7f3-109">If your source code files are in an encoding other than UTF-8 and use characters other than 7-bit ASCII characters, use the **-codepage** option to specify which code page should be used.</span></span> <span data-ttu-id="9f7f3-110">Параметр **-codepage** применяется ко всем файлам исходного кода, включенным в компиляцию.</span><span class="sxs-lookup"><span data-stu-id="9f7f3-110">**-codepage** applies to all source code files in your compilation.</span></span>  

 <span data-ttu-id="9f7f3-111">Сведения о том, как найти кодовые страницы, которые поддерживаются в системе, см. на странице, посвященной функции [GetCPInfo](/windows/desktop/api/winnls/nf-winnls-getcpinfo).</span><span class="sxs-lookup"><span data-stu-id="9f7f3-111">See [GetCPInfo](/windows/desktop/api/winnls/nf-winnls-getcpinfo) for information on how to find which code pages are supported on your system.</span></span>  
  
 <span data-ttu-id="9f7f3-112">Этот параметр компилятора недоступен в Visual Studio и не может быть изменен программным способом.</span><span class="sxs-lookup"><span data-stu-id="9f7f3-112">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f7f3-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="9f7f3-113">See also</span></span>

- [<span data-ttu-id="9f7f3-114">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="9f7f3-114">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="9f7f3-115">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="9f7f3-115">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
