---
title: Managed Extensibility Framework (MEF)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Managed Extensibility Framework, overview
- MEF, overview
ms.assetid: 6c61b4ec-c6df-4651-80f1-4854f8b14dde
caps.latest.revision: "31"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0994303cb758439dda08ee7df206f0a3bcecd854
ms.sourcegitcommit: bbde43da655ae7bea1977f7af7345eb87bd7fd5f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2017
---
# <a name="managed-extensibility-framework-mef"></a><span data-ttu-id="c3834-102">Managed Extensibility Framework (MEF)</span><span class="sxs-lookup"><span data-stu-id="c3834-102">Managed Extensibility Framework (MEF)</span></span>
<span data-ttu-id="c3834-103">В этом разделе содержится обзор Managed Extensibility Framework, которая появилась на платформе .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="c3834-103">This topic provides an overview of the Managed Extensibility Framework introduced in the .NET Framework 4.</span></span>  
  
<a name="what_is_mef"></a>   
## <a name="what-is-mef"></a><span data-ttu-id="c3834-104">Что такое MEF</span><span class="sxs-lookup"><span data-stu-id="c3834-104">What is MEF?</span></span>  
 <span data-ttu-id="c3834-105">Платформа Managed Extensibility Framework (MEF) — это библиотека для создания простых расширяемых приложений.</span><span class="sxs-lookup"><span data-stu-id="c3834-105">The Managed Extensibility Framework or MEF is a library for creating lightweight, extensible applications.</span></span> <span data-ttu-id="c3834-106">Она позволяет разработчикам приложений находить и использовать расширения без каких-либо настроек.</span><span class="sxs-lookup"><span data-stu-id="c3834-106">It allows application developers to discover and use extensions with no configuration required.</span></span> <span data-ttu-id="c3834-107">Она также позволяет разработчикам расширений легко инкапсулировать код и избегать ненадежных жестких зависимостей.</span><span class="sxs-lookup"><span data-stu-id="c3834-107">It also lets extension developers easily encapsulate code and avoid fragile hard dependencies.</span></span> <span data-ttu-id="c3834-108">MEF позволяет повторно использовать в приложениях не только расширения, но и целые приложения.</span><span class="sxs-lookup"><span data-stu-id="c3834-108">MEF not only allows extensions to be reused within applications, but across applications as well.</span></span>  
  
<a name="the_problem_of_extensibility"></a>   
## <a name="the-problem-of-extensibility"></a><span data-ttu-id="c3834-109">Проблема расширяемости</span><span class="sxs-lookup"><span data-stu-id="c3834-109">The Problem of Extensibility</span></span>  
 <span data-ttu-id="c3834-110">Представьте себе, что вы являетесь архитектором крупного приложения, которое должно обеспечивать поддержку для расширяемости.</span><span class="sxs-lookup"><span data-stu-id="c3834-110">Imagine that you are the architect of a large application that must provide support for extensibility.</span></span> <span data-ttu-id="c3834-111">Приложение должно включать потенциально большое количество небольших компонентов, а также отвечает за их создание и запуск.</span><span class="sxs-lookup"><span data-stu-id="c3834-111">Your application has to include a potentially large number of smaller components, and is responsible for creating and running them.</span></span>  
  
 <span data-ttu-id="c3834-112">Простейшим подходом к решению такой проблемы является включение компонентов в виде исходного кода в приложение и их вызов прямо из кода.</span><span class="sxs-lookup"><span data-stu-id="c3834-112">The simplest approach to the problem is to include the components as source code in your application, and call them directly from your code.</span></span>  <span data-ttu-id="c3834-113">Такой подход имеет ряд очевидных недостатков.</span><span class="sxs-lookup"><span data-stu-id="c3834-113">This has a number of obvious drawbacks.</span></span>  <span data-ttu-id="c3834-114">Самое главное, что нельзя добавлять новые компоненты без изменения исходного кода — данное ограничение может быть приемлемым, например, для веб-приложения, но не для клиентского приложения.</span><span class="sxs-lookup"><span data-stu-id="c3834-114">Most importantly, you cannot add new components without modifying the source code, a restriction that might be acceptable in, for example, a Web application, but is unworkable in a client application.</span></span>  <span data-ttu-id="c3834-115">Столь же проблематичной может оказаться ситуация, что у вас не будет доступа к исходному коду для компонентов, так как они могут разрабатываться сторонними производителями, и в силу ряда причин вы не сможете разрешить им доступ к своим приложениям.</span><span class="sxs-lookup"><span data-stu-id="c3834-115">Equally problematic, you may not have access to the source code for the components, because they might be developed by third parties, and for the same reason you cannot allow them to access yours.</span></span>  
  
 <span data-ttu-id="c3834-116">Несколько более сложный подход будет заключаться в предоставлении точки или интерфейса расширения, позволяющего разделять приложение и его компоненты.</span><span class="sxs-lookup"><span data-stu-id="c3834-116">A slightly more sophisticated approach would be to provide an extension point or interface, to permit decoupling between the application and its components.</span></span>  <span data-ttu-id="c3834-117">В рамках этой модели можно предоставить интерфейс, который может реализовывать компонент, а также интерфейс API, позволяющий ему взаимодействовать с приложением.</span><span class="sxs-lookup"><span data-stu-id="c3834-117">Under this model, you might provide an interface that a component can implement, and an API to enable it to interact with your application.</span></span>  <span data-ttu-id="c3834-118">Это позволяет решить проблему необходимости доступа к исходному коду, но по-прежнему имеет свои собственные сложности.</span><span class="sxs-lookup"><span data-stu-id="c3834-118">This solves the problem of requiring source code access, but it still has its own difficulties.</span></span>  
  
 <span data-ttu-id="c3834-119">Так как приложение не в состоянии самостоятельно обнаруживать компоненты, ему по-прежнему необходимо явным образом сообщать, какие компоненты имеются в наличии и подлежат загрузке.</span><span class="sxs-lookup"><span data-stu-id="c3834-119">Because the application lacks any capacity for discovering components on its own, it must still be explicitly told which components are available and should be loaded.</span></span>  <span data-ttu-id="c3834-120">Обычно для этого применяется явная регистрация доступных компонентов в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="c3834-120">This is typically accomplished by explicitly registering the available components in a configuration file.</span></span> <span data-ttu-id="c3834-121">Это означает, что обеспечение нужных компонентов превращается в задачу обслуживания, особенно в тех случаях, когда обновление должен выполнять конечный пользователь, а не сам разработчик.</span><span class="sxs-lookup"><span data-stu-id="c3834-121">This means that assuring that the components are correct becomes a maintenance issue, particularly if it is the end user and not the developer who is expected to do the updating.</span></span>  
  
 <span data-ttu-id="c3834-122">Кроме того, компоненты могут взаимодействовать друг с другом, за исключением строго определенных каналов самого приложения.</span><span class="sxs-lookup"><span data-stu-id="c3834-122">In addition, components are incapable of communicating with one another, except through the rigidly defined channels of the application itself.</span></span>  <span data-ttu-id="c3834-123">Если в архитектуре приложения не учтена потребность в определенной связи, то обычно это оказывается невозможным.</span><span class="sxs-lookup"><span data-stu-id="c3834-123">If the application architect has not anticipated the need for a particular communication, it is usually impossible.</span></span>  
  
 <span data-ttu-id="c3834-124">Наконец, разработчики компонентов вынуждены принимать жесткие зависимости от того, какая именно сборка содержит реализуемый ими интерфейс.</span><span class="sxs-lookup"><span data-stu-id="c3834-124">Finally, the component developers must accept a hard dependency on what assembly contains the interface they implement.</span></span>  <span data-ttu-id="c3834-125">Это затрудняет возможное применение компонента в нескольких приложениях и также может вызвать проблемы при создании тестовой платформы для компонентов.</span><span class="sxs-lookup"><span data-stu-id="c3834-125">This makes it difficult for a component to be used in more than one application, and can also create problems when you create a test framework for components.</span></span>  
  
