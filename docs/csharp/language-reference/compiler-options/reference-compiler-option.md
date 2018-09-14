---
title: -reference (параметры компилятора C#)
ms.date: 07/20/2015
f1_keywords:
- /reference
helpviewer_keywords:
- /r compiler option [C#]
- reference compiler option [C#]
- r compiler option [C#]
- /reference compiler option [C#]
- -r compiler option [C#]
- metadata import [C#]
- public type information [C#]
- -reference compiler option [C#]
ms.assetid: 8d13e5b0-abf6-4c46-bf71-2daf2cd0a6c4
ms.openlocfilehash: 131cdf62917ab2fc8d564b85c30d13c8971e5809
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/09/2018
ms.locfileid: "44213719"
---
# <a name="-reference-c-compiler-options"></a><span data-ttu-id="169e9-102">-reference (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="169e9-102">-reference (C# Compiler Options)</span></span>
<span data-ttu-id="169e9-103">Параметр **-reference** предписывает компилятору импортировать сведения типа [public](../../../csharp/language-reference/keywords/public.md) из указанного файла в текущий проект. Это позволяет ссылаться на метаданные из указанных файлов сборки.</span><span class="sxs-lookup"><span data-stu-id="169e9-103">The **-reference** option causes the compiler to import [public](../../../csharp/language-reference/keywords/public.md) type information in the specified file into the current project, thus enabling you to reference metadata from the specified assembly files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="169e9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="169e9-104">Syntax</span></span>  
  
```console  
-reference:[alias=]filename  
-reference:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="169e9-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="169e9-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="169e9-106">Имя файла, содержащего манифест сборки.</span><span class="sxs-lookup"><span data-stu-id="169e9-106">The name of a file that contains an assembly manifest.</span></span> <span data-ttu-id="169e9-107">Чтобы импортировать данные из нескольких файлов, включите отдельный параметр **-reference** для каждого файла.</span><span class="sxs-lookup"><span data-stu-id="169e9-107">To import more than one file, include a separate **-reference** option for each file.</span></span>  
  
 `alias`  
 <span data-ttu-id="169e9-108">Допустимый идентификатор C#, который представляет корневое пространство имен, содержащее все пространства имен сборки.</span><span class="sxs-lookup"><span data-stu-id="169e9-108">A valid C# identifier that will represent a root namespace that will contain all namespaces in the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="169e9-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="169e9-109">Remarks</span></span>  
 <span data-ttu-id="169e9-110">Чтобы импортировать данные из нескольких файлов, включите параметр **-reference** для каждого файла.</span><span class="sxs-lookup"><span data-stu-id="169e9-110">To import from more than one file, include a **-reference** option for each file.</span></span>  
  
 <span data-ttu-id="169e9-111">Импортируемые файлы должны содержать манифест; выходной файл следует компилировать с одним из параметров [-target](../../../csharp/language-reference/compiler-options/target-compiler-option.md), отличных от [-target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="169e9-111">The files you import must contain a manifest; the output file must have been compiled with one of the [-target](../../../csharp/language-reference/compiler-options/target-compiler-option.md) options other than [-target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md).</span></span>  
  
 <span data-ttu-id="169e9-112">**-r** является краткой формой **-reference**.</span><span class="sxs-lookup"><span data-stu-id="169e9-112">**-r** is the short form of **-reference**.</span></span>  
  
 <span data-ttu-id="169e9-113">Для импорта метаданных из выходного файла, который не содержит манифест сборки, используется параметр [-addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="169e9-113">Use [-addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md) to import metadata from an output file that does not contain an assembly manifest.</span></span>  
  
 <span data-ttu-id="169e9-114">При ссылке на сборку (сборку А), которая, в свою очередь, ссылается на другую сборку (сборку Б), необходимо ссылаться на сборку Б в указанных ниже случаях.</span><span class="sxs-lookup"><span data-stu-id="169e9-114">If you reference an assembly (Assembly A) that references another assembly (Assembly B), you will need to reference Assembly B if:</span></span>  
  
-   <span data-ttu-id="169e9-115">Используемый в сборке A тип наследует от типа сборки Б или реализует интерфейс из этой сборки.</span><span class="sxs-lookup"><span data-stu-id="169e9-115">A type you use from Assembly A inherits from a type or implements an interface from Assembly B.</span></span>  
  
-   <span data-ttu-id="169e9-116">Вызывается поле, свойство, событие или метод, которые имеют тип возвращаемых данных или тип параметра из сборки Б.</span><span class="sxs-lookup"><span data-stu-id="169e9-116">You invoke a field, property, event, or method that has a return type or parameter type from Assembly B.</span></span>  
  
 <span data-ttu-id="169e9-117">Для указания каталога, где находится одна или несколько ссылок на сборки, используется параметр [-lib](../../../csharp/language-reference/compiler-options/lib-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="169e9-117">Use [-lib](../../../csharp/language-reference/compiler-options/lib-compiler-option.md) to specify the directory in which one or more of your assembly references is located.</span></span> <span data-ttu-id="169e9-118">В разделе, посвященном параметру **-lib**, также рассматриваются каталоги, в которых компилятор ищет сборки.</span><span class="sxs-lookup"><span data-stu-id="169e9-118">The **-lib** topic also discusses the directories in which the compiler searches for assemblies.</span></span>  
  
 <span data-ttu-id="169e9-119">Чтобы компилятор мог распознавать тип в сборке (не в модуле), ему следует указать принудительно разрешать типы. Это можно сделать, определив экземпляр типа.</span><span class="sxs-lookup"><span data-stu-id="169e9-119">In order for the compiler to recognize a type in an assembly, and not in a module, it needs to be forced to resolve the type, which you can do by defining an instance of the type.</span></span> <span data-ttu-id="169e9-120">Возможны и другие способы разрешения компилятором имен типов в сборке. Например, если тип наследуется от типа в сборке, его имя будет распознаваться компилятором.</span><span class="sxs-lookup"><span data-stu-id="169e9-120">There are other ways to resolve type names in an assembly for the compiler: for example, if you inherit from a type in an assembly, the type name will then be recognized by the compiler.</span></span>  
  
 <span data-ttu-id="169e9-121">Иногда бывает необходимо сослаться на две различные версии одного компонента из одной сборки.</span><span class="sxs-lookup"><span data-stu-id="169e9-121">Sometimes it is necessary to reference two different versions of the same component from within one assembly.</span></span> <span data-ttu-id="169e9-122">Для этого следует использовать подпараметр псевдонима для параметра **-reference** для каждого файла, чтобы различать два этих файла.</span><span class="sxs-lookup"><span data-stu-id="169e9-122">To do this, use the alias suboption on the **-reference** switch for each file to distinguish between the two files.</span></span> <span data-ttu-id="169e9-123">Этот псевдоним используется в качестве квалификатора имени компонента и разрешается в компонент в одном из файлов.</span><span class="sxs-lookup"><span data-stu-id="169e9-123">This alias will be used as a qualifier for the component name, and will resolve to the component in one of the files.</span></span>  
  
 <span data-ttu-id="169e9-124">Файл ответов csc (RSP-файл), который ссылается на часто используемые сборки .NET Framework, используется по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="169e9-124">The csc response (.rsp) file, which references commonly used .NET Framework assemblies, is used by default.</span></span> <span data-ttu-id="169e9-125">Параметр [-noconfig](../../../csharp/language-reference/compiler-options/noconfig-compiler-option.md) позволяет запретить компилятору использовать файл csc.rsp.</span><span class="sxs-lookup"><span data-stu-id="169e9-125">Use [-noconfig](../../../csharp/language-reference/compiler-options/noconfig-compiler-option.md) if you do not want the compiler to use csc.rsp.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="169e9-126">В Visual Studio используйте диалоговое окно **Добавление ссылки**.</span><span class="sxs-lookup"><span data-stu-id="169e9-126">In Visual Studio, use the **Add Reference** dialog box.</span></span> <span data-ttu-id="169e9-127">Дополнительные сведения см. в разделе [Практическое руководство. Добавление или удаление ссылок с помощью диспетчера ссылок](/visualstudio/ide/how-to-add-or-remove-references-by-using-the-reference-manager).</span><span class="sxs-lookup"><span data-stu-id="169e9-127">For more information, see [How to: Add or Remove References By Using the Reference Manager](/visualstudio/ide/how-to-add-or-remove-references-by-using-the-reference-manager).</span></span> <span data-ttu-id="169e9-128">Чтобы обеспечить эквивалентное поведение при добавлении ссылок с помощью `-reference` и диалогового окна **Добавление ссылки**, свойству **Внедрить типы взаимодействия** добавляемой сборки должно быть задано значение **False**.</span><span class="sxs-lookup"><span data-stu-id="169e9-128">To ensure equivalent behavior between adding references by using `-reference` and adding references by using the **Add Reference** dialog box, set the **Embed Interop Types** property to **False** for the assembly that you're adding.</span></span> <span data-ttu-id="169e9-129">**True** является значением по умолчанию для этого свойства.</span><span class="sxs-lookup"><span data-stu-id="169e9-129">**True** is the default value for the property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="169e9-130">Пример</span><span class="sxs-lookup"><span data-stu-id="169e9-130">Example</span></span>  
 <span data-ttu-id="169e9-131">В этом примере показано, как использовать [псевдоним extern](../../../csharp/language-reference/keywords/extern-alias.md).</span><span class="sxs-lookup"><span data-stu-id="169e9-131">This example shows how to use the [extern alias](../../../csharp/language-reference/keywords/extern-alias.md) feature.</span></span>  
  
 <span data-ttu-id="169e9-132">В примере компилируется файл исходного кода и импортируются метаданные из сборок `grid.dll` и `grid20.dll`, которые были скомпилированы ранее.</span><span class="sxs-lookup"><span data-stu-id="169e9-132">You compile the source file and import metadata from `grid.dll` and `grid20.dll`, which have been compiled previously.</span></span> <span data-ttu-id="169e9-133">Два DLL-файла содержат разные версии одного компонента, поэтому для компиляции файла исходного кода используются два параметра **-reference** с подпараметрами псевдонимов.</span><span class="sxs-lookup"><span data-stu-id="169e9-133">The two DLLs contain separate versions of the same component, and you use two **-reference** with alias options to compile the source file.</span></span> <span data-ttu-id="169e9-134">Параметры выглядят следующим образом:</span><span class="sxs-lookup"><span data-stu-id="169e9-134">The options look like this:</span></span>  

```console
-reference:GridV1=grid.dll -reference:GridV2=grid20.dll  
```
  
 <span data-ttu-id="169e9-135">При этом устанавливаются внешние псевдонимы `GridV1` и `GridV2`, которые используются посредством оператора `extern`.</span><span class="sxs-lookup"><span data-stu-id="169e9-135">This sets up the external aliases `GridV1` and `GridV2`, which you use in your program by means of an `extern` statement:</span></span>  
  
```csharp  
extern alias GridV1;  
extern alias GridV2;  
// Using statements go here.  
```  
  
 <span data-ttu-id="169e9-136">После выполнения описанных выше действий можно ссылаться на элемент управления "сетка" из файла `grid.dll`, предваряя имя элемента управления префиксом `GridV1`, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="169e9-136">Once this is done, you can refer to the grid control from `grid.dll` by prefixing the control name with `GridV1`, like this:</span></span>  
  
```csharp  
GridV1::Grid  
```  
  
 <span data-ttu-id="169e9-137">Кроме того, можно ссылаться на элемент управления "сетка" из файла `grid20.dll`, предваряя имя элемента управления префиксом `GridV2`, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="169e9-137">In addition, you can refer to the grid control from `grid20.dll` by prefixing the control name with `GridV2` like this:</span></span>  
  
```csharp  
GridV2::Grid   
```  
  
## <a name="see-also"></a><span data-ttu-id="169e9-138">См. также</span><span class="sxs-lookup"><span data-stu-id="169e9-138">See Also</span></span>  

- [<span data-ttu-id="169e9-139">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="169e9-139">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
- [<span data-ttu-id="169e9-140">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="169e9-140">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
