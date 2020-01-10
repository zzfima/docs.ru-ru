---
title: -libpath
ms.date: 03/10/2018
helpviewer_keywords:
- libpath compiler option [Visual Basic]
- /libpath compiler option [Visual Basic]
- -libpath compiler option [Visual Basic]
ms.assetid: 5f1c26c9-3455-4e89-bdf3-b12d6c2e655b
ms.openlocfilehash: 9a5822a097828f818da020735c3822e86eb3236b
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716641"
---
# <a name="-libpath"></a><span data-ttu-id="ab76d-102">-libpath</span><span class="sxs-lookup"><span data-stu-id="ab76d-102">-libpath</span></span>
<span data-ttu-id="ab76d-103">Задает расположение сборок, на которые указывают ссылки.</span><span class="sxs-lookup"><span data-stu-id="ab76d-103">Specifies the location of referenced assemblies.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab76d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ab76d-104">Syntax</span></span>  
  
```console  
-libpath:dirList  
```  
  
## <a name="arguments"></a><span data-ttu-id="ab76d-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="ab76d-105">Arguments</span></span>  
  
|<span data-ttu-id="ab76d-106">Термин</span><span class="sxs-lookup"><span data-stu-id="ab76d-106">Term</span></span>|<span data-ttu-id="ab76d-107">Определение</span><span class="sxs-lookup"><span data-stu-id="ab76d-107">Definition</span></span>|  
|---|---|  
|`dirList`|<span data-ttu-id="ab76d-108">Обязательное</span><span class="sxs-lookup"><span data-stu-id="ab76d-108">Required.</span></span> <span data-ttu-id="ab76d-109">Разделенный точками с запятой список каталогов, в которых компилятор должен искать, если сборка, на которую указывает ссылка, не найдена ни в текущем рабочем каталоге (каталоге, из которого вызывается компилятор), ни в системном каталоге среды CLR.</span><span class="sxs-lookup"><span data-stu-id="ab76d-109">Semicolon-delimited list of directories for the compiler to look in if a referenced assembly is not found in either the current working directory (the directory from which you are invoking the compiler) or the common language runtime's system directory.</span></span> <span data-ttu-id="ab76d-110">Если имя каталога содержит пробел, заключите его в кавычки ("").</span><span class="sxs-lookup"><span data-stu-id="ab76d-110">If the directory name contains a space, enclose the name in quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ab76d-111">Заметки</span><span class="sxs-lookup"><span data-stu-id="ab76d-111">Remarks</span></span>  
 <span data-ttu-id="ab76d-112">Параметр `-libpath` задает расположение сборок, на которые ссылается параметр [-Reference](../../../visual-basic/reference/command-line-compiler/reference.md) .</span><span class="sxs-lookup"><span data-stu-id="ab76d-112">The `-libpath` option specifies the location of assemblies referenced by the [-reference](../../../visual-basic/reference/command-line-compiler/reference.md) option.</span></span>  
  
 <span data-ttu-id="ab76d-113">Компилятор выполняет поиск связанных сборок, для которых не указано полное имя, в следующем порядке:</span><span class="sxs-lookup"><span data-stu-id="ab76d-113">The compiler searches for assembly references that are not fully qualified in the following order:</span></span>  
  
1. <span data-ttu-id="ab76d-114">Текущая рабочая папка.</span><span class="sxs-lookup"><span data-stu-id="ab76d-114">Current working directory.</span></span> <span data-ttu-id="ab76d-115">Это папка, из которой был вызван компилятор.</span><span class="sxs-lookup"><span data-stu-id="ab76d-115">This is the directory from which the compiler is invoked.</span></span>  
  
2. <span data-ttu-id="ab76d-116">Системный каталог среды CLR.</span><span class="sxs-lookup"><span data-stu-id="ab76d-116">The common language runtime system directory.</span></span>  
  
3. <span data-ttu-id="ab76d-117">Каталоги, заданные `-libpath`.</span><span class="sxs-lookup"><span data-stu-id="ab76d-117">Directories specified by `-libpath`.</span></span>  
  
4. <span data-ttu-id="ab76d-118">Каталоги, указанные переменной среды LIB.</span><span class="sxs-lookup"><span data-stu-id="ab76d-118">Directories specified by the LIB environment variable.</span></span>  
  
 <span data-ttu-id="ab76d-119">Параметр `-libpath` является аддитивным; При указании более одного раза к любым предшествующим значениям добавляется.</span><span class="sxs-lookup"><span data-stu-id="ab76d-119">The `-libpath` option is additive; specifying it more than once appends to any prior values.</span></span>  
  
 <span data-ttu-id="ab76d-120">Используйте `-reference`, чтобы указать ссылку на сборку.</span><span class="sxs-lookup"><span data-stu-id="ab76d-120">Use `-reference` to specify an assembly reference.</span></span>  
  
|<span data-ttu-id="ab76d-121">Установка параметра-LIBPATH в интегрированной среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ab76d-121">To set -libpath in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="ab76d-122">1. Выберите проект в **Обозреватель решений**.</span><span class="sxs-lookup"><span data-stu-id="ab76d-122">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="ab76d-123">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="ab76d-123">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="ab76d-124">2. Перейдите на вкладку **ссылки** .</span><span class="sxs-lookup"><span data-stu-id="ab76d-124">2.  Click the **References** tab.</span></span><br /><span data-ttu-id="ab76d-125">3. Нажмите кнопку **пути для ссылок...** .</span><span class="sxs-lookup"><span data-stu-id="ab76d-125">3.  Click the **Reference Paths...** button.</span></span><br /><span data-ttu-id="ab76d-126">4. в диалоговом окне **пути для ссылок** введите имя каталога в поле **Папка:** .</span><span class="sxs-lookup"><span data-stu-id="ab76d-126">4.  In the **Reference Paths** dialog box, enter the directory name in the **Folder:** box.</span></span><br /><span data-ttu-id="ab76d-127">5. Нажмите кнопку **Добавить папку**.</span><span class="sxs-lookup"><span data-stu-id="ab76d-127">5.  Click **Add Folder**.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ab76d-128">Пример</span><span class="sxs-lookup"><span data-stu-id="ab76d-128">Example</span></span>  
 <span data-ttu-id="ab76d-129">Следующий код компилирует `T2.vb`, чтобы создать exe файл.</span><span class="sxs-lookup"><span data-stu-id="ab76d-129">The following code compiles `T2.vb` to create an .exe file.</span></span> <span data-ttu-id="ab76d-130">Компилятор выполняет поиск в рабочем каталоге, в корневом каталоге диска C: и в каталоге новых сборок диска C: для ссылок на сборки.</span><span class="sxs-lookup"><span data-stu-id="ab76d-130">The compiler looks in the working directory, in the root directory of the C: drive, and in the New Assemblies directory of the C: drive for assembly references.</span></span>  
  
```console  
vbc -libpath:c:\;"c:\New Assemblies" -reference:t2.dll t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="ab76d-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="ab76d-131">See also</span></span>

- [<span data-ttu-id="ab76d-132">Сборки в .NET</span><span class="sxs-lookup"><span data-stu-id="ab76d-132">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
- [<span data-ttu-id="ab76d-133">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="ab76d-133">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="ab76d-134">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="ab76d-134">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
