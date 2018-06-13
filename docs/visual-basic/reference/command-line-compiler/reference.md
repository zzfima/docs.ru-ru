---
title: -ссылке (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- /reference compiler option [Visual Basic]
- r compiler option [Visual Basic]
- -reference compiler option [Visual Basic]
- /r compiler option [Visual Basic]
- reference compiler option [Visual Basic]
- -r compiler option [Visual Basic]
ms.assetid: 66bdfced-bbf6-43d1-a554-bc0990315737
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cb5d3b4c50a9c22880bdcc8406835cf51481e3cd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33654373"
---
# <a name="-reference-visual-basic"></a><span data-ttu-id="55ed9-102">-ссылке (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="55ed9-102">-reference (Visual Basic)</span></span>
<span data-ttu-id="55ed9-103">Указывает компилятору на необходимость сделать сведения о типе в указанных сборках доступными для проекта, которые в настоящее время компиляции.</span><span class="sxs-lookup"><span data-stu-id="55ed9-103">Causes the compiler to make type information in the specified assemblies available to the project you are currently compiling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55ed9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="55ed9-104">Syntax</span></span>  
  
```  
-reference:fileList  
' -or-  
-r:fileList  
```  
  
## <a name="arguments"></a><span data-ttu-id="55ed9-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="55ed9-105">Arguments</span></span>  
  
|<span data-ttu-id="55ed9-106">Термин</span><span class="sxs-lookup"><span data-stu-id="55ed9-106">Term</span></span>|<span data-ttu-id="55ed9-107">Определение</span><span class="sxs-lookup"><span data-stu-id="55ed9-107">Definition</span></span>|  
|---|---|  
|`fileList`|<span data-ttu-id="55ed9-108">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="55ed9-108">Required.</span></span> <span data-ttu-id="55ed9-109">Список всех имен файлов сборки, разделенных запятыми.</span><span class="sxs-lookup"><span data-stu-id="55ed9-109">Comma-delimited list of assembly file names.</span></span> <span data-ttu-id="55ed9-110">Если имя файла содержит пробел, заключите его в кавычки.</span><span class="sxs-lookup"><span data-stu-id="55ed9-110">If the file name contains a space, enclose the name in quotation marks.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="55ed9-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="55ed9-111">Remarks</span></span>  
 <span data-ttu-id="55ed9-112">Импортируемые файлы должны содержать метаданные сборки.</span><span class="sxs-lookup"><span data-stu-id="55ed9-112">The file(s) you import must contain assembly metadata.</span></span> <span data-ttu-id="55ed9-113">Только открытые типы являются видимыми за пределами сборки.</span><span class="sxs-lookup"><span data-stu-id="55ed9-113">Only public types are visible outside the assembly.</span></span> <span data-ttu-id="55ed9-114">[/Addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md) параметр импортирует метаданные из модуля.</span><span class="sxs-lookup"><span data-stu-id="55ed9-114">The [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md) option imports metadata from a module.</span></span>  
  
 <span data-ttu-id="55ed9-115">При ссылках на сборки (сборка A), который в свою очередь ссылается на другую сборку (сборку Б), необходимо ссылаться на сборку Б, если:</span><span class="sxs-lookup"><span data-stu-id="55ed9-115">If you reference an assembly (Assembly A) which itself references another assembly (Assembly B), you need to reference Assembly B if:</span></span>  
  
-   <span data-ttu-id="55ed9-116">Тип из сборки A наследуется из типа или реализует интерфейс сборки Б.</span><span class="sxs-lookup"><span data-stu-id="55ed9-116">A type from Assembly A inherits from a type or implements an interface from Assembly B.</span></span>  
  
-   <span data-ttu-id="55ed9-117">Вызывается поле, свойство, событие или метод, имеющий тип возвращаемого значения или тип параметра из сборки Б.</span><span class="sxs-lookup"><span data-stu-id="55ed9-117">A field, property, event, or method that has a return type or parameter type from Assembly B is invoked.</span></span>  
  
 <span data-ttu-id="55ed9-118">Используйте [- libpath](../../../visual-basic/reference/command-line-compiler/libpath.md) для указания каталога, в котором находится один или несколько ссылок на сборки.</span><span class="sxs-lookup"><span data-stu-id="55ed9-118">Use [-libpath](../../../visual-basic/reference/command-line-compiler/libpath.md) to specify the directory in which one or more of your assembly references is located.</span></span>  
  
 <span data-ttu-id="55ed9-119">Компилятор должен распознавать тип в сборке (не в модуле) он должен иметь возможность для разрешения типа.</span><span class="sxs-lookup"><span data-stu-id="55ed9-119">For the compiler to recognize a type in an assembly (not a module), it must be forced to resolve the type.</span></span> <span data-ttu-id="55ed9-120">Как это можно сделать одним из примеров является определение экземпляра типа.</span><span class="sxs-lookup"><span data-stu-id="55ed9-120">One example of how you can do this is to define an instance of the type.</span></span> <span data-ttu-id="55ed9-121">Существуют другие способы для разрешения имен типов в сборке, компилятор.</span><span class="sxs-lookup"><span data-stu-id="55ed9-121">Other ways are available to resolve type names in an assembly for the compiler.</span></span> <span data-ttu-id="55ed9-122">Например при наследовании из типа в сборке, имя типа затем становится известно компилятору.</span><span class="sxs-lookup"><span data-stu-id="55ed9-122">For example, if you inherit from a type in an assembly, the type name then becomes known to the compiler.</span></span>  
  
 <span data-ttu-id="55ed9-123">Файл ответов Vbc.rsp, который ссылается на часто используемые [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] сборок, используемых по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="55ed9-123">The Vbc.rsp response file, which references commonly used [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] assemblies, is used by default.</span></span> <span data-ttu-id="55ed9-124">Использовать `-noconfig` запретить компилятору использовать файл Vbc.rsp.</span><span class="sxs-lookup"><span data-stu-id="55ed9-124">Use `-noconfig` if you do not want the compiler to use Vbc.rsp.</span></span>  
  
 <span data-ttu-id="55ed9-125">Краткой формой `-reference` является `/r`.</span><span class="sxs-lookup"><span data-stu-id="55ed9-125">The short form of `-reference` is `/r`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="55ed9-126">Пример</span><span class="sxs-lookup"><span data-stu-id="55ed9-126">Example</span></span>  
 <span data-ttu-id="55ed9-127">Следующая команда компилирует исходный файл `Input.vb` и ссылки на сборки из `Metad1.dll` и `Metad2.dll` для создания `Out.exe`.</span><span class="sxs-lookup"><span data-stu-id="55ed9-127">The following command compiles source file `Input.vb` and reference assemblies from `Metad1.dll` and `Metad2.dll` to produce `Out.exe`.</span></span>  
  
```console
vbc -reference:metad1.dll,metad2.dll -out:out.exe input.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="55ed9-128">См. также</span><span class="sxs-lookup"><span data-stu-id="55ed9-128">See Also</span></span>  
 [<span data-ttu-id="55ed9-129">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="55ed9-129">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="55ed9-130">-noconfig</span><span class="sxs-lookup"><span data-stu-id="55ed9-130">-noconfig</span></span>](../../../visual-basic/reference/command-line-compiler/noconfig.md)  
 [<span data-ttu-id="55ed9-131">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="55ed9-131">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)  
 [<span data-ttu-id="55ed9-132">Public</span><span class="sxs-lookup"><span data-stu-id="55ed9-132">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
 [<span data-ttu-id="55ed9-133">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="55ed9-133">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
