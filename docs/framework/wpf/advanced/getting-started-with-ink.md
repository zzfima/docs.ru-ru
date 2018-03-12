---
title: "Начало работы с рукописными данными"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- procedural code in lieu of XAML [WPF]
- gradient brush [WPF], animating colors of
- XAML [WPF], procedural code in lieu of
- animation [WPF], gradient brush colors
- brushes [WPF], animating colors of
ms.assetid: 760332dd-594a-475d-865b-01659db8cab7
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 74227ebe815e971087569ff39ac0a3479c1b0d14
ms.sourcegitcommit: d3cfda0943364aaf6ccd574f55f584576c8a4fee
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/08/2018
---
# <a name="getting-started-with-ink"></a><span data-ttu-id="e8c85-102">Начало работы с рукописными данными</span><span class="sxs-lookup"><span data-stu-id="e8c85-102">Getting Started with Ink</span></span>
<span data-ttu-id="e8c85-103">Включение рукописного ввода в приложения проще, чем когда-либо.</span><span class="sxs-lookup"><span data-stu-id="e8c85-103">Incorporating digital ink into your applications is easier than ever.</span></span> <span data-ttu-id="e8c85-104">Рукописный ввод развивался с дополнения метод COM и Windows Forms программирования для достижения полной интеграции в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e8c85-104">Ink has evolved from being a corollary to the COM and Windows Forms method of programming to achieving full integration into the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span> <span data-ttu-id="e8c85-105">Необходимо установить отдельные пакеты SDK или библиотеки времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="e8c85-105">You do not need to install separate SDKs or runtime libraries.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e8c85-106">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="e8c85-106">Prerequisites</span></span>  
 <span data-ttu-id="e8c85-107">Чтобы использовать следующие примеры, необходимо сначала установить Microsoft Visual Studio 2005 и [!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e8c85-107">To use the following examples, you must first install Microsoft Visual Studio 2005 and the [!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)].</span></span> <span data-ttu-id="e8c85-108">Кроме того, необходимо иметь представление о создании приложений для [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e8c85-108">You should also understand how to write applications for the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span> <span data-ttu-id="e8c85-109">Дополнительные сведения о начале работы с [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], в разделе [Пошаговое руководство: My первого классического приложения WPF](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).</span><span class="sxs-lookup"><span data-stu-id="e8c85-109">For more information about getting started with the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], see [Walkthrough: My first WPF desktop application](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span>  
  
## <a name="quick-start"></a><span data-ttu-id="e8c85-110">Быстрый запуск</span><span class="sxs-lookup"><span data-stu-id="e8c85-110">Quick Start</span></span>  
 <span data-ttu-id="e8c85-111">Этот раздел помогает написать простое [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложение, которое собирает рукописного ввода.</span><span class="sxs-lookup"><span data-stu-id="e8c85-111">This section helps you write a simple [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application that collects ink.</span></span>  
  
 <span data-ttu-id="e8c85-112">Если это еще не сделано, установите Microsoft Visual Studio 2005 и [!INCLUDE[TLA#tla_winfxsdk](../../../../includes/tlasharptla-winfxsdk-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e8c85-112">If you haven't already done so, install Microsoft Visual Studio 2005 and the [!INCLUDE[TLA#tla_winfxsdk](../../../../includes/tlasharptla-winfxsdk-md.md)].</span></span> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="e8c85-113"> Обычно приложения должны быть скомпилированы перед просмотром, даже если они состоят только из [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e8c85-113"> applications usually must be compiled before you can view them, even if they consist entirely of [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span> <span data-ttu-id="e8c85-114">Тем не менее [!INCLUDE[TLA#tla_winfxsdk](../../../../includes/tlasharptla-winfxsdk-md.md)] включает в себя приложения, средство XamlPad, позволяющий ускорить процесс реализации [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-на основе пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="e8c85-114">However, the [!INCLUDE[TLA#tla_winfxsdk](../../../../includes/tlasharptla-winfxsdk-md.md)] includes an application, XamlPad, designed to speed up the process of implementing a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-based UI.</span></span> <span data-ttu-id="e8c85-115">Это приложение можно использовать для просмотра и ознакомления с несколькими первыми примерами данного документа.</span><span class="sxs-lookup"><span data-stu-id="e8c85-115">You can use that application to view and tinker with the first few samples in this document.</span></span> <span data-ttu-id="e8c85-116">Процесс создания компилируемых приложений из [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] рассматривается далее в этом документе.</span><span class="sxs-lookup"><span data-stu-id="e8c85-116">The process of creating compiled applications from [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] is covered later in this document.</span></span>  
  
 <span data-ttu-id="e8c85-117">Чтобы запустить средство XAMLPad, нажмите **запустить** последовательно выберите пункты **все программы**, пункты **Microsoft Windows SDK**, пункты **средства**и нажмите кнопку **XAMLPad**.</span><span class="sxs-lookup"><span data-stu-id="e8c85-117">To launch XAMLPad, click the **Start** menu, point to **All Programs**, point to **Microsoft Windows SDK**, point to **Tools**, and click **XAMLPad**.</span></span> <span data-ttu-id="e8c85-118">В области отрисовки XAMLPad отображается визуализация кода XAML, написанного в области кода.</span><span class="sxs-lookup"><span data-stu-id="e8c85-118">In the rendering pane, XAMLPad renders the XAML code written in the code pane.</span></span> <span data-ttu-id="e8c85-119">Можно изменить код XAML, а изменения немедленно отражаются в области отрисовки.</span><span class="sxs-lookup"><span data-stu-id="e8c85-119">You can edit the XAML code, and the changes immediately appear in the rendering pane.</span></span>  
  
#### <a name="got-ink"></a><span data-ttu-id="e8c85-120">У вас есть рукописного ввода?</span><span class="sxs-lookup"><span data-stu-id="e8c85-120">Got Ink?</span></span>  
 <span data-ttu-id="e8c85-121">Чтобы запустить первое [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложения с поддержкой рукописного ввода:</span><span class="sxs-lookup"><span data-stu-id="e8c85-121">To start your first [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application that supports ink:</span></span>  
  
1.  <span data-ttu-id="e8c85-122">Откройте Microsoft Visual Studio 2005</span><span class="sxs-lookup"><span data-stu-id="e8c85-122">Open Microsoft Visual Studio 2005</span></span>  
  
2.  <span data-ttu-id="e8c85-123">Создайте новый **приложения Windows (WPF)**</span><span class="sxs-lookup"><span data-stu-id="e8c85-123">Create a new **Windows Application (WPF)**</span></span>  
  
3.  <span data-ttu-id="e8c85-124">Тип `<InkCanvas/>` между `<Grid>` тегов</span><span class="sxs-lookup"><span data-stu-id="e8c85-124">Type `<InkCanvas/>` between the `<Grid>` tags</span></span>  
  
4.  <span data-ttu-id="e8c85-125">Нажмите клавишу **F5** для запуска приложения в отладчике</span><span class="sxs-lookup"><span data-stu-id="e8c85-125">Press **F5** to launch your application in the debugger</span></span>  
  
5.  <span data-ttu-id="e8c85-126">Используя перо или мышь, напишите **Здравствуй, мир!** в окне</span><span class="sxs-lookup"><span data-stu-id="e8c85-126">Using a stylus or mouse, write **hello world** in the window</span></span>  
  
 <span data-ttu-id="e8c85-127">Вы написали рукописный эквивалент приложения «hello world» с всего 12 клавиш!</span><span class="sxs-lookup"><span data-stu-id="e8c85-127">You've written the ink equivalent of a "hello world" application with only 12 keystrokes!</span></span>  
  
#### <a name="spice-up-your-application"></a><span data-ttu-id="e8c85-128">Изюминку в приложение</span><span class="sxs-lookup"><span data-stu-id="e8c85-128">Spice Up Your Application</span></span>  
 <span data-ttu-id="e8c85-129">Воспользуемся преимуществами некоторых возможностей [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e8c85-129">Let’s take advantage of some features of the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span>  <span data-ttu-id="e8c85-130">Замените весь код между открывающим \<окна > и закрытие \</Window > теги с следующую разметку, чтобы получить градиентный фон поверхности рукописного ввода.</span><span class="sxs-lookup"><span data-stu-id="e8c85-130">Replace everything between the opening \<Window> and closing \</Window> tags with the following markup to get a gradient brush background on your inking surface.</span></span>  
  
 [!code-xaml[DigitalInkTopics#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml#1)]  
[!code-xaml[DigitalInkTopics#1a](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml#1a)]  
  
#### <a name="using-animation"></a><span data-ttu-id="e8c85-131">С помощью анимации</span><span class="sxs-lookup"><span data-stu-id="e8c85-131">Using Animation</span></span>  
 <span data-ttu-id="e8c85-132">Для практики давайте анимация цвета градиента кисти.</span><span class="sxs-lookup"><span data-stu-id="e8c85-132">For fun, let's animate the colors of the gradient brush.</span></span> <span data-ttu-id="e8c85-133">Добавьте следующие [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] после закрывающего `</InkCanvas>` тег, но перед закрывающим тегом `</Page>` тег.</span><span class="sxs-lookup"><span data-stu-id="e8c85-133">Add the following [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] after the closing `</InkCanvas>` tag but before the closing `</Page>` tag.</span></span>  
  
 [!code-xaml[DigitalInkTopics#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml#2)]  
  
#### <a name="adding-some-code-behind-the-xaml"></a><span data-ttu-id="e8c85-134">Добавление кода программной части XAML</span><span class="sxs-lookup"><span data-stu-id="e8c85-134">Adding Some Code Behind the XAML</span></span>  
 <span data-ttu-id="e8c85-135">Хотя XAML позволяет очень легко разработать пользовательский интерфейс, любые реальных приложений необходимо добавить код для обработки событий.</span><span class="sxs-lookup"><span data-stu-id="e8c85-135">While XAML makes it very easy to design the user interface, any real-world application needs to add code to handle events.</span></span> <span data-ttu-id="e8c85-136">Ниже приведен простой пример увеличения рукописного ввода в ответ на щелчок правой кнопкой мыши:</span><span class="sxs-lookup"><span data-stu-id="e8c85-136">Here is a simple example that zooms in on the ink in response to a right-click from a mouse:</span></span>  
  
 <span data-ttu-id="e8c85-137">Задать `MouseRightButtonUp` обработчик в вашей [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="e8c85-137">Set the `MouseRightButtonUp` handler in your [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]:</span></span>  
  
 [!code-xaml[DigitalInkTopics#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#3)]  
  
 <span data-ttu-id="e8c85-138">В обозревателе решений Visual Studio разверните Windows1.xaml и откройте файл кода Window1.xaml.cs или Window1.xaml.vb при использовании Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="e8c85-138">In Visual Studio’s Solution Explorer, expand Windows1.xaml and open the code-behind file, Window1.xaml.cs or Window1.xaml.vb if you are using Visual Basic.</span></span> <span data-ttu-id="e8c85-139">Добавьте следующий код обработчика событий:</span><span class="sxs-lookup"><span data-stu-id="e8c85-139">Add the following event handler code:</span></span>  
  
 [!code-csharp[DigitalInkTopics#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml.cs#4)]
 [!code-vb[DigitalInkTopics#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window2.xaml.vb#4)]  
  
 <span data-ttu-id="e8c85-140">Теперь запустите приложение.</span><span class="sxs-lookup"><span data-stu-id="e8c85-140">Now, run your application.</span></span> <span data-ttu-id="e8c85-141">Добавьте рукописные и правой кнопкой мыши или нажатие и удерживание эквивалента с помощью пера.</span><span class="sxs-lookup"><span data-stu-id="e8c85-141">Add some ink and then right-click with the mouse or perform a press-and-hold equivalent with a stylus.</span></span>  
  
#### <a name="using-procedural-code-instead-of-xaml"></a><span data-ttu-id="e8c85-142">С использованием процедурного кода вместо XAML</span><span class="sxs-lookup"><span data-stu-id="e8c85-142">Using Procedural Code Instead of XAML</span></span>  
 <span data-ttu-id="e8c85-143">Можно получить доступ ко всем [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] функций из процедурного кода.</span><span class="sxs-lookup"><span data-stu-id="e8c85-143">You can access all [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] features from procedural code.</span></span> <span data-ttu-id="e8c85-144">Вот приложение «Hello Ink World» для [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] , не использует [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] вообще.</span><span class="sxs-lookup"><span data-stu-id="e8c85-144">Here is a "Hello Ink World" application for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] that doesn’t use any [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] at all.</span></span> <span data-ttu-id="e8c85-145">Вставьте приведенный ниже код в пустое консольное приложение в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e8c85-145">Paste the code below into an empty Console Application in Visual Studio.</span></span> <span data-ttu-id="e8c85-146">Добавление ссылки на сборки PresentationCore и PresentationFramework, WindowsBase и построить приложение, нажав клавишу **F5**:</span><span class="sxs-lookup"><span data-stu-id="e8c85-146">Add references to the PresentationCore, PresentationFramework, and WindowsBase assemblies, and build the application by pressing **F5**:</span></span>  
  
 [!code-csharp[InkCanvasConsoleApp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasConsoleApp/CSharp/Program.cs#1)]
 [!code-vb[InkCanvasConsoleApp#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InkCanvasConsoleApp/VisualBasic/Module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="e8c85-147">См. также</span><span class="sxs-lookup"><span data-stu-id="e8c85-147">See Also</span></span>  
 [<span data-ttu-id="e8c85-148">Рукописный ввод</span><span class="sxs-lookup"><span data-stu-id="e8c85-148">Digital Ink</span></span>](../../../../docs/framework/wpf/advanced/digital-ink.md)  
 [<span data-ttu-id="e8c85-149">Сбор рукописных данных</span><span class="sxs-lookup"><span data-stu-id="e8c85-149">Collecting Ink</span></span>](../../../../docs/framework/wpf/advanced/collecting-ink.md)  
 [<span data-ttu-id="e8c85-150">Распознавание рукописного ввода</span><span class="sxs-lookup"><span data-stu-id="e8c85-150">Handwriting Recognition</span></span>](../../../../docs/framework/wpf/advanced/handwriting-recognition.md)  
 [<span data-ttu-id="e8c85-151">Хранение рукописных данных</span><span class="sxs-lookup"><span data-stu-id="e8c85-151">Storing Ink</span></span>](../../../../docs/framework/wpf/advanced/storing-ink.md)
