---
title: "/ filealign | Документы Microsoft"
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
- sections compiler option [Visual Basic]
- alignment compiler option [Visual Basic]
- -filealign compiler option [Visual Basic]
- section alignment
- /filealign compiler option [Visual Basic]
- filealign compiler option [Visual Basic]
ms.assetid: cc61ec3d-ad38-4b28-9659-099d73cad099
caps.latest.revision: 14
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
ms.openlocfilehash: 5e0cd0a2a7e4c88df1087faee963f541c325b272
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="filealign"></a><span data-ttu-id="5ece3-102">/filealign</span><span class="sxs-lookup"><span data-stu-id="5ece3-102">/filealign</span></span>
<span data-ttu-id="5ece3-103">Задает выравнивание размеров выходного файла.</span><span class="sxs-lookup"><span data-stu-id="5ece3-103">Specifies where to align the sections of the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ece3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5ece3-104">Syntax</span></span>  
  
```  
/filealign:number  
```  
  
## <a name="arguments"></a><span data-ttu-id="5ece3-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="5ece3-105">Arguments</span></span>  
 `number`  
 <span data-ttu-id="5ece3-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="5ece3-106">Required.</span></span> <span data-ttu-id="5ece3-107">Значение, задающее выравнивание разделов в выходном файле.</span><span class="sxs-lookup"><span data-stu-id="5ece3-107">A value that specifies the alignment of sections in the output file.</span></span> <span data-ttu-id="5ece3-108">Допустимые значения: 512, 1024, 2048, 4096 и 8192.</span><span class="sxs-lookup"><span data-stu-id="5ece3-108">Valid values are 512, 1024, 2048, 4096, and 8192.</span></span> <span data-ttu-id="5ece3-109">Эти значения задаются в байтах.</span><span class="sxs-lookup"><span data-stu-id="5ece3-109">These values are in bytes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5ece3-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="5ece3-110">Remarks</span></span>  
 <span data-ttu-id="5ece3-111">Можно использовать `/filealign` возможность задать выравнивание разделов в выходном файле.</span><span class="sxs-lookup"><span data-stu-id="5ece3-111">You can use the `/filealign` option to specify the alignment of sections in your output file.</span></span> <span data-ttu-id="5ece3-112">Разделы являются блоками непрерывной памяти в переносимых исполняемых (PE) файле, который содержит код или данные.</span><span class="sxs-lookup"><span data-stu-id="5ece3-112">Sections are blocks of contiguous memory in a Portable Executable (PE) file that contains either code or data.</span></span> <span data-ttu-id="5ece3-113">`/filealign` Позволяет скомпилировать приложение с нестандартным выравниванием; большинство разработчиков не требуется использовать этот параметр.</span><span class="sxs-lookup"><span data-stu-id="5ece3-113">The `/filealign` option lets you compile your application with a nonstandard alignment; most developers do not need to use this option.</span></span>  
  
 <span data-ttu-id="5ece3-114">Каждый раздел выравнивается по границе, кратной `/filealign` значение.</span><span class="sxs-lookup"><span data-stu-id="5ece3-114">Each section is aligned on a boundary that is a multiple of the `/filealign` value.</span></span> <span data-ttu-id="5ece3-115">Фиксированный по умолчанию отсутствует.</span><span class="sxs-lookup"><span data-stu-id="5ece3-115">There is no fixed default.</span></span> <span data-ttu-id="5ece3-116">Если `/filealign` не указан, компилятор выбирает значение по умолчанию во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="5ece3-116">If `/filealign` is not specified, the compiler picks a default at compile time.</span></span>  
  
 <span data-ttu-id="5ece3-117">Указав размер раздела, можно изменить размер выходного файла.</span><span class="sxs-lookup"><span data-stu-id="5ece3-117">By specifying the section size, you can change the size of the output file.</span></span> <span data-ttu-id="5ece3-118">Изменение размера раздела может применяться для программ, выполняющихся на небольших устройствах.</span><span class="sxs-lookup"><span data-stu-id="5ece3-118">Modifying section size may be useful for programs that will run on smaller devices.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5ece3-119">`/filealign` Параметр недоступен из среды разработки Visual Studio; она доступна только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="5ece3-119">The `/filealign` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ece3-120">См. также</span><span class="sxs-lookup"><span data-stu-id="5ece3-120">See Also</span></span>  
 [<span data-ttu-id="5ece3-121">Компилятор командной строки Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5ece3-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
