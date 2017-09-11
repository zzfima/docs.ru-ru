---
title: "/ Reference (Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- /reference compiler option [Visual Basic]
- r compiler option [Visual Basic]
- -reference compiler option [Visual Basic]
- /r compiler option [Visual Basic]
- reference compiler option [Visual Basic]
- -r compiler option [Visual Basic]
ms.assetid: 66bdfced-bbf6-43d1-a554-bc0990315737
caps.latest.revision: 16
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
ms.openlocfilehash: 6870c0b6008124bad18f8eba9207d06e085f2307
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="reference-visual-basic"></a><span data-ttu-id="a27ba-102">/reference (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a27ba-102">/reference (Visual Basic)</span></span>
<span data-ttu-id="a27ba-103">Указывает компилятору сделать доступными для проекта, компилируемого в данный момент сведения о типе в указанных сборках.</span><span class="sxs-lookup"><span data-stu-id="a27ba-103">Causes the compiler to make type information in the specified assemblies available to the project you are currently compiling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a27ba-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a27ba-104">Syntax</span></span>  
  
```  
/reference:fileList  
' -or-  
/r:fileList  
```  
  
## <a name="arguments"></a><span data-ttu-id="a27ba-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="a27ba-105">Arguments</span></span>  
  
|<span data-ttu-id="a27ba-106">Термин</span><span class="sxs-lookup"><span data-stu-id="a27ba-106">Term</span></span>|<span data-ttu-id="a27ba-107">Определение</span><span class="sxs-lookup"><span data-stu-id="a27ba-107">Definition</span></span>|  
|---|---|  
|`fileList`|<span data-ttu-id="a27ba-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="a27ba-108">Required.</span></span> <span data-ttu-id="a27ba-109">Разделенный запятыми список имен файлов сборки.</span><span class="sxs-lookup"><span data-stu-id="a27ba-109">Comma-delimited list of assembly file names.</span></span> <span data-ttu-id="a27ba-110">Если имя файла содержит пробел, заключите имя в кавычки.</span><span class="sxs-lookup"><span data-stu-id="a27ba-110">If the file name contains a space, enclose the name in quotation marks.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a27ba-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="a27ba-111">Remarks</span></span>  
 <span data-ttu-id="a27ba-112">Импортируемые файлы должны содержать метаданные сборки.</span><span class="sxs-lookup"><span data-stu-id="a27ba-112">The file(s) you import must contain assembly metadata.</span></span> <span data-ttu-id="a27ba-113">Только открытые типы видимы за пределами сборки.</span><span class="sxs-lookup"><span data-stu-id="a27ba-113">Only public types are visible outside the assembly.</span></span> <span data-ttu-id="a27ba-114">[/Addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md) параметр импортирует метаданные из модуля.</span><span class="sxs-lookup"><span data-stu-id="a27ba-114">The [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md) option imports metadata from a module.</span></span>  
  
 <span data-ttu-id="a27ba-115">При ссылке на сборки (сборка A), которая сама ссылается на другую сборку (сборку Б), необходимо ссылаться на сборку Б, если:</span><span class="sxs-lookup"><span data-stu-id="a27ba-115">If you reference an assembly (Assembly A) which itself references another assembly (Assembly B), you need to reference Assembly B if:</span></span>  
  
-   <span data-ttu-id="a27ba-116">Из сборки A тип наследуется от типа или реализует интерфейс из сборки б.</span><span class="sxs-lookup"><span data-stu-id="a27ba-116">A type from Assembly A inherits from a type or implements an interface from Assembly B.</span></span>  
  
-   <span data-ttu-id="a27ba-117">Вызывается поле, свойство, событие или метод, который имеет возвращаемый тип или параметр типа из сборки Б.</span><span class="sxs-lookup"><span data-stu-id="a27ba-117">A field, property, event, or method that has a return type or parameter type from Assembly B is invoked.</span></span>  
  
 <span data-ttu-id="a27ba-118">Используйте [/LIBPATH](../../../visual-basic/reference/command-line-compiler/libpath.md) указать каталог, в котором находится один или несколько ссылки на сборки.</span><span class="sxs-lookup"><span data-stu-id="a27ba-118">Use [/libpath](../../../visual-basic/reference/command-line-compiler/libpath.md) to specify the directory in which one or more of your assembly references is located.</span></span>  
  
 <span data-ttu-id="a27ba-119">Компилятор мог распознавать тип в сборке (не в модуле) он должен иметь возможность разрешать типы.</span><span class="sxs-lookup"><span data-stu-id="a27ba-119">For the compiler to recognize a type in an assembly (not a module), it must be forced to resolve the type.</span></span> <span data-ttu-id="a27ba-120">Одним из примеров того, как это можно сделать является определение экземпляра типа.</span><span class="sxs-lookup"><span data-stu-id="a27ba-120">One example of how you can do this is to define an instance of the type.</span></span> <span data-ttu-id="a27ba-121">Другие способы доступны для разрешения имен типов в сборке для компилятора.</span><span class="sxs-lookup"><span data-stu-id="a27ba-121">Other ways are available to resolve type names in an assembly for the compiler.</span></span> <span data-ttu-id="a27ba-122">Например при наследовании от типа в сборке, имя типа затем становится известно компилятору.</span><span class="sxs-lookup"><span data-stu-id="a27ba-122">For example, if you inherit from a type in an assembly, the type name then becomes known to the compiler.</span></span>  
  
 <span data-ttu-id="a27ba-123">Файл ответов Vbc.rsp, который ссылается на часто используемые [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] сборок, используемых по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a27ba-123">The Vbc.rsp response file, which references commonly used [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] assemblies, is used by default.</span></span> <span data-ttu-id="a27ba-124">Используйте `/noconfig` , если не нужно, чтобы компилятор использовал файл Vbc.rsp.</span><span class="sxs-lookup"><span data-stu-id="a27ba-124">Use `/noconfig` if you do not want the compiler to use Vbc.rsp.</span></span>  
  
 <span data-ttu-id="a27ba-125">Краткая форма `/reference` — `/r`.</span><span class="sxs-lookup"><span data-stu-id="a27ba-125">The short form of `/reference` is `/r`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a27ba-126">Пример</span><span class="sxs-lookup"><span data-stu-id="a27ba-126">Example</span></span>  
 <span data-ttu-id="a27ba-127">Следующий код компилирует источник файла я`nput.vb` и ссылаться на сборки из M`etad1.dll` и M`etad2.dll` производить O`ut.exe`.</span><span class="sxs-lookup"><span data-stu-id="a27ba-127">The following code compiles source file I`nput.vb` and reference assemblies from M`etad1.dll` and M`etad2.dll` to produce O`ut.exe`.</span></span>  
  
```  
vbc /reference:metad1.dll,metad2.dll /out:out.exe input.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="a27ba-128">См. также</span><span class="sxs-lookup"><span data-stu-id="a27ba-128">See Also</span></span>  
 <span data-ttu-id="a27ba-129">[Компилятор командной строки Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="a27ba-129">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="a27ba-130"> [/ noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md) </span><span class="sxs-lookup"><span data-stu-id="a27ba-130"> [/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md) </span></span>  
<span data-ttu-id="a27ba-131"> [/ Target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) </span><span class="sxs-lookup"><span data-stu-id="a27ba-131"> [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) </span></span>  
<span data-ttu-id="a27ba-132"> [Public](../../../visual-basic/language-reference/modifiers/public.md) </span><span class="sxs-lookup"><span data-stu-id="a27ba-132"> [Public](../../../visual-basic/language-reference/modifiers/public.md) </span></span>  
<span data-ttu-id="a27ba-133"> [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="a27ba-133"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>
