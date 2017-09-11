---
title: "/ sdkpath | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- sdkpath
- /sdkpath
dev_langs:
- VB
helpviewer_keywords:
- -sdkpath compiler option [Visual Basic]
- /sdkpath compiler option [Visual Basic]
- sdkpath compiler option [Visual Basic]
ms.assetid: fec8a3f1-b791-4a37-8af7-344859f8212d
caps.latest.revision: 15
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
ms.openlocfilehash: 2e32bb403347063edcf0d47fd4a7511a0da1f340
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="sdkpath"></a><span data-ttu-id="243d6-102">/sdkpath</span><span class="sxs-lookup"><span data-stu-id="243d6-102">/sdkpath</span></span>
<span data-ttu-id="243d6-103">Задает расположение библиотек mscorlib.dll и microsoft.visualbasic.dll.</span><span class="sxs-lookup"><span data-stu-id="243d6-103">Specifies the location of Mscorlib.dll and Microsoft.VisualBasic.dll.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="243d6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="243d6-104">Syntax</span></span>  
  
```  
/sdkpath:path  
```  
  
## <a name="arguments"></a><span data-ttu-id="243d6-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="243d6-105">Arguments</span></span>  
 `path`  
 <span data-ttu-id="243d6-106">Каталог, содержащий версии Mscorlib.dll и Microsoft.VisualBasic.dll, используемые при компиляции.</span><span class="sxs-lookup"><span data-stu-id="243d6-106">The directory containing the versions of Mscorlib.dll and Microsoft.VisualBasic.dll to use for compilation.</span></span> <span data-ttu-id="243d6-107">Этот путь не проверяется до загрузки.</span><span class="sxs-lookup"><span data-stu-id="243d6-107">This path is not verified until it is loaded.</span></span> <span data-ttu-id="243d6-108">Заключите имя каталога в кавычки (» «), если он содержит пробел.</span><span class="sxs-lookup"><span data-stu-id="243d6-108">Enclose the directory name in quotation marks (" ") if it contains a space.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="243d6-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="243d6-109">Remarks</span></span>  
 <span data-ttu-id="243d6-110">Этот параметр указывает [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] компилятору загрузить файлы Mscorlib.dll и Microsoft.VisualBasic.dll из расположения, не по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="243d6-110">This option tells the [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler to load the Mscorlib.dll and Microsoft.VisualBasic.dll files from a non-default location.</span></span> <span data-ttu-id="243d6-111">`/sdkpath` Параметр был разработан для использования с [/netcf](../../../visual-basic/reference/command-line-compiler/netcf.md).</span><span class="sxs-lookup"><span data-stu-id="243d6-111">The `/sdkpath` option was designed to be used with [/netcf](../../../visual-basic/reference/command-line-compiler/netcf.md).</span></span> <span data-ttu-id="243d6-112">[!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)] Применяются различные версии поддерживаемых библиотек, чтобы избежать использования типов и функций языка не найден на устройствах.</span><span class="sxs-lookup"><span data-stu-id="243d6-112">The [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)] uses different versions of these support libraries to avoid the use of types and language features not found on the devices.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="243d6-113">`/sdkpath` Параметр недоступен из среды разработки Visual Studio; она доступна только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="243d6-113">The `/sdkpath` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span> <span data-ttu-id="243d6-114">`/sdkpath` Параметр задается при [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] загрузке проекта устройства.</span><span class="sxs-lookup"><span data-stu-id="243d6-114">The `/sdkpath` option is set when a [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] device project is loaded.</span></span>  
  
 <span data-ttu-id="243d6-115">Можно указать, что компилятор должен выполнять компиляцию без ссылки на библиотеку времени выполнения Visual Basic с помощью `/vbruntime` параметр компилятора.</span><span class="sxs-lookup"><span data-stu-id="243d6-115">You can specify that the compiler should compile without a reference to the Visual Basic Runtime Library by using the `/vbruntime` compiler option.</span></span> <span data-ttu-id="243d6-116">Дополнительные сведения см. в разделе [/vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md).</span><span class="sxs-lookup"><span data-stu-id="243d6-116">For more information, see [/vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="243d6-117">Пример</span><span class="sxs-lookup"><span data-stu-id="243d6-117">Example</span></span>  
 <span data-ttu-id="243d6-118">Следующий код компилирует `Myfile.vb` с [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)], с помощью версии Mscorlib.dll и Microsoft.VisualBasic.dll найти в каталоге установки по умолчанию [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)] на диске C:.</span><span class="sxs-lookup"><span data-stu-id="243d6-118">The following code compiles `Myfile.vb` with the [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)], using the versions of Mscorlib.dll and Microsoft.VisualBasic.dll found in the default installation directory of the [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)] on the C drive.</span></span> <span data-ttu-id="243d6-119">Как правило, используется последней версии [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)].</span><span class="sxs-lookup"><span data-stu-id="243d6-119">Typically, you would use the most recent version of the [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)].</span></span>  
  
```  
vbc /netcf /sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="243d6-120">См. также</span><span class="sxs-lookup"><span data-stu-id="243d6-120">See Also</span></span>  
 <span data-ttu-id="243d6-121">[Компилятор командной строки Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="243d6-121">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="243d6-122"> [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="243d6-122"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="243d6-123"> [/ netcf](../../../visual-basic/reference/command-line-compiler/netcf.md) </span><span class="sxs-lookup"><span data-stu-id="243d6-123"> [/netcf](../../../visual-basic/reference/command-line-compiler/netcf.md) </span></span>  
<span data-ttu-id="243d6-124"> [/vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md)</span><span class="sxs-lookup"><span data-stu-id="243d6-124"> [/vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md)</span></span>
