---
title: Разработка больших, быстро реагирующих приложений .NET Framework
ms.date: 03/30/2017
ms.assetid: 123457ac-4223-4273-bb58-3bc0e4957e9d
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: c320d004b05e58fc7c239cd8c1f3bcec84ad8f78
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937910"
---
# <a name="writing-large-responsive-net-framework-apps"></a><span data-ttu-id="2f281-102">Разработка больших, быстро реагирующих приложений .NET Framework</span><span class="sxs-lookup"><span data-stu-id="2f281-102">Writing Large, Responsive .NET Framework Apps</span></span>

<span data-ttu-id="2f281-103">В этой статье приведены советы по повышению производительности крупных приложений .NET Framework или приложений, обрабатывающих большой объем данных, например файлов или баз данных.</span><span class="sxs-lookup"><span data-stu-id="2f281-103">This article provides tips for improving the performance of large .NET Framework apps, or apps that process a large amount of data such as files or databases.</span></span> <span data-ttu-id="2f281-104">Эти советы выработаны во время перевода компиляторов C# и Visual Basic на управляемый код, кроме того, здесь приведено несколько реальных примеров из компилятора C#.</span><span class="sxs-lookup"><span data-stu-id="2f281-104">These tips come from rewriting the C# and Visual Basic compilers in managed code, and this article includes several real examples from the C# compiler.</span></span> 
  
<span data-ttu-id="2f281-105">Платформа .NET Framework отлично подходит для создания приложений.</span><span class="sxs-lookup"><span data-stu-id="2f281-105">The .NET Framework is highly productive for building apps.</span></span> <span data-ttu-id="2f281-106">Эффективные и безопасные языки и обширная коллекция библиотек делают процесс создания приложений крайне плодотворным.</span><span class="sxs-lookup"><span data-stu-id="2f281-106">Powerful and safe languages and a rich collection of libraries make app building highly fruitful.</span></span> <span data-ttu-id="2f281-107">Однако высокая производительность требует высокой ответственности.</span><span class="sxs-lookup"><span data-stu-id="2f281-107">However, with great productivity comes responsibility.</span></span> <span data-ttu-id="2f281-108">Вам следует использовать все возможности платформы .NET Framework, однако быть готовым к подстройке производительности кода по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="2f281-108">You should use all the power of the .NET Framework, but be prepared to tune your code’s performance when needed.</span></span> 
  
## <a name="why-the-new-compiler-performance-applies-to-your-app"></a><span data-ttu-id="2f281-109">Как производительность нового компилятора затрагивает ваше приложение</span><span class="sxs-lookup"><span data-stu-id="2f281-109">Why the new compiler performance applies to your app</span></span>  
 <span data-ttu-id="2f281-110">Группа разработчиков платформы компиляторов .NET ("Roslyn") переписала компиляторы для языков C# и Visual Basic в управляемом коде, чтобы предоставить новые API для моделирования и анализа кода, средства разработки, а также реализовать в Visual Studio более обширные возможности взаимодействия с учетом кода.</span><span class="sxs-lookup"><span data-stu-id="2f281-110">The .NET Compiler Platform ("Roslyn") team rewrote the C# and Visual Basic compilers in managed code to provide new APIs for modeling and analyzing code, building tools, and enabling much richer, code-aware experiences in Visual Studio.</span></span> <span data-ttu-id="2f281-111">Переработка компиляторов и создание процедур взаимодействия Visual Studio на базе новых компиляторов позволили получить ценные сведения по поводу производительности, распространяющиеся на любое крупное приложение .NET Framework или любое приложение, обрабатывающее большой объем данных.</span><span class="sxs-lookup"><span data-stu-id="2f281-111">Rewriting the compilers and building Visual Studio experiences on the new compilers revealed useful performance insights that are applicable to any large .NET Framework app or any app that processes a lot of data.</span></span> <span data-ttu-id="2f281-112">Чтобы с пользой воспользоваться этими ценными сведениями и примерами из компилятора C#, вам не нужно углубляться в изучение компиляторов.</span><span class="sxs-lookup"><span data-stu-id="2f281-112">You don't need to know about compilers to take advantage of the insights and examples from the C# compiler.</span></span> 
  
 <span data-ttu-id="2f281-113">Visual Studio использует API компиляторов для сборки всех любимых пользователями возможностей IntelliSense, таких как раскраска идентификаторов и ключевых слов, списки завершения синтаксиса, подчеркивание слов с ошибками, подсказки по параметрам, проблемы с кодом и действия кода.</span><span class="sxs-lookup"><span data-stu-id="2f281-113">Visual Studio uses the compiler APIs to build all the IntelliSense features that users love, such as colorization of identifiers and keywords, syntax completion lists, squiggles for errors, parameter tips, code issues, and code actions.</span></span> <span data-ttu-id="2f281-114">Visual Studio предоставляет эти вспомогательные средства, пока разработчики вводят и изменяют код, поэтому среда Visual Studio должна сохранять возможность реагирования в условиях, когда компилятор постоянно моделирует изменяемый разработчиками код.</span><span class="sxs-lookup"><span data-stu-id="2f281-114">Visual Studio provides this help while developers are typing and changing their code, and Visual Studio must remain responsive while the compiler continually models the code developers edit.</span></span> 
  
 <span data-ttu-id="2f281-115">Когда конечные пользователи взаимодействуют с приложением, они ожидают, что оно отреагирует на их действия.</span><span class="sxs-lookup"><span data-stu-id="2f281-115">When your end users interact with your app, they expect it to be responsive.</span></span> <span data-ttu-id="2f281-116">Ввод кода или обработка команд не должны блокироваться ни в каких ситуациях.</span><span class="sxs-lookup"><span data-stu-id="2f281-116">Typing or command handling should never be blocked.</span></span> <span data-ttu-id="2f281-117">Справка должна отображаться быстро или пропадать, если пользователь продолжает ввод.</span><span class="sxs-lookup"><span data-stu-id="2f281-117">Help should pop up quickly or give up if the user continues typing.</span></span> <span data-ttu-id="2f281-118">Ваше приложение не должно блокировать поток пользовательского интерфейса длительными вычислительными операциями, так как пользователь воспринимает такое приложение как работающее медленно.</span><span class="sxs-lookup"><span data-stu-id="2f281-118">Your app should avoid blocking the UI thread with long computations that make the app feel sluggish.</span></span> 
  
 <span data-ttu-id="2f281-119">Дополнительные сведения о компиляторах Roslyn см. [в разделе пакет SDK для .NET Compiler Platform](../../csharp/roslyn-sdk/index.md).</span><span class="sxs-lookup"><span data-stu-id="2f281-119">For more information about Roslyn compilers, see [The .NET Compiler Platform SDK](../../csharp/roslyn-sdk/index.md).</span></span>
  
## <a name="just-the-facts"></a><span data-ttu-id="2f281-120">Только факты</span><span class="sxs-lookup"><span data-stu-id="2f281-120">Just the Facts</span></span>  
 <span data-ttu-id="2f281-121">Принимайте эти факты во внимание во время подстройки производительности и создания приложений .NET Framework, активно реагирующих на действия пользователя.</span><span class="sxs-lookup"><span data-stu-id="2f281-121">Consider these facts when tuning performance and creating responsive .NET Framework apps.</span></span> 
  
### <a name="fact-1-dont-prematurely-optimize"></a><span data-ttu-id="2f281-122">Факт 1. Не проводите преждевременную оптимизацию</span><span class="sxs-lookup"><span data-stu-id="2f281-122">Fact 1: Don’t prematurely optimize</span></span>  
 <span data-ttu-id="2f281-123">Если создаваемый код сложнее, чем требуется, он потребует дополнительных расходов на обслуживание, отладку и доводку.</span><span class="sxs-lookup"><span data-stu-id="2f281-123">Writing code that is more complex than it needs to be incurs maintenance, debugging, and polishing costs.</span></span> <span data-ttu-id="2f281-124">Опытные программисты обладают чутьем, подсказывающим им способы решения возникающих проблем для получения наиболее эффективного кода.</span><span class="sxs-lookup"><span data-stu-id="2f281-124">Experienced programmers have an intuitive grasp of how to solve coding problems and write more efficient code.</span></span> <span data-ttu-id="2f281-125">Однако иногда они оптимизируют свой код преждевременно.</span><span class="sxs-lookup"><span data-stu-id="2f281-125">However, they sometimes prematurely optimize their code.</span></span> <span data-ttu-id="2f281-126">Например, они используют хэш-таблицу там, где было бы достаточно простого массива, или используют сложное кэширование, которое может вызвать утечку памяти, вместо того, чтобы просто пересчитать значения.</span><span class="sxs-lookup"><span data-stu-id="2f281-126">For example, they use a hash table when a simple array would suffice, or use complicated caching that may leak memory instead of simply recomputing values.</span></span> <span data-ttu-id="2f281-127">Даже если вы обладает определенным опытом программирования, необходимо тестировать производительность и анализировать код при обнаружении проблем.</span><span class="sxs-lookup"><span data-stu-id="2f281-127">Even if you’re an experience programmer, you should test for performance and analyze your code when you find issues.</span></span> 
  