<a name="what_mef_provides"></a>   
## <a name="what-mef-provides"></a><span data-ttu-id="c3834-126">Сведения о возможностях MEF</span><span class="sxs-lookup"><span data-stu-id="c3834-126">What MEF Provides</span></span>  
 <span data-ttu-id="c3834-127">Вместо явной регистрации доступных компонентов, MEF позволяет обнаруживать их неявным образом, через *композиции*.</span><span class="sxs-lookup"><span data-stu-id="c3834-127">Instead of this explicit registration of available components, MEF provides a way to discover them implicitly, via *composition*.</span></span>  <span data-ttu-id="c3834-128">Компонент MEF, называемый *часть*, декларативно указывает как свои зависимости (известный как *импортирует*) и свои возможности (известный как *экспортирует*) делает доступными.</span><span class="sxs-lookup"><span data-stu-id="c3834-128">A MEF component, called a *part*, declaratively specifies both its dependencies (known as *imports*) and what capabilities (known as *exports*) it makes available.</span></span> <span data-ttu-id="c3834-129">При создании некоторой части обработчик композиции MEF удовлетворяет свои импортируемые компоненты за счет элементов, доступных из других частей.</span><span class="sxs-lookup"><span data-stu-id="c3834-129">When a part is created, the MEF composition engine satisfies its imports with what is available from other parts.</span></span>  
  
 <span data-ttu-id="c3834-130">Такой поход позволяет решить проблемы, рассмотренные в предыдущем разделе.</span><span class="sxs-lookup"><span data-stu-id="c3834-130">This approach solves the problems discussed in the previous section.</span></span>  <span data-ttu-id="c3834-131">Так как части MEF декларативно указывают свои возможности, они могут быть обнаружены во время выполнения, то есть, приложение может применять части без жестко кодированных ссылок или ненадежных файлов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="c3834-131">Because MEF parts declaratively specify their capabilities, they are discoverable at runtime, which means an application can make use of parts without either hard-coded references or fragile configuration files.</span></span>  <span data-ttu-id="c3834-132">Платформа MEF позволяет приложениям обнаруживать и анализировать части с помощью своих метаданных без создания экземпляров и даже без загрузки их сборок.</span><span class="sxs-lookup"><span data-stu-id="c3834-132">MEF allows applications to discover and examine parts by their metadata, without instantiating them or even loading their assemblies.</span></span> <span data-ttu-id="c3834-133">В результате нет необходимости четко указывать время и способ загрузки расширений.</span><span class="sxs-lookup"><span data-stu-id="c3834-133">As a result, there is no need to carefully specify when and how extensions should be loaded.</span></span>  
  
 <span data-ttu-id="c3834-134">Кроме обеспечиваемого экспорта, часть может указать свои импортируемые элементы, которые будут заполнены другими частями.</span><span class="sxs-lookup"><span data-stu-id="c3834-134">In addition to its provided exports, a part can specify its imports, which will be filled by other parts.</span></span>  <span data-ttu-id="c3834-135">Это делает связь между частями не только возможной, но и простой, и обеспечивает качественное разбиение кода.</span><span class="sxs-lookup"><span data-stu-id="c3834-135">This makes communication among parts not only possible, but easy, and allows for good factoring of code.</span></span> <span data-ttu-id="c3834-136">Например, общие для нескольких компонентов службы можно выделить в отдельную часть, которую можно будет легко изменять или заменять.</span><span class="sxs-lookup"><span data-stu-id="c3834-136">For example, services common to many components can be factored into a separate part and easily modified or replaced.</span></span>  
  
 <span data-ttu-id="c3834-137">Так как для модели MEF жесткие зависимости от определенной сборки приложения не требуются, она позволяет повторно использовать расширения в различных приложениях.</span><span class="sxs-lookup"><span data-stu-id="c3834-137">Because the MEF model requires no hard dependency on a particular application assembly, it allows extensions to be reused from application to application.</span></span>  <span data-ttu-id="c3834-138">Это также упрощает разработку окружения теста, не зависящего от приложения, для тестирования компонентов расширений.</span><span class="sxs-lookup"><span data-stu-id="c3834-138">This also makes it easy to develop a test harness, independent of the application, to test extension components.</span></span>  
  
 <span data-ttu-id="c3834-139">Расширяемое приложение, созданное с помощью платформы MEF, объявляет импортируемый элемент, который может быть заполнен компонентами расширения, а также может объявить экспортируемые элементы, позволяющие применять службы приложений для расширений.</span><span class="sxs-lookup"><span data-stu-id="c3834-139">An extensible application written by using MEF declares an import that can be filled by extension components, and may also declare exports in order to expose application services to extensions.</span></span>  <span data-ttu-id="c3834-140">Каждый компонент расширения объявляет экспортируемый элемент, а также может объявлять импортируемые элементы.</span><span class="sxs-lookup"><span data-stu-id="c3834-140">Each extension component declares an export, and may also declare imports.</span></span>  <span data-ttu-id="c3834-141">Таким образом, сами компоненты расширения автоматически становятся расширяемыми.</span><span class="sxs-lookup"><span data-stu-id="c3834-141">In this way, extension components themselves are automatically extensible.</span></span>  
  
<a name="where_is_mef_available"></a>   
## <a name="where-is-mef-available"></a><span data-ttu-id="c3834-142">Где находится MEF?</span><span class="sxs-lookup"><span data-stu-id="c3834-142">Where Is MEF Available?</span></span>  
 <span data-ttu-id="c3834-143">MEF является неотъемлемой частью [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] и присутствует везде, где применяется платформа.NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c3834-143">MEF is an integral part of the [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], and is available wherever the .NET Framework is used.</span></span>  <span data-ttu-id="c3834-144">MEF можно использовать в клиентских приложениях, независимо от того, применяют они Windows Forms, WPF или любую другую технологию, либо в серверных приложениях, где применяется ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="c3834-144">You can use MEF in your client applications, whether they use Windows Forms, WPF, or any other technology, or in server applications that use ASP.NET.</span></span>  
  
<a name="mef_and_maf"></a>   
## <a name="mef-and-maf"></a><span data-ttu-id="c3834-145">MEF и MAF</span><span class="sxs-lookup"><span data-stu-id="c3834-145">MEF and MAF</span></span>  
 <span data-ttu-id="c3834-146">На платформе .NET Framework предыдущих версий появилась платформа Managed Add-in Framework (MAF), которая позволяет изолировать и управлять расширениями в приложениях.</span><span class="sxs-lookup"><span data-stu-id="c3834-146">Previous versions of the .NET Framework introduced the Managed Add-in Framework (MAF), designed to allow applications to isolate and manage extensions.</span></span>  <span data-ttu-id="c3834-147">MAF находится на более высоком уровне, чем MEF, и отвечает за изоляцию расширения, а также загрузку и выгрузку сборки, тогда как MEF отвечает за возможность обнаружения, расширяемости и переноса.</span><span class="sxs-lookup"><span data-stu-id="c3834-147">The focus of MAF is slightly higher-level than MEF, concentrating on extension isolation and assembly loading and unloading, while MEF's focus is on discoverability, extensibility, and portability.</span></span>  <span data-ttu-id="c3834-148">Обе эти платформы тесно взаимодействуют друг с другом, и каждое одиночное приложение могут воспользоваться преимуществами их обоих.</span><span class="sxs-lookup"><span data-stu-id="c3834-148">The two frameworks interoperate smoothly, and a single application can take advantage of both.</span></span>  
  
