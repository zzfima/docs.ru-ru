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
ms.openlocfilehash: 382dcc6571aa06ecdfc32bf43080c4b7a36eb1f0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69961305"
---
# <a name="-win32resource"></a><span data-ttu-id="6eb03-102">-win32resource</span><span class="sxs-lookup"><span data-stu-id="6eb03-102">-win32resource</span></span>
<span data-ttu-id="6eb03-103">Вставляет файл ресурсов Win32 в выходной файл.</span><span class="sxs-lookup"><span data-stu-id="6eb03-103">Inserts a Win32 resource file in the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6eb03-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6eb03-104">Syntax</span></span>  
  
```  
-win32resource:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="6eb03-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="6eb03-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="6eb03-106">Имя файла ресурсов, добавляемого в выходной файл.</span><span class="sxs-lookup"><span data-stu-id="6eb03-106">The name of the resource file to add to your output file.</span></span> <span data-ttu-id="6eb03-107">Заключите имя файла в кавычки (""), если оно содержит пробел.</span><span class="sxs-lookup"><span data-stu-id="6eb03-107">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6eb03-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="6eb03-108">Remarks</span></span>  
 <span data-ttu-id="6eb03-109">Вы можете создать файл ресурсов Win32 с помощью компилятора ресурсов Microsoft Windows (RC).</span><span class="sxs-lookup"><span data-stu-id="6eb03-109">You can create a Win32 resource file with the Microsoft Windows Resource Compiler (RC).</span></span>  
  
 <span data-ttu-id="6eb03-110">Ресурс Win32 может содержать сведения о версии или битовой карте (значок), которые помогают в определении приложения в **проводнике**.</span><span class="sxs-lookup"><span data-stu-id="6eb03-110">A Win32 resource can contain version or bitmap (icon) information that helps identify your application in **File Explorer**.</span></span> <span data-ttu-id="6eb03-111">Если не указать `-win32resource`, компилятор создает сведения о версии на основе версии сборки.</span><span class="sxs-lookup"><span data-stu-id="6eb03-111">If you do not specify `-win32resource`, the compiler generates version information based on the assembly version.</span></span> <span data-ttu-id="6eb03-112">Параметры `-win32resource` и`-win32icon` являются взаимоисключающими.</span><span class="sxs-lookup"><span data-stu-id="6eb03-112">The `-win32resource` and `-win32icon` options are mutually exclusive.</span></span>  
  
 <span data-ttu-id="6eb03-113">Чтобы присоединить файл ресурсов .NET Framework, см. раздел [-linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) для ссылки на файл ресурсов .NET Framework или [-Resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) .</span><span class="sxs-lookup"><span data-stu-id="6eb03-113">See [-linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) to reference a .NET Framework resource file, or [-resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) to attach a .NET Framework resource file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6eb03-114">Этот `-win32resource` параметр недоступен в среде разработки Visual Studio; он доступен только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="6eb03-114">The `-win32resource` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6eb03-115">Пример</span><span class="sxs-lookup"><span data-stu-id="6eb03-115">Example</span></span>  
 <span data-ttu-id="6eb03-116">Следующий код компилирует `In.vb` и присоединяет `Rf.res`файл ресурсов Win32:</span><span class="sxs-lookup"><span data-stu-id="6eb03-116">The following code compiles `In.vb` and attaches a Win32 resource file, `Rf.res`:</span></span>  
  
```console  
vbc -win32resource:rf.res in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="6eb03-117">См. также</span><span class="sxs-lookup"><span data-stu-id="6eb03-117">See also</span></span>

- [<span data-ttu-id="6eb03-118">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="6eb03-118">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="6eb03-119">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="6eb03-119">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
