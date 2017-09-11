---
title: "-target:winexe (параметры компилятора C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /target:winexe
dev_langs:
- CSharp
helpviewer_keywords:
- /target compiler options [C#], /target:winexe
- -target compiler options [C#], /target:winexe
- target compiler options [C#], /target:winexe
ms.assetid: b5a0619c-8caa-46a5-a743-1cf68408ad7a
caps.latest.revision: 11
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: afb49fc6d45cc904c97988ab1b569f37a4e44a51
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="targetwinexe-c-compiler-options"></a><span data-ttu-id="85787-102">/target:winexe (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="85787-102">/target:winexe (C# Compiler Options)</span></span>
<span data-ttu-id="85787-103">Параметр **/target:winexe** заставляет компилятор создать исполняемый файл (EXE), программу Windows.</span><span class="sxs-lookup"><span data-stu-id="85787-103">The **/target:winexe** option causes the compiler to create an executable (EXE), Windows program.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85787-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="85787-104">Syntax</span></span>  
  
```console  
/target:winexe  
```  
  
## <a name="remarks"></a><span data-ttu-id="85787-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="85787-105">Remarks</span></span>  
 <span data-ttu-id="85787-106">Исполняемый файл создается с расширением ЕХЕ.</span><span class="sxs-lookup"><span data-stu-id="85787-106">The executable file will be created with the .exe extension.</span></span> <span data-ttu-id="85787-107">Программа Windows предоставляет пользовательский интерфейс либо из библиотеки .NET Framework, либо с помощью API Win32.</span><span class="sxs-lookup"><span data-stu-id="85787-107">A Windows program is one that provides a user interface from either the .NET Framework library or with the Win32 APIs.</span></span>  
  
 <span data-ttu-id="85787-108">Воспользуйтесь параметром [/target:exe](../../../csharp/language-reference/compiler-options/target-exe-compiler-option.md), чтобы создать консольное приложение.</span><span class="sxs-lookup"><span data-stu-id="85787-108">Use [/target:exe](../../../csharp/language-reference/compiler-options/target-exe-compiler-option.md) to create a console application.</span></span>  
  
 <span data-ttu-id="85787-109">Если не указано иное с помощью параметра [/out](../../../csharp/language-reference/compiler-options/out-compiler-option.md), имя выходного файла совпадает с именем входного файла, который содержит метод [Main](../../../csharp/programming-guide/main-and-command-args/index.md).</span><span class="sxs-lookup"><span data-stu-id="85787-109">Unless otherwise specified with the [/out](../../../csharp/language-reference/compiler-options/out-compiler-option.md) option, the output file name takes the name of the input file that contains the [Main](../../../csharp/programming-guide/main-and-command-args/index.md) method.</span></span>  
  
 <span data-ttu-id="85787-110">Для создания DLL-файла используются все файлы, указанные в командной строке вплоть до следующего параметра **/out** или [/target](../../../csharp/language-reference/compiler-options/target-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="85787-110">When specified at the command line, all files until the next **/out** or [/target](../../../csharp/language-reference/compiler-options/target-compiler-option.md) option are used to create the Windows program.</span></span>  
  
 <span data-ttu-id="85787-111">В файлах исходного кода, который компилируется в EXE-файл, должен содержаться один и только один метод **Main**.</span><span class="sxs-lookup"><span data-stu-id="85787-111">One and only one **Main** method is required in the source code files that are compiled into an .exe file.</span></span> <span data-ttu-id="85787-112">Параметр [/main](../../../csharp/language-reference/compiler-options/main-compiler-option.md) позволяет указывать класс, содержащий метод **Main**, в случаях, когда код содержит несколько классов с методом **Main**.</span><span class="sxs-lookup"><span data-stu-id="85787-112">The [/main](../../../csharp/language-reference/compiler-options/main-compiler-option.md) option lets you specify which class contains the **Main** method, in cases where your code has more than one class with a **Main** method.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="85787-113">Установка данного параметра компилятора в среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="85787-113">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="85787-114">Откройте страницу **Свойства** проекта.</span><span class="sxs-lookup"><span data-stu-id="85787-114">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="85787-115">Перейдите на страницу свойств **Приложение**.</span><span class="sxs-lookup"><span data-stu-id="85787-115">Click the **Application** property page.</span></span>  
  
3.  <span data-ttu-id="85787-116">Измените значение свойства **Тип выходных данных**.</span><span class="sxs-lookup"><span data-stu-id="85787-116">Modify the **Output type** property.</span></span>  
  
 <span data-ttu-id="85787-117">Сведения об установке этого параметра компилятора программными средствами см. в разделе <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span><span class="sxs-lookup"><span data-stu-id="85787-117">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="85787-118">Пример</span><span class="sxs-lookup"><span data-stu-id="85787-118">Example</span></span>  
 <span data-ttu-id="85787-119">Компиляция `in.cs` в программу Windows:</span><span class="sxs-lookup"><span data-stu-id="85787-119">Compile `in.cs` into a Windows program:</span></span>  
  
```console  
csc /target:winexe in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="85787-120">См. также</span><span class="sxs-lookup"><span data-stu-id="85787-120">See Also</span></span>  
 <span data-ttu-id="85787-121">[/target (параметры компилятора C#)](../../../csharp/language-reference/compiler-options/target-compiler-option.md) </span><span class="sxs-lookup"><span data-stu-id="85787-121">[/target (C# Compiler Options)](../../../csharp/language-reference/compiler-options/target-compiler-option.md) </span></span>  
 [<span data-ttu-id="85787-122">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="85787-122">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)

