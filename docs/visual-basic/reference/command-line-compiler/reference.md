---
title: -reference
ms.date: 03/13/2018
helpviewer_keywords:
- /reference compiler option [Visual Basic]
- r compiler option [Visual Basic]
- -reference compiler option [Visual Basic]
- /r compiler option [Visual Basic]
- reference compiler option [Visual Basic]
- -r compiler option [Visual Basic]
ms.assetid: 66bdfced-bbf6-43d1-a554-bc0990315737
ms.openlocfilehash: 35e02d1ad4409e754c2466f7d0ae7e68214772e6
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716703"
---
# <a name="-reference-visual-basic"></a><span data-ttu-id="afcb0-102">-Reference (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="afcb0-102">-reference (Visual Basic)</span></span>
<span data-ttu-id="afcb0-103">Заставляет компилятор предоставлять сведения о типах в указанных сборках, доступных для компилируемого в данный момент проекта.</span><span class="sxs-lookup"><span data-stu-id="afcb0-103">Causes the compiler to make type information in the specified assemblies available to the project you are currently compiling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="afcb0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="afcb0-104">Syntax</span></span>  
  
```console  
-reference:fileList  
```

<span data-ttu-id="afcb0-105">или</span><span class="sxs-lookup"><span data-stu-id="afcb0-105">or</span></span>

```console
-r:fileList  
```  
  
## <a name="arguments"></a><span data-ttu-id="afcb0-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="afcb0-106">Arguments</span></span>  
  
|<span data-ttu-id="afcb0-107">Термин</span><span class="sxs-lookup"><span data-stu-id="afcb0-107">Term</span></span>|<span data-ttu-id="afcb0-108">Определение</span><span class="sxs-lookup"><span data-stu-id="afcb0-108">Definition</span></span>|  
|---|---|  
|`fileList`|<span data-ttu-id="afcb0-109">Обязательное</span><span class="sxs-lookup"><span data-stu-id="afcb0-109">Required.</span></span> <span data-ttu-id="afcb0-110">Список всех имен файлов сборки, разделенных запятыми.</span><span class="sxs-lookup"><span data-stu-id="afcb0-110">Comma-delimited list of assembly file names.</span></span> <span data-ttu-id="afcb0-111">Если имя файла содержит пробел, заключите его в кавычки.</span><span class="sxs-lookup"><span data-stu-id="afcb0-111">If the file name contains a space, enclose the name in quotation marks.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="afcb0-112">Заметки</span><span class="sxs-lookup"><span data-stu-id="afcb0-112">Remarks</span></span>  
 <span data-ttu-id="afcb0-113">Импортируемые файлы должны содержать метаданные сборки.</span><span class="sxs-lookup"><span data-stu-id="afcb0-113">The file(s) you import must contain assembly metadata.</span></span> <span data-ttu-id="afcb0-114">За пределами сборки видны только открытые типы.</span><span class="sxs-lookup"><span data-stu-id="afcb0-114">Only public types are visible outside the assembly.</span></span> <span data-ttu-id="afcb0-115">Параметр [-addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md) импортирует метаданные из модуля.</span><span class="sxs-lookup"><span data-stu-id="afcb0-115">The [-addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md) option imports metadata from a module.</span></span>  
  
 <span data-ttu-id="afcb0-116">При ссылке на сборку (сборку A), которая сама ссылается на другую сборку (сборка B), необходимо ссылаться на сборку б, если:</span><span class="sxs-lookup"><span data-stu-id="afcb0-116">If you reference an assembly (Assembly A) which itself references another assembly (Assembly B), you need to reference Assembly B if:</span></span>  
  
- <span data-ttu-id="afcb0-117">Тип из сборки A наследуется из типа или реализует интерфейс сборки Б.</span><span class="sxs-lookup"><span data-stu-id="afcb0-117">A type from Assembly A inherits from a type or implements an interface from Assembly B.</span></span>  
  
