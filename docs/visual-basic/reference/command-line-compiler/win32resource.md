---
title: /win32resource
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- /win32resource
- win32resource
helpviewer_keywords:
- /win32resource compiler option [Visual Basic]
- -win32resource compiler option [Visual Basic]
- win32resource compiler option [Visual Basic]
ms.assetid: e226946d-19ce-4cc9-91f5-aed24f77aa2b
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d839b1100b1ae76fbd4653ebc60c79db11b77685
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="win32resource"></a><span data-ttu-id="d8dac-102">/win32resource</span><span class="sxs-lookup"><span data-stu-id="d8dac-102">/win32resource</span></span>
<span data-ttu-id="d8dac-103">Вставляет файл ресурсов Win32 в выходной файл.</span><span class="sxs-lookup"><span data-stu-id="d8dac-103">Inserts a Win32 resource file in the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8dac-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d8dac-104">Syntax</span></span>  
  
```  
/win32resource:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="d8dac-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="d8dac-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="d8dac-106">Имя файла ресурсов, чтобы добавить в выходной файл.</span><span class="sxs-lookup"><span data-stu-id="d8dac-106">The name of the resource file to add to your output file.</span></span> <span data-ttu-id="d8dac-107">Заключите имя файла в кавычки (» «), если он содержит пробелы.</span><span class="sxs-lookup"><span data-stu-id="d8dac-107">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d8dac-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="d8dac-108">Remarks</span></span>  
 <span data-ttu-id="d8dac-109">С помощью компилятора ресурсов Microsoft Windows (RC) можно создать файл ресурсов Win32.</span><span class="sxs-lookup"><span data-stu-id="d8dac-109">You can create a Win32 resource file with the Microsoft Windows Resource Compiler (RC).</span></span>  
  
 <span data-ttu-id="d8dac-110">Ресурс Win32 может содержать версию или точечный рисунок (значок) информацию, помогающую идентификации приложения в **проводнике**.</span><span class="sxs-lookup"><span data-stu-id="d8dac-110">A Win32 resource can contain version or bitmap (icon) information that helps identify your application in **File Explorer**.</span></span> <span data-ttu-id="d8dac-111">Если вы не укажете `/win32resource`, компилятор создает сведения о версии на основе версии сборки.</span><span class="sxs-lookup"><span data-stu-id="d8dac-111">If you do not specify `/win32resource`, the compiler generates version information based on the assembly version.</span></span> <span data-ttu-id="d8dac-112">`/win32resource` И `/win32icon` являются взаимоисключающими.</span><span class="sxs-lookup"><span data-stu-id="d8dac-112">The `/win32resource` and `/win32icon` options are mutually exclusive.</span></span>  
  
 <span data-ttu-id="d8dac-113">В разделе [/linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) ссылка [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] файла ресурсов или [/Resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) для присоединения [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] файла ресурсов.</span><span class="sxs-lookup"><span data-stu-id="d8dac-113">See [/linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) to reference a [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] resource file, or [/resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) to attach a [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] resource file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d8dac-114">`/win32resource` Параметр недоступен в среде разработки Visual Studio; она доступна только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="d8dac-114">The `/win32resource` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d8dac-115">Пример</span><span class="sxs-lookup"><span data-stu-id="d8dac-115">Example</span></span>  
 <span data-ttu-id="d8dac-116">Следующий код компилирует `In.vb` и присоединяет файл ресурсов Win32 `Rf.res`:</span><span class="sxs-lookup"><span data-stu-id="d8dac-116">The following code compiles `In.vb` and attaches a Win32 resource file, `Rf.res`:</span></span>  
  
```  
vbc /win32resource:rf.res in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="d8dac-117">См. также</span><span class="sxs-lookup"><span data-stu-id="d8dac-117">See Also</span></span>  
 [<span data-ttu-id="d8dac-118">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="d8dac-118">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="d8dac-119">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="d8dac-119">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
