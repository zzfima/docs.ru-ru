---
title: Создание объекту класса InkCanvas в приложении WPF в Visual Studio
ms.date: 08/15/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- procedural code in lieu of XAML [WPF]
- XAML [WPF], procedural code in lieu of
- InkCanvas (WPF)
ms.assetid: 760332dd-594a-475d-865b-01659db8cab7
ms.openlocfilehash: 2fb3f975fedbae1cf898d5ec2f7c0809e0215ecd
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57365572"
---
# <a name="get-started-with-ink-in-wpf"></a><span data-ttu-id="ca682-102">Начало работы с рукописными данными в WPF</span><span class="sxs-lookup"><span data-stu-id="ca682-102">Get Started with Ink in WPF</span></span>

<span data-ttu-id="ca682-103">Windows Presentation Foundation (WPF) есть функция рукописного ввода, которая позволяет легко внедрить рукописный ввод в приложение.</span><span class="sxs-lookup"><span data-stu-id="ca682-103">Windows Presentation Foundation (WPF) has an ink feature that makes it easy to incorporate digital ink into your app.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ca682-104">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="ca682-104">Prerequisites</span></span>

<span data-ttu-id="ca682-105">Чтобы использовать в следующих примерах, в первую очередь [установите Microsoft Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017).</span><span class="sxs-lookup"><span data-stu-id="ca682-105">To use the following examples, first [install Microsoft Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017).</span></span> <span data-ttu-id="ca682-106">Полезно также знать способы написания базовых приложений WPF.</span><span class="sxs-lookup"><span data-stu-id="ca682-106">It also helps to know how to write basic WPF apps.</span></span> <span data-ttu-id="ca682-107">Помощь по началу работы с WPF, см. в разделе [Пошаговое руководство: Создание первого классического приложения WPF](../getting-started/walkthrough-my-first-wpf-desktop-application.md).</span><span class="sxs-lookup"><span data-stu-id="ca682-107">For help getting started with WPF, see [Walkthrough: My first WPF desktop application](../getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span>

## <a name="quick-start"></a><span data-ttu-id="ca682-108">Быстрый запуск</span><span class="sxs-lookup"><span data-stu-id="ca682-108">Quick Start</span></span>

<span data-ttu-id="ca682-109">Этот раздел поможет написать простое приложение WPF, сбора данных рукописного ввода.</span><span class="sxs-lookup"><span data-stu-id="ca682-109">This section helps you write a simple WPF application that collects ink.</span></span>

### <a name="got-ink"></a><span data-ttu-id="ca682-110">У вас есть рукописного ввода?</span><span class="sxs-lookup"><span data-stu-id="ca682-110">Got Ink?</span></span>

<span data-ttu-id="ca682-111">Создание приложения WPF с поддержкой рукописного ввода:</span><span class="sxs-lookup"><span data-stu-id="ca682-111">To create a WPF app that supports ink:</span></span>

1. <span data-ttu-id="ca682-112">Запустите Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ca682-112">Open Visual Studio.</span></span>

2. <span data-ttu-id="ca682-113">Создайте новый **приложение WPF**.</span><span class="sxs-lookup"><span data-stu-id="ca682-113">Create a new **WPF App**.</span></span>

   <span data-ttu-id="ca682-114">В **новый проект** диалоговом окне разверните **установленные** > **Visual C#** или **Visual Basic**  >   **Windows Desktop** категории.</span><span class="sxs-lookup"><span data-stu-id="ca682-114">In the **New Project** dialog, expand the **Installed** > **Visual C#** or **Visual Basic** > **Windows Desktop** category.</span></span> <span data-ttu-id="ca682-115">Выберите **приложение WPF (.NET Framework)** шаблон приложения.</span><span class="sxs-lookup"><span data-stu-id="ca682-115">Then, select the **WPF App (.NET Framework)** app template.</span></span> <span data-ttu-id="ca682-116">Введите имя, а затем выберите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ca682-116">Enter a name, and then select **OK**.</span></span>

   <span data-ttu-id="ca682-117">Visual Studio создает проект, и *MainWindow.xaml* откроется в конструкторе.</span><span class="sxs-lookup"><span data-stu-id="ca682-117">Visual Studio creates the project, and *MainWindow.xaml* opens in the designer.</span></span>

3. <span data-ttu-id="ca682-118">Тип `<InkCanvas/>` между `<Grid>` теги.</span><span class="sxs-lookup"><span data-stu-id="ca682-118">Type `<InkCanvas/>` between the `<Grid>` tags.</span></span>

   ![Конструктор XAML с тегом InkCanvas](./media/getting-started-with-ink/inkcanvas-xaml.png)

4. <span data-ttu-id="ca682-120">Нажмите клавишу **F5** для запуска приложения в отладчике.</span><span class="sxs-lookup"><span data-stu-id="ca682-120">Press **F5** to launch your application in the debugger.</span></span>

5. <span data-ttu-id="ca682-121">С помощью пера или мышь, писать **Здравствуй, мир** в окне.</span><span class="sxs-lookup"><span data-stu-id="ca682-121">Using a stylus or mouse, write **hello world** in the window.</span></span>

<span data-ttu-id="ca682-122">Вы написали рукописный эквивалент приложения на «hello world» с помощью всего 12 клавиш!</span><span class="sxs-lookup"><span data-stu-id="ca682-122">You've written the ink equivalent of a "hello world" application with only 12 keystrokes!</span></span>

### <a name="spice-up-your-app"></a><span data-ttu-id="ca682-123">Оживить приложения</span><span class="sxs-lookup"><span data-stu-id="ca682-123">Spice Up Your App</span></span>

<span data-ttu-id="ca682-124">Рассмотрим преимущества некоторых функций WPF.</span><span class="sxs-lookup"><span data-stu-id="ca682-124">Let’s take advantage of some features of the WPF.</span></span> <span data-ttu-id="ca682-125">Замените весь код между открывающим и закрывающим \<окна > теги, используя следующую разметку:</span><span class="sxs-lookup"><span data-stu-id="ca682-125">Replace everything between the opening and closing \<Window> tags with the following markup:</span></span>

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

<span data-ttu-id="ca682-126">Этот XAML создает градиентный фон поверхности рукописного ввода.</span><span class="sxs-lookup"><span data-stu-id="ca682-126">This XAML creates a gradient brush background on your inking surface.</span></span>

![Цвета градиента на рукописный ввод поверхности в приложении WPF](./media/getting-started-with-ink/gradient-colors.png)

### <a name="add-some-code-behind-the-xaml"></a><span data-ttu-id="ca682-128">Добавление кода программной части XAML</span><span class="sxs-lookup"><span data-stu-id="ca682-128">Add Some Code Behind the XAML</span></span>

<span data-ttu-id="ca682-129">Хотя XAML позволяет очень легко разрабатывать пользовательский интерфейс, любой реальных приложений необходимо добавить код для обработки событий.</span><span class="sxs-lookup"><span data-stu-id="ca682-129">While XAML makes it very easy to design the user interface, any real-world application needs to add code to handle events.</span></span> <span data-ttu-id="ca682-130">Ниже приведен простой пример увеличения рукописный ввод в ответ на щелчок правой кнопкой мыши.</span><span class="sxs-lookup"><span data-stu-id="ca682-130">Here is a simple example that zooms in on the ink in response to a right-click from a mouse.</span></span>

1. <span data-ttu-id="ca682-131">Задайте `MouseRightButtonUp` обработчика в вашей XAML:</span><span class="sxs-lookup"><span data-stu-id="ca682-131">Set the `MouseRightButtonUp` handler in your XAML:</span></span>

   [!code-xaml[DigitalInkTopics#3](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#3)]

1. <span data-ttu-id="ca682-132">В **обозревателе решений**, разверните файл MainWindow.xaml и откройте файл с выделенным кодом (MainWindow.xaml.cs или MainWindow.xaml.vb).</span><span class="sxs-lookup"><span data-stu-id="ca682-132">In **Solution Explorer**, expand MainWindow.xaml and open the code-behind file (MainWindow.xaml.cs or MainWindow.xaml.vb).</span></span> <span data-ttu-id="ca682-133">Добавьте следующий код обработчика событий:</span><span class="sxs-lookup"><span data-stu-id="ca682-133">Add the following event handler code:</span></span>

   [!code-csharp[DigitalInkTopics#4](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml.cs#4)]
   [!code-vb[DigitalInkTopics#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window2.xaml.vb#4)]

1. <span data-ttu-id="ca682-134">Запустите приложение.</span><span class="sxs-lookup"><span data-stu-id="ca682-134">Run the application.</span></span> <span data-ttu-id="ca682-135">Добавьте рукописные и щелкните правой кнопкой мыши, с помощью мыши или эквивалента нажатие и удерживание с помощью пера.</span><span class="sxs-lookup"><span data-stu-id="ca682-135">Add some ink, and then right-click with the mouse or perform a press-and-hold equivalent with a stylus.</span></span>

   <span data-ttu-id="ca682-136">Отображение увеличивает каждый раз, когда щелчком правой кнопки мыши.</span><span class="sxs-lookup"><span data-stu-id="ca682-136">The display zooms in each time you click with the right mouse button.</span></span>

### <a name="use-procedural-code-instead-of-xaml"></a><span data-ttu-id="ca682-137">Используйте процедурный код вместо XAML</span><span class="sxs-lookup"><span data-stu-id="ca682-137">Use Procedural Code Instead of XAML</span></span>

<span data-ttu-id="ca682-138">От процедурного кода доступны все возможности WPF.</span><span class="sxs-lookup"><span data-stu-id="ca682-138">You can access all WPF features from procedural code.</span></span> <span data-ttu-id="ca682-139">Выполните следующие действия, чтобы создать приложение «Hello Ink World» для WPF, не использующего любого XAML.</span><span class="sxs-lookup"><span data-stu-id="ca682-139">Follow these steps to create a "Hello Ink World" application for WPF that doesn’t use any XAML at all.</span></span>

1. <span data-ttu-id="ca682-140">Создайте новый проект консольного приложения в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ca682-140">Create a new console application project in Visual Studio.</span></span>

   <span data-ttu-id="ca682-141">В **новый проект** диалоговом окне разверните **установленные** > **Visual C#** или **Visual Basic**  >   **Windows Desktop** категории.</span><span class="sxs-lookup"><span data-stu-id="ca682-141">In the **New Project** dialog, expand the **Installed** > **Visual C#** or **Visual Basic** > **Windows Desktop** category.</span></span> <span data-ttu-id="ca682-142">Выберите **консольное приложение (.NET Framework)** шаблон приложения.</span><span class="sxs-lookup"><span data-stu-id="ca682-142">Then, select the **Console App (.NET Framework)** app template.</span></span> <span data-ttu-id="ca682-143">Введите имя, а затем выберите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ca682-143">Enter a name, and then select **OK**.</span></span>

1. <span data-ttu-id="ca682-144">Вставьте следующий код в файле Program.cs или Program.vb:</span><span class="sxs-lookup"><span data-stu-id="ca682-144">Paste the following code into the Program.cs or Program.vb file:</span></span>

   [!code-csharp[InkCanvasConsoleApp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasConsoleApp/CSharp/Program.cs#1)]
   [!code-vb[InkCanvasConsoleApp#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/InkCanvasConsoleApp/VisualBasic/Module1.vb#1)]

1. <span data-ttu-id="ca682-145">Добавьте ссылки на сборки PresentationCore, PresentationFramework и WindowsBase, щелкнув правой кнопкой мыши **ссылки** в **обозревателе решений** и выбрав **добавить ссылку на**.</span><span class="sxs-lookup"><span data-stu-id="ca682-145">Add references to the PresentationCore, PresentationFramework, and WindowsBase assemblies by right-clicking on **References** in **Solution Explorer** and choosing **Add Reference**.</span></span>

   ![Диспетчер ссылок, показывающий PresentationCore и PresentationFramework](./media/getting-started-with-ink/references.png)

1. <span data-ttu-id="ca682-147">Постройте приложение, нажав клавишу **F5**.</span><span class="sxs-lookup"><span data-stu-id="ca682-147">Build the application by pressing **F5**.</span></span>

## <a name="see-also"></a><span data-ttu-id="ca682-148">См. также</span><span class="sxs-lookup"><span data-stu-id="ca682-148">See also</span></span>

- [<span data-ttu-id="ca682-149">Рукописный ввод</span><span class="sxs-lookup"><span data-stu-id="ca682-149">Digital Ink</span></span>](digital-ink.md)
- [<span data-ttu-id="ca682-150">Сбор рукописных данных</span><span class="sxs-lookup"><span data-stu-id="ca682-150">Collecting Ink</span></span>](collecting-ink.md)
- [<span data-ttu-id="ca682-151">Распознавание рукописного ввода</span><span class="sxs-lookup"><span data-stu-id="ca682-151">Handwriting Recognition</span></span>](handwriting-recognition.md)
- [<span data-ttu-id="ca682-152">Хранение рукописных данных</span><span class="sxs-lookup"><span data-stu-id="ca682-152">Storing Ink</span></span>](storing-ink.md)