- <span data-ttu-id="afcb0-118">Вызывается поле, свойство, событие или метод, имеющий тип возвращаемого значения или тип параметра из сборки Б.</span><span class="sxs-lookup"><span data-stu-id="afcb0-118">A field, property, event, or method that has a return type or parameter type from Assembly B is invoked.</span></span>  
  
 <span data-ttu-id="afcb0-119">Используйте параметр [-libpath](../../../visual-basic/reference/command-line-compiler/libpath.md) , чтобы указать каталог, в котором находится одна или несколько ссылок на сборки.</span><span class="sxs-lookup"><span data-stu-id="afcb0-119">Use [-libpath](../../../visual-basic/reference/command-line-compiler/libpath.md) to specify the directory in which one or more of your assembly references is located.</span></span>  
  
 <span data-ttu-id="afcb0-120">Чтобы компилятор распознал тип в сборке (а не в модуле), необходимо принудительно разрешить тип.</span><span class="sxs-lookup"><span data-stu-id="afcb0-120">For the compiler to recognize a type in an assembly (not a module), it must be forced to resolve the type.</span></span> <span data-ttu-id="afcb0-121">Одним из примеров того, как это можно сделать, является определение экземпляра типа.</span><span class="sxs-lookup"><span data-stu-id="afcb0-121">One example of how you can do this is to define an instance of the type.</span></span> <span data-ttu-id="afcb0-122">Существуют другие способы разрешения имен типов в сборке для компилятора.</span><span class="sxs-lookup"><span data-stu-id="afcb0-122">Other ways are available to resolve type names in an assembly for the compiler.</span></span> <span data-ttu-id="afcb0-123">Например, при наследовании от типа в сборке имя типа будет называться компилятором.</span><span class="sxs-lookup"><span data-stu-id="afcb0-123">For example, if you inherit from a type in an assembly, the type name then becomes known to the compiler.</span></span>  
  
 <span data-ttu-id="afcb0-124">Файл ответов Vbc. rsp, который ссылается на часто используемые .NET Framework сборки, используется по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="afcb0-124">The Vbc.rsp response file, which references commonly used .NET Framework assemblies, is used by default.</span></span> <span data-ttu-id="afcb0-125">Используйте `-noconfig`, если не нужно, чтобы компилятор использовал Vbc. rsp.</span><span class="sxs-lookup"><span data-stu-id="afcb0-125">Use `-noconfig` if you do not want the compiler to use Vbc.rsp.</span></span>  
  
 <span data-ttu-id="afcb0-126">Краткой формой `-reference` является `-r`.</span><span class="sxs-lookup"><span data-stu-id="afcb0-126">The short form of `-reference` is `-r`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="afcb0-127">Пример</span><span class="sxs-lookup"><span data-stu-id="afcb0-127">Example</span></span>  
 <span data-ttu-id="afcb0-128">Следующая команда компилирует исходный файл `Input.vb` и ссылочные сборки из `Metad1.dll` и `Metad2.dll` для создания `Out.exe`.</span><span class="sxs-lookup"><span data-stu-id="afcb0-128">The following command compiles source file `Input.vb` and reference assemblies from `Metad1.dll` and `Metad2.dll` to produce `Out.exe`.</span></span>  
  
```console
vbc -reference:metad1.dll,metad2.dll -out:out.exe input.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="afcb0-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="afcb0-129">See also</span></span>

- [<span data-ttu-id="afcb0-130">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="afcb0-130">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="afcb0-131">-noconfig</span><span class="sxs-lookup"><span data-stu-id="afcb0-131">-noconfig</span></span>](../../../visual-basic/reference/command-line-compiler/noconfig.md)
- [<span data-ttu-id="afcb0-132">-Target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="afcb0-132">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="afcb0-133">Public</span><span class="sxs-lookup"><span data-stu-id="afcb0-133">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="afcb0-134">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="afcb0-134">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
