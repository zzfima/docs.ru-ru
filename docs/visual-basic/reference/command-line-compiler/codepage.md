---
title: -codepage (Visual Basic)
ms.date: 03/09/2018
helpviewer_keywords:
- -codepage compiler option [Visual Basic]
- codepage compiler option [Visual Basic]
- -codepage compiler option [Visual Basic]
ms.assetid: be36ec33-6800-4505-838c-4124564f5cc9
ms.openlocfilehash: e4cdc27ab021fe055f157b78946538f2b76870e1
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72002360"
---
# <a name="-codepage-visual-basic"></a><span data-ttu-id="6b14d-102">-codepage (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6b14d-102">-codepage (Visual Basic)</span></span>
<span data-ttu-id="6b14d-103">Задает кодовую страницу, используемую для всех файлов исходного кода при компиляции.</span><span class="sxs-lookup"><span data-stu-id="6b14d-103">Specifies the code page to use for all source-code files in the compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b14d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6b14d-104">Syntax</span></span>  
  
```console  
-codepage:id  
```  
  
## <a name="arguments"></a><span data-ttu-id="6b14d-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="6b14d-105">Arguments</span></span>  
  
|<span data-ttu-id="6b14d-106">Термин</span><span class="sxs-lookup"><span data-stu-id="6b14d-106">Term</span></span>|<span data-ttu-id="6b14d-107">Определение</span><span class="sxs-lookup"><span data-stu-id="6b14d-107">Definition</span></span>|  
|---|---|  
|`id`|<span data-ttu-id="6b14d-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="6b14d-108">Required.</span></span> <span data-ttu-id="6b14d-109">Компилятор использует кодовую страницу, указанную `id`, для интерпретации кодировки исходных файлов.</span><span class="sxs-lookup"><span data-stu-id="6b14d-109">The compiler uses the code page specified by `id` to interpret the encoding of the source files.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6b14d-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="6b14d-110">Remarks</span></span>  
 <span data-ttu-id="6b14d-111">Чтобы скомпилировать исходный код, сохраненный с определенной кодировкой, можно использовать `-codepage`, чтобы указать, какую кодовую страницу следует использовать.</span><span class="sxs-lookup"><span data-stu-id="6b14d-111">To compile source code saved with a specific encoding, you can use `-codepage` to specify which code page should be used.</span></span> <span data-ttu-id="6b14d-112">Параметр `-codepage` применяется ко всем файлам исходного кода в компиляции.</span><span class="sxs-lookup"><span data-stu-id="6b14d-112">The `-codepage` option applies to all source-code files in your compilation.</span></span> <span data-ttu-id="6b14d-113">Дополнительные сведения см. [в разделе кодировка символов в .NET Framework](../../../standard/base-types/character-encoding.md).</span><span class="sxs-lookup"><span data-stu-id="6b14d-113">For more information, see [Character Encoding in the .NET Framework](../../../standard/base-types/character-encoding.md).</span></span>  
  
 <span data-ttu-id="6b14d-114">Параметр `-codepage` не требуется, если файлы исходного кода были сохранены с помощью текущей кодовой страницы ANSI, Юникода или UTF-8 с сигнатурой.</span><span class="sxs-lookup"><span data-stu-id="6b14d-114">The `-codepage` option is not needed if the source-code files were saved using the current ANSI code page, Unicode, or UTF-8 with a signature.</span></span> <span data-ttu-id="6b14d-115">Visual Studio по умолчанию сохраняет все файлы исходного кода с текущей кодовой страницей ANSI, если пользователь не задает другую кодировку в диалоговом окне **Кодировка** .</span><span class="sxs-lookup"><span data-stu-id="6b14d-115">Visual Studio saves all source-code files with the current ANSI code page by default, unless the user specifies another encoding in the **Encoding** dialog box.</span></span> <span data-ttu-id="6b14d-116">Visual Studio использует диалоговое окно **Кодировка** для открытия файлов исходного кода, сохраненных с другой кодовой страницей.</span><span class="sxs-lookup"><span data-stu-id="6b14d-116">Visual Studio uses the **Encoding** dialog box to open source-code files saved with a different code page.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6b14d-117">Параметр `-codepage` недоступен в среде разработки Visual Studio; Он доступен только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="6b14d-117">The `-codepage` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b14d-118">См. также</span><span class="sxs-lookup"><span data-stu-id="6b14d-118">See also</span></span>

- [<span data-ttu-id="6b14d-119">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="6b14d-119">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
