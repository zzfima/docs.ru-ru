---
title: -sdkpath
ms.date: 07/20/2015
f1_keywords:
- sdkpath
- -sdkpath
helpviewer_keywords:
- -sdkpath compiler option [Visual Basic]
- /sdkpath compiler option [Visual Basic]
- sdkpath compiler option [Visual Basic]
ms.assetid: fec8a3f1-b791-4a37-8af7-344859f8212d
ms.openlocfilehash: 46cec7ac3cb78c4fc97e299535f9085eff6daeff
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004690"
---
# <a name="-sdkpath"></a><span data-ttu-id="b20ed-102">-sdkpath</span><span class="sxs-lookup"><span data-stu-id="b20ed-102">-sdkpath</span></span>
<span data-ttu-id="b20ed-103">Указывает расположение библиотеки mscorlib. dll и Microsoft. VisualBasic. dll.</span><span class="sxs-lookup"><span data-stu-id="b20ed-103">Specifies the location of mscorlib.dll and Microsoft.VisualBasic.dll.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b20ed-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b20ed-104">Syntax</span></span>  
  
```console  
-sdkpath:path  
```  
  
## <a name="arguments"></a><span data-ttu-id="b20ed-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="b20ed-105">Arguments</span></span>  
 `path`  
 <span data-ttu-id="b20ed-106">Каталог, содержащий версии mscorlib. dll и Microsoft. VisualBasic. dll, используемые для компиляции.</span><span class="sxs-lookup"><span data-stu-id="b20ed-106">The directory containing the versions of mscorlib.dll and Microsoft.VisualBasic.dll to use for compilation.</span></span> <span data-ttu-id="b20ed-107">Этот путь не проверяется до загрузки.</span><span class="sxs-lookup"><span data-stu-id="b20ed-107">This path is not verified until it is loaded.</span></span> <span data-ttu-id="b20ed-108">Заключите имя каталога в кавычки (""), если оно содержит пробел.</span><span class="sxs-lookup"><span data-stu-id="b20ed-108">Enclose the directory name in quotation marks (" ") if it contains a space.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b20ed-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="b20ed-109">Remarks</span></span>  
 <span data-ttu-id="b20ed-110">Этот параметр указывает компилятору Visual Basic загрузить файлы mscorlib. dll и Microsoft. VisualBasic. dll из расположения, отличного от используемого по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b20ed-110">This option tells the Visual Basic compiler to load the mscorlib.dll and Microsoft.VisualBasic.dll files from a non-default location.</span></span> <span data-ttu-id="b20ed-111">Параметр `-sdkpath` разработан для использования с параметром [-netcf](../../../visual-basic/reference/command-line-compiler/netcf.md).</span><span class="sxs-lookup"><span data-stu-id="b20ed-111">The `-sdkpath` option was designed to be used with [-netcf](../../../visual-basic/reference/command-line-compiler/netcf.md).</span></span> <span data-ttu-id="b20ed-112">.NET Compact Framework использует различные версии этих библиотек поддержки, чтобы избежать использования типов и функций языка, не найденных на устройствах.</span><span class="sxs-lookup"><span data-stu-id="b20ed-112">The .NET Compact Framework uses different versions of these support libraries to avoid the use of types and language features not found on the devices.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b20ed-113">Параметр `-sdkpath` недоступен в среде разработки Visual Studio; Он доступен только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="b20ed-113">The `-sdkpath` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span> <span data-ttu-id="b20ed-114">Параметр `-sdkpath` задается при загрузке проекта Visual Basic устройства.</span><span class="sxs-lookup"><span data-stu-id="b20ed-114">The `-sdkpath` option is set when a Visual Basic device project is loaded.</span></span>  
  
 <span data-ttu-id="b20ed-115">Можно указать, что компилятор должен компилироваться без ссылки на библиотеку времени выполнения Visual Basic с помощью параметра компилятора `-vbruntime`.</span><span class="sxs-lookup"><span data-stu-id="b20ed-115">You can specify that the compiler should compile without a reference to the Visual Basic Runtime Library by using the `-vbruntime` compiler option.</span></span> <span data-ttu-id="b20ed-116">Дополнительные сведения см. в разделе [-вбрунтиме](../../../visual-basic/reference/command-line-compiler/vbruntime.md).</span><span class="sxs-lookup"><span data-stu-id="b20ed-116">For more information, see [-vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b20ed-117">Пример</span><span class="sxs-lookup"><span data-stu-id="b20ed-117">Example</span></span>  
 <span data-ttu-id="b20ed-118">Следующий код компилирует `Myfile.vb` с .NET Compact Framework, используя версии mscorlib. dll и Microsoft. VisualBasic. dll, найденные в .NET Compact Framework каталоге установки по умолчанию на диске C.</span><span class="sxs-lookup"><span data-stu-id="b20ed-118">The following code compiles `Myfile.vb` with the .NET Compact Framework, using the versions of Mscorlib.dll and Microsoft.VisualBasic.dll found in the default installation directory of the .NET Compact Framework on the C drive.</span></span> <span data-ttu-id="b20ed-119">Как правило, используется самая последняя версия .NET Compact Framework.</span><span class="sxs-lookup"><span data-stu-id="b20ed-119">Typically, you would use the most recent version of the .NET Compact Framework.</span></span>  
  
```console
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="b20ed-120">См. также</span><span class="sxs-lookup"><span data-stu-id="b20ed-120">See also</span></span>

- [<span data-ttu-id="b20ed-121">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="b20ed-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="b20ed-122">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="b20ed-122">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="b20ed-123">-netcf</span><span class="sxs-lookup"><span data-stu-id="b20ed-123">-netcf</span></span>](../../../visual-basic/reference/command-line-compiler/netcf.md)
- [<span data-ttu-id="b20ed-124">-vbruntime</span><span class="sxs-lookup"><span data-stu-id="b20ed-124">-vbruntime</span></span>](../../../visual-basic/reference/command-line-compiler/vbruntime.md)
