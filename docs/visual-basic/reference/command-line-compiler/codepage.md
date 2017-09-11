---
title: "/ codepage (Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- /codepage compiler option [Visual Basic]
- codepage compiler option [Visual Basic]
- -codepage compiler option [Visual Basic]
ms.assetid: be36ec33-6800-4505-838c-4124564f5cc9
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 6f4919bc4fc8eda700edbd80fead5b5d9fe0dba1
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="codepage-visual-basic"></a><span data-ttu-id="fd205-102">/codepage (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fd205-102">/codepage (Visual Basic)</span></span>
<span data-ttu-id="fd205-103">Задает кодовую страницу, используемую для всех файлов исходного кода при компиляции.</span><span class="sxs-lookup"><span data-stu-id="fd205-103">Specifies the code page to use for all source-code files in the compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd205-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fd205-104">Syntax</span></span>  
  
```  
/codepage:id  
```  
  
## <a name="arguments"></a><span data-ttu-id="fd205-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="fd205-105">Arguments</span></span>  
  
|<span data-ttu-id="fd205-106">Термин</span><span class="sxs-lookup"><span data-stu-id="fd205-106">Term</span></span>|<span data-ttu-id="fd205-107">Определение</span><span class="sxs-lookup"><span data-stu-id="fd205-107">Definition</span></span>|  
|---|---|  
|`id`|<span data-ttu-id="fd205-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="fd205-108">Required.</span></span> <span data-ttu-id="fd205-109">Компилятор использует кодовую страницу, определяемую по `id` для интерпретации кодировки исходных файлов.</span><span class="sxs-lookup"><span data-stu-id="fd205-109">The compiler uses the code page specified by `id` to interpret the encoding of the source files.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fd205-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="fd205-110">Remarks</span></span>  
 <span data-ttu-id="fd205-111">Для компиляции исходного кода, сохраненного в определенной кодировке, можно использовать `/codepage` для указания того, какая кодовая страница должна использоваться.</span><span class="sxs-lookup"><span data-stu-id="fd205-111">To compile source code saved with a specific encoding, you can use `/codepage` to specify which code page should be used.</span></span> <span data-ttu-id="fd205-112">`/codepage` Параметр применяется ко всем файлам исходного кода при компиляции.</span><span class="sxs-lookup"><span data-stu-id="fd205-112">The `/codepage` option applies to all source-code files in your compilation.</span></span> <span data-ttu-id="fd205-113">Дополнительные сведения см. в разделе [кодировку символов, в .NET Framework](http://msdn.microsoft.com/library/bf6d9823-4c2d-48af-b280-919c5af66ae9).</span><span class="sxs-lookup"><span data-stu-id="fd205-113">For more information, see [Character Encoding in the .NET Framework](http://msdn.microsoft.com/library/bf6d9823-4c2d-48af-b280-919c5af66ae9).</span></span>  
  
 <span data-ttu-id="fd205-114">`/codepage` Не нужен, если файлы исходного кода были сохранены с помощью текущей кодовой страницы ANSI, Юникод или UTF-8 с подписью.</span><span class="sxs-lookup"><span data-stu-id="fd205-114">The `/codepage` option is not needed if the source-code files were saved using the current ANSI code page, Unicode, or UTF-8 with a signature.</span></span> [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]<span data-ttu-id="fd205-115">сохраняет все файлы исходного кода с текущей кодовой страницы ANSI по умолчанию, если пользователь не указывает другую кодировку в **кодировка** диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="fd205-115"> saves all source-code files with the current ANSI code page by default, unless the user specifies another encoding in the **Encoding** dialog box.</span></span> [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]<span data-ttu-id="fd205-116">использует **кодировка** диалоговое окно открытия файлов исходного кода, сохраненных с другой кодовой страницей.</span><span class="sxs-lookup"><span data-stu-id="fd205-116"> uses the **Encoding** dialog box to open source-code files saved with a different code page.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fd205-117">`/codepage` Параметр не доступен в [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] среде разработки; он доступен только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="fd205-117">The `/codepage` option is not available from within the [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd205-118">См. также</span><span class="sxs-lookup"><span data-stu-id="fd205-118">See Also</span></span>  
 [<span data-ttu-id="fd205-119">Компилятор командной строки Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fd205-119">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
