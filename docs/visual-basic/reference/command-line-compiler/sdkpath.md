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
ms.openlocfilehash: 2024ccadb06fdea0c24d9d304c2fe040f8cce1d5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61639066"
---
# <a name="-sdkpath"></a><span data-ttu-id="38c39-102">-sdkpath</span><span class="sxs-lookup"><span data-stu-id="38c39-102">-sdkpath</span></span>
<span data-ttu-id="38c39-103">Указывает расположение библиотек mscorlib.dll и Microsoft.VisualBasic.dll.</span><span class="sxs-lookup"><span data-stu-id="38c39-103">Specifies the location of mscorlib.dll and Microsoft.VisualBasic.dll.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38c39-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="38c39-104">Syntax</span></span>  
  
```  
-sdkpath:path  
```  
  
## <a name="arguments"></a><span data-ttu-id="38c39-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="38c39-105">Arguments</span></span>  
 `path`  
 <span data-ttu-id="38c39-106">Каталог, содержащий версии mscorlib.dll и Microsoft.VisualBasic.dll, используемые для компиляции.</span><span class="sxs-lookup"><span data-stu-id="38c39-106">The directory containing the versions of mscorlib.dll and Microsoft.VisualBasic.dll to use for compilation.</span></span> <span data-ttu-id="38c39-107">Этот путь не проверяется до его загрузки.</span><span class="sxs-lookup"><span data-stu-id="38c39-107">This path is not verified until it is loaded.</span></span> <span data-ttu-id="38c39-108">Заключите имя каталога в кавычки (» «), если он содержит пробел.</span><span class="sxs-lookup"><span data-stu-id="38c39-108">Enclose the directory name in quotation marks (" ") if it contains a space.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="38c39-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="38c39-109">Remarks</span></span>  
 <span data-ttu-id="38c39-110">Этот параметр указывает компилятору Visual Basic для загрузки библиотеки mscorlib.dll и Microsoft.VisualBasic.dll файлы из расположения не по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="38c39-110">This option tells the Visual Basic compiler to load the mscorlib.dll and Microsoft.VisualBasic.dll files from a non-default location.</span></span> <span data-ttu-id="38c39-111">`-sdkpath` Параметр был разработан для использования с [- netcf](../../../visual-basic/reference/command-line-compiler/netcf.md).</span><span class="sxs-lookup"><span data-stu-id="38c39-111">The `-sdkpath` option was designed to be used with [-netcf](../../../visual-basic/reference/command-line-compiler/netcf.md).</span></span> <span data-ttu-id="38c39-112">[!INCLUDE[Compact](~/includes/compact-md.md)] Применяются различные версии поддерживаемых библиотек, чтобы избежать использования типов и языковые компоненты, не найден на устройствах.</span><span class="sxs-lookup"><span data-stu-id="38c39-112">The [!INCLUDE[Compact](~/includes/compact-md.md)] uses different versions of these support libraries to avoid the use of types and language features not found on the devices.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="38c39-113">`-sdkpath` Не доступна из среды разработки Visual Studio; она доступна только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="38c39-113">The `-sdkpath` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span> <span data-ttu-id="38c39-114">`-sdkpath` Был установлен при загрузке проекта Visual Basic для устройства.</span><span class="sxs-lookup"><span data-stu-id="38c39-114">The `-sdkpath` option is set when a Visual Basic device project is loaded.</span></span>  
  
 <span data-ttu-id="38c39-115">Можно указать, что компилятор должен выполнять компиляцию без ссылки на библиотеку времени выполнения Visual Basic с помощью `-vbruntime` параметр компилятора.</span><span class="sxs-lookup"><span data-stu-id="38c39-115">You can specify that the compiler should compile without a reference to the Visual Basic Runtime Library by using the `-vbruntime` compiler option.</span></span> <span data-ttu-id="38c39-116">Дополнительные сведения см. в разделе [- vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md).</span><span class="sxs-lookup"><span data-stu-id="38c39-116">For more information, see [-vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="38c39-117">Пример</span><span class="sxs-lookup"><span data-stu-id="38c39-117">Example</span></span>  
 <span data-ttu-id="38c39-118">Следующий код компилирует `Myfile.vb` с [!INCLUDE[Compact](~/includes/compact-md.md)], с помощью версии библиотеки Mscorlib.dll и Microsoft.VisualBasic.dll см. в каталог установки по умолчанию для [!INCLUDE[Compact](~/includes/compact-md.md)] на диске C:.</span><span class="sxs-lookup"><span data-stu-id="38c39-118">The following code compiles `Myfile.vb` with the [!INCLUDE[Compact](~/includes/compact-md.md)], using the versions of Mscorlib.dll and Microsoft.VisualBasic.dll found in the default installation directory of the [!INCLUDE[Compact](~/includes/compact-md.md)] on the C drive.</span></span> <span data-ttu-id="38c39-119">Как правило, используется самую последнюю версию [!INCLUDE[Compact](~/includes/compact-md.md)].</span><span class="sxs-lookup"><span data-stu-id="38c39-119">Typically, you would use the most recent version of the [!INCLUDE[Compact](~/includes/compact-md.md)].</span></span>  
  
```console
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="38c39-120">См. также</span><span class="sxs-lookup"><span data-stu-id="38c39-120">See also</span></span>

- [<span data-ttu-id="38c39-121">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="38c39-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="38c39-122">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="38c39-122">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="38c39-123">-netcf</span><span class="sxs-lookup"><span data-stu-id="38c39-123">-netcf</span></span>](../../../visual-basic/reference/command-line-compiler/netcf.md)
- [<span data-ttu-id="38c39-124">-vbruntime</span><span class="sxs-lookup"><span data-stu-id="38c39-124">-vbruntime</span></span>](../../../visual-basic/reference/command-line-compiler/vbruntime.md)
