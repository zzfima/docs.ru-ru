---
title: Пошаговое руководство. Размещение содержимого Direct3D9 в WPF
ms.date: 03/30/2017
helpviewer_keywords:
- Direct3D9 [WPF interoperability], hosting Direct3D9 content
- WPF [WPF], hosting Direct3D9 content
ms.assetid: 60983736-0ab5-42cc-8b16-e9fbde261a43
ms.openlocfilehash: c8bee03cc3a72e1938cca182d59818f9bc2eabc4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54626092"
---
# <a name="walkthrough-hosting-direct3d9-content-in-wpf"></a><span data-ttu-id="368fa-102">Пошаговое руководство. Размещение содержимого Direct3D9 в WPF</span><span class="sxs-lookup"><span data-stu-id="368fa-102">Walkthrough: Hosting Direct3D9 Content in WPF</span></span>
<span data-ttu-id="368fa-103">В этом пошаговом руководстве показано, как размещение содержимого Direct3D9 в приложении Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="368fa-103">This walkthrough shows how to host Direct3D9 content in a Windows Presentation Foundation (WPF) application.</span></span>  
  
 <span data-ttu-id="368fa-104">В руководстве выполняются следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="368fa-104">In this walkthrough, you perform the following tasks:</span></span>  
  
-   <span data-ttu-id="368fa-105">Создание проекта WPF для размещения содержимого Direct3D9.</span><span class="sxs-lookup"><span data-stu-id="368fa-105">Create a WPF project to host the Direct3D9 content.</span></span>  
  
-   <span data-ttu-id="368fa-106">Импорт содержимого Direct3D9.</span><span class="sxs-lookup"><span data-stu-id="368fa-106">Import the Direct3D9 content.</span></span>  
  
-   <span data-ttu-id="368fa-107">Отображение содержимого Direct3D9 с помощью <xref:System.Windows.Interop.D3DImage> класса.</span><span class="sxs-lookup"><span data-stu-id="368fa-107">Display the Direct3D9 content by using the <xref:System.Windows.Interop.D3DImage> class.</span></span>  
  
 <span data-ttu-id="368fa-108">Когда вы закончите, будет известно о размещении содержимого Direct3D9 в WPF-приложение.</span><span class="sxs-lookup"><span data-stu-id="368fa-108">When you are finished, you will know how to host Direct3D9 content in a WPF application.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="368fa-109">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="368fa-109">Prerequisites</span></span>  
 <span data-ttu-id="368fa-110">Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.</span><span class="sxs-lookup"><span data-stu-id="368fa-110">You need the following components to complete this walkthrough:</span></span>  
  
-   <span data-ttu-id="368fa-111">Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="368fa-111">Visual Studio.</span></span>  
  
-   <span data-ttu-id="368fa-112">DirectX SDK, 9 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="368fa-112">DirectX SDK 9 or later.</span></span>  
  