### <a name="fact-2-if-youre-not-measuring-youre-guessing"></a><span data-ttu-id="2f281-128">Факт 2. Если вы не измеряете, значит, вы угадываете</span><span class="sxs-lookup"><span data-stu-id="2f281-128">Fact 2: If you’re not measuring, you’re guessing</span></span>  
 <span data-ttu-id="2f281-129">Профили и измерения не врут.</span><span class="sxs-lookup"><span data-stu-id="2f281-129">Profiles and measurements don’t lie.</span></span> <span data-ttu-id="2f281-130">Профили показывают, полностью ли загружен ЦП или выполняется ли блокировка на уровне операций ввода-вывода диска.</span><span class="sxs-lookup"><span data-stu-id="2f281-130">Profiles show you whether the CPU is fully loaded or whether you’re blocked on disk I/O.</span></span> <span data-ttu-id="2f281-131">Профили сообщают вам, какой тип и объем памяти вы выделяете и тратит ли ЦП слишком много времени на [сборку мусора](../../standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="2f281-131">Profiles tell you what kind and how much memory you’re allocating and whether your CPU is spending a lot of time in [garbage collection](../../standard/garbage-collection/index.md) (GC).</span></span> 
  
 <span data-ttu-id="2f281-132">Вам следует задать целевые показатели производительности для ключевых пользовательских функций или сценариев в приложении и написать тесты для измерения производительности.</span><span class="sxs-lookup"><span data-stu-id="2f281-132">You should set performance goals for key customer experiences or scenarios in your app and write tests to measure performance.</span></span> <span data-ttu-id="2f281-133">Случаи сбоя тестов следует рассматривать с применением научного подхода: используйте профили для определения признаков, сделайте предположение о характере неполадки и подтвердите или опровергните это предположение с помощью эксперимента или изменения кода.</span><span class="sxs-lookup"><span data-stu-id="2f281-133">Investigate failing tests by applying the scientific method: use profiles to guide you, hypothesize what the issue might be, and test your hypothesis with an experiment or code change.</span></span> <span data-ttu-id="2f281-134">Проводите измерения базовой производительности и регулярные тестирования, чтобы иметь возможность исключить изменения, вызывающие снижение производительности.</span><span class="sxs-lookup"><span data-stu-id="2f281-134">Establish baseline performance measurements over time with regular testing, so you can isolate changes that cause regressions in performance.</span></span> <span data-ttu-id="2f281-135">Выбрав правильный подход к работе над производительностью, вы избавите себя от потери времени на внесение в код ненужных обновлений.</span><span class="sxs-lookup"><span data-stu-id="2f281-135">By approaching performance work in a rigorous way, you’ll avoid wasting time with code updates you don’t need.</span></span> 
  
### <a name="fact-3-good-tools-make-all-the-difference"></a><span data-ttu-id="2f281-136">Факт 3. Значение хороших средств трудно переоценить</span><span class="sxs-lookup"><span data-stu-id="2f281-136">Fact 3: Good tools make all the difference</span></span>  
 <span data-ttu-id="2f281-137">Хорошие средства позволяют вам быстро выявлять наиболее важные проблемы с производительностью (ЦП, память или диск) и помогают локализовать код, вызывающий такие узкие места.</span><span class="sxs-lookup"><span data-stu-id="2f281-137">Good tools let you drill quickly into the biggest performance issues (CPU, memory, or disk) and help you locate the code that causes those bottlenecks.</span></span> <span data-ttu-id="2f281-138">Корпорация Майкрософт поставляет разнообразные средства повышения производительности, такие как [профилировщик Visual Studio](/visualstudio/profiling/beginners-guide-to-performance-profiling) и [PerfView](https://www.microsoft.com/download/details.aspx?id=28567).</span><span class="sxs-lookup"><span data-stu-id="2f281-138">Microsoft ships a variety of performance tools such as [Visual Studio Profiler](/visualstudio/profiling/beginners-guide-to-performance-profiling) and [PerfView](https://www.microsoft.com/download/details.aspx?id=28567).</span></span> 
  
 <span data-ttu-id="2f281-139">PerfView — это бесплатное и крайне эффективное средство, помогающее вам сконцентрироваться на самых важных проблемах — операциях ввода-вывода диска, событиях сборки мусора и памяти.</span><span class="sxs-lookup"><span data-stu-id="2f281-139">PerfView is a free and amazingly powerful tool that helps you focus on deep issues such as disk I/O, GC events, and memory.</span></span> <span data-ttu-id="2f281-140">Вы можете перехватывать связанные с производительностью события [трассировки событий Windows](../wcf/samples/etw-tracing.md) и просматривать информацию для отдельных приложений, процессов, стеков и потоков.</span><span class="sxs-lookup"><span data-stu-id="2f281-140">You can capture performance-related [Event Tracing for Windows](../wcf/samples/etw-tracing.md) (ETW) events and view easily per app, per process, per stack, and per thread information.</span></span> <span data-ttu-id="2f281-141">PerfView показывает, какой объем и тип памяти выделяет ваше приложение, а также какие функции или стеки вызовов чаще всего осуществляют выделение памяти.</span><span class="sxs-lookup"><span data-stu-id="2f281-141">PerfView shows you how much and what kind of memory your app allocates, and which functions or call stacks contribute how much to the memory allocations.</span></span> <span data-ttu-id="2f281-142">Дополнительные сведения см. в разделах справки, демонстрациях и видеозаписях, поставляемых вместе с этим средством (например, [учебники по PerfView](https://channel9.msdn.com/Series/PerfView-Tutorial) в Channel 9).</span><span class="sxs-lookup"><span data-stu-id="2f281-142">For details, see the rich help topics, demos, and videos included with the tool (such as the [PerfView tutorials](https://channel9.msdn.com/Series/PerfView-Tutorial) on Channel 9).</span></span> 
  
### <a name="fact-4-its-all-about-allocations"></a><span data-ttu-id="2f281-143">Факт 4. Выделения памяти значат больше всего</span><span class="sxs-lookup"><span data-stu-id="2f281-143">Fact 4: It’s all about allocations</span></span>  
 <span data-ttu-id="2f281-144">Вы можете считать, что при создании приложения .NET Framework, активно реагирующего на действия пользователя, самыми важными являются алгоритмы, например использование быстрой сортировки вместо пузырьковой, но это не так.</span><span class="sxs-lookup"><span data-stu-id="2f281-144">You might think that building a responsive .NET Framework app is all about algorithms, such as using quick sort instead of bubble sort, but that's not the case.</span></span> <span data-ttu-id="2f281-145">При создании такого приложения важнее всего выделение памяти, особенно в том случае, если это приложение имеет очень большой размер или обрабатывает большие объемы данных.</span><span class="sxs-lookup"><span data-stu-id="2f281-145">The biggest factor in building a responsive app is allocating memory, especially when your app is very large or processes large amounts of data.</span></span> 
  
 <span data-ttu-id="2f281-146">Практически вся работа по созданию процедур взаимодействия IDE с помощью API новых компиляторов связана с предотвращением выделений и управлением стратегиями кэширования.</span><span class="sxs-lookup"><span data-stu-id="2f281-146">Almost all the work to build responsive IDE experiences with the new compiler APIs involved avoiding allocations and managing caching strategies.</span></span> <span data-ttu-id="2f281-147">Трассировки PerfView показывают, что производительность новых компиляторов C# и Visual редко привязана к ЦП.</span><span class="sxs-lookup"><span data-stu-id="2f281-147">PerfView traces show that the performance of the new C# and Visual Basic compilers is rarely CPU bound.</span></span> <span data-ttu-id="2f281-148">Компиляторы могут зависеть от операций ввода-вывода при считывании сотен тысяч или миллионов строк кода, считывании метаданных или выводе сформированного кода.</span><span class="sxs-lookup"><span data-stu-id="2f281-148">The compilers can be I/O bound when reading hundreds of thousands or millions of lines of code, reading metadata, or emitting generated code.</span></span> <span data-ttu-id="2f281-149">Практически все задержки потока пользовательского интерфейса вызваны сборкой мусора.</span><span class="sxs-lookup"><span data-stu-id="2f281-149">The UI thread delays are nearly all due to garbage collection.</span></span> <span data-ttu-id="2f281-150">Процедура сборки мусора в .NET Framework реализована с учетом обеспечения высокой производительности и выполняет основную часть работы параллельно с выполнением кода приложения.</span><span class="sxs-lookup"><span data-stu-id="2f281-150">The .NET Framework GC is highly tuned for performance and does much of its work concurrently while app code executes.</span></span> <span data-ttu-id="2f281-151">Однако отдельное выделение может активировать ресурсоемкую сборку [gen2](../../standard/garbage-collection/fundamentals.md), остановив все потоки.</span><span class="sxs-lookup"><span data-stu-id="2f281-151">However, a single allocation can trigger an expensive [gen2](../../standard/garbage-collection/fundamentals.md) collection, stopping all threads.</span></span> 
  
## <a name="common-allocations-and-examples"></a><span data-ttu-id="2f281-152">Распространенные выделения и примеры</span><span class="sxs-lookup"><span data-stu-id="2f281-152">Common allocations and examples</span></span>  
 <span data-ttu-id="2f281-153">Примеры выражение в этом разделе имеют скрытые выделения, которые кажутся незначительными.</span><span class="sxs-lookup"><span data-stu-id="2f281-153">The example expressions in this section have hidden allocations that appear small.</span></span> <span data-ttu-id="2f281-154">Однако если крупное приложение выполняет эти выражения достаточно большое число раз, они могут вызвать выделение сотен мегабайт и даже нескольких гигабайт памяти.</span><span class="sxs-lookup"><span data-stu-id="2f281-154">However, if a large app executes the expressions enough times, they can causes hundreds of megabytes, even gigabytes, of allocations.</span></span> <span data-ttu-id="2f281-155">Например, минутные тесты, имитирующие ввод кода разработчиком в редакторе, выделили гигабайты памяти и вынудили группу по обеспечению производительности сосредоточить усилия на сценариях ввода.</span><span class="sxs-lookup"><span data-stu-id="2f281-155">For example, one-minute tests that simulated a developer’s typing in the editor allocated gigabytes of memory and led the performance team to focus on typing scenarios.</span></span> 
  
### <a name="boxing"></a><span data-ttu-id="2f281-156">Упаковка</span><span class="sxs-lookup"><span data-stu-id="2f281-156">Boxing</span></span>  
 <span data-ttu-id="2f281-157">[Упаковка-преобразование](../../csharp/programming-guide/types/boxing-and-unboxing.md) происходит, когда типы значения, которые обычно находятся в стеке или структурах данных, упаковываются в объект.</span><span class="sxs-lookup"><span data-stu-id="2f281-157">[Boxing](../../csharp/programming-guide/types/boxing-and-unboxing.md) occurs when value types that normally live on the stack or in data structures are wrapped in an object.</span></span> <span data-ttu-id="2f281-158">То есть вы выделяете объект для хранения данных, а затем возвращаете указатель на этот объект.</span><span class="sxs-lookup"><span data-stu-id="2f281-158">That is, you allocate an object to hold the data, and then return a pointer to the object.</span></span> <span data-ttu-id="2f281-159">Платформа .NET Framework иногда выполняет упаковку-преобразование значений в связи с сигнатурой метода или типом выделения хранилища.</span><span class="sxs-lookup"><span data-stu-id="2f281-159">The .NET Framework sometimes boxes values due to the signature of a method or the type of a storage location.</span></span> <span data-ttu-id="2f281-160">Упаковка типа значения в объект приводит к выделению памяти.</span><span class="sxs-lookup"><span data-stu-id="2f281-160">Wrapping a value type in an object causes memory allocation.</span></span> <span data-ttu-id="2f281-161">Многие операции упаковки-преобразования могут приводить к выделению мегабайт и гигабайт памяти в приложении, что увеличит объем сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="2f281-161">Many boxing operations can contribute megabytes or gigabytes of allocations to your app, which means that your app will cause more GCs.</span></span> <span data-ttu-id="2f281-162">Платформа .NET Framework и компиляторы языков стараются по возможности не использовать упаковку-преобразование, но иногда оно возникает в самый неожиданный момент.</span><span class="sxs-lookup"><span data-stu-id="2f281-162">The .NET Framework and the language compilers avoid boxing when possible, but sometimes it happens when you least expect it.</span></span> 
  
 <span data-ttu-id="2f281-163">Чтобы просмотреть упаковку-преобразование в PerfView, откройте трассировку и просмотрите "GC Heap Alloc Stacks" (Стеки выделения кучи сборки мусора) под именем процесса вашего приложения (помните, что PerfView включает в отчет все процессы).</span><span class="sxs-lookup"><span data-stu-id="2f281-163">To see boxing in PerfView, open a trace and look at GC Heap Alloc Stacks under your app’s process name (remember, PerfView reports on all processes).</span></span> <span data-ttu-id="2f281-164">Если в выделениях видны такие типы, как <xref:System.Int32?displayProperty=nameWithType> и <xref:System.Char?displayProperty=nameWithType>, значит, вы выполняете упаковку-преобразование типов значения.</span><span class="sxs-lookup"><span data-stu-id="2f281-164">If you see types like <xref:System.Int32?displayProperty=nameWithType> and <xref:System.Char?displayProperty=nameWithType> under allocations, you are boxing value types.</span></span> <span data-ttu-id="2f281-165">При выборе одного из этих типов отображаются стеки и функции, в которые выполнено упаковка-преобразование.</span><span class="sxs-lookup"><span data-stu-id="2f281-165">Choosing one of these types will show the stacks and functions in which they are boxed.</span></span> 
  
 <span data-ttu-id="2f281-166">**Пример 1: строковые методы и аргументы типов значения**</span><span class="sxs-lookup"><span data-stu-id="2f281-166">**Example 1: string methods and value type arguments**</span></span>  
  
 <span data-ttu-id="2f281-167">Этот пример кода показывает ненужное и излишнее упаковка-преобразование:</span><span class="sxs-lookup"><span data-stu-id="2f281-167">This sample code illustrates potentially unnecessary and excessive boxing:</span></span>  
  
```csharp  
public class Logger  
{  
    public static void WriteLine(string s) { /*...*/ }  
}  
  
public class BoxingExample  
{  
    public void Log(int id, int size)  
    {  
        var s = string.Format("{0}:{1}", id, size);  
        Logger.WriteLine(s);  
    }  
}  
```  
  
 <span data-ttu-id="2f281-168">Данный код предоставляет функциональность ведения журналов, поэтому приложение может вызывать функцию `Log` очень часть, возможно, несколько миллионов раз.</span><span class="sxs-lookup"><span data-stu-id="2f281-168">This code provides logging functionality, so an app may call the `Log` function frequently, maybe millions of times.</span></span> <span data-ttu-id="2f281-169">Проблема заключается в том, что вызов `string.Format` разрешается в перегрузку <xref:System.String.Format%28System.String%2CSystem.Object%2CSystem.Object%29>.</span><span class="sxs-lookup"><span data-stu-id="2f281-169">The problem is that the call to `string.Format` resolves to the <xref:System.String.Format%28System.String%2CSystem.Object%2CSystem.Object%29> overload.</span></span> 
  
 <span data-ttu-id="2f281-170">Эта перегрузка требует, чтобы платформа .NET Framework выполнила упаковку-преобразование значений `int` в объекты, чтобы передать их в этот вызов метода.</span><span class="sxs-lookup"><span data-stu-id="2f281-170">This overload requires the .NET Framework to box the `int` values into objects to pass them to this method call.</span></span> <span data-ttu-id="2f281-171">Частичное исправление заключается в вызове `id.ToString()` и `size.ToString()` и передаче всех строк (которые являются объектами) в вызов `string.Format`.</span><span class="sxs-lookup"><span data-stu-id="2f281-171">A partial fix is to call `id.ToString()` and `size.ToString()` and pass all strings (which are objects) to the `string.Format` call.</span></span> <span data-ttu-id="2f281-172">Вызов `ToString()`не выделяет строку, однако такое выделение все равно произойдет внутри `string.Format`.</span><span class="sxs-lookup"><span data-stu-id="2f281-172">Calling `ToString()` does allocate a string, but that allocation will happen anyway inside `string.Format`.</span></span> 
  
 <span data-ttu-id="2f281-173">Вы можете предположить, что этот базовый вызов `string.Format` представляет собой просто объединение строк, и написать следующий код:</span><span class="sxs-lookup"><span data-stu-id="2f281-173">You might consider that this basic call to `string.Format` is just string concatenation, so you might write this code instead:</span></span>  
  
```csharp  
var s = id.ToString() + ':' + size.ToString();  
```  
  
 <span data-ttu-id="2f281-174">Однако эта строка кода вызывает выделение памяти с упаковкой-преобразованием, так как она компилируется в <xref:System.String.Concat%28System.Object%2CSystem.Object%2CSystem.Object%29>.</span><span class="sxs-lookup"><span data-stu-id="2f281-174">However, that line of code introduces a boxing allocation because it compiles to <xref:System.String.Concat%28System.Object%2CSystem.Object%2CSystem.Object%29>.</span></span> <span data-ttu-id="2f281-175">Платформа .NET Framework должна выполнить упаковку-преобразование символьного литерала для вызова `Concat`.</span><span class="sxs-lookup"><span data-stu-id="2f281-175">The .NET Framework must box the character literal to invoke `Concat`</span></span>  
  
 <span data-ttu-id="2f281-176">**Исправление для примера 1**</span><span class="sxs-lookup"><span data-stu-id="2f281-176">**Fix for example 1**</span></span>  
  
 <span data-ttu-id="2f281-177">Полное исправление довольно простое.</span><span class="sxs-lookup"><span data-stu-id="2f281-177">The complete fix is simple.</span></span> <span data-ttu-id="2f281-178">Просто замените символьный литерал на строковый, который не требует упаковку-преобразование, так как строки уже являются объектами:</span><span class="sxs-lookup"><span data-stu-id="2f281-178">Just replace the character literal with a string literal, which incurs no boxing because strings are already objects:</span></span>  
  
```csharp  
var s = id.ToString() + ":" + size.ToString();  
```  
  
 <span data-ttu-id="2f281-179">**Пример 2: упаковка-преобразование перечисления**</span><span class="sxs-lookup"><span data-stu-id="2f281-179">**Example 2: enum boxing**</span></span>  
  
 <span data-ttu-id="2f281-180">Этот пример вызывает выделение большого объема памяти в новых компиляторах C# и Visual Basic из-за частого использования типов перечисления, особенно в операциях поиска в словаре.</span><span class="sxs-lookup"><span data-stu-id="2f281-180">This example was responsible for a huge amount of allocation in the new C# and Visual Basic compilers due to frequent use of enumeration types, especially in dictionary lookup operations.</span></span> 
  
```csharp  
public enum Color  
{  
    Red, Green, Blue  
}  
  
public class BoxingExample  
{  
    private string name;  
    private Color color;  
    public override int GetHashCode()  
    {  
        return name.GetHashCode() ^ color.GetHashCode();  
    }  
}  
```  
  
 <span data-ttu-id="2f281-181">Эту проблему очень нелегко выявить.</span><span class="sxs-lookup"><span data-stu-id="2f281-181">This problem is very subtle.</span></span> <span data-ttu-id="2f281-182">PerfView сообщает о ней как об упаковке-преобразовании <xref:System.Enum.GetHashCode>, так как для реализации данный метод выполняет упаковку-преобразование базового представления типа перечисления.</span><span class="sxs-lookup"><span data-stu-id="2f281-182">PerfView would report this as <xref:System.Enum.GetHashCode> boxing because the method boxes the underlying representation of the enumeration type, for implementation reasons.</span></span> <span data-ttu-id="2f281-183">Если тщательнее просмотреть данные в PerfView, можно заметить два выделения памяти с упаковкой-преобразованием для каждого вызова <xref:System.Enum.GetHashCode>.</span><span class="sxs-lookup"><span data-stu-id="2f281-183">If you look closely in PerfView, you may see two boxing allocations for each call to <xref:System.Enum.GetHashCode>.</span></span> <span data-ttu-id="2f281-184">Один из них вставляет компилятор, другой — платформа .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2f281-184">The compiler inserts one, and the .NET Framework inserts the other.</span></span> 
  
 <span data-ttu-id="2f281-185">**Исправление для примера 2**</span><span class="sxs-lookup"><span data-stu-id="2f281-185">**Fix for example 2**</span></span>  
  
 <span data-ttu-id="2f281-186">вы можете легко избежать обоих выделений, выполнив перед вызовом <xref:System.Enum.GetHashCode> приведение к базовому представлению:</span><span class="sxs-lookup"><span data-stu-id="2f281-186">You can easily avoid both allocations by casting to the underlying representation before calling <xref:System.Enum.GetHashCode>:</span></span>  
  
```csharp  
((int)color).GetHashCode()  
```  
  
 <span data-ttu-id="2f281-187">Другой распространенной причиной упаковки-преобразования типов перечисления является метод <xref:System.Enum.HasFlag%28System.Enum%29?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2f281-187">Another common source of boxing on enumeration types is the <xref:System.Enum.HasFlag%28System.Enum%29?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="2f281-188">Передаваемый в <xref:System.Enum.HasFlag%28System.Enum%29> аргумент подлежит упаковке-преобразованию.</span><span class="sxs-lookup"><span data-stu-id="2f281-188">The argument passed to <xref:System.Enum.HasFlag%28System.Enum%29> has to be boxed.</span></span> <span data-ttu-id="2f281-189">В большинстве случаев замена вызовов <xref:System.Enum.HasFlag%28System.Enum%29?displayProperty=nameWithType> на побитовое тестирование упрощает код и не требует выделения памяти.</span><span class="sxs-lookup"><span data-stu-id="2f281-189">In most cases, replacing calls to <xref:System.Enum.HasFlag%28System.Enum%29?displayProperty=nameWithType> with a bitwise test is simpler and allocation-free.</span></span> 
  
 <span data-ttu-id="2f281-190">Не забывайте о первом факте о производительности (не проводить преждевременную оптимизацию) и не начинайте переписывать весь свой код таким образом.</span><span class="sxs-lookup"><span data-stu-id="2f281-190">Keep the first performance fact in mind (that is, don’t prematurely optimize) and don’t start rewriting all your code in this way.</span></span> <span data-ttu-id="2f281-191">Помните о ресурсоемкости упаковки-преобразования, но изменения в код вносите только после профилирования приложения и выявления актуальных проблем.</span><span class="sxs-lookup"><span data-stu-id="2f281-191">Be aware of these boxing costs, but change your code only after profiling your app and finding the hot spots.</span></span> 
  
### <a name="strings"></a><span data-ttu-id="2f281-192">Строки</span><span class="sxs-lookup"><span data-stu-id="2f281-192">Strings</span></span>  
 <span data-ttu-id="2f281-193">Операции со строками являются самым большим источником выделений памяти и часто входят в число первых пяти выделений в PerfView.</span><span class="sxs-lookup"><span data-stu-id="2f281-193">String manipulations are some of the biggest culprits for allocations, and they often show up in PerfView in the top five allocations.</span></span> <span data-ttu-id="2f281-194">Программы используют строки для сериализации, JSON и REST API.</span><span class="sxs-lookup"><span data-stu-id="2f281-194">Programs use strings for serialization, JSON, and REST APIs.</span></span> <span data-ttu-id="2f281-195">Вы не можете использовать строки в качестве программных констант для взаимодействия с системами в тех случаях, когда нельзя использовать типы перечисления.</span><span class="sxs-lookup"><span data-stu-id="2f281-195">You can use strings as programmatic constants for interoperating with systems when you can’t use enumeration types.</span></span> <span data-ttu-id="2f281-196">Когда профилирование указывает на то, что строки оказывают сильное негативное влияние на производительность, выполните поиск вызовов методов <xref:System.String>, таких как <xref:System.String.Format%2A>, <xref:System.String.Concat%2A>, <xref:System.String.Split%2A>, <xref:System.String.Join%2A>, <xref:System.String.Substring%2A> и т. п.</span><span class="sxs-lookup"><span data-stu-id="2f281-196">When your profiling shows that strings are highly affecting performance, look for calls to <xref:System.String> methods such as <xref:System.String.Format%2A>, <xref:System.String.Concat%2A>, <xref:System.String.Split%2A>, <xref:System.String.Join%2A>, <xref:System.String.Substring%2A>, and so on.</span></span> <span data-ttu-id="2f281-197">Использование <xref:System.Text.StringBuilder> для предотвращения создания одной строки из нескольких частей может помочь, однако даже выделение объекта <xref:System.Text.StringBuilder> может стать узким местом, требующим вашего внимания.</span><span class="sxs-lookup"><span data-stu-id="2f281-197">Using <xref:System.Text.StringBuilder> to avoid the cost of creating one string from many pieces helps, but even allocating the <xref:System.Text.StringBuilder> object might become a bottleneck that you need to manage.</span></span> 
  
 <span data-ttu-id="2f281-198">**Пример 3: строковые операции**</span><span class="sxs-lookup"><span data-stu-id="2f281-198">**Example 3: string operations**</span></span>  
  
 <span data-ttu-id="2f281-199">Компилятор C# содержал этот код, который записывает текст форматированного комментария XML-документа:</span><span class="sxs-lookup"><span data-stu-id="2f281-199">The C# compiler had this code that writes the text of a formatted XML doc comment:</span></span>  
  
```csharp  
public void WriteFormattedDocComment(string text)  
{  
    string[] lines = text.Split(new[] { "\r\n", "\r", "\n" },  
                                StringSplitOptions.None);  
    int numLines = lines.Length;  
    bool skipSpace = true;  
    if (lines[0].TrimStart().StartsWith("///"))  
    {  
        for (int i = 0; i < numLines; i++)  
        {  
            string trimmed = lines[i].TrimStart();  
            if (trimmed.Length < 4 || !char.IsWhiteSpace(trimmed[3]))  
            {  
                skipSpace = false;  
                break;  
            }  
        }  
        int substringStart = skipSpace ? 4 : 3;  
        for (int i = 0; i < numLines; i++)  
            WriteLine(lines[i].TrimStart().Substring(substringStart));  
    }  
    else { /* ... */ }  
```  
  
 <span data-ttu-id="2f281-200">Видно, что этот код выполняет множество операций со строками.</span><span class="sxs-lookup"><span data-stu-id="2f281-200">You can see that this code does a lot of string manipulation.</span></span> <span data-ttu-id="2f281-201">Код использует методы библиотеки для разделения строчек кода на отдельные строки, усечения пробела, проверки того, является ли аргумент `text` комментарием XML-документа, и извлечения подстрок из строчек кода.</span><span class="sxs-lookup"><span data-stu-id="2f281-201">The code uses library methods to split lines into separate strings, to trim white space, to check whether the argument `text` is an XML documentation comment, and to extract substrings from lines.</span></span> 
  
 <span data-ttu-id="2f281-202">На первой строчке внутри `WriteFormattedDocComment` вызов `text.Split` при каждом выполнении выделяет новый массив с тремя элементами в качестве аргумента.</span><span class="sxs-lookup"><span data-stu-id="2f281-202">On the first line inside `WriteFormattedDocComment`, the `text.Split` call allocates a new three-element array as the argument every time it’s called.</span></span> <span data-ttu-id="2f281-203">Компилятору требуется выводить код для каждого выделения этого массива.</span><span class="sxs-lookup"><span data-stu-id="2f281-203">The compiler has to emit code to allocate this array each time.</span></span> <span data-ttu-id="2f281-204">Это вызвано тем, что компилятор не знает, хранит ли <xref:System.String.Split%2A> массив в таком месте, где он может быть изменен другим кодом, что повлияло бы на дальнейшие вызовы `WriteFormattedDocComment`.</span><span class="sxs-lookup"><span data-stu-id="2f281-204">That’s because the compiler doesn’t know if <xref:System.String.Split%2A> stores the array somewhere where the array might be modified by other code, which would affect later calls to `WriteFormattedDocComment`.</span></span> <span data-ttu-id="2f281-205">Вызов <xref:System.String.Split%2A> также выделяет строку для каждой строчки кода в `text` и выделяет другой объем памяти для выполнения этой операции.</span><span class="sxs-lookup"><span data-stu-id="2f281-205">The call to <xref:System.String.Split%2A> also allocates a string for every line in `text` and allocates other memory to perform the operation.</span></span> 
  
 <span data-ttu-id="2f281-206">`WriteFormattedDocComment` содержит три вызова метода <xref:System.String.TrimStart%2A>.</span><span class="sxs-lookup"><span data-stu-id="2f281-206">`WriteFormattedDocComment` has three calls to the <xref:System.String.TrimStart%2A> method.</span></span> <span data-ttu-id="2f281-207">Два находятся во внутренних циклах, которые дублируют работу и выделения.</span><span class="sxs-lookup"><span data-stu-id="2f281-207">Two are in inner loops that duplicate work and allocations.</span></span> <span data-ttu-id="2f281-208">Ситуацию усугубляет то, что вызов метода <xref:System.String.TrimStart%2A> без аргументов в дополнение к строковому результату выделяет пустой массив (для параметра `params`).</span><span class="sxs-lookup"><span data-stu-id="2f281-208">To make matters worse, calling the <xref:System.String.TrimStart%2A> method with no arguments allocates an empty array (for the `params` parameter) in addition to the string result.</span></span> 
  
 <span data-ttu-id="2f281-209">Наконец, имеется вызов метода <xref:System.String.Substring%2A>, который обычно выделяет новую строку.</span><span class="sxs-lookup"><span data-stu-id="2f281-209">Lastly, there is a call to the <xref:System.String.Substring%2A> method, which usually allocates a new string.</span></span> 
  
 <span data-ttu-id="2f281-210">**Исправление для примера 3**</span><span class="sxs-lookup"><span data-stu-id="2f281-210">**Fix for example 3**</span></span>  
  
 <span data-ttu-id="2f281-211">В отличие от приведенных ранее примеров данные выделения нельзя устранить небольшой правкой кода.</span><span class="sxs-lookup"><span data-stu-id="2f281-211">Unlike the earlier examples, small edits cannot fix these allocations.</span></span> <span data-ttu-id="2f281-212">Вам нужно отвлечься, проанализировать проблему и найти иной подход.</span><span class="sxs-lookup"><span data-stu-id="2f281-212">You need to step back, look at the problem, and approach it differently.</span></span> <span data-ttu-id="2f281-213">Например, вы заметите, что аргумент для `WriteFormattedDocComment()` представляет собой строку со всей нужной методу информацией, поэтому код может осуществлять дополнительное индексирование вместо выделения множества частичных строк.</span><span class="sxs-lookup"><span data-stu-id="2f281-213">For example, you'll notice that the argument to `WriteFormattedDocComment()` is a string that has all the information that the method needs, so the code could do more indexing instead of allocating many partial strings.</span></span> 
  
 <span data-ttu-id="2f281-214">Команда по обеспечению производительности компиляторов решила проблему всех этих выделений с помощью следующего кода:</span><span class="sxs-lookup"><span data-stu-id="2f281-214">The compiler’s performance team tackled all these allocations with code like this:</span></span>  
  
```csharp  
private int IndexOfFirstNonWhiteSpaceChar(string text, int start) {  
    while (start < text.Length && char.IsWhiteSpace(text[start])) start++;  
    return start;  
}  
  
private bool TrimmedStringStartsWith(string text, int start, string prefix) {  
    start = IndexOfFirstNonWhiteSpaceChar(text, start);  
    int len = text.Length - start;  
    if (len < prefix.Length) return false;  
    for (int i = 0; i < len; i++)  
    {  
        if (prefix[i] != text[start + i]) return false;  
    }  
    return true;  
}  
  
// etc... 
```  
  
 <span data-ttu-id="2f281-215">Первая версия `WriteFormattedDocComment()` выделяла массив, несколько подстрок и усеченную подстроку, а также пустой массив `params`.</span><span class="sxs-lookup"><span data-stu-id="2f281-215">The first version of `WriteFormattedDocComment()` allocated an array, several substrings, and a trimmed substring along with an empty `params` array.</span></span> <span data-ttu-id="2f281-216">Он также проверяется на "///".</span><span class="sxs-lookup"><span data-stu-id="2f281-216">It also checked for "///".</span></span> <span data-ttu-id="2f281-217">Переработанный код использует только индексирование и ничего не выделяет.</span><span class="sxs-lookup"><span data-stu-id="2f281-217">The revised code uses only indexing and allocates nothing.</span></span> <span data-ttu-id="2f281-218">Он находит первый символ, не являющийся пробелом, а затем проверяет символ по символу, чтобы узнать, начинается ли строка с символа "///".</span><span class="sxs-lookup"><span data-stu-id="2f281-218">It finds the first character that is not white space, and then checks character by character to see if the string starts with "///".</span></span> <span data-ttu-id="2f281-219">Новый код использует `IndexOfFirstNonWhiteSpaceChar` вместо <xref:System.String.TrimStart%2A> для возврата первого индекса (после указанного начального индекса), где происходит символ, не являющийся пробелом.</span><span class="sxs-lookup"><span data-stu-id="2f281-219">The new code uses `IndexOfFirstNonWhiteSpaceChar` instead of <xref:System.String.TrimStart%2A> to return the first index (after a specified start index) where a non-white-space character occurs.</span></span> <span data-ttu-id="2f281-220">Такое исправление нельзя назвать окончательным, но из него можно понять, как применять аналогичные исправления для всего решения.</span><span class="sxs-lookup"><span data-stu-id="2f281-220">The fix is not complete, but you can see how to apply similar fixes for a complete solution.</span></span> <span data-ttu-id="2f281-221">Используя такой подход для всего кода, можно удалить все выделения в `WriteFormattedDocComment()`.</span><span class="sxs-lookup"><span data-stu-id="2f281-221">By applying this approach throughout the code, you can remove all allocations in `WriteFormattedDocComment()`.</span></span> 
  
 <span data-ttu-id="2f281-222">**Пример 4: StringBuilder**</span><span class="sxs-lookup"><span data-stu-id="2f281-222">**Example 4: StringBuilder**</span></span>  
  
 <span data-ttu-id="2f281-223">В этом примере используется объект <xref:System.Text.StringBuilder>.</span><span class="sxs-lookup"><span data-stu-id="2f281-223">This example uses a <xref:System.Text.StringBuilder> object.</span></span> <span data-ttu-id="2f281-224">Следующая функция создает полное имя типа для универсальных типов:</span><span class="sxs-lookup"><span data-stu-id="2f281-224">The following function generates a full type name for generic types:</span></span>  
  
```csharp  
public class Example  
{  
    // Constructs a name like "SomeType<T1, T2, T3>"  
    public string GenerateFullTypeName(string name, int arity)  
    {  
        StringBuilder sb = new StringBuilder();  
  
        sb.Append(name);  
        if (arity != 0)  
        {  
            sb.Append("<");  
            for (int i = 1; i < arity; i++)  
            {  
                sb.Append("T"); sb.Append(i.ToString()); sb.Append(", ");  
            }  
            sb.Append("T"); sb.Append(i.ToString()); sb.Append(">");  
        }  
  
        return sb.ToString();  
    }  
}  
```  
  
 <span data-ttu-id="2f281-225">Обратите внимание на строку, создающую новый экземпляр <xref:System.Text.StringBuilder>.</span><span class="sxs-lookup"><span data-stu-id="2f281-225">The focus is on the line that creates a new <xref:System.Text.StringBuilder> instance.</span></span> <span data-ttu-id="2f281-226">Этот код вызывает выделение для `sb.ToString()` и внутренние выделения в реализации <xref:System.Text.StringBuilder>, однако вы не можете управлять этими выделениями, если хотите получить строковый результат.</span><span class="sxs-lookup"><span data-stu-id="2f281-226">The code causes an allocation for `sb.ToString()` and internal allocations within the <xref:System.Text.StringBuilder> implementation, but you cannot control those allocations if you want the string result.</span></span> 
  
 <span data-ttu-id="2f281-227">**Исправление для примера 4**</span><span class="sxs-lookup"><span data-stu-id="2f281-227">**Fix for example 4**</span></span>  
  
 <span data-ttu-id="2f281-228">Чтобы исправить выделение объекта `StringBuilder`, кэшируйте его.</span><span class="sxs-lookup"><span data-stu-id="2f281-228">To fix the `StringBuilder` object allocation, cache the  object.</span></span> <span data-ttu-id="2f281-229">Даже кэширование отдельного экземпляра, который может быть отброшен, может существенно повысить производительность.</span><span class="sxs-lookup"><span data-stu-id="2f281-229">Even caching a single instance that might get thrown away can improve performance significantly.</span></span> <span data-ttu-id="2f281-230">Это новая реализация функции, в которой опущен весь код, за исключением новой первой и последней строк:</span><span class="sxs-lookup"><span data-stu-id="2f281-230">This is the function’s new implementation, omitting all the code except for the new first and last lines:</span></span>  
  
```csharp  
// Constructs a name like "MyType<T1, T2, T3>"  
public string GenerateFullTypeName(string name, int arity)  
{  
    StringBuilder sb = AcquireBuilder();  
    /* Use sb as before */  
    return GetStringAndReleaseBuilder(sb);  
}  
```  
  
 <span data-ttu-id="2f281-231">Основными компонентами являются новые функции `AcquireBuilder()` и `GetStringAndReleaseBuilder()`:</span><span class="sxs-lookup"><span data-stu-id="2f281-231">The key parts are the new `AcquireBuilder()` and `GetStringAndReleaseBuilder()` functions:</span></span>  
  
```csharp  
[ThreadStatic]  
private static StringBuilder cachedStringBuilder;  
  
private static StringBuilder AcquireBuilder()  
{  
    StringBuilder result = cachedStringBuilder;  
    if (result == null)  
    {  
        return new StringBuilder();  
    }  
    result.Clear();  
    cachedStringBuilder = null;  
    return result;  
}  
  
private static string GetStringAndReleaseBuilder(StringBuilder sb)  
{  
    string result = sb.ToString();  
    cachedStringBuilder = sb;  
    return result;  
}  
```  
  
 <span data-ttu-id="2f281-232">Поскольку новые компиляторы использую потоки, эти реализации используют потокостатическое поле (атрибут <xref:System.ThreadStaticAttribute>) для кэширования <xref:System.Text.StringBuilder>, и вы с большой долей вероятности сможете отказаться от объявления `ThreadStatic`.</span><span class="sxs-lookup"><span data-stu-id="2f281-232">Because the new compilers use threading, these implementations use a thread-static field (<xref:System.ThreadStaticAttribute> attribute) to cache the <xref:System.Text.StringBuilder>, and you likely can forgo the `ThreadStatic` declaration.</span></span> <span data-ttu-id="2f281-233">Потокостатическое поле содержит уникальное значение для каждого потока, выполняющего данный код.</span><span class="sxs-lookup"><span data-stu-id="2f281-233">The thread-static field holds a unique value for each thread that executes this code.</span></span> 
  
 <span data-ttu-id="2f281-234">`AcquireBuilder()` возвращает кэшированный экземпляр <xref:System.Text.StringBuilder>, если он имеется, после его очистки и установки значения NULL для поля или кэша.</span><span class="sxs-lookup"><span data-stu-id="2f281-234">`AcquireBuilder()` returns the cached <xref:System.Text.StringBuilder> instance if there is one, after clearing it and setting the field or cache to null.</span></span> <span data-ttu-id="2f281-235">В противном случае `AcquireBuilder()` создает новый экземпляр и возвращает его, оставив для поля или кэша значение NULL.</span><span class="sxs-lookup"><span data-stu-id="2f281-235">Otherwise, `AcquireBuilder()` creates a new instance and returns it, leaving the field or cache set to null.</span></span> 
  
 <span data-ttu-id="2f281-236">После завершения работы с <xref:System.Text.StringBuilder> вы вызываете `GetStringAndReleaseBuilder()`, чтобы получить строковый результат, сохраняете экземпляр <xref:System.Text.StringBuilder> в поле или кэше, а затем возвращаете результат.</span><span class="sxs-lookup"><span data-stu-id="2f281-236">When you’re done with <xref:System.Text.StringBuilder> , you call `GetStringAndReleaseBuilder()` to get the string result, save the <xref:System.Text.StringBuilder> instance in the field or cache, and then return the result.</span></span> <span data-ttu-id="2f281-237">Процесс выполнения может повторно входить в этот код и создать несколько объектов <xref:System.Text.StringBuilder> (хотя это происходит довольно редко).</span><span class="sxs-lookup"><span data-stu-id="2f281-237">It is possible for execution to re-enter this code and to create multiple <xref:System.Text.StringBuilder> objects (although that rarely happens).</span></span> <span data-ttu-id="2f281-238">Код сохраняет только последний освобожденный экземпляр <xref:System.Text.StringBuilder> для дальнейшего использования.</span><span class="sxs-lookup"><span data-stu-id="2f281-238">The code saves only the last released <xref:System.Text.StringBuilder> instance for later use.</span></span> <span data-ttu-id="2f281-239">Такая простая стратегия кэширования значительно уменьшает число выделений в новых компиляторах.</span><span class="sxs-lookup"><span data-stu-id="2f281-239">This simple caching strategy significantly reduced allocations in the new compilers.</span></span> <span data-ttu-id="2f281-240">В частях .NET Framework и MSBuild ("MSBuild") для повышения производительности используется та же методика.</span><span class="sxs-lookup"><span data-stu-id="2f281-240">Parts of the .NET Framework and MSBuild ("MSBuild") use a similar technique to improve performance.</span></span> 
  
 <span data-ttu-id="2f281-241">Эта простая стратегия кэширования придерживается разумного подхода к кэшированию из-за наличия ограничения размера.</span><span class="sxs-lookup"><span data-stu-id="2f281-241">This simple caching strategy adheres to good cache design because it has a size cap.</span></span> <span data-ttu-id="2f281-242">Однако теперь объем кода увеличился, что требует больше затрат на обслуживание.</span><span class="sxs-lookup"><span data-stu-id="2f281-242">However, there is more code now than in the original, which means more maintenance costs.</span></span> <span data-ttu-id="2f281-243">Вам следует внедрять стратегию кэширования только в том случае, если обнаружена проблема с производительностью, а PerfView показал, что одной из основных причин являются выделения <xref:System.Text.StringBuilder>.</span><span class="sxs-lookup"><span data-stu-id="2f281-243">You should adopt the caching strategy only if you’ve found a performance problem, and PerfView has shown that <xref:System.Text.StringBuilder> allocations are a significant contributor.</span></span> 
  
### <a name="linq-and-lambdas"></a><span data-ttu-id="2f281-244">LINQ и лямбда-выражения</span><span class="sxs-lookup"><span data-stu-id="2f281-244">LINQ and lambdas</span></span>  
<span data-ttu-id="2f281-245">Языковой интегрированный запрос (LINQ) в сочетании с лямбда-выражениями — это пример функции повышения производительности.</span><span class="sxs-lookup"><span data-stu-id="2f281-245">Language-Integrated Query (LINQ), in conjunction with lambda expressions, is an example of a productivity feature.</span></span> <span data-ttu-id="2f281-246">Однако его использование может оказать значительное влияние на производительность с течением времени, и вам может потребоваться переписать код.</span><span class="sxs-lookup"><span data-stu-id="2f281-246">However, its use may have a significant impact on performance over time, and you might find you need to rewrite your code.</span></span>
  
 <span data-ttu-id="2f281-247">**Пример 5: лямбда-выражения, List\<T> и IEnumerable\<T>**</span><span class="sxs-lookup"><span data-stu-id="2f281-247">**Example 5: Lambdas, List\<T>, and IEnumerable\<T>**</span></span>  
  
 <span data-ttu-id="2f281-248">В этом примере [LINQ и код в функциональном стиле](https://docs.microsoft.com/archive/blogs/charlie/anders-hejlsberg-on-linq-and-functional-programming) применяются для поиска символа в модели компилятора при заданной строке имени:</span><span class="sxs-lookup"><span data-stu-id="2f281-248">This example uses [LINQ and functional style code](https://docs.microsoft.com/archive/blogs/charlie/anders-hejlsberg-on-linq-and-functional-programming) to find a symbol in the compiler’s model, given a name string:</span></span>  
  
```csharp  
class Symbol {  
    public string Name { get; private set; }  
    /*...*/  
}  
  
class Compiler {  
    private List<Symbol> symbols;  
    public Symbol FindMatchingSymbol(string name)  
    {  
        return symbols.FirstOrDefault(s => s.Name == name);  
    }  
}  
```  
  
 <span data-ttu-id="2f281-249">Новый компилятор и основанные на нем процедуры взаимодействия IDE очень часто вызывают `FindMatchingSymbol()`, а всего в одной строчке кода этой функции имеется несколько скрытых выделений.</span><span class="sxs-lookup"><span data-stu-id="2f281-249">The new compiler and the IDE experiences built on it call `FindMatchingSymbol()` very frequently, and there are several hidden allocations in this function’s single line of code.</span></span> <span data-ttu-id="2f281-250">Чтобы изучить эти выделения, сначала разделите одну строчку кода функции на две строчки:</span><span class="sxs-lookup"><span data-stu-id="2f281-250">To examine those allocations, first split the function’s single line of code into two lines:</span></span>  
  
```csharp  
Func<Symbol, bool> predicate = s => s.Name == name;  
     return symbols.FirstOrDefault(predicate);  
```  
  
 <span data-ttu-id="2f281-251">В первой строке [лямбда-выражение](../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md) `s => s.Name == name` [закрывается](https://docs.microsoft.com/archive/blogs/ericlippert/what-are-closures) в локальной переменной `name`.</span><span class="sxs-lookup"><span data-stu-id="2f281-251">In the first line, the [lambda expression](../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md) `s => s.Name == name` [closes over](https://docs.microsoft.com/archive/blogs/ericlippert/what-are-closures) the local variable `name`.</span></span> <span data-ttu-id="2f281-252">Это означает, что в дополнение к выделению объекта для [делегата](../../csharp/language-reference/builtin-types/reference-types.md#the-delegate-type), содержащегося в `predicate`, код выделяет статический класс для среды, которая перехватывает значение `name`.</span><span class="sxs-lookup"><span data-stu-id="2f281-252">This means that in addition to allocating an object for the [delegate](../../csharp/language-reference/builtin-types/reference-types.md#the-delegate-type) that `predicate` holds, the code allocates a static class to hold the environment that captures the value of `name`.</span></span> <span data-ttu-id="2f281-253">Компилятор формирует код, аналогичный следующему:</span><span class="sxs-lookup"><span data-stu-id="2f281-253">The compiler generates code like the following:</span></span>  
  
```csharp  
// Compiler-generated class to hold environment state for lambda  
private class Lambda1Environment  
{  
    public string capturedName;  
    public bool Evaluate(Symbol s)  
    {  
        return s.Name == this.capturedName;  
    }  
}  
  
// Expanded Func<Symbol, bool> predicate = s => s.Name == name;  
Lambda1Environment l = new Lambda1Environment() { capturedName = name };  
var predicate = new Func<Symbol, bool>(l.Evaluate);  
```  
  
 <span data-ttu-id="2f281-254">Два выделения `new` (одно для класса среды и одно для делегата) теперь являются явными.</span><span class="sxs-lookup"><span data-stu-id="2f281-254">The two `new` allocations (one for the environment class and one for the delegate) are explicit now.</span></span> 
  
 <span data-ttu-id="2f281-255">Теперь рассмотрим вызов `FirstOrDefault`.</span><span class="sxs-lookup"><span data-stu-id="2f281-255">Now look at the call to `FirstOrDefault`.</span></span> <span data-ttu-id="2f281-256">Этот метод расширения в типе <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> также вызывает выделение.</span><span class="sxs-lookup"><span data-stu-id="2f281-256">This extension method on the <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> type incurs an allocation too.</span></span> <span data-ttu-id="2f281-257">Поскольку `FirstOrDefault` принимает объект <xref:System.Collections.Generic.IEnumerable%601> в качестве своего первого аргумента, вы можете развернуть вызов в следующий код (он немного упрощен для облегчения восприятия):</span><span class="sxs-lookup"><span data-stu-id="2f281-257">Because `FirstOrDefault` takes an <xref:System.Collections.Generic.IEnumerable%601> object as its first argument, you can expand the call to the following code (simplified a bit for discussion):</span></span>  
  
```csharp  
// Expanded return symbols.FirstOrDefault(predicate) ... 
     IEnumerable<Symbol> enumerable = symbols;  
     IEnumerator<Symbol> enumerator = enumerable.GetEnumerator();  
     while(enumerator.MoveNext())  
     {  
         if (predicate(enumerator.Current))  
             return enumerator.Current;  
     }  
     return default(Symbol);  
```  
  
 <span data-ttu-id="2f281-258">Переменная `symbols` имеет тип <xref:System.Collections.Generic.List%601>.</span><span class="sxs-lookup"><span data-stu-id="2f281-258">The `symbols` variable has type <xref:System.Collections.Generic.List%601>.</span></span> <span data-ttu-id="2f281-259">Тип коллекции <xref:System.Collections.Generic.List%601> реализует <xref:System.Collections.Generic.IEnumerable%601> и продуманно определяет перечислитель (интерфейс <xref:System.Collections.Generic.IEnumerator%601>), который <xref:System.Collections.Generic.List%601> реализует с помощью `struct`.</span><span class="sxs-lookup"><span data-stu-id="2f281-259">The <xref:System.Collections.Generic.List%601> collection type implements <xref:System.Collections.Generic.IEnumerable%601> and cleverly defines an enumerator (<xref:System.Collections.Generic.IEnumerator%601> interface) that <xref:System.Collections.Generic.List%601> implements with a `struct`.</span></span> <span data-ttu-id="2f281-260">В большинстве случаев использование структуры вместо класса позволяет избежать выделений кучи, что может повлиять на производительность сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="2f281-260">Using a structure instead of a class means that you usually avoid any heap allocations, which, in turn, can affect garbage collection performance.</span></span> <span data-ttu-id="2f281-261">Перечислители обычно используются в цикле `foreach` языка, который использует структуру перечислителя, когда она возвращается в стек вызовов.</span><span class="sxs-lookup"><span data-stu-id="2f281-261">Enumerators are typically used with the language’s `foreach` loop, which uses the enumerator structure as it is returned on the call stack.</span></span> <span data-ttu-id="2f281-262">Увеличение указателя стека вызовов для освобождения места для объекта не затрагивает сборку мусора так сильно, как это делает выделение кучи.</span><span class="sxs-lookup"><span data-stu-id="2f281-262">Incrementing the call stack pointer to make room for an object does not affect GC the way a heap allocation does.</span></span> 
  
 <span data-ttu-id="2f281-263">В случае развернутого вызова `FirstOrDefault` коду требуется вызвать `GetEnumerator()` в <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="2f281-263">In the case of the expanded `FirstOrDefault` call, the code needs to call `GetEnumerator()` on an <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="2f281-264">При назначении значения `symbols` переменной `enumerable`, имеющей тип `IEnumerable<Symbol>`, приводит к потере информации о том, что фактический объект является <xref:System.Collections.Generic.List%601>.</span><span class="sxs-lookup"><span data-stu-id="2f281-264">Assigning `symbols` to the `enumerable` variable of type `IEnumerable<Symbol>` loses the information that the actual object is a <xref:System.Collections.Generic.List%601>.</span></span> <span data-ttu-id="2f281-265">Это означает, что при получении перечислителя кодом с помощью `enumerable.GetEnumerator()`, платформа .NET Framework вынуждена выполнить упаковку-преобразование возвращенной структуры, чтобы назначить ее переменной `enumerator`.</span><span class="sxs-lookup"><span data-stu-id="2f281-265">This means that when the code fetches the enumerator with `enumerable.GetEnumerator()`, the .NET Framework has to box the returned structure to assign it to the `enumerator` variable.</span></span> 
  
 <span data-ttu-id="2f281-266">**Исправление для примера 5**</span><span class="sxs-lookup"><span data-stu-id="2f281-266">**Fix for example 5**</span></span>  
  
 <span data-ttu-id="2f281-267">Для исправления ситуации нужно переписать `FindMatchingSymbol` следующим образом, заменив одну строчку кода шестью строчками, которые сохраняют краткость, удобны для восприятия и обслуживания:</span><span class="sxs-lookup"><span data-stu-id="2f281-267">The fix is to rewrite `FindMatchingSymbol` as follows, replacing its single line of code with six lines of code that are still concise, easy to read and understand, and easy to maintain:</span></span>  
  
```csharp  
public Symbol FindMatchingSymbol(string name)  
    {  
        foreach (Symbol s in symbols)  
        {  
            if (s.Name == name)  
                return s;  
        }  
        return null;  
    }  
```  
  
 <span data-ttu-id="2f281-268">Этот код не использует методы расширения LINQ, лямбда-выражения или перечислители, а также не вызывает выделений памяти.</span><span class="sxs-lookup"><span data-stu-id="2f281-268">This code doesn’t use LINQ extension methods, lambdas, or enumerators, and it incurs no allocations.</span></span> <span data-ttu-id="2f281-269">Выделения отсутствуют, так как компилятор может определить, что коллекция `symbols` является <xref:System.Collections.Generic.List%601>, и может привязать итоговый перечислитель (структуру) к локальной переменной с помощью подходящего типа, чтобы предотвратить упаковку-преобразование.</span><span class="sxs-lookup"><span data-stu-id="2f281-269">There are no allocations because the compiler can see that the `symbols` collection is a <xref:System.Collections.Generic.List%601> and can bind the resulting enumerator (a structure) to a local variable with the right type to avoid boxing.</span></span> <span data-ttu-id="2f281-270">Исходная версия данной функции была отличным примером выразительных возможностей языка C# и производительности платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2f281-270">The original version of this function was a great example of the expressive power of C# and the productivity of the .NET Framework.</span></span> <span data-ttu-id="2f281-271">Эта новая и более эффективная версия сохраняет данные качества и не имеет сложного в обслуживании кода.</span><span class="sxs-lookup"><span data-stu-id="2f281-271">This new and more efficient version preserves those qualities without adding any complex code to maintain.</span></span> 
  
### <a name="async-method-caching"></a><span data-ttu-id="2f281-272">Кэширование асинхронных методов</span><span class="sxs-lookup"><span data-stu-id="2f281-272">Async method caching</span></span>  

<span data-ttu-id="2f281-273">В приведенном ниже примере показана распространенная проблема, возникающая при попытке использования кэшированных результатов в [асинхронном](../../csharp/programming-guide/concepts/async/index.md) методе.</span><span class="sxs-lookup"><span data-stu-id="2f281-273">The next example shows a common problem when you try to use cached results in an [async](../../csharp/programming-guide/concepts/async/index.md) method.</span></span>
  
 <span data-ttu-id="2f281-274">**Пример 6: кэширование в асинхронных методах**</span><span class="sxs-lookup"><span data-stu-id="2f281-274">**Example 6: caching in async methods**</span></span>  
  
 <span data-ttu-id="2f281-275">Компоненты IDE Visual Studio, созданные на базе новых компиляторов C# и Visual Basic, часто получают деревья синтаксиса, в этом случае компиляторы используют асинхронный режим для обеспечения быстрого реагирования Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2f281-275">The Visual Studio IDE features built on the new C# and Visual Basic compilers frequently fetch syntax trees, and the compilers use async when doing so to keep Visual Studio responsive.</span></span> <span data-ttu-id="2f281-276">Вот первый вариант кода, который вы могли бы написать для получения дерева синтаксиса:</span><span class="sxs-lookup"><span data-stu-id="2f281-276">Here’s the first version of the code you might write to get a syntax tree:</span></span>  
  
```csharp  
class SyntaxTree { /*...*/ }  
  
class Parser { /*...*/  
    public SyntaxTree Syntax { get; }  
    public Task ParseSourceCode() { /*...*/ }  
}  
  
class Compilation { /*...*/  
    public async Task<SyntaxTree> GetSyntaxTreeAsync()  
    {  
        var parser = new Parser(); // allocation  
        await parser.ParseSourceCode(); // expensive  
        return parser.Syntax;  
    }  
}  
```  
  
 <span data-ttu-id="2f281-277">Видно, что вызов `GetSyntaxTreeAsync()` создает экземпляр `Parser`, анализирует код и возвращает объект <xref:System.Threading.Tasks.Task> — `Task<SyntaxTree>`.</span><span class="sxs-lookup"><span data-stu-id="2f281-277">You can see that calling `GetSyntaxTreeAsync()` instantiates a `Parser`, parses the code, and then returns a <xref:System.Threading.Tasks.Task> object, `Task<SyntaxTree>`.</span></span> <span data-ttu-id="2f281-278">Ресурсоемким является выделение экземпляра `Parser` и синтаксический анализ кода.</span><span class="sxs-lookup"><span data-stu-id="2f281-278">The expensive part is allocating the `Parser` instance and parsing the code.</span></span> <span data-ttu-id="2f281-279">Функция возвращает <xref:System.Threading.Tasks.Task>, чтобы вызывающие объекты могли дождаться анализа и освободить поток пользовательского интерфейса, обеспечив возможность реагирования на действия пользователя.</span><span class="sxs-lookup"><span data-stu-id="2f281-279">The function returns a <xref:System.Threading.Tasks.Task> so that callers can await the parsing work and free the UI thread to be responsive to user input.</span></span> 
  
 <span data-ttu-id="2f281-280">Несколько компонентов Visual Studio могут попытаться получить то же самое дерево синтаксиса, поэтому вы можете написать следующий код для кэширования результата анализа, чтобы сэкономить время и сократить число выделений памяти.</span><span class="sxs-lookup"><span data-stu-id="2f281-280">Several Visual Studio features might try to get the same syntax tree, so you might write the following code to cache the parsing result to save time and allocations.</span></span> <span data-ttu-id="2f281-281">Однако этот код осуществляет выделение:</span><span class="sxs-lookup"><span data-stu-id="2f281-281">However, this code incurs an allocation:</span></span>  
  
```csharp  
class Compilation { /*...*/  
  
    private SyntaxTree cachedResult;  
  
    public async Task<SyntaxTree> GetSyntaxTreeAsync()  
    {  
        if (this.cachedResult == null)  
        {  
            var parser = new Parser(); // allocation  
            await parser.ParseSourceCode(); // expensive  
            this.cachedResult = parser.Syntax;  
        }  
        return this.cachedResult;  
    }  
}  
```  
  
 <span data-ttu-id="2f281-282">Видно, что новый код с кэшированием имеет поле `SyntaxTree` с именем `cachedResult`.</span><span class="sxs-lookup"><span data-stu-id="2f281-282">You see that the new code with caching has a `SyntaxTree` field named `cachedResult`.</span></span> <span data-ttu-id="2f281-283">Когда значение этого поля равно NULL, `GetSyntaxTreeAsync()` выполняет работу и сохраняет результат в кэш.</span><span class="sxs-lookup"><span data-stu-id="2f281-283">When this field is null, `GetSyntaxTreeAsync()` does the work and saves the result in the cache.</span></span> <span data-ttu-id="2f281-284">`GetSyntaxTreeAsync()` возвращает объект `SyntaxTree`.</span><span class="sxs-lookup"><span data-stu-id="2f281-284">`GetSyntaxTreeAsync()` returns the `SyntaxTree` object.</span></span> <span data-ttu-id="2f281-285">Проблема заключается в том, что если при наличии функции `async` типа `Task<SyntaxTree>` вы возвращаете значение типа `SyntaxTree`, компилятор выдает код для выделения задачи под хранение результата (с помощью `Task<SyntaxTree>.FromResult()`).</span><span class="sxs-lookup"><span data-stu-id="2f281-285">The problem is that when you have an `async` function of type `Task<SyntaxTree>`, and you return a value of type `SyntaxTree`, the compiler emits code to allocate a Task to hold the result (by using `Task<SyntaxTree>.FromResult()`).</span></span> <span data-ttu-id="2f281-286">Эта задача помечается как завершенная, и результат становится доступен сразу же.</span><span class="sxs-lookup"><span data-stu-id="2f281-286">The Task is marked as completed, and the result is immediately available.</span></span> <span data-ttu-id="2f281-287">В коде для новых компиляторов объекты <xref:System.Threading.Tasks.Task>, которые уже были завершены, встречались так часто, что исправление таких выделений памяти позволило заметно повысить скорость реагирования.</span><span class="sxs-lookup"><span data-stu-id="2f281-287">In the code for the new compilers, <xref:System.Threading.Tasks.Task> objects that were already completed occurred so often that fixing these allocations improved responsiveness noticeably.</span></span> 
  
 <span data-ttu-id="2f281-288">**Исправление для примера 6**</span><span class="sxs-lookup"><span data-stu-id="2f281-288">**Fix for example 6**</span></span>  
  
 <span data-ttu-id="2f281-289">Чтобы удалить завершенное выделение <xref:System.Threading.Tasks.Task>, можно кэшировать объект Task с завершенным результатом:</span><span class="sxs-lookup"><span data-stu-id="2f281-289">To remove the completed <xref:System.Threading.Tasks.Task> allocation, you can cache the Task object with the completed result:</span></span>  
  
```csharp  
class Compilation { /*...*/  
  
    private Task<SyntaxTree> cachedResult;  
  
    public Task<SyntaxTree> GetSyntaxTreeAsync()  
    {  
        return this.cachedResult ??   
               (this.cachedResult = GetSyntaxTreeUncachedAsync());  
    }  
  
    private async Task<SyntaxTree> GetSyntaxTreeUncachedAsync()  
    {  
        var parser = new Parser(); // allocation  
        await parser.ParseSourceCode(); // expensive  
        return parser.Syntax;  
    }  
}  
```  
  
 <span data-ttu-id="2f281-290">Этот код изменяет тип `cachedResult` на `Task<SyntaxTree>` и применяет вспомогательную функцию `async`, которая содержит исходный код `GetSyntaxTreeAsync()`.</span><span class="sxs-lookup"><span data-stu-id="2f281-290">This code changes the type of `cachedResult` to `Task<SyntaxTree>` and employs an `async` helper function that holds the original code from `GetSyntaxTreeAsync()`.</span></span> <span data-ttu-id="2f281-291">`GetSyntaxTreeAsync()` теперь использует [оператор объединения со значением NULL](../../csharp/language-reference/operators/null-coalescing-operator.md) для возврата `cachedResult`, если он имеет отличное от NULL значение.</span><span class="sxs-lookup"><span data-stu-id="2f281-291">`GetSyntaxTreeAsync()` now uses the [null coalescing operator](../../csharp/language-reference/operators/null-coalescing-operator.md) to return `cachedResult` if it isn't null.</span></span> <span data-ttu-id="2f281-292">Если `cachedResult` имеет значение NULL, то `GetSyntaxTreeAsync()` вызывает `GetSyntaxTreeUncachedAsync()` и кэширует результат.</span><span class="sxs-lookup"><span data-stu-id="2f281-292">If `cachedResult` is null, then `GetSyntaxTreeAsync()` calls `GetSyntaxTreeUncachedAsync()` and caches the result.</span></span> <span data-ttu-id="2f281-293">Обратите внимание на то, что `GetSyntaxTreeAsync()` не дожидается вызова `GetSyntaxTreeUncachedAsync()`, как это делает обычный код.</span><span class="sxs-lookup"><span data-stu-id="2f281-293">Notice that `GetSyntaxTreeAsync()` doesn’t await the call to `GetSyntaxTreeUncachedAsync()` as the code would normally.</span></span> <span data-ttu-id="2f281-294">Это означает, что когда `GetSyntaxTreeUncachedAsync()` возвращает свой объект <xref:System.Threading.Tasks.Task>, `GetSyntaxTreeAsync()` сразу же возвращает <xref:System.Threading.Tasks.Task>.</span><span class="sxs-lookup"><span data-stu-id="2f281-294">Not using await means that when `GetSyntaxTreeUncachedAsync()` returns its <xref:System.Threading.Tasks.Task> object, `GetSyntaxTreeAsync()` immediately returns the <xref:System.Threading.Tasks.Task>.</span></span> <span data-ttu-id="2f281-295">Теперь кэшированный результат является <xref:System.Threading.Tasks.Task>, поэтому выделения памяти для возврата кэшированного результата отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="2f281-295">Now, the cached result is a <xref:System.Threading.Tasks.Task>, so there are no allocations to return the cached result.</span></span> 
  
### <a name="additional-considerations"></a><span data-ttu-id="2f281-296">Дополнительные вопросы</span><span class="sxs-lookup"><span data-stu-id="2f281-296">Additional considerations</span></span>  
 <span data-ttu-id="2f281-297">Здесь приведено несколько замечания по поводу возможных проблем в крупных приложениях, обрабатывающих большие объемы данных.</span><span class="sxs-lookup"><span data-stu-id="2f281-297">Here are a few more points about potential problems in large apps or apps that process a lot of data.</span></span> 
  
 <span data-ttu-id="2f281-298">**Словари**</span><span class="sxs-lookup"><span data-stu-id="2f281-298">**Dictionaries**</span></span>  
  
 <span data-ttu-id="2f281-299">Словари повсеместно применяется во многих программах, так как они крайне удобны и эффективны.</span><span class="sxs-lookup"><span data-stu-id="2f281-299">Dictionaries are used ubiquitously in many programs, and though dictionaries are very convenient and inherently efficient.</span></span> <span data-ttu-id="2f281-300">Однако часто они используются нецелесообразно.</span><span class="sxs-lookup"><span data-stu-id="2f281-300">However, they’re often used inappropriately.</span></span> <span data-ttu-id="2f281-301">Анализ в Visual Studio и новых компиляторах показывает, что многие словари содержали всего один элемент или были пустыми.</span><span class="sxs-lookup"><span data-stu-id="2f281-301">In Visual Studio and the new compilers, analysis shows that many of the dictionaries contained a single element or were empty.</span></span> <span data-ttu-id="2f281-302">Пустой <xref:System.Collections.Generic.Dictionary%602> содержит десять полей и занимает 48 байт в куче на компьютере с архитектурой x86.</span><span class="sxs-lookup"><span data-stu-id="2f281-302">An empty <xref:System.Collections.Generic.Dictionary%602> has ten fields and occupies 48 bytes on the heap on an x86 machine.</span></span> <span data-ttu-id="2f281-303">Словари отлично подходят для случаев, когда требуется сопоставление или ассоциативная структура данных с постоянным по времени поиском.</span><span class="sxs-lookup"><span data-stu-id="2f281-303">Dictionaries are great when you need a mapping or associative data structure with constant-time lookup.</span></span> <span data-ttu-id="2f281-304">Однако при наличии всего нескольких элементов использование словаря приведет лишь к потере места.</span><span class="sxs-lookup"><span data-stu-id="2f281-304">However, when you have only a few elements, you waste a lot of space by using a dictionary.</span></span> <span data-ttu-id="2f281-305">Вместо этого можно, например, с той же самой скоростью осуществить итерационный просмотр `List<KeyValuePair\<K,V>>`.</span><span class="sxs-lookup"><span data-stu-id="2f281-305">Instead, for example, you could iteratively look through a `List<KeyValuePair\<K,V>>`, just as fast.</span></span> <span data-ttu-id="2f281-306">Если вы используете словарь только для загрузки в него данных и последующего их считывания (весьма распространенный случай), применение отсортированного массива с подстановкой N(log(N)) может обеспечивать близкое быстродействие (зависит от числа используемых элементов).</span><span class="sxs-lookup"><span data-stu-id="2f281-306">If you use a dictionary only to load it with data and then read from it (a very common pattern), using a sorted array with an N(log(N)) lookup might be nearly as fast, depending on the number of elements you're using.</span></span> 
  
 <span data-ttu-id="2f281-307">**Классы и структуры**</span><span class="sxs-lookup"><span data-stu-id="2f281-307">**Classes vs. structures**</span></span>  
  
 <span data-ttu-id="2f281-308">В некотором смысле классы и структуры представляют собой классический компромисс между местом и временем, используемый при подстройке приложений.</span><span class="sxs-lookup"><span data-stu-id="2f281-308">In a way, classes and structures provide a classic space/time tradeoff for tuning your apps.</span></span> <span data-ttu-id="2f281-309">Классы создают нагрузку в 12 байт на компьютере с архитектурой x86, даже если они не содержат полей, однако они легко передаются, так как для ссылки на экземпляр класса достаточно указателя.</span><span class="sxs-lookup"><span data-stu-id="2f281-309">Classes incur 12 bytes of overhead on an x86 machine even if they have no fields, but they are inexpensive to pass around because it only takes a pointer to refer to a class instance.</span></span> <span data-ttu-id="2f281-310">Структуры не вызывают выделений памяти в куче, если для них не используется упаковка-преобразование, однако при передаче больших структур в виде аргументов функций или возвращаемых значений, на атомарное копирование всех членов данных таких структур затрачивается время ЦП.</span><span class="sxs-lookup"><span data-stu-id="2f281-310">Structures incur no heap allocations if they aren’t boxed, but when you pass large structures as function arguments or return values, it takes CPU time to atomically copy all the data members of the structures.</span></span> <span data-ttu-id="2f281-311">Выявляйте повторяющиеся вызовы свойств, возвращающие структуры, и кэшируйте значение свойства в локальной переменной, чтобы избежать излишнего копирования данных.</span><span class="sxs-lookup"><span data-stu-id="2f281-311">Watch out for repeated calls to properties that return structures, and cache the property’s value in a local variable to avoid excessive data copying.</span></span> 
  
 <span data-ttu-id="2f281-312">**Кэши**</span><span class="sxs-lookup"><span data-stu-id="2f281-312">**Caches**</span></span>  
  
 <span data-ttu-id="2f281-313">Для обеспечения производительности часто применяют кэширование результатов.</span><span class="sxs-lookup"><span data-stu-id="2f281-313">A common performance trick is to cache results.</span></span> <span data-ttu-id="2f281-314">Однако кэш без ограничения размера или политики утилизации может привести к утечке памяти.</span><span class="sxs-lookup"><span data-stu-id="2f281-314">However, a cache without a size cap or disposal policy can be a memory leak.</span></span> <span data-ttu-id="2f281-315">В случае хранения большого объема памяти в кэшах сборка мусора при обработке больших объемов данных может нивелировать преимущества кэширования.</span><span class="sxs-lookup"><span data-stu-id="2f281-315">When processing large amounts of data, if you hold on to a lot of memory in caches, you can cause garbage collection to override the benefits of your cached lookups.</span></span> 
  
 <span data-ttu-id="2f281-316">В данной статье мы рассмотрели, как следует поступать при появлении признаков узких мест производительности, которые могут повлиять скорость реагирования приложения, особенно для крупных систем или систем, обрабатывающих большой объем данных.</span><span class="sxs-lookup"><span data-stu-id="2f281-316">In this article, we discussed how you should be aware of performance bottleneck symptoms that can affect your app's responsiveness, especially for large systems or systems that process a large amount of data.</span></span> <span data-ttu-id="2f281-317">К основным источникам проблем относится упаковка-преобразование, операции со строками, LINQ и лямбда-выражения, кэширование в асинхронных методах, кэширование без ограничения размера или политики утилизации, неуместное использование словарей и передача структур.</span><span class="sxs-lookup"><span data-stu-id="2f281-317">Common culprits include boxing, string manipulations, LINQ and lambda, caching in async methods, caching without a size limit or disposal policy, inappropriate use of dictionaries, and passing around structures.</span></span> <span data-ttu-id="2f281-318">При подстройке приложений помните о четырех фактах:</span><span class="sxs-lookup"><span data-stu-id="2f281-318">Keep in mind the four facts for tuning your apps:</span></span>  
  
- <span data-ttu-id="2f281-319">Не проводите преждевременную оптимизацию — сохраните производительность своего труда и производите подстройку приложения при обнаружении проблем.</span><span class="sxs-lookup"><span data-stu-id="2f281-319">Don’t prematurely optimize – be productive and tune your app when you spot problems.</span></span> 
  
- <span data-ttu-id="2f281-320">Профили не лгут — если вы не измеряете, значит, вы угадываете.</span><span class="sxs-lookup"><span data-stu-id="2f281-320">Profiles don’t lie – you’re guessing if you’re not measuring.</span></span> 
  
- <span data-ttu-id="2f281-321">Значение хороших средств трудно переоценить — загрузите PerfView и оцените его в работе.</span><span class="sxs-lookup"><span data-stu-id="2f281-321">Good tools make all the difference – download PerfView and try it out.</span></span> 
  
- <span data-ttu-id="2f281-322">Выделения памяти значат больше всего — именно на них команда разработчиков платформы компиляторов потратила больше всего времени, стремясь повысить производительность новых компиляторов.</span><span class="sxs-lookup"><span data-stu-id="2f281-322">It's all about allocations – that is where the compiler platform team spent most of their time improving the performance of the new compilers.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="2f281-323">См. также:</span><span class="sxs-lookup"><span data-stu-id="2f281-323">See also</span></span>

- [<span data-ttu-id="2f281-324">Видеоролик с представлением этого раздела</span><span class="sxs-lookup"><span data-stu-id="2f281-324">Video of presentation of this topic</span></span>](https://channel9.msdn.com/Events/TechEd/NorthAmerica/2013/DEV-B333)
- [<span data-ttu-id="2f281-325">Руководство по профилированию производительности для начинающих</span><span class="sxs-lookup"><span data-stu-id="2f281-325">Beginners Guide to Performance Profiling</span></span>](/visualstudio/profiling/beginners-guide-to-performance-profiling)
- [<span data-ttu-id="2f281-326">Производительность</span><span class="sxs-lookup"><span data-stu-id="2f281-326">Performance</span></span>](index.md)
- <span data-ttu-id="2f281-327">[Советы по повышению производительности .NET](https://docs.microsoft.com/previous-versions/dotnet/articles/ms973839(v%3dmsdn.10))</span><span class="sxs-lookup"><span data-stu-id="2f281-327">[.NET Performance Tips](https://docs.microsoft.com/previous-versions/dotnet/articles/ms973839(v%3dmsdn.10))</span></span>
- [<span data-ttu-id="2f281-328">Учебники по PerfView Channel 9</span><span class="sxs-lookup"><span data-stu-id="2f281-328">Channel 9 PerfView tutorials</span></span>](https://channel9.msdn.com/Series/PerfView-Tutorial)
- [<span data-ttu-id="2f281-329">Пакет SDK для .NET Compiler Platform</span><span class="sxs-lookup"><span data-stu-id="2f281-329">The .NET Compiler Platform SDK</span></span>](../../csharp/roslyn-sdk/index.md)
- [<span data-ttu-id="2f281-330">репозиторий DotNet/Roslyn на GitHub</span><span class="sxs-lookup"><span data-stu-id="2f281-330">dotnet/roslyn repo on GitHub</span></span>](https://github.com/dotnet/roslyn)
