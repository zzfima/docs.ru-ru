---
title: -target:exe (параметры компилятора C#)
ms.date: 07/20/2015
f1_keywords:
- /exe
helpviewer_keywords:
- target compiler options [C#], /target:exe
- /target compiler options [C#], /target:exe
- -target compiler options [C#], /target:exe
ms.assetid: bda5717d-1b91-4848-956b-fcf85c30e432
ms.openlocfilehash: 4a2d3ea2bda56caf6a16f52877ad36b3947357e8
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2018
ms.locfileid: "43391114"
---
# <a name="-targetexe-c-compiler-options"></a><span data-ttu-id="ad541-102">-target:exe (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="ad541-102">-target:exe (C# Compiler Options)</span></span>
<span data-ttu-id="ad541-103">Параметр **-target:exe** предписывает компилятору создать исполняемое (EXE) консольное приложение.</span><span class="sxs-lookup"><span data-stu-id="ad541-103">The **-target:exe** option causes the compiler to create an executable (EXE), console application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad541-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ad541-104">Syntax</span></span>  
  
```console  
-target:exe  
```  
  
## <a name="remarks"></a><span data-ttu-id="ad541-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="ad541-105">Remarks</span></span>  
 <span data-ttu-id="ad541-106">Параметр **-target:exe** действует по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ad541-106">The **-target:exe** option is in effect by default.</span></span> <span data-ttu-id="ad541-107">Исполняемый файл создается с расширением ЕХЕ.</span><span class="sxs-lookup"><span data-stu-id="ad541-107">The executable file will be created with the .exe extension.</span></span>  
  
 <span data-ttu-id="ad541-108">Используйте параметр [-target:winexe](../../../csharp/language-reference/compiler-options/target-winexe-compiler-option.md) для создания исполняемого файла программы Windows.</span><span class="sxs-lookup"><span data-stu-id="ad541-108">Use [-target:winexe](../../../csharp/language-reference/compiler-options/target-winexe-compiler-option.md) to create a Windows program executable.</span></span>  
  
 <span data-ttu-id="ad541-109">Если не указано иное с помощью параметра [-out](../../../csharp/language-reference/compiler-options/out-compiler-option.md), имя выходного файла совпадает с именем входного файла, который содержит метод [Main](../../../csharp/programming-guide/main-and-command-args/index.md).</span><span class="sxs-lookup"><span data-stu-id="ad541-109">Unless otherwise specified with the [-out](../../../csharp/language-reference/compiler-options/out-compiler-option.md) option, the output file name takes the name of the input file that contains the [Main](../../../csharp/programming-guide/main-and-command-args/index.md) method.</span></span>  
  
 <span data-ttu-id="ad541-110">Для создания EXE-файла используются все файлы, указанные в командной строке до следующего параметра **-out** или **-target:module**.</span><span class="sxs-lookup"><span data-stu-id="ad541-110">When specified at the command line, all files up to the next **-out** or **-target:module** option are used to create the .exe file</span></span>  
  
 <span data-ttu-id="ad541-111">В файлах исходного кода, который компилируется в EXE-файл, должен содержаться один и только один метод **Main**.</span><span class="sxs-lookup"><span data-stu-id="ad541-111">One and only one **Main** method is required in the source code files that are compiled into an .exe file.</span></span> <span data-ttu-id="ad541-112">Если код содержит несколько классов с методом **Main**, то указать, какой класс содержит метод **Main**, можно с помощью параметра компилятора [-main](../../../csharp/language-reference/compiler-options/main-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="ad541-112">The [-main](../../../csharp/language-reference/compiler-options/main-compiler-option.md) compiler option lets you specify which class contains the **Main** method, in cases where your code has more than one class with a **Main** method.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="ad541-113">Установка данного параметра компилятора в среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ad541-113">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="ad541-114">Откройте страницу **Свойства** проекта.</span><span class="sxs-lookup"><span data-stu-id="ad541-114">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="ad541-115">Перейдите на страницу свойств **Приложение**.</span><span class="sxs-lookup"><span data-stu-id="ad541-115">Click the **Application** property page.</span></span>  
  
3.  <span data-ttu-id="ad541-116">Измените значение свойства **Тип выходных данных**.</span><span class="sxs-lookup"><span data-stu-id="ad541-116">Modify the **Output type** property.</span></span>  
  
 <span data-ttu-id="ad541-117">Сведения об установке этого параметра компилятора программными средствами см. в разделе <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span><span class="sxs-lookup"><span data-stu-id="ad541-117">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ad541-118">Пример</span><span class="sxs-lookup"><span data-stu-id="ad541-118">Example</span></span>  
 <span data-ttu-id="ad541-119">В каждой из представленных ниже команд командной строки выполняется компиляция файла `in.cs` для создания файла `in.exe`.</span><span class="sxs-lookup"><span data-stu-id="ad541-119">Each of the following command lines will compile `in.cs`, creating `in.exe`:</span></span>  
  
```console  
csc -target:exe in.cs  
csc in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="ad541-120">См. также</span><span class="sxs-lookup"><span data-stu-id="ad541-120">See Also</span></span>  

- [<span data-ttu-id="ad541-121">-target (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="ad541-121">-target (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/target-compiler-option.md)  
- [<span data-ttu-id="ad541-122">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="ad541-122">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
