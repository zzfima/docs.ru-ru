---
title: -codepage (Visual Basic)
ms.date: 03/09/2018
helpviewer_keywords:
- -codepage compiler option [Visual Basic]
- codepage compiler option [Visual Basic]
- -codepage compiler option [Visual Basic]
ms.assetid: be36ec33-6800-4505-838c-4124564f5cc9
ms.openlocfilehash: 8aee51df3ba9f92ca662fbbfbd73998e4a3b4538
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43532514"
---
# <a name="-codepage-visual-basic"></a><span data-ttu-id="162bf-102">-codepage (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="162bf-102">-codepage (Visual Basic)</span></span>
<span data-ttu-id="162bf-103">Задает кодовую страницу, используемую для всех файлов исходного кода при компиляции.</span><span class="sxs-lookup"><span data-stu-id="162bf-103">Specifies the code page to use for all source-code files in the compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="162bf-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="162bf-104">Syntax</span></span>  
  
```  
-codepage:id  
```  
  
## <a name="arguments"></a><span data-ttu-id="162bf-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="162bf-105">Arguments</span></span>  
  
|<span data-ttu-id="162bf-106">Термин</span><span class="sxs-lookup"><span data-stu-id="162bf-106">Term</span></span>|<span data-ttu-id="162bf-107">Определение</span><span class="sxs-lookup"><span data-stu-id="162bf-107">Definition</span></span>|  
|---|---|  
|`id`|<span data-ttu-id="162bf-108">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="162bf-108">Required.</span></span> <span data-ttu-id="162bf-109">Компилятор использует кодовая страница, указанная `id` для интерпретации кодировки исходных файлов.</span><span class="sxs-lookup"><span data-stu-id="162bf-109">The compiler uses the code page specified by `id` to interpret the encoding of the source files.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="162bf-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="162bf-110">Remarks</span></span>  
 <span data-ttu-id="162bf-111">Для компиляции исходного кода сохранен в определенной кодировке, можно использовать `-codepage` указать нужную кодовую страницу следует использовать.</span><span class="sxs-lookup"><span data-stu-id="162bf-111">To compile source code saved with a specific encoding, you can use `-codepage` to specify which code page should be used.</span></span> <span data-ttu-id="162bf-112">`-codepage` Параметр применяется ко всем файлам исходного кода при компиляции.</span><span class="sxs-lookup"><span data-stu-id="162bf-112">The `-codepage` option applies to all source-code files in your compilation.</span></span> <span data-ttu-id="162bf-113">Дополнительные сведения см. в разделе [кодировка символов в .NET Framework](https://msdn.microsoft.com/library/bf6d9823-4c2d-48af-b280-919c5af66ae9).</span><span class="sxs-lookup"><span data-stu-id="162bf-113">For more information, see [Character Encoding in the .NET Framework](https://msdn.microsoft.com/library/bf6d9823-4c2d-48af-b280-919c5af66ae9).</span></span>  
  
 <span data-ttu-id="162bf-114">`-codepage` Параметр не требуется, если файлы исходного кода были сохранены с помощью текущей кодовой страницы ANSI, Юникод или UTF-8 с подписью.</span><span class="sxs-lookup"><span data-stu-id="162bf-114">The `-codepage` option is not needed if the source-code files were saved using the current ANSI code page, Unicode, or UTF-8 with a signature.</span></span> <span data-ttu-id="162bf-115">Visual Studio сохраняет все файлы исходного кода с текущей кодовой страницы ANSI по умолчанию, если пользователь не указывает другую кодировку в **кодировка** диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="162bf-115">Visual Studio saves all source-code files with the current ANSI code page by default, unless the user specifies another encoding in the **Encoding** dialog box.</span></span> <span data-ttu-id="162bf-116">Visual Studio использует **кодировка** диалоговое окно, чтобы открыть файлы исходного кода, сохраненные с кодовой страницей.</span><span class="sxs-lookup"><span data-stu-id="162bf-116">Visual Studio uses the **Encoding** dialog box to open source-code files saved with a different code page.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="162bf-117">`-codepage` Не доступна из среды разработки Visual Studio; она доступна только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="162bf-117">The `-codepage` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="162bf-118">См. также</span><span class="sxs-lookup"><span data-stu-id="162bf-118">See Also</span></span>  
 [<span data-ttu-id="162bf-119">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="162bf-119">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
