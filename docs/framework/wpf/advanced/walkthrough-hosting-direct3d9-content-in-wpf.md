---
title: Пошаговое руководство. Размещение содержимого Direct3D9 в WPF
ms.date: 03/30/2017
helpviewer_keywords:
- Direct3D9 [WPF interoperability], hosting Direct3D9 content
- WPF [WPF], hosting Direct3D9 content
ms.assetid: 60983736-0ab5-42cc-8b16-e9fbde261a43
ms.openlocfilehash: 2c31c044aa50a74255a61da1675037ab3d09f615
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053455"
---
# <a name="walkthrough-hosting-direct3d9-content-in-wpf"></a><span data-ttu-id="b9d23-102">Пошаговое руководство. Размещение содержимого Direct3D9 в WPF</span><span class="sxs-lookup"><span data-stu-id="b9d23-102">Walkthrough: Hosting Direct3D9 Content in WPF</span></span>

<span data-ttu-id="b9d23-103">В этом пошаговом руководстве показано, как разместить содержимое Direct3D9 в приложении Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="b9d23-103">This walkthrough shows how to host Direct3D9 content in a Windows Presentation Foundation (WPF) application.</span></span>

<span data-ttu-id="b9d23-104">В руководстве выполняются следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="b9d23-104">In this walkthrough, you perform the following tasks:</span></span>

- <span data-ttu-id="b9d23-105">Создайте проект WPF для размещения содержимого Direct3D9.</span><span class="sxs-lookup"><span data-stu-id="b9d23-105">Create a WPF project to host the Direct3D9 content.</span></span>

- <span data-ttu-id="b9d23-106">Импортируйте содержимое Direct3D9.</span><span class="sxs-lookup"><span data-stu-id="b9d23-106">Import the Direct3D9 content.</span></span>

- <span data-ttu-id="b9d23-107">Отображение содержимого Direct3D9 с помощью <xref:System.Windows.Interop.D3DImage> класса.</span><span class="sxs-lookup"><span data-stu-id="b9d23-107">Display the Direct3D9 content by using the <xref:System.Windows.Interop.D3DImage> class.</span></span>

 <span data-ttu-id="b9d23-108">По завершении вы узнаете, как разместить содержимое Direct3D9 в приложении WPF.</span><span class="sxs-lookup"><span data-stu-id="b9d23-108">When you are finished, you will know how to host Direct3D9 content in a WPF application.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b9d23-109">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="b9d23-109">Prerequisites</span></span>

<span data-ttu-id="b9d23-110">Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.</span><span class="sxs-lookup"><span data-stu-id="b9d23-110">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="b9d23-111">Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b9d23-111">Visual Studio.</span></span>

- <span data-ttu-id="b9d23-112">Пакет SDK для DirectX 9 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="b9d23-112">DirectX SDK 9 or later.</span></span>

