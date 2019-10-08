---
title: -win32icon
ms.date: 03/13/2018
helpviewer_keywords:
- win32icon compiler option [Visual Basic]
- -win32icon compiler option [Visual Basic]
- /win32icon compiler option [Visual Basic]
ms.assetid: aecaab01-9353-46c5-941c-6edabd4eff92
ms.openlocfilehash: 6b4b69d227c857442de6857fac023090b3698e81
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004644"
---
# <a name="-win32icon"></a><span data-ttu-id="3111f-102">-win32icon</span><span class="sxs-lookup"><span data-stu-id="3111f-102">-win32icon</span></span>
<span data-ttu-id="3111f-103">Вставляет ICO файл в выходной файл.</span><span class="sxs-lookup"><span data-stu-id="3111f-103">Inserts an .ico file in the output file.</span></span> <span data-ttu-id="3111f-104">Этот ICO файл представляет выходной файл в **проводнике**.</span><span class="sxs-lookup"><span data-stu-id="3111f-104">This .ico file represents the output file in **File Explorer**.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3111f-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3111f-105">Syntax</span></span>  
  
```console  
-win32icon:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="3111f-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="3111f-106">Arguments</span></span>  
  
|<span data-ttu-id="3111f-107">Термин</span><span class="sxs-lookup"><span data-stu-id="3111f-107">Term</span></span>|<span data-ttu-id="3111f-108">Определение</span><span class="sxs-lookup"><span data-stu-id="3111f-108">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="3111f-109">ICO файл, добавляемый в выходной файл.</span><span class="sxs-lookup"><span data-stu-id="3111f-109">The .ico file to add to your output file.</span></span> <span data-ttu-id="3111f-110">Заключите имя файла в кавычки (""), если оно содержит пробел.</span><span class="sxs-lookup"><span data-stu-id="3111f-110">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3111f-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="3111f-111">Remarks</span></span>  
 <span data-ttu-id="3111f-112">Вы можете создать ICO-файл с помощью компилятора ресурсов Microsoft Windows (RC).</span><span class="sxs-lookup"><span data-stu-id="3111f-112">You can create an .ico file with the Microsoft Windows Resource Compiler (RC).</span></span> <span data-ttu-id="3111f-113">Компилятор ресурсов вызывается при компиляции визуальной C++ программы; ICO-файл создается из файла. rc.</span><span class="sxs-lookup"><span data-stu-id="3111f-113">The resource compiler is invoked when you compile a Visual C++ program; an .ico file is created from the .rc file.</span></span> <span data-ttu-id="3111f-114">Параметры `-win32icon` и `-win32resource` являются взаимоисключающими.</span><span class="sxs-lookup"><span data-stu-id="3111f-114">The `-win32icon` and `-win32resource` options are mutually exclusive.</span></span>  
  
 <span data-ttu-id="3111f-115">Чтобы присоединить файл ресурсов .NET Framework, см. раздел [-linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) для ссылки на файл ресурсов .NET Framework или [-Resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) .</span><span class="sxs-lookup"><span data-stu-id="3111f-115">See [-linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) to reference a .NET Framework resource file, or [-resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) to attach a .NET Framework resource file.</span></span> <span data-ttu-id="3111f-116">Чтобы импортировать RES-файл, см. [win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) .</span><span class="sxs-lookup"><span data-stu-id="3111f-116">See [-win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) to import a .res file.</span></span>  
  
|<span data-ttu-id="3111f-117">Установка параметра-win32icon в интегрированной среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="3111f-117">To set -win32icon in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="3111f-118">1.  Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="3111f-118">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="3111f-119">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="3111f-119">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="3111f-120">2.  Перейдите на вкладку **Приложение** .</span><span class="sxs-lookup"><span data-stu-id="3111f-120">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="3111f-121">3.  Измените значение в поле **значок** .</span><span class="sxs-lookup"><span data-stu-id="3111f-121">3.  Modify the value in the **Icon** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="3111f-122">Пример</span><span class="sxs-lookup"><span data-stu-id="3111f-122">Example</span></span>  
 <span data-ttu-id="3111f-123">Следующий код компилирует `In.vb` и прикрепляет файл ICO, `Rf.ico`.</span><span class="sxs-lookup"><span data-stu-id="3111f-123">The following code compiles `In.vb` and attaches an .ico file, `Rf.ico`.</span></span>  
  
```console
vbc -win32icon:rf.ico in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="3111f-124">См. также</span><span class="sxs-lookup"><span data-stu-id="3111f-124">See also</span></span>

- [<span data-ttu-id="3111f-125">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="3111f-125">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="3111f-126">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="3111f-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
