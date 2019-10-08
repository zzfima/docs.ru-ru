---
title: -libpath
ms.date: 03/10/2018
helpviewer_keywords:
- libpath compiler option [Visual Basic]
- /libpath compiler option [Visual Basic]
- -libpath compiler option [Visual Basic]
ms.assetid: 5f1c26c9-3455-4e89-bdf3-b12d6c2e655b
ms.openlocfilehash: 8f4e415576562885c9edbd3d2dddbe2a271e9923
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005465"
---
# <a name="-libpath"></a><span data-ttu-id="8e80e-102">-libpath</span><span class="sxs-lookup"><span data-stu-id="8e80e-102">-libpath</span></span>
<span data-ttu-id="8e80e-103">Задает расположение сборок, на которые указывают ссылки.</span><span class="sxs-lookup"><span data-stu-id="8e80e-103">Specifies the location of referenced assemblies.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e80e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8e80e-104">Syntax</span></span>  
  
```console  
-libpath:dirList  
```  
  
## <a name="arguments"></a><span data-ttu-id="8e80e-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="8e80e-105">Arguments</span></span>  
  
|<span data-ttu-id="8e80e-106">Термин</span><span class="sxs-lookup"><span data-stu-id="8e80e-106">Term</span></span>|<span data-ttu-id="8e80e-107">Определение</span><span class="sxs-lookup"><span data-stu-id="8e80e-107">Definition</span></span>|  
|---|---|  
|`dirList`|<span data-ttu-id="8e80e-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="8e80e-108">Required.</span></span> <span data-ttu-id="8e80e-109">Разделенный точками с запятой список каталогов, в которых компилятор должен искать, если сборка, на которую указывает ссылка, не найдена ни в текущем рабочем каталоге (каталоге, из которого вызывается компилятор), ни в системном каталоге среды CLR.</span><span class="sxs-lookup"><span data-stu-id="8e80e-109">Semicolon-delimited list of directories for the compiler to look in if a referenced assembly is not found in either the current working directory (the directory from which you are invoking the compiler) or the common language runtime's system directory.</span></span> <span data-ttu-id="8e80e-110">Если имя каталога содержит пробел, заключите его в кавычки ("").</span><span class="sxs-lookup"><span data-stu-id="8e80e-110">If the directory name contains a space, enclose the name in quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8e80e-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="8e80e-111">Remarks</span></span>  
 <span data-ttu-id="8e80e-112">Параметр `-libpath` указывает расположение сборок, на которые ссылается параметр [-Reference](../../../visual-basic/reference/command-line-compiler/reference.md) .</span><span class="sxs-lookup"><span data-stu-id="8e80e-112">The `-libpath` option specifies the location of assemblies referenced by the [-reference](../../../visual-basic/reference/command-line-compiler/reference.md) option.</span></span>  
  
 <span data-ttu-id="8e80e-113">Компилятор выполняет поиск связанных сборок, для которых не указано полное имя, в следующем порядке:</span><span class="sxs-lookup"><span data-stu-id="8e80e-113">The compiler searches for assembly references that are not fully qualified in the following order:</span></span>  
  
1. <span data-ttu-id="8e80e-114">Текущая рабочая папка.</span><span class="sxs-lookup"><span data-stu-id="8e80e-114">Current working directory.</span></span> <span data-ttu-id="8e80e-115">Это папка, из которой был вызван компилятор.</span><span class="sxs-lookup"><span data-stu-id="8e80e-115">This is the directory from which the compiler is invoked.</span></span>  
  
2. <span data-ttu-id="8e80e-116">Системный каталог среды CLR.</span><span class="sxs-lookup"><span data-stu-id="8e80e-116">The common language runtime system directory.</span></span>  
  
3. <span data-ttu-id="8e80e-117">Каталоги, заданные параметром `/libpath`.</span><span class="sxs-lookup"><span data-stu-id="8e80e-117">Directories specified by `/libpath`.</span></span>  
  
4. <span data-ttu-id="8e80e-118">Каталоги, указанные переменной среды LIB.</span><span class="sxs-lookup"><span data-stu-id="8e80e-118">Directories specified by the LIB environment variable.</span></span>  
  
 <span data-ttu-id="8e80e-119">Параметр `-libpath` является аддитивным; При указании более одного раза к любым предшествующим значениям добавляется.</span><span class="sxs-lookup"><span data-stu-id="8e80e-119">The `-libpath` option is additive; specifying it more than once appends to any prior values.</span></span>  
  
 <span data-ttu-id="8e80e-120">Чтобы указать ссылку на сборку, используйте `-reference`.</span><span class="sxs-lookup"><span data-stu-id="8e80e-120">Use `-reference` to specify an assembly reference.</span></span>  
  
|<span data-ttu-id="8e80e-121">Установка параметра/LIBPATH в интегрированной среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="8e80e-121">To set /libpath in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="8e80e-122">1.  Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="8e80e-122">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="8e80e-123">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="8e80e-123">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="8e80e-124">2.  Перейдите на вкладку **Ссылки**.</span><span class="sxs-lookup"><span data-stu-id="8e80e-124">2.  Click the **References** tab.</span></span><br /><span data-ttu-id="8e80e-125">3.  Нажмите кнопку **пути для ссылок...** .</span><span class="sxs-lookup"><span data-stu-id="8e80e-125">3.  Click the **Reference Paths...** button.</span></span><br /><span data-ttu-id="8e80e-126">4.  В диалоговом окне **пути для ссылок** введите имя каталога в поле **Папка:** .</span><span class="sxs-lookup"><span data-stu-id="8e80e-126">4.  In the **Reference Paths** dialog box, enter the directory name in the **Folder:** box.</span></span><br /><span data-ttu-id="8e80e-127">5.  Нажмите кнопку **Добавить папку**.</span><span class="sxs-lookup"><span data-stu-id="8e80e-127">5.  Click **Add Folder**.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="8e80e-128">Пример</span><span class="sxs-lookup"><span data-stu-id="8e80e-128">Example</span></span>  
 <span data-ttu-id="8e80e-129">Следующий код компилирует `T2.vb` для создания файла exe.</span><span class="sxs-lookup"><span data-stu-id="8e80e-129">The following code compiles `T2.vb` to create an .exe file.</span></span> <span data-ttu-id="8e80e-130">Компилятор выполняет поиск в рабочем каталоге, в корневом каталоге диска C: и в каталоге новых сборок диска C: для ссылок на сборки.</span><span class="sxs-lookup"><span data-stu-id="8e80e-130">The compiler looks in the working directory, in the root directory of the C: drive, and in the New Assemblies directory of the C: drive for assembly references.</span></span>  
  
```console  
vbc -libpath:c:\;"c:\New Assemblies" -reference:t2.dll t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="8e80e-131">См. также</span><span class="sxs-lookup"><span data-stu-id="8e80e-131">See also</span></span>

- [<span data-ttu-id="8e80e-132">Сборки в .NET</span><span class="sxs-lookup"><span data-stu-id="8e80e-132">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
- [<span data-ttu-id="8e80e-133">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="8e80e-133">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="8e80e-134">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="8e80e-134">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
