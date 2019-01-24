---
title: -libpath
ms.date: 03/10/2018
helpviewer_keywords:
- libpath compiler option [Visual Basic]
- /libpath compiler option [Visual Basic]
- -libpath compiler option [Visual Basic]
ms.assetid: 5f1c26c9-3455-4e89-bdf3-b12d6c2e655b
ms.openlocfilehash: 6285deb97b05659283071b8940fe8730890b98e8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54609867"
---
# <a name="-libpath"></a><span data-ttu-id="d183c-102">-libpath</span><span class="sxs-lookup"><span data-stu-id="d183c-102">-libpath</span></span>
<span data-ttu-id="d183c-103">Указывает расположение сборок, на которую указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="d183c-103">Specifies the location of referenced assemblies.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d183c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d183c-104">Syntax</span></span>  
  
```  
-libpath:dirList  
```  
  
## <a name="arguments"></a><span data-ttu-id="d183c-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="d183c-105">Arguments</span></span>  
  
|<span data-ttu-id="d183c-106">Термин</span><span class="sxs-lookup"><span data-stu-id="d183c-106">Term</span></span>|<span data-ttu-id="d183c-107">Определение</span><span class="sxs-lookup"><span data-stu-id="d183c-107">Definition</span></span>|  
|---|---|  
|`dirList`|<span data-ttu-id="d183c-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="d183c-108">Required.</span></span> <span data-ttu-id="d183c-109">Разделенный точками с запятой список каталогов искать сборку, если компилятор не найден в любой текущий рабочий каталог (каталог, из которого был вызван компилятор) или системный каталог среды CLR.</span><span class="sxs-lookup"><span data-stu-id="d183c-109">Semicolon-delimited list of directories for the compiler to look in if a referenced assembly is not found in either the current working directory (the directory from which you are invoking the compiler) or the common language runtime's system directory.</span></span> <span data-ttu-id="d183c-110">Если имя каталога содержит пробел, заключите имя в кавычки (» «).</span><span class="sxs-lookup"><span data-stu-id="d183c-110">If the directory name contains a space, enclose the name in quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d183c-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="d183c-111">Remarks</span></span>  
 <span data-ttu-id="d183c-112">`-libpath` Указывает расположение сборок, указанных по [-ссылка](../../../visual-basic/reference/command-line-compiler/reference.md) параметр.</span><span class="sxs-lookup"><span data-stu-id="d183c-112">The `-libpath` option specifies the location of assemblies referenced by the [-reference](../../../visual-basic/reference/command-line-compiler/reference.md) option.</span></span>  
  
 <span data-ttu-id="d183c-113">Компилятор выполняет поиск связанных сборок, для которых не указано полное имя, в следующем порядке:</span><span class="sxs-lookup"><span data-stu-id="d183c-113">The compiler searches for assembly references that are not fully qualified in the following order:</span></span>  
  
1.  <span data-ttu-id="d183c-114">Текущая рабочая папка.</span><span class="sxs-lookup"><span data-stu-id="d183c-114">Current working directory.</span></span> <span data-ttu-id="d183c-115">Это папка, из которой был вызван компилятор.</span><span class="sxs-lookup"><span data-stu-id="d183c-115">This is the directory from which the compiler is invoked.</span></span>  
  
2.  <span data-ttu-id="d183c-116">Системный каталог среды CLR.</span><span class="sxs-lookup"><span data-stu-id="d183c-116">The common language runtime system directory.</span></span>  
  
3.  <span data-ttu-id="d183c-117">Каталоги, заданные параметром `/libpath`.</span><span class="sxs-lookup"><span data-stu-id="d183c-117">Directories specified by `/libpath`.</span></span>  
  
4.  <span data-ttu-id="d183c-118">Каталоги, указанные переменной среды LIB.</span><span class="sxs-lookup"><span data-stu-id="d183c-118">Directories specified by the LIB environment variable.</span></span>  
  
 <span data-ttu-id="d183c-119">`-libpath` Параметр аддитивные; каждое следующее указание этого параметра присоединяется к предыдущим значениям.</span><span class="sxs-lookup"><span data-stu-id="d183c-119">The `-libpath` option is additive; specifying it more than once appends to any prior values.</span></span>  
  
 <span data-ttu-id="d183c-120">Используйте `-reference` для указания ссылки на сборку.</span><span class="sxs-lookup"><span data-stu-id="d183c-120">Use `-reference` to specify an assembly reference.</span></span>  
  
|<span data-ttu-id="d183c-121">Чтобы задать параметр/LIBPATH в Visual Studio интегрированной среды разработки</span><span class="sxs-lookup"><span data-stu-id="d183c-121">To set /libpath in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="d183c-122">1.  Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="d183c-122">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="d183c-123">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="d183c-123">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="d183c-124">2.  Перейдите на вкладку **Ссылки**.</span><span class="sxs-lookup"><span data-stu-id="d183c-124">2.  Click the **References** tab.</span></span><br /><span data-ttu-id="d183c-125">3.  Нажмите кнопку **пути ссылки на...**  кнопки.</span><span class="sxs-lookup"><span data-stu-id="d183c-125">3.  Click the **Reference Paths...** button.</span></span><br /><span data-ttu-id="d183c-126">4.  В **пути для ссылок** диалогового окна введите имя каталога в **папки:** поле.</span><span class="sxs-lookup"><span data-stu-id="d183c-126">4.  In the **Reference Paths** dialog box, enter the directory name in the **Folder:** box.</span></span><br /><span data-ttu-id="d183c-127">5.  Нажмите кнопку **добавить папку**.</span><span class="sxs-lookup"><span data-stu-id="d183c-127">5.  Click **Add Folder**.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d183c-128">Пример</span><span class="sxs-lookup"><span data-stu-id="d183c-128">Example</span></span>  
 <span data-ttu-id="d183c-129">Следующий код компилирует `T2.vb` для создания файла .exe.</span><span class="sxs-lookup"><span data-stu-id="d183c-129">The following code compiles `T2.vb` to create an .exe file.</span></span> <span data-ttu-id="d183c-130">Компилятор выполняет в рабочем каталоге, в корневом каталоге диска C: и в каталоге новых сборок на диске C: для ссылки на сборки.</span><span class="sxs-lookup"><span data-stu-id="d183c-130">The compiler looks in the working directory, in the root directory of the C: drive, and in the New Assemblies directory of the C: drive for assembly references.</span></span>  
  
```console  
vbc -libpath:c:\;"c:\New Assemblies" -reference:t2.dll t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="d183c-131">См. также</span><span class="sxs-lookup"><span data-stu-id="d183c-131">See also</span></span>
- [<span data-ttu-id="d183c-132">Сборки и глобальный кэш сборок</span><span class="sxs-lookup"><span data-stu-id="d183c-132">Assemblies and the Global Assembly Cache</span></span>](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)
- [<span data-ttu-id="d183c-133">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="d183c-133">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="d183c-134">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="d183c-134">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
