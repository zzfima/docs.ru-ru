---
title: /libpath
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- libpath compiler option [Visual Basic]
- /libpath compiler option [Visual Basic]
- -libpath compiler option [Visual Basic]
ms.assetid: 5f1c26c9-3455-4e89-bdf3-b12d6c2e655b
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2be2c460fddf2e8ea4fe1239ec073f208c072d34
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="libpath"></a><span data-ttu-id="9dbb4-102">/libpath</span><span class="sxs-lookup"><span data-stu-id="9dbb4-102">/libpath</span></span>
<span data-ttu-id="9dbb4-103">Указывает расположение сборок, на которую указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="9dbb4-103">Specifies the location of referenced assemblies.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9dbb4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9dbb4-104">Syntax</span></span>  
  
```  
/libpath:dirList  
```  
  
## <a name="arguments"></a><span data-ttu-id="9dbb4-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="9dbb4-105">Arguments</span></span>  
  
|<span data-ttu-id="9dbb4-106">Термин</span><span class="sxs-lookup"><span data-stu-id="9dbb4-106">Term</span></span>|<span data-ttu-id="9dbb4-107">Определение</span><span class="sxs-lookup"><span data-stu-id="9dbb4-107">Definition</span></span>|  
|---|---|  
|`dirList`|<span data-ttu-id="9dbb4-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="9dbb4-108">Required.</span></span> <span data-ttu-id="9dbb4-109">Разделенный точками с запятой список каталогов, компилятор должен искать сборку, если она отсутствует в либо в текущем рабочем каталоге (каталог, из которого был вызван компилятор) или системный каталог среды CLR.</span><span class="sxs-lookup"><span data-stu-id="9dbb4-109">Semicolon-delimited list of directories for the compiler to look in if a referenced assembly is not found in either the current working directory (the directory from which you are invoking the compiler) or the common language runtime's system directory.</span></span> <span data-ttu-id="9dbb4-110">Если имя каталога содержит пробелы, заключите имя в кавычки (» «).</span><span class="sxs-lookup"><span data-stu-id="9dbb4-110">If the directory name contains a space, enclose the name in quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9dbb4-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="9dbb4-111">Remarks</span></span>  
 <span data-ttu-id="9dbb4-112">`/libpath` Указывает расположение ссылок на сборки с [/reference](../../../visual-basic/reference/command-line-compiler/reference.md) параметр.</span><span class="sxs-lookup"><span data-stu-id="9dbb4-112">The `/libpath` option specifies the location of assemblies referenced by the [/reference](../../../visual-basic/reference/command-line-compiler/reference.md) option.</span></span>  
  
 <span data-ttu-id="9dbb4-113">Компилятор выполняет поиск связанных сборок, для которых не указано полное имя, в следующем порядке:</span><span class="sxs-lookup"><span data-stu-id="9dbb4-113">The compiler searches for assembly references that are not fully qualified in the following order:</span></span>  
  
1.  <span data-ttu-id="9dbb4-114">Текущая рабочая папка.</span><span class="sxs-lookup"><span data-stu-id="9dbb4-114">Current working directory.</span></span> <span data-ttu-id="9dbb4-115">Это папка, из которой был вызван компилятор.</span><span class="sxs-lookup"><span data-stu-id="9dbb4-115">This is the directory from which the compiler is invoked.</span></span>  
  
2.  <span data-ttu-id="9dbb4-116">Системный каталог среды CLR.</span><span class="sxs-lookup"><span data-stu-id="9dbb4-116">The common language runtime system directory.</span></span>  
  
3.  <span data-ttu-id="9dbb4-117">Каталоги, заданные параметром `/libpath`.</span><span class="sxs-lookup"><span data-stu-id="9dbb4-117">Directories specified by `/libpath`.</span></span>  
  
4.  <span data-ttu-id="9dbb4-118">Каталоги, указанные переменной среды LIB.</span><span class="sxs-lookup"><span data-stu-id="9dbb4-118">Directories specified by the LIB environment variable.</span></span>  
  
 <span data-ttu-id="9dbb4-119">`/libpath` Параметр аддитивными, указав его более чем один раз добавляет к предыдущим значениям.</span><span class="sxs-lookup"><span data-stu-id="9dbb4-119">The `/libpath` option is additive; specifying it more than once appends to any prior values.</span></span>  
  
 <span data-ttu-id="9dbb4-120">Используйте `/reference` для указания ссылки на сборку.</span><span class="sxs-lookup"><span data-stu-id="9dbb4-120">Use `/reference` to specify an assembly reference.</span></span>  
  
|<span data-ttu-id="9dbb4-121">Чтобы задать параметр/LIBPATH в Visual Studio интегрированной среде разработки</span><span class="sxs-lookup"><span data-stu-id="9dbb4-121">To set /libpath in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="9dbb4-122">1.  Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="9dbb4-122">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="9dbb4-123">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="9dbb4-123">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="9dbb4-124">Дополнительные сведения см. в разделе [Знакомство с конструктором проектов](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="9dbb4-124">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="9dbb4-125">2.  Перейдите на вкладку **Ссылки**.</span><span class="sxs-lookup"><span data-stu-id="9dbb4-125">2.  Click the **References** tab.</span></span><br /><span data-ttu-id="9dbb4-126">3.  Нажмите кнопку **ссылке на пути к...**  кнопки.</span><span class="sxs-lookup"><span data-stu-id="9dbb4-126">3.  Click the **Reference Paths...** button.</span></span><br /><span data-ttu-id="9dbb4-127">4.  В **пути для ссылок** диалогового окна введите имя каталога в **папки:** поле.</span><span class="sxs-lookup"><span data-stu-id="9dbb4-127">4.  In the **Reference Paths** dialog box, enter the directory name in the **Folder:** box.</span></span><br /><span data-ttu-id="9dbb4-128">5.  Нажмите кнопку **добавить папку**.</span><span class="sxs-lookup"><span data-stu-id="9dbb4-128">5.  Click **Add Folder**.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="9dbb4-129">Пример</span><span class="sxs-lookup"><span data-stu-id="9dbb4-129">Example</span></span>  
 <span data-ttu-id="9dbb4-130">Следующий код компилирует `T2.vb` для создания файла .exe.</span><span class="sxs-lookup"><span data-stu-id="9dbb4-130">The following code compiles `T2.vb` to create an .exe file.</span></span> <span data-ttu-id="9dbb4-131">Компилятор в рабочем каталоге, в корневом каталоге диска C: и в каталоге создания сборки на диске c: ищет ссылки на сборки.</span><span class="sxs-lookup"><span data-stu-id="9dbb4-131">The compiler looks in the working directory, in the root directory of the C: drive, and in the New Assemblies directory of the C: drive for assembly references.</span></span>  
  
```  
vbc /libpath:c:\;"c:\New Assemblies" /reference:t2.dll t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="9dbb4-132">См. также</span><span class="sxs-lookup"><span data-stu-id="9dbb4-132">See Also</span></span>  
 [<span data-ttu-id="9dbb4-133">Сборки и глобальный кэш сборок</span><span class="sxs-lookup"><span data-stu-id="9dbb4-133">Assemblies and the Global Assembly Cache</span></span>](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [<span data-ttu-id="9dbb4-134">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="9dbb4-134">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="9dbb4-135">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="9dbb4-135">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
