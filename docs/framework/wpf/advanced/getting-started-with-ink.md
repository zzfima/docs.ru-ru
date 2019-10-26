---
title: Создание InkCanvas в приложении WPF в Visual Studio
ms.date: 08/15/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- procedural code in lieu of XAML [WPF]
- XAML [WPF], procedural code in lieu of
- InkCanvas (WPF)
ms.assetid: 760332dd-594a-475d-865b-01659db8cab7
ms.openlocfilehash: ebbf25037921e7802b2bfcb6ffa562d16a849ffa
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2019
ms.locfileid: "72920253"
---
# <a name="get-started-with-ink-in-wpf"></a><span data-ttu-id="883f9-102">Начало работы с рукописным вводом в WPF</span><span class="sxs-lookup"><span data-stu-id="883f9-102">Get Started with Ink in WPF</span></span>

<span data-ttu-id="883f9-103">Windows Presentation Foundation (WPF) имеет функцию рукописного ввода, которая упрощает внедрение цифровых рукописных данных в приложение.</span><span class="sxs-lookup"><span data-stu-id="883f9-103">Windows Presentation Foundation (WPF) has an ink feature that makes it easy to incorporate digital ink into your app.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="883f9-104">Необходимые компоненты</span><span class="sxs-lookup"><span data-stu-id="883f9-104">Prerequisites</span></span>

