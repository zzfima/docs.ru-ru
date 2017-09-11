---
title: "/ win32resource | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /win32resource
- win32resource
dev_langs:
- VB
helpviewer_keywords:
- /win32resource compiler option [Visual Basic]
- -win32resource compiler option [Visual Basic]
- win32resource compiler option [Visual Basic]
ms.assetid: e226946d-19ce-4cc9-91f5-aed24f77aa2b
caps.latest.revision: 13
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
ms.openlocfilehash: dc6bbb5948a5dd505f0fc4d1c8a86650214d657a
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="win32resource"></a><span data-ttu-id="318ca-102">/win32resource</span><span class="sxs-lookup"><span data-stu-id="318ca-102">/win32resource</span></span>
<span data-ttu-id="318ca-103">Вставляет файл ресурсов Win32 в выходной файл.</span><span class="sxs-lookup"><span data-stu-id="318ca-103">Inserts a Win32 resource file in the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="318ca-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="318ca-104">Syntax</span></span>  
  
```  
/win32resource:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="318ca-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="318ca-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="318ca-106">Имя файла ресурсов для добавления в выходной файл.</span><span class="sxs-lookup"><span data-stu-id="318ca-106">The name of the resource file to add to your output file.</span></span> <span data-ttu-id="318ca-107">Заключите имя файла в кавычки («»), если он содержит пробел.</span><span class="sxs-lookup"><span data-stu-id="318ca-107">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="318ca-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="318ca-108">Remarks</span></span>  
 <span data-ttu-id="318ca-109">Можно создать файл ресурсов Win32 с помощью компилятора ресурсов Microsoft Windows (RC).</span><span class="sxs-lookup"><span data-stu-id="318ca-109">You can create a Win32 resource file with the Microsoft Windows Resource Compiler (RC).</span></span>  
  
 <span data-ttu-id="318ca-110">Ресурс Win32 может содержать версию или растровое изображение (значок) сведения для идентификации приложения в **проводнике**.</span><span class="sxs-lookup"><span data-stu-id="318ca-110">A Win32 resource can contain version or bitmap (icon) information that helps identify your application in **File Explorer**.</span></span> <span data-ttu-id="318ca-111">Если вы не укажете `/win32resource`, компилятор создает сведения о версии на основе версии сборки.</span><span class="sxs-lookup"><span data-stu-id="318ca-111">If you do not specify `/win32resource`, the compiler generates version information based on the assembly version.</span></span> <span data-ttu-id="318ca-112">`/win32resource` И `/win32icon` являются взаимоисключающими.</span><span class="sxs-lookup"><span data-stu-id="318ca-112">The `/win32resource` and `/win32icon` options are mutually exclusive.</span></span>  
  
 <span data-ttu-id="318ca-113">В разделе [/linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) ссылка [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] файл ресурсов или [/Resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) присоединить [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] файла ресурсов.</span><span class="sxs-lookup"><span data-stu-id="318ca-113">See [/linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) to reference a [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] resource file, or [/resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) to attach a [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] resource file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="318ca-114">`/win32resource` Параметр недоступен из среды разработки Visual Studio; она доступна только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="318ca-114">The `/win32resource` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="318ca-115">Пример</span><span class="sxs-lookup"><span data-stu-id="318ca-115">Example</span></span>  
 <span data-ttu-id="318ca-116">Следующий код компилирует `In.vb` и присоединяет файл ресурсов Win32 `Rf.res`:</span><span class="sxs-lookup"><span data-stu-id="318ca-116">The following code compiles `In.vb` and attaches a Win32 resource file, `Rf.res`:</span></span>  
  
```  
vbc /win32resource:rf.res in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="318ca-117">См. также</span><span class="sxs-lookup"><span data-stu-id="318ca-117">See Also</span></span>  
 <span data-ttu-id="318ca-118">[Компилятор командной строки Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="318ca-118">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="318ca-119"> [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="318ca-119"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>
