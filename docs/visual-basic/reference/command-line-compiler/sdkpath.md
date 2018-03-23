---
title: -sdkpath
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- sdkpath
- -sdkpath
helpviewer_keywords:
- -sdkpath compiler option [Visual Basic]
- /sdkpath compiler option [Visual Basic]
- sdkpath compiler option [Visual Basic]
ms.assetid: fec8a3f1-b791-4a37-8af7-344859f8212d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 53362c2eb5517d9230ea88975745315d6db7f1ba
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/22/2018
---
# <a name="-sdkpath"></a><span data-ttu-id="2ecda-102">-sdkpath</span><span class="sxs-lookup"><span data-stu-id="2ecda-102">-sdkpath</span></span>
<span data-ttu-id="2ecda-103">Указывает расположение библиотек mscorlib.dll и Microsoft.VisualBasic.dll.</span><span class="sxs-lookup"><span data-stu-id="2ecda-103">Specifies the location of mscorlib.dll and Microsoft.VisualBasic.dll.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ecda-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2ecda-104">Syntax</span></span>  
  
```  
-sdkpath:path  
```  
  
## <a name="arguments"></a><span data-ttu-id="2ecda-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="2ecda-105">Arguments</span></span>  
 `path`  
 <span data-ttu-id="2ecda-106">Каталог, содержащий версии mscorlib.dll и Microsoft.VisualBasic.dll, используемые при компиляции.</span><span class="sxs-lookup"><span data-stu-id="2ecda-106">The directory containing the versions of mscorlib.dll and Microsoft.VisualBasic.dll to use for compilation.</span></span> <span data-ttu-id="2ecda-107">Этот путь не проверяется до загрузки.</span><span class="sxs-lookup"><span data-stu-id="2ecda-107">This path is not verified until it is loaded.</span></span> <span data-ttu-id="2ecda-108">Заключите имя каталога в кавычки (» «), если он содержит пробелы.</span><span class="sxs-lookup"><span data-stu-id="2ecda-108">Enclose the directory name in quotation marks (" ") if it contains a space.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2ecda-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="2ecda-109">Remarks</span></span>  
 <span data-ttu-id="2ecda-110">При выборе этого параметра [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] компилятора для загрузки библиотеки mscorlib.dll и Microsoft.VisualBasic.dll файлов из расположения не по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2ecda-110">This option tells the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler to load the mscorlib.dll and Microsoft.VisualBasic.dll files from a non-default location.</span></span> <span data-ttu-id="2ecda-111">`-sdkpath` Параметр был разработан для использования с [- netcf](../../../visual-basic/reference/command-line-compiler/netcf.md).</span><span class="sxs-lookup"><span data-stu-id="2ecda-111">The `-sdkpath` option was designed to be used with [-netcf](../../../visual-basic/reference/command-line-compiler/netcf.md).</span></span> <span data-ttu-id="2ecda-112">[!INCLUDE[Compact](~/includes/compact-md.md)] Применяются различные версии поддерживаемых библиотек, чтобы избежать использования типы и функции языка, не найден на устройствах.</span><span class="sxs-lookup"><span data-stu-id="2ecda-112">The [!INCLUDE[Compact](~/includes/compact-md.md)] uses different versions of these support libraries to avoid the use of types and language features not found on the devices.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2ecda-113">`-sdkpath` Параметр недоступен в среде разработки Visual Studio; она доступна только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="2ecda-113">The `-sdkpath` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span> <span data-ttu-id="2ecda-114">`-sdkpath` Параметр задан, если [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] загрузке проекта устройства.</span><span class="sxs-lookup"><span data-stu-id="2ecda-114">The `-sdkpath` option is set when a [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] device project is loaded.</span></span>  
  
 <span data-ttu-id="2ecda-115">Можно указать, что компилятор должен выполнять компиляцию без ссылки на библиотеку времени выполнения Visual Basic с помощью `-vbruntime` параметр компилятора.</span><span class="sxs-lookup"><span data-stu-id="2ecda-115">You can specify that the compiler should compile without a reference to the Visual Basic Runtime Library by using the `-vbruntime` compiler option.</span></span> <span data-ttu-id="2ecda-116">Дополнительные сведения см. в разделе [- vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md).</span><span class="sxs-lookup"><span data-stu-id="2ecda-116">For more information, see [-vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2ecda-117">Пример</span><span class="sxs-lookup"><span data-stu-id="2ecda-117">Example</span></span>  
 <span data-ttu-id="2ecda-118">Следующий код компилирует `Myfile.vb` с [!INCLUDE[Compact](~/includes/compact-md.md)], с помощью версии Mscorlib.dll и Microsoft.VisualBasic.dll найден в каталоге установки по умолчанию для [!INCLUDE[Compact](~/includes/compact-md.md)] на диске C.</span><span class="sxs-lookup"><span data-stu-id="2ecda-118">The following code compiles `Myfile.vb` with the [!INCLUDE[Compact](~/includes/compact-md.md)], using the versions of Mscorlib.dll and Microsoft.VisualBasic.dll found in the default installation directory of the [!INCLUDE[Compact](~/includes/compact-md.md)] on the C drive.</span></span> <span data-ttu-id="2ecda-119">Обычно, следует использовать самую последнюю версию [!INCLUDE[Compact](~/includes/compact-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2ecda-119">Typically, you would use the most recent version of the [!INCLUDE[Compact](~/includes/compact-md.md)].</span></span>  
  
```console
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="2ecda-120">См. также</span><span class="sxs-lookup"><span data-stu-id="2ecda-120">See Also</span></span>  
 [<span data-ttu-id="2ecda-121">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="2ecda-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="2ecda-122">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="2ecda-122">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="2ecda-123">-netcf</span><span class="sxs-lookup"><span data-stu-id="2ecda-123">-netcf</span></span>](../../../visual-basic/reference/command-line-compiler/netcf.md)  
 [<span data-ttu-id="2ecda-124">-vbruntime</span><span class="sxs-lookup"><span data-stu-id="2ecda-124">-vbruntime</span></span>](../../../visual-basic/reference/command-line-compiler/vbruntime.md)
