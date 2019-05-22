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
ms.openlocfilehash: 59dc1abc3f678a4cf15543c11f9f200ff318ce8f
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2019
ms.locfileid: "65876926"
---
# <a name="-codepage-c-compiler-options"></a><span data-ttu-id="556a6-102">-codepage (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="556a6-102">-codepage (C# Compiler Options)</span></span>
<span data-ttu-id="556a6-103">Этот параметр задает кодовую страницу, используемую во время компиляции, если требуемая страница не является текущей кодовой страницей системы по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="556a6-103">This option specifies which codepage to use during compilation if the required page is not the current default codepage for the system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="556a6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="556a6-104">Syntax</span></span>  
  
```console  
-codepage:id  
```  
  
## <a name="arguments"></a><span data-ttu-id="556a6-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="556a6-105">Arguments</span></span>  
 `id`  
 <span data-ttu-id="556a6-106">Идентификатор кодовой страницы, используемой для всех файлов исходного кода при компиляции.</span><span class="sxs-lookup"><span data-stu-id="556a6-106">The id of the code page to use for all source code files in the compilation.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="556a6-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="556a6-107">Remarks</span></span>  
 <span data-ttu-id="556a6-108">Во-первых, компилятор будет пытаться интерпретировать все исходные файлы в кодировке UTF-8.</span><span class="sxs-lookup"><span data-stu-id="556a6-108">The compiler will first attempt to interpret all source files as UTF-8.</span></span> <span data-ttu-id="556a6-109">Если кодировка файлов исходного кода отличается от UTF-8 и использует символы, отличные от 7-разрядных символов ASCII, используйте параметр **-codepage**, чтобы указать нужную кодовую страницу.</span><span class="sxs-lookup"><span data-stu-id="556a6-109">If your source code files are in an encoding other than UTF-8 and use characters other than 7-bit ASCII characters, use the **-codepage** option to specify which code page should be used.</span></span> <span data-ttu-id="556a6-110">Параметр **-codepage** применяется ко всем файлам исходного кода, включенным в компиляцию.</span><span class="sxs-lookup"><span data-stu-id="556a6-110">**-codepage** applies to all source code files in your compilation.</span></span>  
    
 <span data-ttu-id="556a6-111">Сведения о том, как найти кодовые страницы, которые поддерживаются в системе, см. на странице, посвященной функции [GetCPInfo](/windows/desktop/api/winnls/nf-winnls-getcpinfo).</span><span class="sxs-lookup"><span data-stu-id="556a6-111">See [GetCPInfo](/windows/desktop/api/winnls/nf-winnls-getcpinfo) for information on how to find which code pages are supported on your system.</span></span>  
  
 <span data-ttu-id="556a6-112">Этот параметр компилятора недоступен в Visual Studio и не может быть изменен программным способом.</span><span class="sxs-lookup"><span data-stu-id="556a6-112">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="556a6-113">См. также</span><span class="sxs-lookup"><span data-stu-id="556a6-113">See also</span></span>

- [<span data-ttu-id="556a6-114">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="556a6-114">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
- [<span data-ttu-id="556a6-115">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="556a6-115">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
