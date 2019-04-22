---
title: -win32resource
ms.date: 03/13/2018
f1_keywords:
- -win32resource
- win32resource
helpviewer_keywords:
- /win32resource compiler option [Visual Basic]
- -win32resource compiler option [Visual Basic]
- win32resource compiler option [Visual Basic]
ms.assetid: e226946d-19ce-4cc9-91f5-aed24f77aa2b
ms.openlocfilehash: 9351e9f6bcb7660dac2c49667ca8db6d578eff7c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58835002"
---
# <a name="-win32resource"></a><span data-ttu-id="49741-102">-win32resource</span><span class="sxs-lookup"><span data-stu-id="49741-102">-win32resource</span></span>
<span data-ttu-id="49741-103">Вставляет файл ресурсов Win32 в выходной файл.</span><span class="sxs-lookup"><span data-stu-id="49741-103">Inserts a Win32 resource file in the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49741-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="49741-104">Syntax</span></span>  
  
```  
-win32resource:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="49741-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="49741-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="49741-106">Имя файла ресурсов для добавления в выходной файл.</span><span class="sxs-lookup"><span data-stu-id="49741-106">The name of the resource file to add to your output file.</span></span> <span data-ttu-id="49741-107">Заключите имя файла в кавычки (» «), если он содержит пробел.</span><span class="sxs-lookup"><span data-stu-id="49741-107">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="49741-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="49741-108">Remarks</span></span>  
 <span data-ttu-id="49741-109">Файл ресурсов Win32 можно создать с помощью компилятора ресурсов Microsoft Windows (RC).</span><span class="sxs-lookup"><span data-stu-id="49741-109">You can create a Win32 resource file with the Microsoft Windows Resource Compiler (RC).</span></span>  
  
 <span data-ttu-id="49741-110">Ресурс Win32 может содержать версии или точечный рисунок (значок) информацию о идентификации приложения в **проводнике**.</span><span class="sxs-lookup"><span data-stu-id="49741-110">A Win32 resource can contain version or bitmap (icon) information that helps identify your application in **File Explorer**.</span></span> <span data-ttu-id="49741-111">Если вы не укажете `-win32resource`, компилятор создает сведения о версии, на основе версии сборки.</span><span class="sxs-lookup"><span data-stu-id="49741-111">If you do not specify `-win32resource`, the compiler generates version information based on the assembly version.</span></span> <span data-ttu-id="49741-112">`-win32resource` И `-win32icon` параметры являются взаимно исключающими.</span><span class="sxs-lookup"><span data-stu-id="49741-112">The `-win32resource` and `-win32icon` options are mutually exclusive.</span></span>  
  
 <span data-ttu-id="49741-113">См. в разделе [- linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) ссылка [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] файл ресурсов или [-ресурсов (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) для присоединения [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] файла ресурсов.</span><span class="sxs-lookup"><span data-stu-id="49741-113">See [-linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) to reference a [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] resource file, or [-resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) to attach a [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] resource file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="49741-114">`-win32resource` Не доступна из среды разработки Visual Studio; она доступна только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="49741-114">The `-win32resource` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="49741-115">Пример</span><span class="sxs-lookup"><span data-stu-id="49741-115">Example</span></span>  
 <span data-ttu-id="49741-116">Следующий код компилирует `In.vb` и присоединяет файл ресурсов Win32 `Rf.res`:</span><span class="sxs-lookup"><span data-stu-id="49741-116">The following code compiles `In.vb` and attaches a Win32 resource file, `Rf.res`:</span></span>  
  
```console  
vbc -win32resource:rf.res in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="49741-117">См. также</span><span class="sxs-lookup"><span data-stu-id="49741-117">See also</span></span>

- [<span data-ttu-id="49741-118">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="49741-118">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="49741-119">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="49741-119">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
