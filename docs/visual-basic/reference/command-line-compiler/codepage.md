---
title: -codepage (Visual Basic)
ms.date: 03/09/2018
helpviewer_keywords:
- -codepage compiler option [Visual Basic]
- codepage compiler option [Visual Basic]
- -codepage compiler option [Visual Basic]
ms.assetid: be36ec33-6800-4505-838c-4124564f5cc9
ms.openlocfilehash: 383b6adae94c27efdd236de31ddfa8d16a6d4648
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33648532"
---
# <a name="-codepage-visual-basic"></a><span data-ttu-id="04235-102">-codepage (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="04235-102">-codepage (Visual Basic)</span></span>
<span data-ttu-id="04235-103">Задает кодовую страницу, используемую для всех файлов исходного кода при компиляции.</span><span class="sxs-lookup"><span data-stu-id="04235-103">Specifies the code page to use for all source-code files in the compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04235-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="04235-104">Syntax</span></span>  
  
```  
-codepage:id  
```  
  
## <a name="arguments"></a><span data-ttu-id="04235-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="04235-105">Arguments</span></span>  
  
|<span data-ttu-id="04235-106">Термин</span><span class="sxs-lookup"><span data-stu-id="04235-106">Term</span></span>|<span data-ttu-id="04235-107">Определение</span><span class="sxs-lookup"><span data-stu-id="04235-107">Definition</span></span>|  
|---|---|  
|`id`|<span data-ttu-id="04235-108">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="04235-108">Required.</span></span> <span data-ttu-id="04235-109">Компилятор использует кодовая страница, указанная `id` для интерпретации кодировки исходных файлов.</span><span class="sxs-lookup"><span data-stu-id="04235-109">The compiler uses the code page specified by `id` to interpret the encoding of the source files.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="04235-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="04235-110">Remarks</span></span>  
 <span data-ttu-id="04235-111">Чтобы скомпилировать исходный код сохранен в определенной кодировке, можно использовать `-codepage` для указания того, какая кодовая страница должна использоваться.</span><span class="sxs-lookup"><span data-stu-id="04235-111">To compile source code saved with a specific encoding, you can use `-codepage` to specify which code page should be used.</span></span> <span data-ttu-id="04235-112">`-codepage` Параметр применяется ко всем файлам исходного кода при компиляции.</span><span class="sxs-lookup"><span data-stu-id="04235-112">The `-codepage` option applies to all source-code files in your compilation.</span></span> <span data-ttu-id="04235-113">Дополнительные сведения см. в разделе [кодировка символов в .NET Framework](http://msdn.microsoft.com/library/bf6d9823-4c2d-48af-b280-919c5af66ae9).</span><span class="sxs-lookup"><span data-stu-id="04235-113">For more information, see [Character Encoding in the .NET Framework](http://msdn.microsoft.com/library/bf6d9823-4c2d-48af-b280-919c5af66ae9).</span></span>  
  
 <span data-ttu-id="04235-114">`-codepage` Не нужен, если файлы исходного кода были сохранены с помощью текущей кодовой страницы ANSI, Юникод или UTF-8 с подписью.</span><span class="sxs-lookup"><span data-stu-id="04235-114">The `-codepage` option is not needed if the source-code files were saved using the current ANSI code page, Unicode, or UTF-8 with a signature.</span></span> <span data-ttu-id="04235-115">Visual Studio сохраняет все файлы исходного кода с текущей кодовой страницы ANSI по умолчанию, если пользователь не указывает другую кодировку в **кодировка** диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="04235-115">Visual Studio saves all source-code files with the current ANSI code page by default, unless the user specifies another encoding in the **Encoding** dialog box.</span></span> <span data-ttu-id="04235-116">Visual Studio использует **кодировка** диалоговым окном открытия файлов исходного кода, сохраненных с другой кодовой страницей.</span><span class="sxs-lookup"><span data-stu-id="04235-116">Visual Studio uses the **Encoding** dialog box to open source-code files saved with a different code page.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="04235-117">`-codepage` Параметр недоступен в среде разработки Visual Studio; она доступна только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="04235-117">The `-codepage` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04235-118">См. также</span><span class="sxs-lookup"><span data-stu-id="04235-118">See Also</span></span>  
 [<span data-ttu-id="04235-119">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="04235-119">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