- <span data-ttu-id="b9d23-113">Библиотека DLL, содержащая содержимое Direct3D9 в формате, совместимом с WPF.</span><span class="sxs-lookup"><span data-stu-id="b9d23-113">A DLL that contains Direct3D9 content in a WPF-compatible format.</span></span> <span data-ttu-id="b9d23-114">Дополнительные сведения см. в разделе [взаимодействие WPF и Direct3D9](wpf-and-direct3d9-interoperation.md) и [пошаговое руководство. Создание содержимого Direct3D9 для размещения в WPF](walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="b9d23-114">For more information, see [WPF and Direct3D9 Interoperation](wpf-and-direct3d9-interoperation.md) and [Walkthrough: Creating Direct3D9 Content for Hosting in WPF](walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md).</span></span>

## <a name="creating-the-wpf-project"></a><span data-ttu-id="b9d23-115">Создание проекта WPF</span><span class="sxs-lookup"><span data-stu-id="b9d23-115">Creating the WPF Project</span></span>

<span data-ttu-id="b9d23-116">Первым шагом является создание проекта для приложения WPF.</span><span class="sxs-lookup"><span data-stu-id="b9d23-116">The first step is to create the project for the WPF application.</span></span>

### <a name="to-create-the-wpf-project"></a><span data-ttu-id="b9d23-117">Создание проекта WPF</span><span class="sxs-lookup"><span data-stu-id="b9d23-117">To create the WPF project</span></span>

<span data-ttu-id="b9d23-118">Создайте новый проект приложения WPF в Visual C# с именем `D3DHost`.</span><span class="sxs-lookup"><span data-stu-id="b9d23-118">Create a new WPF Application project in Visual C# named `D3DHost`.</span></span> <span data-ttu-id="b9d23-119">Дополнительные сведения см. в разделе [Пошаговое руководство: Мое первое приложение](../getting-started/walkthrough-my-first-wpf-desktop-application.md)WPF для настольных систем.</span><span class="sxs-lookup"><span data-stu-id="b9d23-119">For more information, see [Walkthrough: My first WPF desktop application](../getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span>

<span data-ttu-id="b9d23-120">Файл MainWindow. XAML откроется в [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b9d23-120">MainWindow.xaml opens in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>

## <a name="importing-the-direct3d9-content"></a><span data-ttu-id="b9d23-121">Импорт содержимого Direct3D9</span><span class="sxs-lookup"><span data-stu-id="b9d23-121">Importing the Direct3D9 Content</span></span>

<span data-ttu-id="b9d23-122">Содержимое Direct3D9 импортируется из неуправляемой библиотеки DLL с помощью `DllImport` атрибута.</span><span class="sxs-lookup"><span data-stu-id="b9d23-122">You import the Direct3D9 content from an unmanaged DLL by using the `DllImport` attribute.</span></span>

### <a name="to-import-direct3d9-content"></a><span data-ttu-id="b9d23-123">Импорт содержимого Direct3D9</span><span class="sxs-lookup"><span data-stu-id="b9d23-123">To import Direct3D9 content</span></span>

1. <span data-ttu-id="b9d23-124">Откройте MainWindow.xaml.cs в редакторе кода.</span><span class="sxs-lookup"><span data-stu-id="b9d23-124">Open MainWindow.xaml.cs in the Code Editor.</span></span>

2. <span data-ttu-id="b9d23-125">Замените автоматически созданный код следующим кодом.</span><span class="sxs-lookup"><span data-stu-id="b9d23-125">Replace the automatically generated code with the following code.</span></span>

    [!code-csharp[System.Windows.Interop.D3DImage#1](~/samples/snippets/csharp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/CS/window1.xaml.cs#1)]

## <a name="hosting-the-direct3d9-content"></a><span data-ttu-id="b9d23-126">Размещение содержимого Direct3D9</span><span class="sxs-lookup"><span data-stu-id="b9d23-126">Hosting the Direct3D9 Content</span></span>

<span data-ttu-id="b9d23-127">Наконец, используйте <xref:System.Windows.Interop.D3DImage> класс для размещения содержимого Direct3D9.</span><span class="sxs-lookup"><span data-stu-id="b9d23-127">Finally, use the <xref:System.Windows.Interop.D3DImage> class to host the Direct3D9 content.</span></span>

### <a name="to-host-the-direct3d9-content"></a><span data-ttu-id="b9d23-128">Размещение содержимого Direct3D9</span><span class="sxs-lookup"><span data-stu-id="b9d23-128">To host the Direct3D9 content</span></span>

1. <span data-ttu-id="b9d23-129">В файле MainWindow. XAML замените автоматически созданный код XAML следующим кодом XAML.</span><span class="sxs-lookup"><span data-stu-id="b9d23-129">In MainWindow.xaml, replace the automatically generated XAML with the following XAML.</span></span>

    [!code-xaml[System.Windows.Interop.D3DImage#10](~/samples/snippets/csharp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/CS/window1.xaml#10)]

2. <span data-ttu-id="b9d23-130">Выполните построение проекта.</span><span class="sxs-lookup"><span data-stu-id="b9d23-130">Build the project.</span></span>

3. <span data-ttu-id="b9d23-131">Скопируйте библиотеку DLL, содержащую содержимое Direct3D9, в папку bin/Debug.</span><span class="sxs-lookup"><span data-stu-id="b9d23-131">Copy the DLL that contains the Direct3D9 content to the bin/Debug folder.</span></span>

4. <span data-ttu-id="b9d23-132">Нажмите клавишу F5, чтобы запустить проект.</span><span class="sxs-lookup"><span data-stu-id="b9d23-132">Press F5 to run the project.</span></span>

    <span data-ttu-id="b9d23-133">Содержимое Direct3D9 отображается в приложении WPF.</span><span class="sxs-lookup"><span data-stu-id="b9d23-133">The Direct3D9 content appears within the WPF application.</span></span>

## <a name="see-also"></a><span data-ttu-id="b9d23-134">См. также</span><span class="sxs-lookup"><span data-stu-id="b9d23-134">See also</span></span>

- <xref:System.Windows.Interop.D3DImage>
- [<span data-ttu-id="b9d23-135">Вопросы производительности, связанные с взаимодействием Direct3D9 и WPF</span><span class="sxs-lookup"><span data-stu-id="b9d23-135">Performance Considerations for Direct3D9 and WPF Interoperability</span></span>](performance-considerations-for-direct3d9-and-wpf-interoperability.md)
