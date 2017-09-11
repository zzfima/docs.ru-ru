---
title: "Построение консольных приложений в .NET Framework"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- .NET Framework, building console applications
- application development [.NET Framework], console
- console applications
ms.assetid: c21fb997-9f0e-40a5-8741-f73bba376bd8
caps.latest.revision: 16
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: bba3cde0d4e1c15ea764322b8ab0ef1501e53739
ms.contentlocale: ru-ru
ms.lasthandoff: 08/21/2017

---
# <a name="building-console-applications-in-the-net-framework"></a><span data-ttu-id="7abd7-102">Построение консольных приложений в .NET Framework</span><span class="sxs-lookup"><span data-stu-id="7abd7-102">Building Console Applications in the .NET Framework</span></span>
<span data-ttu-id="7abd7-103">Приложения .NET Framework могут использовать класс <xref:System.Console?displayProperty=fullName> для выполнения консольного ввода-вывода символов.</span><span class="sxs-lookup"><span data-stu-id="7abd7-103">Applications in the .NET Framework can use the <xref:System.Console?displayProperty=fullName> class to read characters from and write characters to the console.</span></span> <span data-ttu-id="7abd7-104">Данные, поступающие от консоли, считываются из стандартного потока ввода, выводимые на консоль данные записываются в стандартный поток вывода, а сведения об ошибках записываются в стандартный поток вывода ошибок.</span><span class="sxs-lookup"><span data-stu-id="7abd7-104">Data from the console is read from the standard input stream, data to the console is written to the standard output stream, and error data to the console is written to the standard error output stream.</span></span> <span data-ttu-id="7abd7-105">Эти потоки автоматически связываются с консолью при запуске приложения и представлены свойствами <xref:System.Console.In%2A>, <xref:System.Console.Out%2A> и <xref:System.Console.Error%2A> соответственно.</span><span class="sxs-lookup"><span data-stu-id="7abd7-105">These streams are automatically associated with the console when the application starts and are presented as the <xref:System.Console.In%2A>, <xref:System.Console.Out%2A>, and <xref:System.Console.Error%2A> properties, respectively.</span></span>  
  
 <span data-ttu-id="7abd7-106">Значением свойства <xref:System.Console.In%2A?displayProperty=fullName> является объект <xref:System.IO.TextReader?displayProperty=fullName>, а значениями свойств <xref:System.Console.Out%2A?displayProperty=fullName> и <xref:System.Console.Error%2A?displayProperty=fullName> — объекты <xref:System.IO.TextWriter?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="7abd7-106">The value of the <xref:System.Console.In%2A?displayProperty=fullName> property is a <xref:System.IO.TextReader?displayProperty=fullName> object, whereas the values of the <xref:System.Console.Out%2A?displayProperty=fullName> and <xref:System.Console.Error%2A?displayProperty=fullName> properties are <xref:System.IO.TextWriter?displayProperty=fullName> objects.</span></span> <span data-ttu-id="7abd7-107">Эти свойства можно связывать с потоками, не представляющими консоль, что позволяет задать для любого из потоков другой источник или приемник данных.</span><span class="sxs-lookup"><span data-stu-id="7abd7-107">You can associate these properties with streams that do not represent the console, making it possible for you to point the stream to a different location for input or output.</span></span> <span data-ttu-id="7abd7-108">Например, можно перенаправить вывод в файл, присвоив свойству <xref:System.Console.Out%2A?displayProperty=fullName> объект <xref:System.IO.StreamWriter?displayProperty=fullName>, инкапсулирующий <xref:System.IO.FileStream?displayProperty=fullName> с помощью метода <xref:System.Console.SetOut%2A?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="7abd7-108">For example, you can redirect the output to a file by setting the <xref:System.Console.Out%2A?displayProperty=fullName> property to a <xref:System.IO.StreamWriter?displayProperty=fullName>, which encapsulates a <xref:System.IO.FileStream?displayProperty=fullName> by means of the <xref:System.Console.SetOut%2A?displayProperty=fullName> method.</span></span> <span data-ttu-id="7abd7-109">Свойства <xref:System.Console.In%2A?displayProperty=fullName> и <xref:System.Console.Out%2A?displayProperty=fullName> не обязательно должны быть связаны с одним потоком.</span><span class="sxs-lookup"><span data-stu-id="7abd7-109">The <xref:System.Console.In%2A?displayProperty=fullName> and <xref:System.Console.Out%2A?displayProperty=fullName> properties do not need to refer to the same stream.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7abd7-110">Дополнительные сведения о построении консольных приложений, включая образцы в C#, Visual Basic, и C++, см. в документации к классу <xref:System.Console>.</span><span class="sxs-lookup"><span data-stu-id="7abd7-110">For more information about building console applications, including examples in C#, Visual Basic, and C++, see the documentation for the <xref:System.Console> class.</span></span>  
  
 <span data-ttu-id="7abd7-111">При отсутствии консоли, например в Windows-приложениях, выводимые в стандартный поток вывода данные не отображаются для пользователя, так как их некуда выводить.</span><span class="sxs-lookup"><span data-stu-id="7abd7-111">If the console does not exist, as in a Windows-based application, output written to the standard output stream will not be visible, because there is no console to write the information to.</span></span> <span data-ttu-id="7abd7-112">Запись информации в недоступную консоль не приводит к возникновению исключения.</span><span class="sxs-lookup"><span data-stu-id="7abd7-112">Writing information to an inaccessible console does not cause an exception to be raised.</span></span>  
  
 <span data-ttu-id="7abd7-113">Кроме того, чтобы использовать консоль для чтения и записи в приложении на базе Windows, разработанном в Visual Studio, откройте диалоговое окно **Свойства** проекта, перейдите на вкладку **Приложение** и задайте для параметра **Тип приложения** значение **Консольное приложение**.</span><span class="sxs-lookup"><span data-stu-id="7abd7-113">Alternately, to enable the console for reading and writing within a Windows-based application that is developed using Visual Studio, open the project's **Properties** dialog box, click the **Application** tab, and set the **Application type** to **Console Application**.</span></span>  
  
 <span data-ttu-id="7abd7-114">У консольных приложений отсутствует запускаемый по умолчанию механизм сообщений.</span><span class="sxs-lookup"><span data-stu-id="7abd7-114">Console applications lack a message pump that starts by default.</span></span> <span data-ttu-id="7abd7-115">Поэтому вызовы таймеров Microsoft Win32 из такого приложения могут завершаться неудачей.</span><span class="sxs-lookup"><span data-stu-id="7abd7-115">Therefore, console calls to Microsoft Win32 timers might fail.</span></span>  
  
 <span data-ttu-id="7abd7-116">У класса **System.Console** имеются методы, позволяющие считывать с консоли отдельные символы или целые строки.</span><span class="sxs-lookup"><span data-stu-id="7abd7-116">The **System.Console** class has methods that can read individual characters or entire lines from the console.</span></span> <span data-ttu-id="7abd7-117">Другие методы выполняют преобразование данных и форматирование строковых значений, а затем выводят отформатированные строки на консоль.</span><span class="sxs-lookup"><span data-stu-id="7abd7-117">Other methods convert data and format strings, and then write the formatted strings to the console.</span></span> <span data-ttu-id="7abd7-118">Дополнительные сведения о форматировании строк см. в статье [Общие сведения о форматировании](../../docs/standard/base-types/formatting-types.md).</span><span class="sxs-lookup"><span data-stu-id="7abd7-118">For more information on formatting strings, see [Formatting Types](../../docs/standard/base-types/formatting-types.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7abd7-119">См. также</span><span class="sxs-lookup"><span data-stu-id="7abd7-119">See Also</span></span>  
 <span data-ttu-id="7abd7-120"><xref:System.Console?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="7abd7-120"><xref:System.Console?displayProperty=fullName></span></span>   
 [<span data-ttu-id="7abd7-121">Типы форматирования</span><span class="sxs-lookup"><span data-stu-id="7abd7-121">Formatting Types</span></span>](../../docs/standard/base-types/formatting-types.md)

