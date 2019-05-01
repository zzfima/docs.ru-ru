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
ms.openlocfilehash: 9a844515a4596064937762ac05b850463f1b5e14
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62051706"
---
# <a name="-filealign"></a><span data-ttu-id="bc8bf-102">-filealign</span><span class="sxs-lookup"><span data-stu-id="bc8bf-102">-filealign</span></span>
<span data-ttu-id="bc8bf-103">Задает выравнивание размеров выходного файла.</span><span class="sxs-lookup"><span data-stu-id="bc8bf-103">Specifies where to align the sections of the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc8bf-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bc8bf-104">Syntax</span></span>  
  
```  
-filealign:number  
```  
  
## <a name="arguments"></a><span data-ttu-id="bc8bf-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="bc8bf-105">Arguments</span></span>  
 `number`  
 <span data-ttu-id="bc8bf-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="bc8bf-106">Required.</span></span> <span data-ttu-id="bc8bf-107">Значение, указывающее выравнивание разделов в выходном файле.</span><span class="sxs-lookup"><span data-stu-id="bc8bf-107">A value that specifies the alignment of sections in the output file.</span></span> <span data-ttu-id="bc8bf-108">Допустимые значения: 512, 1024, 2048, 4096 и 8192.</span><span class="sxs-lookup"><span data-stu-id="bc8bf-108">Valid values are 512, 1024, 2048, 4096, and 8192.</span></span> <span data-ttu-id="bc8bf-109">Эти значения указаны в байтах.</span><span class="sxs-lookup"><span data-stu-id="bc8bf-109">These values are in bytes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bc8bf-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="bc8bf-110">Remarks</span></span>  
 <span data-ttu-id="bc8bf-111">Можно использовать `-filealign` параметр, чтобы указать выравнивание разделов в выходном файле.</span><span class="sxs-lookup"><span data-stu-id="bc8bf-111">You can use the `-filealign` option to specify the alignment of sections in your output file.</span></span> <span data-ttu-id="bc8bf-112">Разделы являются блоками непрерывной памяти в переносимых исполняемых (PE) файл, содержащий код или данные.</span><span class="sxs-lookup"><span data-stu-id="bc8bf-112">Sections are blocks of contiguous memory in a Portable Executable (PE) file that contains either code or data.</span></span> <span data-ttu-id="bc8bf-113">`-filealign` Позволяет скомпилировать приложение с нестандартным выравниванием; большинство разработчиков не обязательно должны использовать этот параметр.</span><span class="sxs-lookup"><span data-stu-id="bc8bf-113">The `-filealign` option lets you compile your application with a nonstandard alignment; most developers do not need to use this option.</span></span>  
  
 <span data-ttu-id="bc8bf-114">Каждый раздел выравнивается по границе, кратной `-filealign` значение.</span><span class="sxs-lookup"><span data-stu-id="bc8bf-114">Each section is aligned on a boundary that is a multiple of the `-filealign` value.</span></span> <span data-ttu-id="bc8bf-115">Фиксированный размер по умолчанию не предусмотрен.</span><span class="sxs-lookup"><span data-stu-id="bc8bf-115">There is no fixed default.</span></span> <span data-ttu-id="bc8bf-116">Если `-filealign` не указан, компилятор выбирает значение по умолчанию во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="bc8bf-116">If `-filealign` is not specified, the compiler picks a default at compile time.</span></span>  
  
 <span data-ttu-id="bc8bf-117">Указывает размер раздела, можно изменить размер выходного файла.</span><span class="sxs-lookup"><span data-stu-id="bc8bf-117">By specifying the section size, you can change the size of the output file.</span></span> <span data-ttu-id="bc8bf-118">Изменение размера раздела может применяться для программ, выполняющихся на небольших устройствах.</span><span class="sxs-lookup"><span data-stu-id="bc8bf-118">Modifying section size may be useful for programs that will run on smaller devices.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bc8bf-119">`-filealign` Не доступна из среды разработки Visual Studio; она доступна только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="bc8bf-119">The `-filealign` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc8bf-120">См. также</span><span class="sxs-lookup"><span data-stu-id="bc8bf-120">See also</span></span>

- [<span data-ttu-id="bc8bf-121">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="bc8bf-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
