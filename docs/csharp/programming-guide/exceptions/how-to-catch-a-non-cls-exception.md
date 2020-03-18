---
title: Практическое руководство. Перехват несовместимого с CLS исключения
ms.date: 07/20/2015
helpviewer_keywords:
- exceptions [C#], non-CLS
ms.assetid: db4630b3-5240-471a-b3a7-c7ff6ab31e8d
ms.openlocfilehash: 635cf0a9142f56dea4b2722fbf3f3eda505d85ee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "75346278"
---
# <a name="how-to-catch-a-non-cls-exception"></a><span data-ttu-id="252d7-102">Практическое руководство. Перехват несовместимого с CLS исключения</span><span class="sxs-lookup"><span data-stu-id="252d7-102">How to catch a non-CLS exception</span></span>
<span data-ttu-id="252d7-103">Некоторые языки .NET, включая C++/CLI, позволяют объектам вызывать исключения, которые не являются производными от <xref:System.Exception>.</span><span class="sxs-lookup"><span data-stu-id="252d7-103">Some .NET languages, including C++/CLI, allow objects to throw exceptions that do not derive from <xref:System.Exception>.</span></span> <span data-ttu-id="252d7-104">Такие исключения называются *несовместимыми с CLS исключениями* или *необработанными исключениями*.</span><span class="sxs-lookup"><span data-stu-id="252d7-104">Such exceptions are called *non-CLS exceptions* or *non-Exceptions*.</span></span> <span data-ttu-id="252d7-105">В C# невозможно вызвать несовместимые с CLS исключения, однако можно перехватить их следующими двумя способами.</span><span class="sxs-lookup"><span data-stu-id="252d7-105">In C# you cannot throw non-CLS exceptions, but you can catch them in two ways:</span></span>  
  
- <span data-ttu-id="252d7-106">В блоке `catch (RuntimeWrappedException e)`.</span><span class="sxs-lookup"><span data-stu-id="252d7-106">Within a `catch (RuntimeWrappedException e)` block.</span></span>
  
     <span data-ttu-id="252d7-107">По умолчанию сборка Visual C# перехватывает несовместимые с CLS исключения как заключенные в оболочку.</span><span class="sxs-lookup"><span data-stu-id="252d7-107">By default, a Visual C# assembly catches non-CLS exceptions as wrapped exceptions.</span></span> <span data-ttu-id="252d7-108">Этот метод следует использовать, если требуется доступ к исходному исключению, который можно получить с помощью свойства <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="252d7-108">Use this method if you need access to the original exception, which can be accessed through the <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="252d7-109">Далее в этом разделе описывается процедура перехвата исключений таким способом.</span><span class="sxs-lookup"><span data-stu-id="252d7-109">The procedure later in this topic explains how to catch exceptions in this manner.</span></span>  
  
- <span data-ttu-id="252d7-110">В общем блоке перехвата (блоке перехвата, для которого не указан тип исключения), который помещается после остальных блоков `catch`.</span><span class="sxs-lookup"><span data-stu-id="252d7-110">Within a general catch block (a catch block without an exception type specified) that is put after all other `catch` blocks.</span></span>
  
     <span data-ttu-id="252d7-111">Используйте этот способ, если требуется выполнить какое-либо действие (например, запись в файл журнала) в ответ на несовместимые с CLS исключения, и вам не нужен доступ к сведениям об исключении.</span><span class="sxs-lookup"><span data-stu-id="252d7-111">Use this method when you want to perform some action (such as writing to a log file) in response to non-CLS exceptions, and you do not need access to the exception information.</span></span> <span data-ttu-id="252d7-112">По умолчанию среда CLR создает оболочку для всех исключений.</span><span class="sxs-lookup"><span data-stu-id="252d7-112">By default the common language runtime wraps all exceptions.</span></span> <span data-ttu-id="252d7-113">Чтобы отключить этот режим, добавьте этот атрибут уровня сборки в код, как правило, в файле AssemblyInfo.cs: `[assembly: RuntimeCompatibilityAttribute(WrapNonExceptionThrows = false)]`.</span><span class="sxs-lookup"><span data-stu-id="252d7-113">To disable this behavior, add this assembly-level attribute to your code, typically in the AssemblyInfo.cs file: `[assembly: RuntimeCompatibilityAttribute(WrapNonExceptionThrows = false)]`.</span></span>  
  
### <a name="to-catch-a-non-cls-exception"></a><span data-ttu-id="252d7-114">Перехват несовместимого с CLS исключения</span><span class="sxs-lookup"><span data-stu-id="252d7-114">To catch a non-CLS exception</span></span>  
  
<span data-ttu-id="252d7-115">В блоке `catch(RuntimeWrappedException e)` для доступа к исходному исключению используйте свойство <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="252d7-115">Within a `catch(RuntimeWrappedException e)` block, access the original exception through the <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="252d7-116">Пример</span><span class="sxs-lookup"><span data-stu-id="252d7-116">Example</span></span>  
 <span data-ttu-id="252d7-117">В следующем примере показано, как перехватить несовместимое с CLS исключение, которое было вызвано из библиотеки классов, написанной на C++/CLI.</span><span class="sxs-lookup"><span data-stu-id="252d7-117">The following example shows how to catch a non-CLS exception that was thrown from a class library written in C++/CLI.</span></span> <span data-ttu-id="252d7-118">Обратите внимание, что в этом примере клиентскому коду C# заранее известно, что тип вызываемого исключения — <xref:System.String?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="252d7-118">Note that in this example, the C# client code knows in advance that the exception type being thrown is a <xref:System.String?displayProperty=nameWithType>.</span></span> <span data-ttu-id="252d7-119">Можно привести свойство <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A?displayProperty=nameWithType> к его исходному типу, если этот тип доступен из кода.</span><span class="sxs-lookup"><span data-stu-id="252d7-119">You can cast the <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A?displayProperty=nameWithType> property back its original type as long as that type is accessible from your code.</span></span>  
  
```csharp
// Class library written in C++/CLI.
var myClass = new ThrowNonCLS.Class1();

try
{
    // throws gcnew System::String(  
    // "I do not derive from System.Exception!");  
    myClass.TestThrow();
}
catch (RuntimeWrappedException e)
{
    String s = e.WrappedException as String;
    if (s != null)
    {
        Console.WriteLine(s);
    }
}
```  
  
## <a name="see-also"></a><span data-ttu-id="252d7-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="252d7-120">See also</span></span>

- <xref:System.Runtime.CompilerServices.RuntimeWrappedException>
- [<span data-ttu-id="252d7-121">Исключения и обработка исключений</span><span class="sxs-lookup"><span data-stu-id="252d7-121">Exceptions and Exception Handling</span></span>](./index.md)
