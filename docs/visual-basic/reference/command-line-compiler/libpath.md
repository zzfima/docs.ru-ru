---
title: "/ LIBPATH | Документы Microsoft"
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
- libpath compiler option [Visual Basic]
- /libpath compiler option [Visual Basic]
- -libpath compiler option [Visual Basic]
ms.assetid: 5f1c26c9-3455-4e89-bdf3-b12d6c2e655b
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
ms.openlocfilehash: 7f24dd7707645f45677dcf7009e1adc64afaaa7c
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="libpath"></a><span data-ttu-id="b486c-102">/libpath</span><span class="sxs-lookup"><span data-stu-id="b486c-102">/libpath</span></span>
<span data-ttu-id="b486c-103">Указывает расположение сборок, на которые имеются ссылки.</span><span class="sxs-lookup"><span data-stu-id="b486c-103">Specifies the location of referenced assemblies.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b486c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b486c-104">Syntax</span></span>  
  
```  
/libpath:dirList  
```  
  
## <a name="arguments"></a><span data-ttu-id="b486c-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="b486c-105">Arguments</span></span>  
  
|<span data-ttu-id="b486c-106">Термин</span><span class="sxs-lookup"><span data-stu-id="b486c-106">Term</span></span>|<span data-ttu-id="b486c-107">Определение</span><span class="sxs-lookup"><span data-stu-id="b486c-107">Definition</span></span>|  
|---|---|  
|`dirList`|<span data-ttu-id="b486c-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="b486c-108">Required.</span></span> <span data-ttu-id="b486c-109">Разделенный точками с запятыми список каталогов, по которому компилятор будет искать сборку, если не найден либо в текущем рабочем каталоге (каталоге, из которого был вызван компилятор) и системном каталоге среды CLR.</span><span class="sxs-lookup"><span data-stu-id="b486c-109">Semicolon-delimited list of directories for the compiler to look in if a referenced assembly is not found in either the current working directory (the directory from which you are invoking the compiler) or the common language runtime's system directory.</span></span> <span data-ttu-id="b486c-110">Если имя каталога содержит пробел, заключите имя в кавычки (» «).</span><span class="sxs-lookup"><span data-stu-id="b486c-110">If the directory name contains a space, enclose the name in quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b486c-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="b486c-111">Remarks</span></span>  
 <span data-ttu-id="b486c-112">`/libpath` Указывает расположение ссылок на сборки с [/reference](../../../visual-basic/reference/command-line-compiler/reference.md) параметр.</span><span class="sxs-lookup"><span data-stu-id="b486c-112">The `/libpath` option specifies the location of assemblies referenced by the [/reference](../../../visual-basic/reference/command-line-compiler/reference.md) option.</span></span>  
  
 <span data-ttu-id="b486c-113">Компилятор выполняет поиск ссылок на сборки, которые не указано полное имя, в следующем порядке:</span><span class="sxs-lookup"><span data-stu-id="b486c-113">The compiler searches for assembly references that are not fully qualified in the following order:</span></span>  
  
1.  <span data-ttu-id="b486c-114">Текущий рабочий каталог.</span><span class="sxs-lookup"><span data-stu-id="b486c-114">Current working directory.</span></span> <span data-ttu-id="b486c-115">Это каталог, из которого был вызван компилятор.</span><span class="sxs-lookup"><span data-stu-id="b486c-115">This is the directory from which the compiler is invoked.</span></span>  
  
2.  <span data-ttu-id="b486c-116">Системном каталоге среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="b486c-116">The common language runtime system directory.</span></span>  
  
3.  <span data-ttu-id="b486c-117">Каталоги, заданные параметром `/libpath`.</span><span class="sxs-lookup"><span data-stu-id="b486c-117">Directories specified by `/libpath`.</span></span>  
  
4.  <span data-ttu-id="b486c-118">Каталоги, указанные в переменной среды LIB.</span><span class="sxs-lookup"><span data-stu-id="b486c-118">Directories specified by the LIB environment variable.</span></span>  
  
 <span data-ttu-id="b486c-119">`/libpath` Параметр аддитивны, указав его несколько раз добавляет к предыдущим значениям.</span><span class="sxs-lookup"><span data-stu-id="b486c-119">The `/libpath` option is additive; specifying it more than once appends to any prior values.</span></span>  
  
 <span data-ttu-id="b486c-120">Используйте `/reference` для указания ссылки на сборку.</span><span class="sxs-lookup"><span data-stu-id="b486c-120">Use `/reference` to specify an assembly reference.</span></span>  
  
|<span data-ttu-id="b486c-121">Чтобы установить параметр/LIBPATH в Visual Studio интегрированная среда разработки</span><span class="sxs-lookup"><span data-stu-id="b486c-121">To set /libpath in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="b486c-122">1.  Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="b486c-122">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="b486c-123">На **проекта** меню, щелкните **свойства**.</span><span class="sxs-lookup"><span data-stu-id="b486c-123">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="b486c-124">Дополнительные сведения см. в разделе [Знакомство с конструктором проектов](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="b486c-124">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="b486c-125">2.  Щелкните **ссылки** вкладки.</span><span class="sxs-lookup"><span data-stu-id="b486c-125">2.  Click the **References** tab.</span></span><br /><span data-ttu-id="b486c-126">3.  Щелкните **ссылающиеся на пути... ** кнопки.</span><span class="sxs-lookup"><span data-stu-id="b486c-126">3.  Click the **Reference Paths...** button.</span></span><br /><span data-ttu-id="b486c-127">4.  В **пути для ссылок** диалогового окна введите имя каталога в **папки:** поле.</span><span class="sxs-lookup"><span data-stu-id="b486c-127">4.  In the **Reference Paths** dialog box, enter the directory name in the **Folder:** box.</span></span><br /><span data-ttu-id="b486c-128">5.  Щелкните **добавить папку**.</span><span class="sxs-lookup"><span data-stu-id="b486c-128">5.  Click **Add Folder**.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="b486c-129">Пример</span><span class="sxs-lookup"><span data-stu-id="b486c-129">Example</span></span>  
 <span data-ttu-id="b486c-130">Следующий код компилирует `T2.vb` для создания файла .exe.</span><span class="sxs-lookup"><span data-stu-id="b486c-130">The following code compiles `T2.vb` to create an .exe file.</span></span> <span data-ttu-id="b486c-131">Компилятор в рабочем каталоге, в корневом каталоге диска C: и в каталоге создания сборки на диске c: ищет ссылки на сборки.</span><span class="sxs-lookup"><span data-stu-id="b486c-131">The compiler looks in the working directory, in the root directory of the C: drive, and in the New Assemblies directory of the C: drive for assembly references.</span></span>  
  
```  
vbc /libpath:c:\;"c:\New Assemblies" /reference:t2.dll t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="b486c-132">См. также</span><span class="sxs-lookup"><span data-stu-id="b486c-132">See Also</span></span>  
 <span data-ttu-id="b486c-133">[Сборки и глобальный кэш сборок](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span><span class="sxs-lookup"><span data-stu-id="b486c-133">[Assemblies and the Global Assembly Cache](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span></span>  
<span data-ttu-id="b486c-134"> [Компилятор командной строки Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="b486c-134"> [Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="b486c-135"> [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="b486c-135"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>