-   <span data-ttu-id="368fa-113">Библиотеку DLL, содержащую содержимого Direct3D9 в WPF-совместимом формате.</span><span class="sxs-lookup"><span data-stu-id="368fa-113">A DLL that contains Direct3D9 content in a WPF-compatible format.</span></span> <span data-ttu-id="368fa-114">Дополнительные сведения см. в разделе [взаимодействие WPF и Direct3D9](../../../../docs/framework/wpf/advanced/wpf-and-direct3d9-interoperation.md) и [Пошаговое руководство: Создание содержимого Direct3D9 для размещения в WPF](../../../../docs/framework/wpf/advanced/walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="368fa-114">For more information, see [WPF and Direct3D9 Interoperation](../../../../docs/framework/wpf/advanced/wpf-and-direct3d9-interoperation.md) and [Walkthrough: Creating Direct3D9 Content for Hosting in WPF](../../../../docs/framework/wpf/advanced/walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md).</span></span>  
  
## <a name="creating-the-wpf-project"></a><span data-ttu-id="368fa-115">Создание проекта WPF</span><span class="sxs-lookup"><span data-stu-id="368fa-115">Creating the WPF Project</span></span>  
 <span data-ttu-id="368fa-116">Первым шагом является создание проекта приложения WPF.</span><span class="sxs-lookup"><span data-stu-id="368fa-116">The first step is to create the project for the WPF application.</span></span>  
  
#### <a name="to-create-the-wpf-project"></a><span data-ttu-id="368fa-117">Создание проекта WPF</span><span class="sxs-lookup"><span data-stu-id="368fa-117">To create the WPF project</span></span>  
  
-   <span data-ttu-id="368fa-118">Создание нового проекта приложения WPF в Visual C# с именем `D3DHost`.</span><span class="sxs-lookup"><span data-stu-id="368fa-118">Create a new WPF Application project in Visual C# named `D3DHost`.</span></span> <span data-ttu-id="368fa-119">Дополнительные сведения см. в разделе [Как Создание нового проекта приложения WPF](https://msdn.microsoft.com/library/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).</span><span class="sxs-lookup"><span data-stu-id="368fa-119">For more information, see [How to: Create a New WPF Application Project](https://msdn.microsoft.com/library/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).</span></span>  
  
     <span data-ttu-id="368fa-120">Файл MainWindow.xaml откроется в [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="368fa-120">MainWindow.xaml opens in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>  
  
## <a name="importing-the-direct3d9-content"></a><span data-ttu-id="368fa-121">Импорт содержимого Direct3D9</span><span class="sxs-lookup"><span data-stu-id="368fa-121">Importing the Direct3D9 Content</span></span>  
 <span data-ttu-id="368fa-122">Импорт содержимого Direct3D9 из неуправляемой библиотеки DLL с помощью `DllImport` атрибута.</span><span class="sxs-lookup"><span data-stu-id="368fa-122">You import the Direct3D9 content from an unmanaged DLL by using the `DllImport` attribute.</span></span>  
  
#### <a name="to-import-direct3d9-content"></a><span data-ttu-id="368fa-123">Для импорта содержимого Direct3D9</span><span class="sxs-lookup"><span data-stu-id="368fa-123">To import Direct3D9 content</span></span>  
  
1.  <span data-ttu-id="368fa-124">Откройте файл MainWindow.xaml.cs в редакторе кода.</span><span class="sxs-lookup"><span data-stu-id="368fa-124">Open MainWindow.xaml.cs in the Code Editor.</span></span>  
  
2.  <span data-ttu-id="368fa-125">Замените автоматически созданный код следующим кодом.</span><span class="sxs-lookup"><span data-stu-id="368fa-125">Replace the automatically generated code with the following code.</span></span>  
  
     [!code-csharp[System.Windows.Interop.D3DImage#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/CS/window1.xaml.cs#1)]  
  
## <a name="hosting-the-direct3d9-content"></a><span data-ttu-id="368fa-126">Размещение содержимого Direct3D9</span><span class="sxs-lookup"><span data-stu-id="368fa-126">Hosting the Direct3D9 Content</span></span>  
 <span data-ttu-id="368fa-127">Наконец, используйте <xref:System.Windows.Interop.D3DImage> класса для размещения содержимого Direct3D9.</span><span class="sxs-lookup"><span data-stu-id="368fa-127">Finally, use the <xref:System.Windows.Interop.D3DImage> class to host the Direct3D9 content.</span></span>  
  
#### <a name="to-host-the-direct3d9-content"></a><span data-ttu-id="368fa-128">Для размещения содержимого Direct3D9</span><span class="sxs-lookup"><span data-stu-id="368fa-128">To host the Direct3D9 content</span></span>  
  
1.  <span data-ttu-id="368fa-129">В файле MainWindow.xaml замените автоматически созданный XAML следующий XAML.</span><span class="sxs-lookup"><span data-stu-id="368fa-129">In MainWindow.xaml, replace the automatically generated XAML with the following XAML.</span></span>  
  
     [!code-xaml[System.Windows.Interop.D3DImage#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/CS/window1.xaml#10)]  
  
2.  <span data-ttu-id="368fa-130">Выполните построение проекта.</span><span class="sxs-lookup"><span data-stu-id="368fa-130">Build the project.</span></span>  
  
3.  <span data-ttu-id="368fa-131">Скопируйте библиотеку DLL, содержащую содержимого Direct3D9 в папку bin/Debug.</span><span class="sxs-lookup"><span data-stu-id="368fa-131">Copy the DLL that contains the Direct3D9 content to the bin/Debug folder.</span></span>  
  
4.  <span data-ttu-id="368fa-132">Нажмите клавишу F5, чтобы запустить проект.</span><span class="sxs-lookup"><span data-stu-id="368fa-132">Press F5 to run the project.</span></span>  
  
     <span data-ttu-id="368fa-133">Содержимое Direct3D9 в WPF-приложении.</span><span class="sxs-lookup"><span data-stu-id="368fa-133">The Direct3D9 content appears within the WPF application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="368fa-134">См. также</span><span class="sxs-lookup"><span data-stu-id="368fa-134">See also</span></span>
- <xref:System.Windows.Interop.D3DImage>
- [<span data-ttu-id="368fa-135">Вопросы производительности, связанные с взаимодействием Direct3D9 и WPF</span><span class="sxs-lookup"><span data-stu-id="368fa-135">Performance Considerations for Direct3D9 and WPF Interoperability</span></span>](../../../../docs/framework/wpf/advanced/performance-considerations-for-direct3d9-and-wpf-interoperability.md)
