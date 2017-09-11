---
title: "Практическое руководство. Перехват несовместимого с CLS исключения"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- exceptions [C#], non-CLS
ms.assetid: db4630b3-5240-471a-b3a7-c7ff6ab31e8d
caps.latest.revision: 8
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
ms.openlocfilehash: 18a19fe34b8ec13bd9fc6d25335d0931a22ce4a3
ms.contentlocale: ru-ru
ms.lasthandoff: 09/08/2017

---
# <a name="how-to-catch-a-non-cls-exception"></a><span data-ttu-id="95ec0-102">Практическое руководство. Перехват несовместимого с CLS исключения</span><span class="sxs-lookup"><span data-stu-id="95ec0-102">How to: Catch a non-CLS Exception</span></span>
<span data-ttu-id="95ec0-103">Некоторые языки .NET, включая C++/CLI, позволяют объектам вызывать исключения, которые не являются производными от <xref:System.Exception>.</span><span class="sxs-lookup"><span data-stu-id="95ec0-103">Some .NET languages, including C++/CLI, allow objects to throw exceptions that do not derive from <xref:System.Exception>.</span></span> <span data-ttu-id="95ec0-104">Такие исключения называются *несовместимыми с CLS исключениями* или *необработанными исключениями*.</span><span class="sxs-lookup"><span data-stu-id="95ec0-104">Such exceptions are called *non-CLS exceptions* or *non-Exceptions*.</span></span> <span data-ttu-id="95ec0-105">В [!INCLUDE[csprcs](~/includes/csprcs-md.md)] невозможно вызвать несовместимые с CLS исключения, однако можно перехватить их следующими двумя способами.</span><span class="sxs-lookup"><span data-stu-id="95ec0-105">In [!INCLUDE[csprcs](~/includes/csprcs-md.md)] you cannot throw non-CLS exceptions, but you can catch them in two ways:</span></span>  
  
-   <span data-ttu-id="95ec0-106">В блоке `catch (Exception e)` как <xref:System.Runtime.CompilerServices.RuntimeWrappedException>.</span><span class="sxs-lookup"><span data-stu-id="95ec0-106">Within a `catch (Exception e)` block as a <xref:System.Runtime.CompilerServices.RuntimeWrappedException>.</span></span>  
  
     <span data-ttu-id="95ec0-107">По умолчанию сборка [!INCLUDE[csprcs](~/includes/csprcs-md.md)] перехватывает несовместимые с CLS исключения как заключенные в оболочку.</span><span class="sxs-lookup"><span data-stu-id="95ec0-107">By default, a [!INCLUDE[csprcs](~/includes/csprcs-md.md)] assembly catches non-CLS exceptions as wrapped exceptions.</span></span> <span data-ttu-id="95ec0-108">Этот метод следует использовать, если требуется доступ к исходному исключению, который можно получить с помощью свойства <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A>.</span><span class="sxs-lookup"><span data-stu-id="95ec0-108">Use this method if you need access to the original exception, which can be accessed through the <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A> property.</span></span> <span data-ttu-id="95ec0-109">Далее в этом разделе описывается процедура перехвата исключений таким способом.</span><span class="sxs-lookup"><span data-stu-id="95ec0-109">The procedure later in this topic explains how to catch exceptions in this manner.</span></span>  
  
-   <span data-ttu-id="95ec0-110">В общем блоке перехвата (блоке перехвата, для которого не указан тип исключения), который помещается после блока `catch (Exception)` или `catch (Exception e)`.</span><span class="sxs-lookup"><span data-stu-id="95ec0-110">Within a general catch block (a catch block without an exception type specified) that is put after a `catch (Exception)` or `catch (Exception e)` block.</span></span>  
  
     <span data-ttu-id="95ec0-111">Используйте этот способ, если требуется выполнить какое-либо действие (например, запись в файл журнала) в ответ на несовместимые с CLS исключения, и вам не нужен доступ к сведениям об исключении.</span><span class="sxs-lookup"><span data-stu-id="95ec0-111">Use this method when you want to perform some action (such as writing to a log file) in response to non-CLS exceptions, and you do not need access to the exception information.</span></span> <span data-ttu-id="95ec0-112">По умолчанию среда CLR создает оболочку для всех исключений.</span><span class="sxs-lookup"><span data-stu-id="95ec0-112">By default the common language runtime wraps all exceptions.</span></span> <span data-ttu-id="95ec0-113">Чтобы отключить этот режим, добавьте этот атрибут уровня сборки в код, как правило, в файле AssemblyInfo.cs: `[assembly: RuntimeCompatibilityAttribute(WrapNonExceptionThrows = false)]`.</span><span class="sxs-lookup"><span data-stu-id="95ec0-113">To disable this behavior, add this assembly-level attribute to your code, typically in the AssemblyInfo.cs file: `[assembly: RuntimeCompatibilityAttribute(WrapNonExceptionThrows = false)]`.</span></span>  
  
### <a name="to-catch-a-non-cls-exception"></a><span data-ttu-id="95ec0-114">Перехват несовместимого с CLS исключения</span><span class="sxs-lookup"><span data-stu-id="95ec0-114">To catch a non-CLS exception</span></span>  
  
1.  <span data-ttu-id="95ec0-115">В `catch(Exception e) block` используйте ключевое слово `as`, чтобы проверить, может ли `e` приводиться к <xref:System.Runtime.CompilerServices.RuntimeWrappedException>.</span><span class="sxs-lookup"><span data-stu-id="95ec0-115">Within a `catch(Exception e) block`, use the `as` keyword to test whether `e` can be cast to a <xref:System.Runtime.CompilerServices.RuntimeWrappedException>.</span></span>  
  
2.  <span data-ttu-id="95ec0-116">Для доступа к исходному исключению используйте свойство <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A>.</span><span class="sxs-lookup"><span data-stu-id="95ec0-116">Access the original exception through the <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="95ec0-117">Пример</span><span class="sxs-lookup"><span data-stu-id="95ec0-117">Example</span></span>  
 <span data-ttu-id="95ec0-118">В следующем примере показано, как перехватить несовместимое с CLS исключение, которое было вызвано из библиотеки классов, написанной на C++/CLR.</span><span class="sxs-lookup"><span data-stu-id="95ec0-118">The following example shows how to catch a non-CLS exception that was thrown from a class library written in C++/CLR.</span></span> <span data-ttu-id="95ec0-119">Обратите внимание, что в этом примере клиентскому коду [!INCLUDE[csprcs](~/includes/csprcs-md.md)] заранее известно, что тип вызываемого исключения — <xref:System.String?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="95ec0-119">Note that in this example, the [!INCLUDE[csprcs](~/includes/csprcs-md.md)] client code knows in advance that the exception type being thrown is a <xref:System.String?displayProperty=fullName>.</span></span> <span data-ttu-id="95ec0-120">Можно привести свойство <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A> к его исходному типу, если этот тип доступен из кода.</span><span class="sxs-lookup"><span data-stu-id="95ec0-120">You can cast the <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A> property back its original type as long as that type is accessible from your code.</span></span>  
  
```  
// Class library written in C++/CLR.  
   ThrowNonCLS.Class1 myClass = new ThrowNonCLS.Class1();  
  
   try  
   {  
    // throws gcnew System::String(  
    // "I do not derive from System.Exception!");  
    myClass.TestThrow();   
   }  
  
   catch (Exception e)  
   {  
    RuntimeWrappedException rwe = e as RuntimeWrappedException;  
    if (rwe != null)      
    {  
      String s = rwe.WrappedException as String;  
      if (s != null)  
      {  
        Console.WriteLine(s);  
      }  
    }  
    else  
    {  
       // Handle other System.Exception types.  
    }  
   }             
```  
  
## <a name="see-also"></a><span data-ttu-id="95ec0-121">См. также</span><span class="sxs-lookup"><span data-stu-id="95ec0-121">See Also</span></span>  
 <span data-ttu-id="95ec0-122"><xref:System.Runtime.CompilerServices.RuntimeWrappedException></span><span class="sxs-lookup"><span data-stu-id="95ec0-122"><xref:System.Runtime.CompilerServices.RuntimeWrappedException></span></span>   
 [<span data-ttu-id="95ec0-123">Исключения и обработка исключений</span><span class="sxs-lookup"><span data-stu-id="95ec0-123">Exceptions and Exception Handling</span></span>](../../../csharp/programming-guide/exceptions/index.md)