<a name="simplecalculator_an_example_application"></a>   
## <a name="simplecalculator-an-example-application"></a><span data-ttu-id="c3834-149">Пример приложения SimpleCalculator</span><span class="sxs-lookup"><span data-stu-id="c3834-149">SimpleCalculator: An Example Application</span></span>  
 <span data-ttu-id="c3834-150">Чтобы узнать о возможностях MEF, проще всего создать простое приложение MEF.</span><span class="sxs-lookup"><span data-stu-id="c3834-150">The simplest way to see what MEF can do is to build a simple MEF application.</span></span> <span data-ttu-id="c3834-151">В этом примере выполняется создание очень простого калькулятора, который называется SimpleCalculator.</span><span class="sxs-lookup"><span data-stu-id="c3834-151">In this example, you build a very simple calculator named SimpleCalculator.</span></span> <span data-ttu-id="c3834-152">SimpleCalculator предназначен для создания консольного приложения, принимающего основные арифметические команды в формате «5 + 3» или «6 - 2» и возвращающего правильные ответы.</span><span class="sxs-lookup"><span data-stu-id="c3834-152">The goal of SimpleCalculator is to create a console application that accepts basic arithmetic commands, in the form "5+3" or "6-2", and returns the correct answers.</span></span> <span data-ttu-id="c3834-153">Благодаря применению MEF, вы сможете добавлять новые операторы без изменения кода приложения.</span><span class="sxs-lookup"><span data-stu-id="c3834-153">Using MEF, you will be able to add new operators without changing the application code.</span></span>  
  
 <span data-ttu-id="c3834-154">Чтобы загрузить полный код для этого примера, в разделе [Пример SimpleCalculator](http://code.msdn.microsoft.com/windowsdesktop/Simple-Calculator-MEF-1152654e).</span><span class="sxs-lookup"><span data-stu-id="c3834-154">To download the complete code for this example, see the [SimpleCalculator sample](http://code.msdn.microsoft.com/windowsdesktop/Simple-Calculator-MEF-1152654e).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c3834-155">Пример с SimpleCalculator предназначен просто для демонстрации концепции и синтаксиса платформы MEF, а не описания реального сценария для ее использования.</span><span class="sxs-lookup"><span data-stu-id="c3834-155">The purpose of SimpleCalculator is to demonstrate the concepts and syntax of MEF, rather than to necessarily provide a realistic scenario for its use.</span></span> <span data-ttu-id="c3834-156">Многие приложения, которые будут использовать возможности MEF, являются более сложными, чем SimpleCalculator.</span><span class="sxs-lookup"><span data-stu-id="c3834-156">Many of the applications that would benefit most from the power of MEF are more complex than SimpleCalculator.</span></span> <span data-ttu-id="c3834-157">Более сложные примеры см. в разделе [Managed Extensibility Framework](https://github.com/MicrosoftArchive/mef) на GitHub.</span><span class="sxs-lookup"><span data-stu-id="c3834-157">For more extensive examples, see the [Managed Extensibility Framework](https://github.com/MicrosoftArchive/mef) on GitHub.</span></span>
  
 <span data-ttu-id="c3834-158">Для запуска в [!INCLUDE[vs_dev10_long](../../../includes/vs-dev10-long-md.md)], создайте новый проект консольного приложения с именем `SimpleCalculator`.</span><span class="sxs-lookup"><span data-stu-id="c3834-158">To start, in [!INCLUDE[vs_dev10_long](../../../includes/vs-dev10-long-md.md)], create a new Console Application project named `SimpleCalculator`.</span></span> <span data-ttu-id="c3834-159">Добавьте ссылку на сборку System.ComponentModel.Composition, где находится MEF.</span><span class="sxs-lookup"><span data-stu-id="c3834-159">Add a reference to the System.ComponentModel.Composition assembly, where MEF resides.</span></span> <span data-ttu-id="c3834-160">Откройте файл Module1.vb или Program.cs и добавьте операторы `Imports` или `using` для System.ComponentModel.Composition и System.ComponentModel.Composition.Hosting.</span><span class="sxs-lookup"><span data-stu-id="c3834-160">Open Module1.vb or Program.cs and add `Imports` or `using` statements for System.ComponentModel.Composition and System.ComponentModel.Composition.Hosting.</span></span> <span data-ttu-id="c3834-161">Оба этих пространства имен содержат типы MEF, необходимые для разработки расширяемого приложения.</span><span class="sxs-lookup"><span data-stu-id="c3834-161">These two namespaces contain MEF types you will need to develop an extensible application.</span></span> <span data-ttu-id="c3834-162">В Visual Basic добавьте ключевое слово `Public` в строку, объявляющую модуль `Module1`.</span><span class="sxs-lookup"><span data-stu-id="c3834-162">In Visual Basic, add the `Public` keyword to the line that declares the `Module1` module.</span></span>  
  
<a name="composition_container_and_catalogs"></a>   
## <a name="composition-container-and-catalogs"></a><span data-ttu-id="c3834-163">Контейнер композиции и каталоги</span><span class="sxs-lookup"><span data-stu-id="c3834-163">Composition Container and Catalogs</span></span>  
 <span data-ttu-id="c3834-164">Основным элементом модели композиции MEF является *контейнер композиции*, который содержит все доступные части и выполняет композицию.</span><span class="sxs-lookup"><span data-stu-id="c3834-164">The core of the MEF composition model is the *composition container*, which contains all the parts available and performs composition.</span></span>  <span data-ttu-id="c3834-165">(То есть, обеспечивает сопоставление импортируемых и экспортируемых элементов.)  Наиболее распространенным типом контейнера композиции является <xref:System.ComponentModel.Composition.Hosting.CompositionContainer>, который будет использоваться для SimpleCalculator.</span><span class="sxs-lookup"><span data-stu-id="c3834-165">(That is, the matching up of imports to exports.)  The most common type of composition container is <xref:System.ComponentModel.Composition.Hosting.CompositionContainer>, and you will use this for SimpleCalculator.</span></span>  
  
 <span data-ttu-id="c3834-166">В Visual Basic в модуле Module1.vb добавьте открытый класс с именем `Program`.</span><span class="sxs-lookup"><span data-stu-id="c3834-166">In Visual Basic, in Module1.vb, add a public class named `Program`.</span></span> <span data-ttu-id="c3834-167">Затем добавьте следующую строку в класс `Program` в модуле Module1.vb или Program.cs:</span><span class="sxs-lookup"><span data-stu-id="c3834-167">Then add the following line to the `Program` class in Module1.vb or Program.cs:</span></span>  
  
```vb  
Dim _container As CompositionContainer  
```  
  
```csharp  
private CompositionContainer _container;  
```  
  
 <span data-ttu-id="c3834-168">Для обнаружения доступных частей в контейнерах композиции используется *каталога*.</span><span class="sxs-lookup"><span data-stu-id="c3834-168">In order to discover the parts available to it, the composition containers makes use of a *catalog*.</span></span> <span data-ttu-id="c3834-169">Каталог – это объект, который делает доступными части, обнаруженные в определенном источнике.</span><span class="sxs-lookup"><span data-stu-id="c3834-169">A catalog is an object that makes available parts discovered from some source.</span></span>  <span data-ttu-id="c3834-170">MEF содержит каталоги для обнаружения частей с заданным типом, сборкой или директорией.</span><span class="sxs-lookup"><span data-stu-id="c3834-170">MEF provides catalogs to discover parts from a provided type, an assembly, or a directory.</span></span> <span data-ttu-id="c3834-171">Разработчики приложений могут легко создавать новые каталоги для обнаружения частей из других источников, например, веб-служб.</span><span class="sxs-lookup"><span data-stu-id="c3834-171">Application developers can easily create new catalogs to discover parts from other sources, such as a Web service.</span></span>  
  
 <span data-ttu-id="c3834-172">Добавьте следующий конструктор в класс `Program`:</span><span class="sxs-lookup"><span data-stu-id="c3834-172">Add the following constructor to the `Program` class:</span></span>  
  
```vb  
Public Sub New()  
    'An aggregate catalog that combines multiple catalogs  
     Dim catalog = New AggregateCatalog()  
  
    'Adds all the parts found in the same assembly as the Program class  
    catalog.Catalogs.Add(New AssemblyCatalog(GetType(Program).Assembly))  
  
    'Create the CompositionContainer with the parts in the catalog  
    _container = New CompositionContainer(catalog)  
  
    'Fill the imports of this object  
    Try  
        _container.ComposeParts(Me)  
    Catch ex As Exception  
        Console.WriteLine(ex.ToString)  
    End Try  
End Sub  
```  
  
```csharp  
private Program()  
{  
    //An aggregate catalog that combines multiple catalogs  
    var catalog = new AggregateCatalog();  
    //Adds all the parts found in the same assembly as the Program class  
    catalog.Catalogs.Add(new AssemblyCatalog(typeof(Program).Assembly));  
  
    //Create the CompositionContainer with the parts in the catalog  
    _container = new CompositionContainer(catalog);  
  
    //Fill the imports of this object  
    try  
    {  
        this._container.ComposeParts(this);  
    }  
    catch (CompositionException compositionException)  
    {  
        Console.WriteLine(compositionException.ToString());  
   }  
}  
```  
  
 <span data-ttu-id="c3834-173">Вызов <xref:System.ComponentModel.Composition.AttributedModelServices.ComposeParts%2A> указывает контейнеру композиции на необходимость компоновки определенного набора частей (в данном случае текущий экземпляр `Program`).</span><span class="sxs-lookup"><span data-stu-id="c3834-173">The call to <xref:System.ComponentModel.Composition.AttributedModelServices.ComposeParts%2A> tells the composition container to compose a specific set of parts, in this case the current instance of `Program`.</span></span> <span data-ttu-id="c3834-174">Однако на этом этапе ничего не происходит, так как в `Program` нет импортируемых элементов для заполнения.</span><span class="sxs-lookup"><span data-stu-id="c3834-174">At this point, however, nothing will happen, since `Program` has no imports to fill.</span></span>  
  
<a name="imports_and_exports_with_attributes"></a>   
## <a name="imports-and-exports-with-attributes"></a><span data-ttu-id="c3834-175">Импортируемые и экспортируемые элементы с атрибутами</span><span class="sxs-lookup"><span data-stu-id="c3834-175">Imports and Exports with Attributes</span></span>  
 <span data-ttu-id="c3834-176">Во-первых, необходимо выбрать `Program` для импорта калькулятора.</span><span class="sxs-lookup"><span data-stu-id="c3834-176">First, you have `Program` import a calculator.</span></span> <span data-ttu-id="c3834-177">Это позволит отделять вопросы пользовательского интерфейса, например, ввод и вывод консоли, который будет поступать в `Program`, от логики калькулятора.</span><span class="sxs-lookup"><span data-stu-id="c3834-177">This allows the separation of user interface concerns, such as the console input and output that will go into `Program`, from the logic of the calculator.</span></span>  
  
 <span data-ttu-id="c3834-178">Добавьте следующий код в класс `Program`:</span><span class="sxs-lookup"><span data-stu-id="c3834-178">Add the following code to the `Program` class:</span></span>  
  
```vb  
<Import(GetType(ICalculator))>  
Public Property calculator As ICalculator  
```  
  
```csharp  
[Import(typeof(ICalculator))]  
public ICalculator calculator;  
```  
  
 <span data-ttu-id="c3834-179">Следует отметить, что объявление объекта `calculator` не является необычным, однако он содержит атрибут <xref:System.ComponentModel.Composition.ImportAttribute>.</span><span class="sxs-lookup"><span data-stu-id="c3834-179">Notice that the declaration of the `calculator` object is not unusual, but that it is decorated with the <xref:System.ComponentModel.Composition.ImportAttribute> attribute.</span></span>  <span data-ttu-id="c3834-180">Этот атрибут объявляет что-нибудь, подлежащее импорту; то есть, это будет заполнено обработчиком композиции при составлении объекта.</span><span class="sxs-lookup"><span data-stu-id="c3834-180">This attribute declares something to be an import; that is, it will be filled by the composition engine when the object is composed.</span></span>  
  
 <span data-ttu-id="c3834-181">Каждый импортируемый элемент имеет *контракта*, который определяет соответствующие его экспортируемые.</span><span class="sxs-lookup"><span data-stu-id="c3834-181">Every import has a *contract*, which determines what exports it will be matched with.</span></span> <span data-ttu-id="c3834-182">Контракт может быть явно заданный строкой, или он может создаваться автоматически платформой MEF из заданного типа (в данном случае интерфейс `ICalculator`).</span><span class="sxs-lookup"><span data-stu-id="c3834-182">The contract can be an explicitly specified string, or it can be automatically generated by MEF from a given type, in this case the interface `ICalculator`.</span></span>  <span data-ttu-id="c3834-183">Любой экспортируемый элемент, объявленный с помощью контракта сопоставления, будет подставляться в этот импорт.</span><span class="sxs-lookup"><span data-stu-id="c3834-183">Any export declared with a matching contract will fulfill this import.</span></span>  <span data-ttu-id="c3834-184">Следует отметить, что типом объекта `calculator` на самом деле является `ICalculator`, это не является обязательным.</span><span class="sxs-lookup"><span data-stu-id="c3834-184">Note that while the type of the `calculator` object is in fact `ICalculator`, this is not required.</span></span> <span data-ttu-id="c3834-185">Контракт не зависит от типа импортирующего объекта.</span><span class="sxs-lookup"><span data-stu-id="c3834-185">The contract is independent from the type of the importing object.</span></span>  <span data-ttu-id="c3834-186">(В этом случае можно опустить `typeof(ICalculator)`.</span><span class="sxs-lookup"><span data-stu-id="c3834-186">(In this case, you could leave out the `typeof(ICalculator)`.</span></span>  <span data-ttu-id="c3834-187">MEF автоматически предположит, что контракт должен быть основан на типе импорта, если не указано явным образом.)</span><span class="sxs-lookup"><span data-stu-id="c3834-187">MEF will automatically assume the contract to be based on the type of the import unless you specify it explicitly.)</span></span>  
  
 <span data-ttu-id="c3834-188">Добавьте этот простейший интерфейс в модуль или пространство имен `SimpleCalculator`:</span><span class="sxs-lookup"><span data-stu-id="c3834-188">Add this very simple interface to the module or `SimpleCalculator` namespace:</span></span>  
  
```vb  
Public Interface ICalculator  
    Function Calculate(ByVal input As String) As String  
End Interface  
```  
  
```csharp  
public interface ICalculator  
{  
    String Calculate(String input);  
}  
```  
  
 <span data-ttu-id="c3834-189">Теперь, после определения `ICalculator`, нужен класс, который его реализует.</span><span class="sxs-lookup"><span data-stu-id="c3834-189">Now that you have defined `ICalculator`, you need a class that implements it.</span></span>  <span data-ttu-id="c3834-190">Добавьте следующий класс в модуль или пространство имен `SimpleCalculator`:</span><span class="sxs-lookup"><span data-stu-id="c3834-190">Add the following class to the module or `SimpleCalculator` namespace:</span></span>  
  
```vb  
<Export(GetType(ICalculator))>  
Public Class MySimpleCalculator  
   Implements ICalculator  
  
End Class  
```  
  
```csharp  
[Export(typeof(ICalculator))]  
class MySimpleCalculator : ICalculator  
{  
  
}  
```  
  
 <span data-ttu-id="c3834-191">Здесь используется экспортируемый элемент, соответствующий импортируемому элементу в `Program`.</span><span class="sxs-lookup"><span data-stu-id="c3834-191">Here is the export that will match the import in `Program`.</span></span> <span data-ttu-id="c3834-192">Чтобы экспортируемый элемент соответствовал импортируемому, экспорт должен иметь такой же контракт.</span><span class="sxs-lookup"><span data-stu-id="c3834-192">In order for the export to match the import, the export must have the same contract.</span></span>  <span data-ttu-id="c3834-193">Экспорт по контракту на основе `typeof(MySimpleCalculator)` вызовет несовпадение, и импортируемый элемент не будет заполнен; контракт должен в точности совпадать.</span><span class="sxs-lookup"><span data-stu-id="c3834-193">Exporting under a contract based on `typeof(MySimpleCalculator)` would produce a mismatch, and the import would not be filled; the contract needs to match exactly.</span></span>  
  
 <span data-ttu-id="c3834-194">Так как контейнер композиции будет заполняться всеми доступными в этой сборке частями, часть `MySimpleCalculator` будет доступна.</span><span class="sxs-lookup"><span data-stu-id="c3834-194">Since the composition container will be populated with all the parts available in this assembly, the `MySimpleCalculator` part will be available.</span></span>  <span data-ttu-id="c3834-195">Когда конструктор для `Program` выполняет композицию для объекта `Program`, его импортируемый элемент будет заполняться объектом `MySimpleCalculator`, который будет создан для этой цели.</span><span class="sxs-lookup"><span data-stu-id="c3834-195">When the constructor for `Program` performs composition on the `Program` object, its import will be filled with a `MySimpleCalculator` object, which will be created for that purpose.</span></span>  
  
 <span data-ttu-id="c3834-196">Для уровня пользовательского интерфейса (`Program`) никакая другая информация не требуется.</span><span class="sxs-lookup"><span data-stu-id="c3834-196">The user interface layer (`Program`) does not need to know anything else.</span></span>  <span data-ttu-id="c3834-197">Таким образом, можно заполнить остальную часть логики интерфейса пользователя в методе `Main`.</span><span class="sxs-lookup"><span data-stu-id="c3834-197">You can therefore fill in the rest of the user interface logic in the `Main` method.</span></span>  
  
 <span data-ttu-id="c3834-198">Добавьте следующий код в метод `Main`.</span><span class="sxs-lookup"><span data-stu-id="c3834-198">Add the following code to the `Main` method:</span></span>  
  
```vb  
Sub Main()  
    Dim p As New Program()  
    Dim s As String  
    Console.WriteLine("Enter Command:")  
    While (True)  
        s = Console.ReadLine()  
        Console.WriteLine(p.calculator.Calculate(s))  
    End While  
End Sub  
```  
  
```csharp  
static void Main(string[] args)  
{  
    Program p = new Program(); //Composition is performed in the constructor  
    String s;  
    Console.WriteLine("Enter Command:");  
    while (true)  
    {  
        s = Console.ReadLine();  
        Console.WriteLine(p.calculator.Calculate(s));  
    }  
}  
```  
  
 <span data-ttu-id="c3834-199">Этот код просто считывает строку входных данных и вызывает функцию `Calculate` калькулятора `ICalculator` с результатом, который он записывает в консоль.</span><span class="sxs-lookup"><span data-stu-id="c3834-199">This code simply reads a line of input and calls the `Calculate` function of `ICalculator` on the result, which it writes back to the console.</span></span> <span data-ttu-id="c3834-200">То есть, весь код, требуемый в `Program`.</span><span class="sxs-lookup"><span data-stu-id="c3834-200">That is all the code you need in `Program`.</span></span>  <span data-ttu-id="c3834-201">Все остальные действия будут выполняться по частям.</span><span class="sxs-lookup"><span data-stu-id="c3834-201">All the rest of the work will happen in the parts.</span></span>  
  
<a name="further_imports_and_importmany"></a>   
## <a name="further-imports-and-importmany"></a><span data-ttu-id="c3834-202">Дополнительные импортируемые элементы и атрибут ImportMany</span><span class="sxs-lookup"><span data-stu-id="c3834-202">Further Imports and ImportMany</span></span>  
 <span data-ttu-id="c3834-203">Чтобы приложение SimpleCalculator было расширяемым, оно должно импортировать список операций.</span><span class="sxs-lookup"><span data-stu-id="c3834-203">In order for SimpleCalculator to be extensible, it needs to import a list of operations.</span></span> <span data-ttu-id="c3834-204">Обычный атрибут <xref:System.ComponentModel.Composition.ImportAttribute> заполняется одним и только одним <xref:System.ComponentModel.Composition.ExportAttribute>.</span><span class="sxs-lookup"><span data-stu-id="c3834-204">An ordinary <xref:System.ComponentModel.Composition.ImportAttribute> attribute is filled by one and only one <xref:System.ComponentModel.Composition.ExportAttribute>.</span></span>  <span data-ttu-id="c3834-205">Если имеется несколько значений, обработчик композиции выдаст ошибку.</span><span class="sxs-lookup"><span data-stu-id="c3834-205">If more than one is available, the composition engine produces an error.</span></span>  <span data-ttu-id="c3834-206">Чтобы создать импортируемый элемент, который может заполняться произвольным количеством экспортируемых элементов, можно использовать атрибут <xref:System.ComponentModel.Composition.ImportManyAttribute>.</span><span class="sxs-lookup"><span data-stu-id="c3834-206">To create an import that can be filled by any number of exports, you can use the <xref:System.ComponentModel.Composition.ImportManyAttribute> attribute.</span></span>  
  
 <span data-ttu-id="c3834-207">Добавьте следующее свойство операций `MySimpleCalculator` класса:</span><span class="sxs-lookup"><span data-stu-id="c3834-207">Add the following operations property to the `MySimpleCalculator` class:</span></span>  
  
```vb  
<ImportMany()>  
Public Property operations As IEnumerable(Of Lazy(Of IOperation, IOperationData))  
```  
  
```csharp  
[ImportMany]  
IEnumerable<Lazy<IOperation, IOperationData>> operations;  
```  
  
 <span data-ttu-id="c3834-208"><xref:System.Lazy%602> — это тип, задаваемый платформой MEF для сохранения косвенных ссылок на экспортируемые элементы.</span><span class="sxs-lookup"><span data-stu-id="c3834-208"><xref:System.Lazy%602> is a type provided by MEF to hold indirect references to exports.</span></span>  <span data-ttu-id="c3834-209">Здесь, кроме самого экспортируемого объекта, вы также получаете *экспорта метаданных*, или информацию, описывающую экспортируемый объект.</span><span class="sxs-lookup"><span data-stu-id="c3834-209">Here, in addition to the exported object itself, you also get *export metadata*, or information that describes the exported object.</span></span> <span data-ttu-id="c3834-210">Каждый <xref:System.Lazy%602> содержит объект `IOperation`, представляющий собой фактическую операцию, и объект `IOperationData`, представляющий ее метаданные.</span><span class="sxs-lookup"><span data-stu-id="c3834-210">Each <xref:System.Lazy%602> contains an `IOperation` object, representing an actual operation, and an `IOperationData` object, representing its metadata.</span></span>  
  
 <span data-ttu-id="c3834-211">Добавьте следующие простые интерфейсы в модуль или пространство имен `SimpleCalculator`:</span><span class="sxs-lookup"><span data-stu-id="c3834-211">Add the following simple interfaces to the module or `SimpleCalculator` namespace:</span></span>  
  
```vb  
Public Interface IOperation  
    Function Operate(ByVal left As Integer, ByVal right As Integer) As Integer  
End Interface  
  
Public Interface IOperationData  
    ReadOnly Property Symbol As Char  
End Interface  
```  
  
```csharp  
public interface IOperation  
{  
     int Operate(int left, int right);  
}  
  
public interface IOperationData  
{  
    Char Symbol { get; }  
}  
```  
  
 <span data-ttu-id="c3834-212">В этом случае метаданными для каждой операции является символ, представляющий данную операцию, например, +, -, * и т. д.</span><span class="sxs-lookup"><span data-stu-id="c3834-212">In this case, the metadata for each operation is the symbol that represents that operation, such as +, -, *, and so on.</span></span> <span data-ttu-id="c3834-213">Чтобы сделать доступной операцию сложения, добавьте следующий класс в модуль или пространство имен `SimpleCalculator`:</span><span class="sxs-lookup"><span data-stu-id="c3834-213">To make the addition operation available, add the following class to the module or `SimpleCalculator` namespace:</span></span>  
  
```vb  
<Export(GetType(IOperation))>  
<ExportMetadata("Symbol", "+"c)>  
Public Class Add  
    Implements IOperation  
  
    Public Function Operate(ByVal left As Integer, ByVal right As Integer) As Integer Implements IOperation.Operate  
        Return left + right  
    End Function  
End Class  
```  
  
```csharp  
[Export(typeof(IOperation))]  
[ExportMetadata("Symbol", '+')]  
class Add: IOperation  
{  
    public int Operate(int left, int right)  
    {  
        return left + right;  
    }  
}  
```  
  
 <span data-ttu-id="c3834-214">Атрибут <xref:System.ComponentModel.Composition.ExportAttribute> функционирует так же, как и раньше.</span><span class="sxs-lookup"><span data-stu-id="c3834-214">The <xref:System.ComponentModel.Composition.ExportAttribute> attribute functions as it did before.</span></span>  <span data-ttu-id="c3834-215">Атрибут <xref:System.ComponentModel.Composition.ExportMetadataAttribute> присоединяет метаданные к данному экспортируемому элементу в виде пары "имя значение".</span><span class="sxs-lookup"><span data-stu-id="c3834-215">The <xref:System.ComponentModel.Composition.ExportMetadataAttribute> attribute attaches metadata, in the form of a name-value pair, to that export.</span></span>  <span data-ttu-id="c3834-216">Если `Add` реализует `IOperation`, то класс, реализующий `IOperationData`, явным образом не определен.</span><span class="sxs-lookup"><span data-stu-id="c3834-216">While the `Add` class implements `IOperation`, a class that implements `IOperationData` is not explicitly defined.</span></span> <span data-ttu-id="c3834-217">Вместо этого, он создается неявным образом платформой MEF со свойствами на основе имен предоставленных метаданных.</span><span class="sxs-lookup"><span data-stu-id="c3834-217">Instead, a class is implicitly created by MEF with properties based on the names of the metadata provided.</span></span>  <span data-ttu-id="c3834-218">(Это один из нескольких способов доступа к метаданным в MEF.)</span><span class="sxs-lookup"><span data-stu-id="c3834-218">(This is one of several ways to access metadata in MEF.)</span></span>  
  
 <span data-ttu-id="c3834-219">Композиция на платформе MEF является *рекурсивные*.</span><span class="sxs-lookup"><span data-stu-id="c3834-219">Composition in MEF is *recursive*.</span></span> <span data-ttu-id="c3834-220">Вы явным образом составили композицию объекта `Program`, импортировавшего `ICalculator`, который получил тип `MySimpleCalculator`.</span><span class="sxs-lookup"><span data-stu-id="c3834-220">You explicitly composed the `Program` object, which imported an `ICalculator` that turned out to be of type `MySimpleCalculator`.</span></span>  <span data-ttu-id="c3834-221">`MySimpleCalculator`, в свою очередь, импортирует коллекцию объектов `IOperation`, и данный импорт будет заполнен при создании `MySimpleCalculator`, одновременно с импортируемыми элементами `Program`.</span><span class="sxs-lookup"><span data-stu-id="c3834-221">`MySimpleCalculator`, in turn, imports a collection of `IOperation` objects, and that import will be filled when `MySimpleCalculator` is created, at the same time as the imports of `Program`.</span></span> <span data-ttu-id="c3834-222">Если `Add` класс объявил дополнительный импортируемый элемент, он тоже должен быть заполнен, и т. д.</span><span class="sxs-lookup"><span data-stu-id="c3834-222">If the `Add` class declared a further import, that too would have to be filled, and so on.</span></span> <span data-ttu-id="c3834-223">Любой незаполненный импорт будет вызывать ошибку композиции.</span><span class="sxs-lookup"><span data-stu-id="c3834-223">Any import left unfilled results in a composition error.</span></span>  <span data-ttu-id="c3834-224">(Однако можно объявить, что импортируемые элементы являются необязательными, или присвоить им значения по умолчанию.)</span><span class="sxs-lookup"><span data-stu-id="c3834-224">(It is possible, however, to declare imports to be optional or to assign them default values.)</span></span>  
  
<a name="calculator_logic"></a>   
## <a name="calculator-logic"></a><span data-ttu-id="c3834-225">Логика калькулятора</span><span class="sxs-lookup"><span data-stu-id="c3834-225">Calculator Logic</span></span>  
 <span data-ttu-id="c3834-226">При наличии всех этих частей все, что остается, представляет собой саму логику калькулятора.</span><span class="sxs-lookup"><span data-stu-id="c3834-226">With these parts in place, all that remains is the calculator logic itself.</span></span> <span data-ttu-id="c3834-227">Добавьте следующий код в класс `MySimpleCalculator` для реализации метода `Calculate`:</span><span class="sxs-lookup"><span data-stu-id="c3834-227">Add the following code in the `MySimpleCalculator` class to implement the `Calculate` method:</span></span>  
  
```vb  
Public Function Calculate(ByVal input As String) As String Implements ICalculator.Calculate  
    Dim left, right As Integer  
    Dim operation As Char  
    Dim fn = FindFirstNonDigit(input) 'Finds the operator  
    If fn < 0 Then  
        Return "Could not parse command."  
    End If  
    operation = input(fn)  
    Try  
        left = Integer.Parse(input.Substring(0, fn))  
        right = Integer.Parse(input.Substring(fn + 1))  
    Catch ex As Exception  
        Return "Could not parse command."  
    End Try  
    For Each i As Lazy(Of IOperation, IOperationData) In operations  
        If i.Metadata.symbol = operation Then  
            Return i.Value.Operate(left, right).ToString()  
        End If  
    Next  
    Return "Operation not found!"  
End Function  
```  
  
```csharp  
public String Calculate(String input)  
{  
    int left;  
    int right;  
    Char operation;  
    int fn = FindFirstNonDigit(input); //finds the operator  
    if (fn < 0) return "Could not parse command.";  
  
    try  
    {  
        //separate out the operands  
        left = int.Parse(input.Substring(0, fn));  
        right = int.Parse(input.Substring(fn + 1));  
    }  
    catch   
    {  
        return "Could not parse command.";  
    }  
  
    operation = input[fn];  
  
    foreach (Lazy<IOperation, IOperationData> i in operations)  
    {  
        if (i.Metadata.Symbol.Equals(operation)) return i.Value.Operate(left, right).ToString();  
    }  
    return "Operation Not Found!";  
}  
```  
  
 <span data-ttu-id="c3834-228">Начальные действия анализируют входную строку по левому и правому операндам, а также символ оператора.</span><span class="sxs-lookup"><span data-stu-id="c3834-228">The initial steps parse the input string into left and right operands and an operator character.</span></span>  <span data-ttu-id="c3834-229">В цикле `foreach` анализируется каждый член коллекции `operations`.</span><span class="sxs-lookup"><span data-stu-id="c3834-229">In the `foreach` loop, every member of the `operations` collection is examined.</span></span> <span data-ttu-id="c3834-230">Эти объекты относятся к типу <xref:System.Lazy%602>, а доступ к значениям их метаданных и экспортируемому объекту можно получить с помощью, соответственно, свойств <xref:System.Lazy%602.Metadata%2A> и <xref:System.Lazy%601.Value%2A>.</span><span class="sxs-lookup"><span data-stu-id="c3834-230">These objects are of type <xref:System.Lazy%602>, and their metadata values and exported object can be accessed with the <xref:System.Lazy%602.Metadata%2A> property and the <xref:System.Lazy%601.Value%2A> property respectively.</span></span> <span data-ttu-id="c3834-231">В этом случае, если обнаружено, что свойство `Symbol` объекта `IOperationData` совпадает, калькулятор вызывает метод `Operate` объекта `IOperation` и возвращает результат.</span><span class="sxs-lookup"><span data-stu-id="c3834-231">In this case, if the `Symbol` property of the `IOperationData` object is discovered to be a match, the calculator calls the `Operate` method of the `IOperation` object and returns the result.</span></span>  
  
 <span data-ttu-id="c3834-232">Для завершения работы над калькулятором также нужен вспомогательный метод, который возвращает позицию первого нецифрового символа в строке.</span><span class="sxs-lookup"><span data-stu-id="c3834-232">To complete the calculator, you also need a helper method that returns the position of the first non-digit character in a string.</span></span>  <span data-ttu-id="c3834-233">Добавьте в класс `MySimpleCalculator` следующий вспомогательный метод:</span><span class="sxs-lookup"><span data-stu-id="c3834-233">Add the following helper method to the `MySimpleCalculator` class:</span></span>  
  
```vb  
Private Function FindFirstNonDigit(ByVal s As String) As Integer  
    For i = 0 To s.Length  
        If (Not (Char.IsDigit(s(i)))) Then Return i  
    Next  
    Return -1  
End Function  
```  
  
```csharp  
private int FindFirstNonDigit(String s)  
{  
    for (int i = 0; i < s.Length; i++)  
    {  
        if (!(Char.IsDigit(s[i]))) return i;  
    }  
    return -1;  
}  
```  
  
 <span data-ttu-id="c3834-234">Теперь вы должны получить возможность скомпилировать и запустить проект.</span><span class="sxs-lookup"><span data-stu-id="c3834-234">You should now be able to compile and run the project.</span></span> <span data-ttu-id="c3834-235">В Visual Basic убедитесь, что вы добавили ключевое слово `Public` в `Module1`.</span><span class="sxs-lookup"><span data-stu-id="c3834-235">In Visual Basic, make sure that you added the `Public` keyword to `Module1`.</span></span> <span data-ttu-id="c3834-236">В окне консоли введите операцию сложения, например, "5 + 3", и калькулятор вернет результат.</span><span class="sxs-lookup"><span data-stu-id="c3834-236">In the console window, type an addition operation, such as "5+3", and the calculator will return the results.</span></span>  <span data-ttu-id="c3834-237">Любой другой оператор вернет сообщение "Операция не найдена</span><span class="sxs-lookup"><span data-stu-id="c3834-237">Any other operator will result in the "Operation Not Found!"</span></span> <span data-ttu-id="c3834-238">!".</span><span class="sxs-lookup"><span data-stu-id="c3834-238">message.</span></span>  
  
<a name="extending_simplecalculator_using_a_new_class"></a>   
## <a name="extending-simplecalculator-using-a-new-class"></a><span data-ttu-id="c3834-239">Расширение приложения SimpleCalculator с помощью нового класса</span><span class="sxs-lookup"><span data-stu-id="c3834-239">Extending SimpleCalculator Using A New Class</span></span>  
 <span data-ttu-id="c3834-240">Теперь, когда калькулятор работает, добавление новой операции является простой задачей.</span><span class="sxs-lookup"><span data-stu-id="c3834-240">Now that the calculator works, adding a new operation is easy.</span></span> <span data-ttu-id="c3834-241">Добавьте следующий класс в модуль или пространство имен `SimpleCalculator`:</span><span class="sxs-lookup"><span data-stu-id="c3834-241">Add the following class to the module or `SimpleCalculator` namespace:</span></span>  
  
```vb  
<Export(GetType(IOperation))>  
<ExportMetadata("Symbol", "-"c)>  
Public Class Subtract  
    Implements IOperation  
  
    Public Function Operate(ByVal left As Integer, ByVal right As Integer) As Integer Implements IOperation.Operate  
        Return left - right  
    End Function  
End Class  
```  
  
```csharp  
[Export(typeof(IOperation))]  
[ExportMetadata("Symbol", '-')]  
class Subtract : IOperation  
{  
    public int Operate(int left, int right)  
    {  
        return left - right;  
    }  
}  
```  
  
 <span data-ttu-id="c3834-242">Скомпилируйте и запустите проект.</span><span class="sxs-lookup"><span data-stu-id="c3834-242">Compile and run the project.</span></span> <span data-ttu-id="c3834-243">Выполните операцию вычитания, например, "5 - 3".</span><span class="sxs-lookup"><span data-stu-id="c3834-243">Type a subtraction operation, such as "5-3".</span></span> <span data-ttu-id="c3834-244">Теперь калькулятор выполняет операции вычитания наряду со сложением.</span><span class="sxs-lookup"><span data-stu-id="c3834-244">The calculator now supports subtraction as well as addition.</span></span>  
  
<a name="extending_simplecalculator_using_a_new_assembly"></a>   
## <a name="extending-simplecalculator-using-a-new-assembly"></a><span data-ttu-id="c3834-245">Расширение приложения SimpleCalculator с помощью новой сборки</span><span class="sxs-lookup"><span data-stu-id="c3834-245">Extending SimpleCalculator Using A New Assembly</span></span>  
 <span data-ttu-id="c3834-246">Процедура добавления классов в исходный код является довольно простой, но MEF позволяет искать части за пределами исходного кода приложения.</span><span class="sxs-lookup"><span data-stu-id="c3834-246">Adding classes to the source code is simple enough, but MEF provides the ability to look outside an application’s own source for parts.</span></span> <span data-ttu-id="c3834-247">Чтобы продемонстрировать это, необходимо изменить приложение SimpleCalculator для поиска в каталоге, а также в его собственной сборке, частей путем добавления <xref:System.ComponentModel.Composition.Hosting.DirectoryCatalog>.</span><span class="sxs-lookup"><span data-stu-id="c3834-247">To demonstrate this, you will need to modify SimpleCalculator to search a directory, as well as its own assembly, for parts, by adding a <xref:System.ComponentModel.Composition.Hosting.DirectoryCatalog>.</span></span>  
  
 <span data-ttu-id="c3834-248">Добавьте новый каталог с именем `Extensions` в проект SimpleCalculator.</span><span class="sxs-lookup"><span data-stu-id="c3834-248">Add a new directory named `Extensions` to the SimpleCalculator project.</span></span>  <span data-ttu-id="c3834-249">Убедитесь, что добавление выполняется на уровне проекта, а не на уровне решения.</span><span class="sxs-lookup"><span data-stu-id="c3834-249">Make sure to add it at the project level, and not at the solution level.</span></span> <span data-ttu-id="c3834-250">Затем добавьте новый проект библиотеки классов в решение с именем `ExtendedOperations`.</span><span class="sxs-lookup"><span data-stu-id="c3834-250">Then add a new Class Library project to the solution, named `ExtendedOperations`.</span></span> <span data-ttu-id="c3834-251">Новый проект будет скомпилирован в отдельную сборку.</span><span class="sxs-lookup"><span data-stu-id="c3834-251">The new project will compile into a separate assembly.</span></span>  
  
 <span data-ttu-id="c3834-252">Откройте конструктор свойств проекта для проекта ExtendedOperations и щелкните **компиляции** или **построения** вкладки. Изменение **выходной путь построения** или **выходной путь** чтобы она указывала на каталог расширений в каталоге проекта SimpleCalculator (.. \SimpleCalculator\Extensions\\).</span><span class="sxs-lookup"><span data-stu-id="c3834-252">Open the Project Properties Designer for the ExtendedOperations project and click the **Compile** or **Build** tab. Change the **Build output path** or **Output path** to point to the Extensions directory in the SimpleCalculator project directory (..\SimpleCalculator\Extensions\\).</span></span>  
  
 <span data-ttu-id="c3834-253">В модуле Module1.vb или Program.cs добавьте следующую строку в конструктор `Program`:</span><span class="sxs-lookup"><span data-stu-id="c3834-253">In Module1.vb or Program.cs, add the following line to the `Program` constructor:</span></span>  
  
```vb  
catalog.Catalogs.Add(New DirectoryCatalog("C:\SimpleCalculator\SimpleCalculator\Extensions"))  
```  
  
```csharp  
catalog.Catalogs.Add(new DirectoryCatalog("C:\\SimpleCalculator\\SimpleCalculator\\Extensions"));  
```  
  
 <span data-ttu-id="c3834-254">Замените пример пути на путь к каталогу расширений.</span><span class="sxs-lookup"><span data-stu-id="c3834-254">Replace the example path with the path to your Extensions directory.</span></span>  <span data-ttu-id="c3834-255">(Этот абсолютный путь используется только для отладки.</span><span class="sxs-lookup"><span data-stu-id="c3834-255">(This absolute path is for debugging purposes only.</span></span>  <span data-ttu-id="c3834-256">В реальном приложении будет использоваться относительный путь.) <xref:System.ComponentModel.Composition.Hosting.DirectoryCatalog> добавит все части, найденные в сборках в каталоге расширений, в контейнер композиции.</span><span class="sxs-lookup"><span data-stu-id="c3834-256">In a production application, you would use a relative path.) The <xref:System.ComponentModel.Composition.Hosting.DirectoryCatalog> will now add any parts found in any assemblies in the Extensions directory to the composition container.</span></span>  
  
 <span data-ttu-id="c3834-257">В проекте ExtendedOperations добавьте ссылки на приложение SimpleCalculator и System.ComponentModel.Composition.</span><span class="sxs-lookup"><span data-stu-id="c3834-257">In the ExtendedOperations project, add references to SimpleCalculator and System.ComponentModel.Composition.</span></span> <span data-ttu-id="c3834-258">В файле класса ExtendedOperations добавьте оператор `Imports` или `using` для System.ComponentModel.Composition.</span><span class="sxs-lookup"><span data-stu-id="c3834-258">In the ExtendedOperations class file, add an `Imports` or a `using` statement for System.ComponentModel.Composition.</span></span> <span data-ttu-id="c3834-259">В Visual Basic также добавьте оператор `Imports` для SimpleCalculator.</span><span class="sxs-lookup"><span data-stu-id="c3834-259">In Visual Basic, also add an `Imports` statement for SimpleCalculator.</span></span> <span data-ttu-id="c3834-260">Затем добавьте следующий класс в файл класса ExtendedOperations:</span><span class="sxs-lookup"><span data-stu-id="c3834-260">Then add the following class to the ExtendedOperations class file:</span></span>  
  
```vb  
<Export(GetType(SimpleCalculator.IOperation))>  
<ExportMetadata("Symbol", "%"c)>  
Public Class Modulo  
    Implements IOperation  
  
    Public Function Operate(ByVal left As Integer, ByVal right As Integer) As Integer Implements IOperation.Operate  
        Return left Mod right  
    End Function  
End Class  
```  
  
```csharp  
[Export(typeof(SimpleCalculator.IOperation))]  
[ExportMetadata("Symbol", '%')]  
public class Mod : SimpleCalculator.IOperation  
{  
    public int Operate(int left, int right)  
    {  
        return left % right;  
    }  
}  
```  
  
 <span data-ttu-id="c3834-261">Следует отметить, что для совпадения контрактов атрибут <xref:System.ComponentModel.Composition.ExportAttribute> должен иметь тот же тип, что и <xref:System.ComponentModel.Composition.ImportAttribute>.</span><span class="sxs-lookup"><span data-stu-id="c3834-261">Note that in order for the contract to match, the <xref:System.ComponentModel.Composition.ExportAttribute> attribute must have the same type as the <xref:System.ComponentModel.Composition.ImportAttribute>.</span></span>  
  
 <span data-ttu-id="c3834-262">Скомпилируйте и запустите проект.</span><span class="sxs-lookup"><span data-stu-id="c3834-262">Compile and run the project.</span></span> <span data-ttu-id="c3834-263">Проверьте новый оператор Mod (%).</span><span class="sxs-lookup"><span data-stu-id="c3834-263">Test the new Mod (%) operator.</span></span>  
  
<a name="conclusion"></a>   
## <a name="conclusion"></a><span data-ttu-id="c3834-264">Заключение</span><span class="sxs-lookup"><span data-stu-id="c3834-264">Conclusion</span></span>  
 <span data-ttu-id="c3834-265">В этом разделе рассмотрены основные концепции платформы MEF.</span><span class="sxs-lookup"><span data-stu-id="c3834-265">This topic covered the basic concepts of MEF.</span></span>  
  
-   <span data-ttu-id="c3834-266">Части, каталоги и контейнер композиции</span><span class="sxs-lookup"><span data-stu-id="c3834-266">Parts, catalogs, and the composition container</span></span>  
  
     <span data-ttu-id="c3834-267">Части и контейнер композиции являются базовыми строительными блоками приложения MEF.</span><span class="sxs-lookup"><span data-stu-id="c3834-267">Parts and the composition container are the basic building blocks of a MEF application.</span></span> <span data-ttu-id="c3834-268">Часть — это любой объект, который импортирует или экспортирует значение, вплоть до самого себя.</span><span class="sxs-lookup"><span data-stu-id="c3834-268">A part is any object that imports or exports a value, up to and including itself.</span></span> <span data-ttu-id="c3834-269">Каталог содержит коллекцию частей из определенного источника.</span><span class="sxs-lookup"><span data-stu-id="c3834-269">A catalog provides a collection of parts from a particular source.</span></span>  <span data-ttu-id="c3834-270">Контейнер композиции использует части, предоставленные каталогом для выполнения композиции, связывания импортируемых и экспортируемых элементов.</span><span class="sxs-lookup"><span data-stu-id="c3834-270">The composition container uses the parts provided by a catalog to perform composition, the binding of imports to exports.</span></span>  
  
-   <span data-ttu-id="c3834-271">Импортируемые и экспортируемые элементы</span><span class="sxs-lookup"><span data-stu-id="c3834-271">Imports and exports</span></span>  
  
     <span data-ttu-id="c3834-272">Импортируемые и экспортируемые элементы позволяют компонентам взаимодействовать друг с другом.</span><span class="sxs-lookup"><span data-stu-id="c3834-272">Imports and exports are the way by which components communicate.</span></span> <span data-ttu-id="c3834-273">При импорте компонент указывает на необходимость в определенном значении или объекте, а при экспорте он указывает на доступность значения.</span><span class="sxs-lookup"><span data-stu-id="c3834-273">With an import, the component specifies a need for a particular value or object, and with an export it specifies the availability of a value.</span></span> <span data-ttu-id="c3834-274">Каждый импортируемый элемент сопоставляется со списком экспортируемых элементов при помощи своего контракта.</span><span class="sxs-lookup"><span data-stu-id="c3834-274">Each import is matched with a list of exports by way of its contract.</span></span>  
  
<a name="where_do_i_go_now"></a>   
## <a name="where-do-i-go-now"></a><span data-ttu-id="c3834-275">Что теперь предстоит делать?</span><span class="sxs-lookup"><span data-stu-id="c3834-275">Where Do I Go Now?</span></span>  
 <span data-ttu-id="c3834-276">Чтобы загрузить полный код для этого примера, в разделе [Пример SimpleCalculator](http://code.msdn.microsoft.com/windowsdesktop/Simple-Calculator-MEF-1152654e).</span><span class="sxs-lookup"><span data-stu-id="c3834-276">To download the complete code for this example, see the [SimpleCalculator sample](http://code.msdn.microsoft.com/windowsdesktop/Simple-Calculator-MEF-1152654e).</span></span>  
  
 <span data-ttu-id="c3834-277">Дополнительные сведения и примеры кода см. в разделе [Managed Extensibility Framework](http://go.microsoft.com/fwlink/?LinkId=144282).</span><span class="sxs-lookup"><span data-stu-id="c3834-277">For more information and code examples, see [Managed Extensibility Framework](http://go.microsoft.com/fwlink/?LinkId=144282).</span></span> <span data-ttu-id="c3834-278">Список типов MEF см. в пространстве имен <xref:System.ComponentModel.Composition?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c3834-278">For a list of the MEF types, see the <xref:System.ComponentModel.Composition?displayProperty=nameWithType> namespace.</span></span>