<span data-ttu-id="883f9-105">Чтобы использовать следующие примеры, сначала установите [Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019).</span><span class="sxs-lookup"><span data-stu-id="883f9-105">To use the following examples, first install [Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019).</span></span> <span data-ttu-id="883f9-106">Кроме того, он помогает понять, как писать базовые приложения WPF.</span><span class="sxs-lookup"><span data-stu-id="883f9-106">It also helps to know how to write basic WPF apps.</span></span> <span data-ttu-id="883f9-107">Сведения о начале работы с WPF см. в разделе [Пошаговое руководство. мое первое классическое приложение WPF](../getting-started/walkthrough-my-first-wpf-desktop-application.md).</span><span class="sxs-lookup"><span data-stu-id="883f9-107">For help getting started with WPF, see [Walkthrough: My first WPF desktop application](../getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span>

## <a name="quick-start"></a><span data-ttu-id="883f9-108">Быстрое начало</span><span class="sxs-lookup"><span data-stu-id="883f9-108">Quick Start</span></span>

<span data-ttu-id="883f9-109">Этот раздел поможет вам написать простое приложение WPF, собирающее рукописный ввод.</span><span class="sxs-lookup"><span data-stu-id="883f9-109">This section helps you write a simple WPF application that collects ink.</span></span>

### <a name="got-ink"></a><span data-ttu-id="883f9-110">У вас есть рукописный ввод?</span><span class="sxs-lookup"><span data-stu-id="883f9-110">Got Ink?</span></span>

<span data-ttu-id="883f9-111">Создание приложения WPF, поддерживающего рукописный ввод:</span><span class="sxs-lookup"><span data-stu-id="883f9-111">To create a WPF app that supports ink:</span></span>

1. <span data-ttu-id="883f9-112">Запустите Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="883f9-112">Open Visual Studio.</span></span>

2. <span data-ttu-id="883f9-113">Создайте новое **приложение WPF**.</span><span class="sxs-lookup"><span data-stu-id="883f9-113">Create a new **WPF App**.</span></span>

   <span data-ttu-id="883f9-114">В диалоговом окне **Новый проект** разверните узел **установленные** > **Visual C#**  или **Visual Basic** > **Windows Desktop** .</span><span class="sxs-lookup"><span data-stu-id="883f9-114">In the **New Project** dialog, expand the **Installed** > **Visual C#** or **Visual Basic** > **Windows Desktop** category.</span></span> <span data-ttu-id="883f9-115">Затем выберите шаблон приложения **WPF (.NET Framework)** .</span><span class="sxs-lookup"><span data-stu-id="883f9-115">Then, select the **WPF App (.NET Framework)** app template.</span></span> <span data-ttu-id="883f9-116">Введите имя и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="883f9-116">Enter a name, and then select **OK**.</span></span>

   <span data-ttu-id="883f9-117">Visual Studio создаст проект, а файл *MainWindow. XAML* откроется в конструкторе.</span><span class="sxs-lookup"><span data-stu-id="883f9-117">Visual Studio creates the project, and *MainWindow.xaml* opens in the designer.</span></span>

3. <span data-ttu-id="883f9-118">Введите `<InkCanvas/>` между тегами `<Grid>`.</span><span class="sxs-lookup"><span data-stu-id="883f9-118">Type `<InkCanvas/>` between the `<Grid>` tags.</span></span>

   ![Конструктор XAML с тегом InkCanvas](./media/getting-started-with-ink/inkcanvas-xaml.png)

4. <span data-ttu-id="883f9-120">Нажмите клавишу **F5** , чтобы запустить приложение в отладчике.</span><span class="sxs-lookup"><span data-stu-id="883f9-120">Press **F5** to launch your application in the debugger.</span></span>

5. <span data-ttu-id="883f9-121">С помощью пера или мыши напишите **Hello World** в окне.</span><span class="sxs-lookup"><span data-stu-id="883f9-121">Using a stylus or mouse, write **hello world** in the window.</span></span>

<span data-ttu-id="883f9-122">Вы написали рукописный эквивалент приложения "Hello World" только с 12 нажатиями!</span><span class="sxs-lookup"><span data-stu-id="883f9-122">You've written the ink equivalent of a "hello world" application with only 12 keystrokes!</span></span>

### <a name="spice-up-your-app"></a><span data-ttu-id="883f9-123">Воссоздание приложения</span><span class="sxs-lookup"><span data-stu-id="883f9-123">Spice Up Your App</span></span>

<span data-ttu-id="883f9-124">Давайте попробуем воспользоваться преимуществами некоторых функций WPF.</span><span class="sxs-lookup"><span data-stu-id="883f9-124">Let’s take advantage of some features of the WPF.</span></span> <span data-ttu-id="883f9-125">Замените все между открывающим и закрывающим \<окном > тегами следующей разметкой:</span><span class="sxs-lookup"><span data-stu-id="883f9-125">Replace everything between the opening and closing \<Window> tags with the following markup:</span></span>

```xaml
<Page>
  <InkCanvas Name="myInkCanvas" MouseRightButtonUp="RightMouseUpHandler">
    <InkCanvas.Background>
      <LinearGradientBrush>
        <GradientStop Color="Yellow" Offset="0.0" />
          <GradientStop Color="Blue" Offset="0.5" />
            <GradientStop Color="HotPink" Offset="1.0" />
              </LinearGradientBrush>
    </InkCanvas.Background>
  </InkCanvas>
</Page>
```

<span data-ttu-id="883f9-126">Этот XAML создает фон градиентной кисти на поверхности рукописного ввода.</span><span class="sxs-lookup"><span data-stu-id="883f9-126">This XAML creates a gradient brush background on your inking surface.</span></span>

![Градиентные цвета на поверхности рукописного ввода в приложении WPF](./media/getting-started-with-ink/gradient-colors.png)

### <a name="add-some-code-behind-the-xaml"></a><span data-ttu-id="883f9-128">Добавьте код, лежащий в основе XAML</span><span class="sxs-lookup"><span data-stu-id="883f9-128">Add Some Code Behind the XAML</span></span>

<span data-ttu-id="883f9-129">Хотя XAML упрощает проектирование пользовательского интерфейса, любое реальное приложение должно добавлять код для работы с событиями.</span><span class="sxs-lookup"><span data-stu-id="883f9-129">While XAML makes it very easy to design the user interface, any real-world application needs to add code to handle events.</span></span> <span data-ttu-id="883f9-130">Ниже приведен простой пример, который позволяет увеличить рукописный ввод в ответ на щелчок правой кнопкой мыши.</span><span class="sxs-lookup"><span data-stu-id="883f9-130">Here is a simple example that zooms in on the ink in response to a right-click from a mouse.</span></span>

1. <span data-ttu-id="883f9-131">Задайте обработчик `MouseRightButtonUp` в коде XAML:</span><span class="sxs-lookup"><span data-stu-id="883f9-131">Set the `MouseRightButtonUp` handler in your XAML:</span></span>

   [!code-xaml[DigitalInkTopics#3](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#3)]

1. <span data-ttu-id="883f9-132">В **Обозреватель решений**разверните MainWindow. XAML и откройте файл кода программной части (MainWindow.XAML.cs или MainWindow. XAML. vb).</span><span class="sxs-lookup"><span data-stu-id="883f9-132">In **Solution Explorer**, expand MainWindow.xaml and open the code-behind file (MainWindow.xaml.cs or MainWindow.xaml.vb).</span></span> <span data-ttu-id="883f9-133">Добавьте следующий код обработчика событий:</span><span class="sxs-lookup"><span data-stu-id="883f9-133">Add the following event handler code:</span></span>

   [!code-csharp[DigitalInkTopics#4](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml.cs#4)]
   [!code-vb[DigitalInkTopics#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window2.xaml.vb#4)]

1. <span data-ttu-id="883f9-134">Запустите приложение.</span><span class="sxs-lookup"><span data-stu-id="883f9-134">Run the application.</span></span> <span data-ttu-id="883f9-135">Добавьте рукописный ввод, а затем щелкните его правой кнопкой мыши или выполните нажатие клавиши с пером.</span><span class="sxs-lookup"><span data-stu-id="883f9-135">Add some ink, and then right-click with the mouse or perform a press-and-hold equivalent with a stylus.</span></span>

   <span data-ttu-id="883f9-136">Экран увеличивается при каждом щелчке правой кнопкой мыши.</span><span class="sxs-lookup"><span data-stu-id="883f9-136">The display zooms in each time you click with the right mouse button.</span></span>

### <a name="use-procedural-code-instead-of-xaml"></a><span data-ttu-id="883f9-137">Использование процедурного кода вместо XAML</span><span class="sxs-lookup"><span data-stu-id="883f9-137">Use Procedural Code Instead of XAML</span></span>

<span data-ttu-id="883f9-138">Вы можете получить доступ ко всем функциям WPF из процедурного кода.</span><span class="sxs-lookup"><span data-stu-id="883f9-138">You can access all WPF features from procedural code.</span></span> <span data-ttu-id="883f9-139">Выполните следующие действия, чтобы создать приложение "Привет для рукописного ввода" для WPF, которое вообще не использует XAML.</span><span class="sxs-lookup"><span data-stu-id="883f9-139">Follow these steps to create a "Hello Ink World" application for WPF that doesn’t use any XAML at all.</span></span>

1. <span data-ttu-id="883f9-140">Создайте новый проект консольного приложения в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="883f9-140">Create a new console application project in Visual Studio.</span></span>

   <span data-ttu-id="883f9-141">В диалоговом окне **Новый проект** разверните узел **установленные** > **Visual C#**  или **Visual Basic** > **Windows Desktop** .</span><span class="sxs-lookup"><span data-stu-id="883f9-141">In the **New Project** dialog, expand the **Installed** > **Visual C#** or **Visual Basic** > **Windows Desktop** category.</span></span> <span data-ttu-id="883f9-142">Затем выберите шаблон приложения " **консольное приложение" (.NET Framework)** .</span><span class="sxs-lookup"><span data-stu-id="883f9-142">Then, select the **Console App (.NET Framework)** app template.</span></span> <span data-ttu-id="883f9-143">Введите имя и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="883f9-143">Enter a name, and then select **OK**.</span></span>

1. <span data-ttu-id="883f9-144">Вставьте следующий код в файл Program.cs или Program. vb:</span><span class="sxs-lookup"><span data-stu-id="883f9-144">Paste the following code into the Program.cs or Program.vb file:</span></span>

   [!code-csharp[InkCanvasConsoleApp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasConsoleApp/CSharp/Program.cs#1)]
   [!code-vb[InkCanvasConsoleApp#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/InkCanvasConsoleApp/VisualBasic/Module1.vb#1)]

1. <span data-ttu-id="883f9-145">Добавьте ссылки на сборки PresentationCore, PresentationFramework и WindowsBase, щелкнув правой кнопкой мыши **ссылки** в **Обозреватель решений** и выбрав **Добавить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="883f9-145">Add references to the PresentationCore, PresentationFramework, and WindowsBase assemblies by right-clicking on **References** in **Solution Explorer** and choosing **Add Reference**.</span></span>

   ![Диспетчер ссылок, отображающий PresentationCore и PresentationFramework](./media/getting-started-with-ink/reference-manager-presentationcore-presentationframework.png)

1. <span data-ttu-id="883f9-147">Постройте приложение, нажав клавишу **F5**.</span><span class="sxs-lookup"><span data-stu-id="883f9-147">Build the application by pressing **F5**.</span></span>

## <a name="see-also"></a><span data-ttu-id="883f9-148">См. также</span><span class="sxs-lookup"><span data-stu-id="883f9-148">See also</span></span>

- [<span data-ttu-id="883f9-149">Рукописный ввод</span><span class="sxs-lookup"><span data-stu-id="883f9-149">Digital Ink</span></span>](digital-ink.md)
- [<span data-ttu-id="883f9-150">Сбор рукописных данных</span><span class="sxs-lookup"><span data-stu-id="883f9-150">Collecting Ink</span></span>](collecting-ink.md)
- [<span data-ttu-id="883f9-151">Распознавание рукописного ввода</span><span class="sxs-lookup"><span data-stu-id="883f9-151">Handwriting Recognition</span></span>](handwriting-recognition.md)
- [<span data-ttu-id="883f9-152">Хранение рукописных данных</span><span class="sxs-lookup"><span data-stu-id="883f9-152">Storing Ink</span></span>](storing-ink.md)
