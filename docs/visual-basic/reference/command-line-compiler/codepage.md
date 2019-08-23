---
title: -codepage (Visual Basic)
ms.date: 03/09/2018
helpviewer_keywords:
- -codepage compiler option [Visual Basic]
- codepage compiler option [Visual Basic]
- -codepage compiler option [Visual Basic]
ms.assetid: be36ec33-6800-4505-838c-4124564f5cc9
ms.openlocfilehash: 3a5974a910303f847679f18c23e00cfaa00caa2c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962613"
---
# <a name="-codepage-visual-basic"></a><span data-ttu-id="16a61-102">-codepage (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="16a61-102">-codepage (Visual Basic)</span></span>
<span data-ttu-id="16a61-103">Задает кодовую страницу, используемую для всех файлов исходного кода при компиляции.</span><span class="sxs-lookup"><span data-stu-id="16a61-103">Specifies the code page to use for all source-code files in the compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16a61-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="16a61-104">Syntax</span></span>  
  
```  
-codepage:id  
```  
  
## <a name="arguments"></a><span data-ttu-id="16a61-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="16a61-105">Arguments</span></span>  
  
|<span data-ttu-id="16a61-106">Термин</span><span class="sxs-lookup"><span data-stu-id="16a61-106">Term</span></span>|<span data-ttu-id="16a61-107">Определение</span><span class="sxs-lookup"><span data-stu-id="16a61-107">Definition</span></span>|  
|---|---|  
|`id`|<span data-ttu-id="16a61-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="16a61-108">Required.</span></span> <span data-ttu-id="16a61-109">Компилятор использует кодовую страницу, заданную `id` параметром, для интерпретации кодировки исходных файлов.</span><span class="sxs-lookup"><span data-stu-id="16a61-109">The compiler uses the code page specified by `id` to interpret the encoding of the source files.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="16a61-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="16a61-110">Remarks</span></span>  
 <span data-ttu-id="16a61-111">Для компиляции исходного кода, сохраненного с определенной кодировкой, можно `-codepage` использовать, чтобы указать, какую кодовую страницу следует использовать.</span><span class="sxs-lookup"><span data-stu-id="16a61-111">To compile source code saved with a specific encoding, you can use `-codepage` to specify which code page should be used.</span></span> <span data-ttu-id="16a61-112">`-codepage` Параметр применяется ко всем файлам исходного кода при компиляции.</span><span class="sxs-lookup"><span data-stu-id="16a61-112">The `-codepage` option applies to all source-code files in your compilation.</span></span> <span data-ttu-id="16a61-113">Дополнительные сведения см. [в разделе кодировка символов в .NET Framework](../../../standard/base-types/character-encoding.md).</span><span class="sxs-lookup"><span data-stu-id="16a61-113">For more information, see [Character Encoding in the .NET Framework](../../../standard/base-types/character-encoding.md).</span></span>  
  
 <span data-ttu-id="16a61-114">Параметр `-codepage` не требуется, если файлы исходного кода были сохранены с помощью текущей кодовой страницы ANSI, Юникода или UTF-8 с подписью.</span><span class="sxs-lookup"><span data-stu-id="16a61-114">The `-codepage` option is not needed if the source-code files were saved using the current ANSI code page, Unicode, or UTF-8 with a signature.</span></span> <span data-ttu-id="16a61-115">Visual Studio по умолчанию сохраняет все файлы исходного кода с текущей кодовой страницей ANSI, если пользователь не задает другую кодировку в диалоговом окне **Кодировка** .</span><span class="sxs-lookup"><span data-stu-id="16a61-115">Visual Studio saves all source-code files with the current ANSI code page by default, unless the user specifies another encoding in the **Encoding** dialog box.</span></span> <span data-ttu-id="16a61-116">Visual Studio использует диалоговое окно **Кодировка** для открытия файлов исходного кода, сохраненных с другой кодовой страницей.</span><span class="sxs-lookup"><span data-stu-id="16a61-116">Visual Studio uses the **Encoding** dialog box to open source-code files saved with a different code page.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="16a61-117">Этот `-codepage` параметр недоступен в среде разработки Visual Studio; он доступен только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="16a61-117">The `-codepage` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16a61-118">См. также</span><span class="sxs-lookup"><span data-stu-id="16a61-118">See also</span></span>

- [<span data-ttu-id="16a61-119">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="16a61-119">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
