---
title: -target:winexe (параметры компилятора C#)
ms.date: 07/20/2015
f1_keywords:
- /target:winexe
helpviewer_keywords:
- /target compiler options [C#], /target:winexe
- -target compiler options [C#], /target:winexe
- target compiler options [C#], /target:winexe
ms.assetid: b5a0619c-8caa-46a5-a743-1cf68408ad7a
ms.openlocfilehash: 5d5e5c62dc1a5fe6901ee232084a704d7d936b76
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2019
ms.locfileid: "58411967"
---
# <a name="-targetwinexe-c-compiler-options"></a><span data-ttu-id="c3d0c-102">-target:winexe (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="c3d0c-102">-target:winexe (C# Compiler Options)</span></span>
<span data-ttu-id="c3d0c-103">Параметр **-target:winexe** предписывает компилятору создать исполняемый файл (EXE), программу Windows.</span><span class="sxs-lookup"><span data-stu-id="c3d0c-103">The **-target:winexe** option causes the compiler to create an executable (EXE), Windows program.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3d0c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c3d0c-104">Syntax</span></span>  
  
```console  
-target:winexe  
```  
  
## <a name="remarks"></a><span data-ttu-id="c3d0c-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="c3d0c-105">Remarks</span></span>  
 <span data-ttu-id="c3d0c-106">Исполняемый файл создается с расширением ЕХЕ.</span><span class="sxs-lookup"><span data-stu-id="c3d0c-106">The executable file will be created with the .exe extension.</span></span> <span data-ttu-id="c3d0c-107">Программа Windows предоставляет пользовательский интерфейс либо из библиотеки .NET Framework, либо с помощью API Windows.</span><span class="sxs-lookup"><span data-stu-id="c3d0c-107">A Windows program is one that provides a user interface from either the .NET Framework library or with the Windows APIs.</span></span>  
  
 <span data-ttu-id="c3d0c-108">Воспользуйтесь параметром [-target:exe](../../../csharp/language-reference/compiler-options/target-exe-compiler-option.md), чтобы создать консольное приложение.</span><span class="sxs-lookup"><span data-stu-id="c3d0c-108">Use [-target:exe](../../../csharp/language-reference/compiler-options/target-exe-compiler-option.md) to create a console application.</span></span>  
  
 <span data-ttu-id="c3d0c-109">Если не указано иное с помощью параметра [-out](../../../csharp/language-reference/compiler-options/out-compiler-option.md), имя выходного файла совпадает с именем входного файла, который содержит метод [Main](../../../csharp/programming-guide/main-and-command-args/index.md).</span><span class="sxs-lookup"><span data-stu-id="c3d0c-109">Unless otherwise specified with the [-out](../../../csharp/language-reference/compiler-options/out-compiler-option.md) option, the output file name takes the name of the input file that contains the [Main](../../../csharp/programming-guide/main-and-command-args/index.md) method.</span></span>  
  
 <span data-ttu-id="c3d0c-110">Для создания DLL-файла используются все файлы, указанные в командной строке вплоть до следующего параметра **-out** или [-target](../../../csharp/language-reference/compiler-options/target-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="c3d0c-110">When specified at the command line, all files until the next **-out** or [-target](../../../csharp/language-reference/compiler-options/target-compiler-option.md) option are used to create the Windows program.</span></span>  
  
 <span data-ttu-id="c3d0c-111">В файлах исходного кода, который компилируется в EXE-файл, должен содержаться один и только один метод **Main**.</span><span class="sxs-lookup"><span data-stu-id="c3d0c-111">One and only one **Main** method is required in the source code files that are compiled into an .exe file.</span></span> <span data-ttu-id="c3d0c-112">Параметр [-main](../../../csharp/language-reference/compiler-options/main-compiler-option.md) позволяет указывать класс, содержащий метод **Main**, в случаях, когда код содержит несколько классов с методом **Main**.</span><span class="sxs-lookup"><span data-stu-id="c3d0c-112">The [-main](../../../csharp/language-reference/compiler-options/main-compiler-option.md) option lets you specify which class contains the **Main** method, in cases where your code has more than one class with a **Main** method.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="c3d0c-113">Установка данного параметра компилятора в среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c3d0c-113">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="c3d0c-114">Откройте страницу **Свойства** проекта.</span><span class="sxs-lookup"><span data-stu-id="c3d0c-114">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="c3d0c-115">Перейдите на страницу свойств **Приложение**.</span><span class="sxs-lookup"><span data-stu-id="c3d0c-115">Click the **Application** property page.</span></span>  
  
3.  <span data-ttu-id="c3d0c-116">Измените значение свойства **Тип выходных данных**.</span><span class="sxs-lookup"><span data-stu-id="c3d0c-116">Modify the **Output type** property.</span></span>  
  
 <span data-ttu-id="c3d0c-117">Сведения об установке этого параметра компилятора программными средствами см. в разделе <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span><span class="sxs-lookup"><span data-stu-id="c3d0c-117">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c3d0c-118">Пример</span><span class="sxs-lookup"><span data-stu-id="c3d0c-118">Example</span></span>  
 <span data-ttu-id="c3d0c-119">Компиляция `in.cs` в программу Windows:</span><span class="sxs-lookup"><span data-stu-id="c3d0c-119">Compile `in.cs` into a Windows program:</span></span>  
  
```console  
csc -target:winexe in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="c3d0c-120">См. также</span><span class="sxs-lookup"><span data-stu-id="c3d0c-120">See also</span></span>

- [<span data-ttu-id="c3d0c-121">-target (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="c3d0c-121">-target (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/target-compiler-option.md)
- [<span data-ttu-id="c3d0c-122">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="c3d0c-122">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
