---
title: "extern (справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- extern_CSharpKeyword
- extern
dev_langs:
- CSharp
helpviewer_keywords:
- DllImport attribute
- extern keyword [C#]
ms.assetid: 9c3f02c4-51b8-4d80-9cb2-f2b6e1ae15c7
caps.latest.revision: 26
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
ms.openlocfilehash: e499ade5ec8a9339b0d425c59809cf7c177466fb
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="extern-c-reference"></a><span data-ttu-id="a6c26-102">extern (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="a6c26-102">extern (C# Reference)</span></span>
<span data-ttu-id="a6c26-103">Модификатор `extern` используется для объявления метода с внешней реализацией.</span><span class="sxs-lookup"><span data-stu-id="a6c26-103">The `extern` modifier is used to declare a method that is implemented externally.</span></span> <span data-ttu-id="a6c26-104">При применении служб взаимодействия для вызова неуправляемого кода модификатор `extern` обычно используется с атрибутом `DllImport`.</span><span class="sxs-lookup"><span data-stu-id="a6c26-104">A common use of the `extern` modifier is with the `DllImport` attribute when you are using Interop services to call into unmanaged code.</span></span> <span data-ttu-id="a6c26-105">В этом случае также необходимо объявить метод как `static` в соответствии со следующим примером:</span><span class="sxs-lookup"><span data-stu-id="a6c26-105">In this case, the method must also be declared as `static`, as shown in the following example:</span></span>  
  
```  
[DllImport("avifil32.dll")]  
private static extern void AVIFileInit();  
```  
  
 <span data-ttu-id="a6c26-106">Ключевое слово `extern` может также определять внешний псевдоним сборки, который позволяет ссылаться на разные версии одного компонента из одной сборки.</span><span class="sxs-lookup"><span data-stu-id="a6c26-106">The `extern` keyword can also define an external assembly alias, which makes it possible to reference different versions of the same component from within a single assembly.</span></span> <span data-ttu-id="a6c26-107">Дополнительные сведения см. в разделе [Псевдоним extern](../../../csharp/language-reference/keywords/extern-alias.md).</span><span class="sxs-lookup"><span data-stu-id="a6c26-107">For more information, see [extern alias](../../../csharp/language-reference/keywords/extern-alias.md).</span></span>  
  
 <span data-ttu-id="a6c26-108">Совместное использование модификаторов [abstract](../../../csharp/language-reference/keywords/abstract.md) и `extern` для изменения одного члена недопустимо.</span><span class="sxs-lookup"><span data-stu-id="a6c26-108">It is an error to use the [abstract](../../../csharp/language-reference/keywords/abstract.md) and `extern` modifiers together to modify the same member.</span></span> <span data-ttu-id="a6c26-109">Использование модификатора `extern` означает, что метод реализуется вне кода C#, а применение модификатора `abstract` указывает на то, что в данном классе реализация метода не обеспечивается.</span><span class="sxs-lookup"><span data-stu-id="a6c26-109">Using the `extern` modifier means that the method is implemented outside the C# code, whereas using the `abstract` modifier means that the method implementation is not provided in the class.</span></span>  
  
 <span data-ttu-id="a6c26-110">В C# ключевое слово extern имеет более ограниченное применение, чем в C++.</span><span class="sxs-lookup"><span data-stu-id="a6c26-110">The extern keyword has more limited uses in C# than in C++.</span></span> <span data-ttu-id="a6c26-111">Сравнительные характеристики использования этого ключевого слова в C# и в C++ см. в разделе "Использование extern для указания компоновки" Справочника по языку C++.</span><span class="sxs-lookup"><span data-stu-id="a6c26-111">To compare the C# keyword with the C++ keyword, see Using extern to Specify Linkage in the C++ Language Reference.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a6c26-112">Пример</span><span class="sxs-lookup"><span data-stu-id="a6c26-112">Example</span></span>  
 <span data-ttu-id="a6c26-113">**Пример 1.**</span><span class="sxs-lookup"><span data-stu-id="a6c26-113">**Example 1.**</span></span> <span data-ttu-id="a6c26-114">В этом примере программа получает от пользователя строку и отображает ее в окне сообщения.</span><span class="sxs-lookup"><span data-stu-id="a6c26-114">In this example, the program receives a string from the user and displays it inside a message box.</span></span> <span data-ttu-id="a6c26-115">В этой программе используется метод `MessageBox`, импортированный из библиотеки User32.dll.</span><span class="sxs-lookup"><span data-stu-id="a6c26-115">The program uses the `MessageBox` method imported from the User32.dll library.</span></span>  
  
 <span data-ttu-id="a6c26-116">[!code-cs[csrefKeywordsModifiers#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/extern_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="a6c26-116">[!code-cs[csrefKeywordsModifiers#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/extern_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="a6c26-117">Пример</span><span class="sxs-lookup"><span data-stu-id="a6c26-117">Example</span></span>  
 <span data-ttu-id="a6c26-118">**Пример 2.**</span><span class="sxs-lookup"><span data-stu-id="a6c26-118">**Example 2.**</span></span> <span data-ttu-id="a6c26-119">В этом примере показана программа C#, в которой вызывается библиотека C (собственная библиотека DLL).</span><span class="sxs-lookup"><span data-stu-id="a6c26-119">This example illustrates a C# program that calls into a C library (a native DLL).</span></span>  
  
 1. <span data-ttu-id="a6c26-120">Создайте следующий файл C и назовите его `cmdll.c`.</span><span class="sxs-lookup"><span data-stu-id="a6c26-120">Create the following C file and name it `cmdll.c`:</span></span>  
  
```  
// cmdll.c  
// Compile with: /LD  
int __declspec(dllexport) SampleMethod(int i)  
{  
   return i*10;  
}  
```  
  
## <a name="example"></a><span data-ttu-id="a6c26-121">Пример</span><span class="sxs-lookup"><span data-stu-id="a6c26-121">Example</span></span>  
 2. <span data-ttu-id="a6c26-122">Откройте из каталога установки Visual Studio окно командной строки Visual Studio x64 (или x32) Native Tools и скомпилируйте файл `cmdll.c`, введя в командной строке **cl /LD cmdll.c**.</span><span class="sxs-lookup"><span data-stu-id="a6c26-122">Open a Visual Studio x64 (or x32) Native Tools Command Prompt window from the Visual Studio installation directory and compile the `cmdll.c` file by typing **cl /LD cmdll.c** at the command prompt.</span></span>  
  
 3. <span data-ttu-id="a6c26-123">В том же каталоге создайте следующий файл C# и назовите его `cm.cs`.</span><span class="sxs-lookup"><span data-stu-id="a6c26-123">In the same directory, create the following C# file and name it `cm.cs`:</span></span>  
  
```  
// cm.cs  
using System;  
using System.Runtime.InteropServices;  
public class MainClass   
{  
   [DllImport("Cmdll.dll")]  
   public static extern int SampleMethod(int x);  
  
   static void Main()   
   {  
      Console.WriteLine("SampleMethod() returns {0}.", SampleMethod(5));  
   }  
}  
```  
  
## <a name="example"></a><span data-ttu-id="a6c26-124">Пример</span><span class="sxs-lookup"><span data-stu-id="a6c26-124">Example</span></span>  
 3. <span data-ttu-id="a6c26-125">Откройте из каталога установки Visual Studio окно командной строки Visual Studio x64 (или x32) Native Tools и скомпилируйте файл `cm.cs`, введя:</span><span class="sxs-lookup"><span data-stu-id="a6c26-125">Open a Visual Studio x64 (or x32) Native Tools Command Prompt window from the Visual Studio installation directory and compile the `cm.cs` file by typing:</span></span>  
  
> <span data-ttu-id="a6c26-126">**csc cm.cs** (для командной строки x64)</span><span class="sxs-lookup"><span data-stu-id="a6c26-126">**csc cm.cs** (for the x64 command prompt)</span></span>   
>  <span data-ttu-id="a6c26-127">—или—</span><span class="sxs-lookup"><span data-stu-id="a6c26-127">—or—</span></span>  
> <span data-ttu-id="a6c26-128">**csc /platform:x86 cm.cs** (для командной строки x32)</span><span class="sxs-lookup"><span data-stu-id="a6c26-128">**csc /platform:x86 cm.cs** (for the x32 command prompt)</span></span>  
  
 <span data-ttu-id="a6c26-129">При этом будет создан исполняемый файл `cm.exe`.</span><span class="sxs-lookup"><span data-stu-id="a6c26-129">This will create the executable file `cm.exe`.</span></span>  
  
 4. <span data-ttu-id="a6c26-130">Запустите `cm.exe`.</span><span class="sxs-lookup"><span data-stu-id="a6c26-130">Run `cm.exe`.</span></span> <span data-ttu-id="a6c26-131">Метод `SampleMethod` передает значение 5 в файл DLL, который возвращает значение, умноженное на 10.</span><span class="sxs-lookup"><span data-stu-id="a6c26-131">The `SampleMethod` method passes the value 5 to the DLL file, which returns the value multiplied by 10.</span></span>  <span data-ttu-id="a6c26-132">Программа выдает следующие результаты.</span><span class="sxs-lookup"><span data-stu-id="a6c26-132">The program produces the following output:</span></span>  
  
```  
SampleMethod() returns 50.  
```  
  
## <a name="c-language-specification"></a><span data-ttu-id="a6c26-133">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="a6c26-133">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a6c26-134">См. также</span><span class="sxs-lookup"><span data-stu-id="a6c26-134">See Also</span></span>  
 <span data-ttu-id="a6c26-135"><xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="a6c26-135"><xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName></span></span>   
 <span data-ttu-id="a6c26-136">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="a6c26-136">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="a6c26-137">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="a6c26-137">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="a6c26-138">[Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="a6c26-138">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 [<span data-ttu-id="a6c26-139">Модификаторы</span><span class="sxs-lookup"><span data-stu-id="a6c26-139">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)

