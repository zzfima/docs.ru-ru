---
title: "-target:winmdobj (параметры компилятора C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 1819a045-659d-498a-9457-c466e902986f
caps.latest.revision: "15"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: f690591b79159a0196a1637903f2cc53442976e3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="targetwinmdobj-c-compiler-options"></a><span data-ttu-id="b2d1a-102">/target:winmdobj (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="b2d1a-102">/target:winmdobj (C# Compiler Options)</span></span>
<span data-ttu-id="b2d1a-103">Если используется параметр компилятора **/target:winmdobj**, компилятор создает промежуточный WINMDOBJ-файл, который можно преобразовать в бинарный WINMD-файл среды выполнения Windows.</span><span class="sxs-lookup"><span data-stu-id="b2d1a-103">If you use the **/target:winmdobj** compiler option, the compiler creates an intermediate .winmdobj file that you can convert to a Windows Runtime binary (.winmd) file.</span></span> <span data-ttu-id="b2d1a-104">Затем WINMD-файл можно использовать в программах на языках JavaScript и C++ в дополнение к программам, использующим управляемые языки.</span><span class="sxs-lookup"><span data-stu-id="b2d1a-104">The .winmd file can then be consumed by JavaScript and C++ programs, in addition to managed language programs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2d1a-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b2d1a-105">Syntax</span></span>  
  
```console  
/target:winmdobj  
```  
  
## <a name="remarks"></a><span data-ttu-id="b2d1a-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="b2d1a-106">Remarks</span></span>  
 <span data-ttu-id="b2d1a-107">Параметр **winmdobj** сигнализирует компилятору, что необходим промежуточный модуль.</span><span class="sxs-lookup"><span data-stu-id="b2d1a-107">The **winmdobj** setting signals to the compiler that an intermediate module is required.</span></span> <span data-ttu-id="b2d1a-108">В результате Visual Studio компилирует библиотеку классов C# в виде WINMDOBJ-файла.</span><span class="sxs-lookup"><span data-stu-id="b2d1a-108">In response, Visual Studio compiles the C# class library as a .winmdobj file.</span></span> <span data-ttu-id="b2d1a-109">Затем WINMDOBJ-файл можно обработать с помощью инструмента экспорта <xref:Microsoft.Build.Tasks.WinMDExp> для создания файла метаданных Windows (WINCMD-файл).</span><span class="sxs-lookup"><span data-stu-id="b2d1a-109">The .winmdobj file can then be fed through the <xref:Microsoft.Build.Tasks.WinMDExp> export tool to produce a Windows metadata (.winmd) file.</span></span> <span data-ttu-id="b2d1a-110">WINMD-файл содержит код из исходной библиотеки и метаданные WinMD, используемые JavaScript, C++ и средой выполнения Windows.</span><span class="sxs-lookup"><span data-stu-id="b2d1a-110">The .winmd file contains both the code from the original library and the WinMD metadata that is used by JavaScript or C++ and by the Windows Runtime.</span></span>  
  
 <span data-ttu-id="b2d1a-111">Выходные данные файла, скомпилированного с помощью параметра **/target:winmdobj**, предназначены только для использования в качестве входных данных инструментом экспорта WimMDExp (на WINMDOBJ-файл нет прямой ссылки).</span><span class="sxs-lookup"><span data-stu-id="b2d1a-111">The output of a file that’s compiled by using the **/target:winmdobj** compiler option is designed to be used only as input for the WimMDExp export tool; the .winmdobj file itself isn’t referenced directly.</span></span>  
  
 <span data-ttu-id="b2d1a-112">Выходной файл получает имя первого входного файла, если только с помощью параметра [/out](../../../csharp/language-reference/compiler-options/out-compiler-option.md) не указано иное.</span><span class="sxs-lookup"><span data-stu-id="b2d1a-112">Unless you use the [/out](../../../csharp/language-reference/compiler-options/out-compiler-option.md) option, the output file name takes the name of the first input file.</span></span> <span data-ttu-id="b2d1a-113">Метод [Main](../../../csharp/programming-guide/main-and-command-args/index.md) не требуется.</span><span class="sxs-lookup"><span data-stu-id="b2d1a-113">A [Main](../../../csharp/programming-guide/main-and-command-args/index.md) method isn’t required.</span></span>  
  
 <span data-ttu-id="b2d1a-114">Если параметр /target:winmdobj указан в командной строке, все файлы до следующего параметра **/out** или [/target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md) будут использоваться для создания программы Windows.</span><span class="sxs-lookup"><span data-stu-id="b2d1a-114">If you specify the /target:winmdobj option at a command prompt, all files until the next **/out** or [/target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md) option are used to create the Windows program.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-ide-for-a-windows-store-app"></a><span data-ttu-id="b2d1a-115">Установка данного параметра компилятора в интегрированной среде разработки Visual Studio для приложения для Магазина Windows</span><span class="sxs-lookup"><span data-stu-id="b2d1a-115">To set this compiler option in the Visual Studio IDE for a Windows Store app</span></span>  
  
1.  <span data-ttu-id="b2d1a-116">В **обозревателе решений** откройте контекстное меню своего проекта и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="b2d1a-116">In **Solution Explorer**, open the shortcut menu for your project, and then choose **Properties**.</span></span>  
  
2.  <span data-ttu-id="b2d1a-117">Перейдите на вкладку **Приложение**.</span><span class="sxs-lookup"><span data-stu-id="b2d1a-117">Choose the **Application** tab.</span></span>  
  
3.  <span data-ttu-id="b2d1a-118">В списке **Тип выходных данных** выберите **Файл WinMD**.</span><span class="sxs-lookup"><span data-stu-id="b2d1a-118">In the **Output type** list, choose **WinMD File**.</span></span>  
  
     <span data-ttu-id="b2d1a-119">Параметр **Файл WinMD[!INCLUDE[win8_appname_long](~/includes/win8-appname-long-md.md)] доступен только для шаблонов приложений для** .</span><span class="sxs-lookup"><span data-stu-id="b2d1a-119">The **WinMD File** option is available only for [!INCLUDE[win8_appname_long](~/includes/win8-appname-long-md.md)] app templates.</span></span>  
  
 <span data-ttu-id="b2d1a-120">Дополнительные сведения об установке этого параметра компилятора программным путем см. в разделе <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span><span class="sxs-lookup"><span data-stu-id="b2d1a-120">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b2d1a-121">Пример</span><span class="sxs-lookup"><span data-stu-id="b2d1a-121">Example</span></span>  
 <span data-ttu-id="b2d1a-122">Следующая команда компилирует `filename.cs` в промежуточный WINMDOBJ-файл.</span><span class="sxs-lookup"><span data-stu-id="b2d1a-122">The following command compiles `filename.cs` into an intermediate .winmdobj file.</span></span>  
  
```console  
csc /target:winmdobj filename.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="b2d1a-123">См. также</span><span class="sxs-lookup"><span data-stu-id="b2d1a-123">See Also</span></span>  
 [<span data-ttu-id="b2d1a-124">/ Target (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="b2d1a-124">/target (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/target-compiler-option.md)  
 [<span data-ttu-id="b2d1a-125">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="b2d1a-125">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
