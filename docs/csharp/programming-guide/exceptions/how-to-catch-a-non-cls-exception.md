---
title: Практическое руководство. Перехват несовместимого с CLS исключения
ms.date: 07/20/2015
helpviewer_keywords:
- exceptions [C#], non-CLS
ms.assetid: db4630b3-5240-471a-b3a7-c7ff6ab31e8d
ms.openlocfilehash: 6169f4b6de2efdfed0dbf43272d708c47b46dbca
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33340025"
---
# <a name="how-to-catch-a-non-cls-exception"></a><span data-ttu-id="fdb91-102">Практическое руководство. Перехват несовместимого с CLS исключения</span><span class="sxs-lookup"><span data-stu-id="fdb91-102">How to: Catch a non-CLS Exception</span></span>
<span data-ttu-id="fdb91-103">Некоторые языки .NET, включая C++/CLI, позволяют объектам вызывать исключения, которые не являются производными от <xref:System.Exception>.</span><span class="sxs-lookup"><span data-stu-id="fdb91-103">Some .NET languages, including C++/CLI, allow objects to throw exceptions that do not derive from <xref:System.Exception>.</span></span> <span data-ttu-id="fdb91-104">Такие исключения называются *несовместимыми с CLS исключениями* или *необработанными исключениями*.</span><span class="sxs-lookup"><span data-stu-id="fdb91-104">Such exceptions are called *non-CLS exceptions* or *non-Exceptions*.</span></span> <span data-ttu-id="fdb91-105">В Visual C# невозможно вызвать несовместимые с CLS исключения, однако можно перехватить их следующими двумя способами.</span><span class="sxs-lookup"><span data-stu-id="fdb91-105">In Visual C# you cannot throw non-CLS exceptions, but you can catch them in two ways:</span></span>  
  
-   <span data-ttu-id="fdb91-106">В блоке `catch (Exception e)` как <xref:System.Runtime.CompilerServices.RuntimeWrappedException>.</span><span class="sxs-lookup"><span data-stu-id="fdb91-106">Within a `catch (Exception e)` block as a <xref:System.Runtime.CompilerServices.RuntimeWrappedException>.</span></span>  
  
     <span data-ttu-id="fdb91-107">По умолчанию сборка Visual C# перехватывает несовместимые с CLS исключения как заключенные в оболочку.</span><span class="sxs-lookup"><span data-stu-id="fdb91-107">By default, a Visual C# assembly catches non-CLS exceptions as wrapped exceptions.</span></span> <span data-ttu-id="fdb91-108">Этот метод следует использовать, если требуется доступ к исходному исключению, который можно получить с помощью свойства <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A>.</span><span class="sxs-lookup"><span data-stu-id="fdb91-108">Use this method if you need access to the original exception, which can be accessed through the <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A> property.</span></span> <span data-ttu-id="fdb91-109">Далее в этом разделе описывается процедура перехвата исключений таким способом.</span><span class="sxs-lookup"><span data-stu-id="fdb91-109">The procedure later in this topic explains how to catch exceptions in this manner.</span></span>  
  
-   <span data-ttu-id="fdb91-110">В общем блоке перехвата (блоке перехвата, для которого не указан тип исключения), который помещается после блока `catch (Exception)` или `catch (Exception e)`.</span><span class="sxs-lookup"><span data-stu-id="fdb91-110">Within a general catch block (a catch block without an exception type specified) that is put after a `catch (Exception)` or `catch (Exception e)` block.</span></span>  
  
     <span data-ttu-id="fdb91-111">Используйте этот способ, если требуется выполнить какое-либо действие (например, запись в файл журнала) в ответ на несовместимые с CLS исключения, и вам не нужен доступ к сведениям об исключении.</span><span class="sxs-lookup"><span data-stu-id="fdb91-111">Use this method when you want to perform some action (such as writing to a log file) in response to non-CLS exceptions, and you do not need access to the exception information.</span></span> <span data-ttu-id="fdb91-112">По умолчанию среда CLR создает оболочку для всех исключений.</span><span class="sxs-lookup"><span data-stu-id="fdb91-112">By default the common language runtime wraps all exceptions.</span></span> <span data-ttu-id="fdb91-113">Чтобы отключить этот режим, добавьте этот атрибут уровня сборки в код, как правило, в файле AssemblyInfo.cs: `[assembly: RuntimeCompatibilityAttribute(WrapNonExceptionThrows = false)]`.</span><span class="sxs-lookup"><span data-stu-id="fdb91-113">To disable this behavior, add this assembly-level attribute to your code, typically in the AssemblyInfo.cs file: `[assembly: RuntimeCompatibilityAttribute(WrapNonExceptionThrows = false)]`.</span></span>  
  
### <a name="to-catch-a-non-cls-exception"></a><span data-ttu-id="fdb91-114">Перехват несовместимого с CLS исключения</span><span class="sxs-lookup"><span data-stu-id="fdb91-114">To catch a non-CLS exception</span></span>  
  
1.  <span data-ttu-id="fdb91-115">В `catch(Exception e) block` используйте ключевое слово `as`, чтобы проверить, может ли `e` приводиться к <xref:System.Runtime.CompilerServices.RuntimeWrappedException>.</span><span class="sxs-lookup"><span data-stu-id="fdb91-115">Within a `catch(Exception e) block`, use the `as` keyword to test whether `e` can be cast to a <xref:System.Runtime.CompilerServices.RuntimeWrappedException>.</span></span>  
  
2.  <span data-ttu-id="fdb91-116">Для доступа к исходному исключению используйте свойство <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A>.</span><span class="sxs-lookup"><span data-stu-id="fdb91-116">Access the original exception through the <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fdb91-117">Пример</span><span class="sxs-lookup"><span data-stu-id="fdb91-117">Example</span></span>  
 <span data-ttu-id="fdb91-118">В следующем примере показано, как перехватить несовместимое с CLS исключение, которое было вызвано из библиотеки классов, написанной на C++/CLR.</span><span class="sxs-lookup"><span data-stu-id="fdb91-118">The following example shows how to catch a non-CLS exception that was thrown from a class library written in C++/CLR.</span></span> <span data-ttu-id="fdb91-119">Обратите внимание, что в этом примере клиентскому коду Visual C# заранее известно, что тип вызываемого исключения — <xref:System.String?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="fdb91-119">Note that in this example, the Visual C# client code knows in advance that the exception type being thrown is a <xref:System.String?displayProperty=nameWithType>.</span></span> <span data-ttu-id="fdb91-120">Можно привести свойство <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A> к его исходному типу, если этот тип доступен из кода.</span><span class="sxs-lookup"><span data-stu-id="fdb91-120">You can cast the <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A> property back its original type as long as that type is accessible from your code.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="fdb91-121">См. также</span><span class="sxs-lookup"><span data-stu-id="fdb91-121">See Also</span></span>  
 <xref:System.Runtime.CompilerServices.RuntimeWrappedException>  
 [<span data-ttu-id="fdb91-122">Исключения и обработка исключений</span><span class="sxs-lookup"><span data-stu-id="fdb91-122">Exceptions and Exception Handling</span></span>](../../../csharp/programming-guide/exceptions/index.md)
