---
title: -filealign
ms.date: 03/10/2018
helpviewer_keywords:
- sections compiler option [Visual Basic]
- alignment compiler option [Visual Basic]
- -filealign compiler option [Visual Basic]
- section alignment
- /filealign compiler option [Visual Basic]
- filealign compiler option [Visual Basic]
ms.assetid: cc61ec3d-ad38-4b28-9659-099d73cad099
ms.openlocfilehash: 2893c1760a856a7d736e9c03ba33d9771722b5b2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69929476"
---
# <a name="-filealign"></a><span data-ttu-id="1163e-102">-filealign</span><span class="sxs-lookup"><span data-stu-id="1163e-102">-filealign</span></span>
<span data-ttu-id="1163e-103">Задает выравнивание размеров выходного файла.</span><span class="sxs-lookup"><span data-stu-id="1163e-103">Specifies where to align the sections of the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1163e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1163e-104">Syntax</span></span>  
  
```  
-filealign:number  
```  
  
## <a name="arguments"></a><span data-ttu-id="1163e-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="1163e-105">Arguments</span></span>  
 `number`  
 <span data-ttu-id="1163e-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="1163e-106">Required.</span></span> <span data-ttu-id="1163e-107">Значение, указывающее выравнивание разделов в выходном файле.</span><span class="sxs-lookup"><span data-stu-id="1163e-107">A value that specifies the alignment of sections in the output file.</span></span> <span data-ttu-id="1163e-108">Допустимые значения: 512, 1024, 2048, 4096 и 8192.</span><span class="sxs-lookup"><span data-stu-id="1163e-108">Valid values are 512, 1024, 2048, 4096, and 8192.</span></span> <span data-ttu-id="1163e-109">Эти значения указаны в байтах.</span><span class="sxs-lookup"><span data-stu-id="1163e-109">These values are in bytes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1163e-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="1163e-110">Remarks</span></span>  
 <span data-ttu-id="1163e-111">С помощью `-filealign` параметра можно указать выравнивание разделов в выходном файле.</span><span class="sxs-lookup"><span data-stu-id="1163e-111">You can use the `-filealign` option to specify the alignment of sections in your output file.</span></span> <span data-ttu-id="1163e-112">Разделы — это блоки непрерывной памяти в переносимом исполняемом (PE) файле, содержащем либо код, либо данные.</span><span class="sxs-lookup"><span data-stu-id="1163e-112">Sections are blocks of contiguous memory in a Portable Executable (PE) file that contains either code or data.</span></span> <span data-ttu-id="1163e-113">`-filealign` Параметр позволяет компилировать приложение с нестандартным выравниванием; большинству разработчиков не нужно использовать этот параметр.</span><span class="sxs-lookup"><span data-stu-id="1163e-113">The `-filealign` option lets you compile your application with a nonstandard alignment; most developers do not need to use this option.</span></span>  
  
 <span data-ttu-id="1163e-114">Каждый раздел соответствует границе, кратной `-filealign` значению.</span><span class="sxs-lookup"><span data-stu-id="1163e-114">Each section is aligned on a boundary that is a multiple of the `-filealign` value.</span></span> <span data-ttu-id="1163e-115">Фиксированный размер по умолчанию не предусмотрен.</span><span class="sxs-lookup"><span data-stu-id="1163e-115">There is no fixed default.</span></span> <span data-ttu-id="1163e-116">Если `-filealign` параметр не указан, компилятор выбирает значение по умолчанию во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="1163e-116">If `-filealign` is not specified, the compiler picks a default at compile time.</span></span>  
  
 <span data-ttu-id="1163e-117">Указав размер раздела, можно изменить размер выходного файла.</span><span class="sxs-lookup"><span data-stu-id="1163e-117">By specifying the section size, you can change the size of the output file.</span></span> <span data-ttu-id="1163e-118">Изменение размера раздела может применяться для программ, выполняющихся на небольших устройствах.</span><span class="sxs-lookup"><span data-stu-id="1163e-118">Modifying section size may be useful for programs that will run on smaller devices.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1163e-119">Этот `-filealign` параметр недоступен в среде разработки Visual Studio; он доступен только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="1163e-119">The `-filealign` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1163e-120">См. также</span><span class="sxs-lookup"><span data-stu-id="1163e-120">See also</span></span>

- [<span data-ttu-id="1163e-121">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="1163e-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
