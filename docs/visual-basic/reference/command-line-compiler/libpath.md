---
title: -libpath
ms.date: 03/10/2018
helpviewer_keywords:
- libpath compiler option [Visual Basic]
- /libpath compiler option [Visual Basic]
- -libpath compiler option [Visual Basic]
ms.assetid: 5f1c26c9-3455-4e89-bdf3-b12d6c2e655b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a5044bc0093960fdf6b063450d8d3a57575ff07c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33653882"
---
# <a name="-libpath"></a><span data-ttu-id="e1991-102">-libpath</span><span class="sxs-lookup"><span data-stu-id="e1991-102">-libpath</span></span>
<span data-ttu-id="e1991-103">Указывает расположение сборок, на которую указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="e1991-103">Specifies the location of referenced assemblies.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1991-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e1991-104">Syntax</span></span>  
  
```  
-libpath:dirList  
```  
  
## <a name="arguments"></a><span data-ttu-id="e1991-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="e1991-105">Arguments</span></span>  
  
|<span data-ttu-id="e1991-106">Термин</span><span class="sxs-lookup"><span data-stu-id="e1991-106">Term</span></span>|<span data-ttu-id="e1991-107">Определение</span><span class="sxs-lookup"><span data-stu-id="e1991-107">Definition</span></span>|  
|---|---|  
|`dirList`|<span data-ttu-id="e1991-108">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="e1991-108">Required.</span></span> <span data-ttu-id="e1991-109">Разделенный точками с запятой список каталогов, компилятор должен искать сборку, если она отсутствует в либо в текущем рабочем каталоге (каталог, из которого был вызван компилятор) или системный каталог среды CLR.</span><span class="sxs-lookup"><span data-stu-id="e1991-109">Semicolon-delimited list of directories for the compiler to look in if a referenced assembly is not found in either the current working directory (the directory from which you are invoking the compiler) or the common language runtime's system directory.</span></span> <span data-ttu-id="e1991-110">Если имя каталога содержит пробелы, заключите имя в кавычки (» «).</span><span class="sxs-lookup"><span data-stu-id="e1991-110">If the directory name contains a space, enclose the name in quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e1991-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="e1991-111">Remarks</span></span>  
 <span data-ttu-id="e1991-112">`-libpath` Указывает расположение ссылок на сборки с [-ссылка](../../../visual-basic/reference/command-line-compiler/reference.md) параметр.</span><span class="sxs-lookup"><span data-stu-id="e1991-112">The `-libpath` option specifies the location of assemblies referenced by the [-reference](../../../visual-basic/reference/command-line-compiler/reference.md) option.</span></span>  
  
 <span data-ttu-id="e1991-113">Компилятор выполняет поиск связанных сборок, для которых не указано полное имя, в следующем порядке:</span><span class="sxs-lookup"><span data-stu-id="e1991-113">The compiler searches for assembly references that are not fully qualified in the following order:</span></span>  
  
1.  <span data-ttu-id="e1991-114">Текущая рабочая папка.</span><span class="sxs-lookup"><span data-stu-id="e1991-114">Current working directory.</span></span> <span data-ttu-id="e1991-115">Это папка, из которой был вызван компилятор.</span><span class="sxs-lookup"><span data-stu-id="e1991-115">This is the directory from which the compiler is invoked.</span></span>  
  
2.  <span data-ttu-id="e1991-116">Системный каталог среды CLR.</span><span class="sxs-lookup"><span data-stu-id="e1991-116">The common language runtime system directory.</span></span>  
  
3.  <span data-ttu-id="e1991-117">Каталоги, заданные параметром `/libpath`.</span><span class="sxs-lookup"><span data-stu-id="e1991-117">Directories specified by `/libpath`.</span></span>  
  
4.  <span data-ttu-id="e1991-118">Каталоги, указанные переменной среды LIB.</span><span class="sxs-lookup"><span data-stu-id="e1991-118">Directories specified by the LIB environment variable.</span></span>  
  
 <span data-ttu-id="e1991-119">`-libpath` Параметр аддитивными, указав его более чем один раз добавляет к предыдущим значениям.</span><span class="sxs-lookup"><span data-stu-id="e1991-119">The `-libpath` option is additive; specifying it more than once appends to any prior values.</span></span>  
  
 <span data-ttu-id="e1991-120">Используйте `-reference` для указания ссылки на сборку.</span><span class="sxs-lookup"><span data-stu-id="e1991-120">Use `-reference` to specify an assembly reference.</span></span>  
  
|<span data-ttu-id="e1991-121">Чтобы задать параметр/LIBPATH в Visual Studio интегрированной среде разработки</span><span class="sxs-lookup"><span data-stu-id="e1991-121">To set /libpath in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="e1991-122">1.  Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="e1991-122">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="e1991-123">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="e1991-123">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="e1991-124">2.  Перейдите на вкладку **Ссылки**.</span><span class="sxs-lookup"><span data-stu-id="e1991-124">2.  Click the **References** tab.</span></span><br /><span data-ttu-id="e1991-125">3.  Нажмите кнопку **ссылке на пути к...**  кнопки.</span><span class="sxs-lookup"><span data-stu-id="e1991-125">3.  Click the **Reference Paths...** button.</span></span><br /><span data-ttu-id="e1991-126">4.  В **пути для ссылок** диалогового окна введите имя каталога в **папки:** поле.</span><span class="sxs-lookup"><span data-stu-id="e1991-126">4.  In the **Reference Paths** dialog box, enter the directory name in the **Folder:** box.</span></span><br /><span data-ttu-id="e1991-127">5.  Нажмите кнопку **добавить папку**.</span><span class="sxs-lookup"><span data-stu-id="e1991-127">5.  Click **Add Folder**.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e1991-128">Пример</span><span class="sxs-lookup"><span data-stu-id="e1991-128">Example</span></span>  
 <span data-ttu-id="e1991-129">Следующий код компилирует `T2.vb` для создания файла .exe.</span><span class="sxs-lookup"><span data-stu-id="e1991-129">The following code compiles `T2.vb` to create an .exe file.</span></span> <span data-ttu-id="e1991-130">Компилятор в рабочем каталоге, в корневом каталоге диска C: и в каталоге создания сборки на диске c: ищет ссылки на сборки.</span><span class="sxs-lookup"><span data-stu-id="e1991-130">The compiler looks in the working directory, in the root directory of the C: drive, and in the New Assemblies directory of the C: drive for assembly references.</span></span>  
  
```console  
vbc -libpath:c:\;"c:\New Assemblies" -reference:t2.dll t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="e1991-131">См. также</span><span class="sxs-lookup"><span data-stu-id="e1991-131">See Also</span></span>  
 [<span data-ttu-id="e1991-132">Сборки и глобальный кэш сборок</span><span class="sxs-lookup"><span data-stu-id="e1991-132">Assemblies and the Global Assembly Cache</span></span>](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [<span data-ttu-id="e1991-133">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="e1991-133">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="e1991-134">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="e1991-134">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
