---
title: "Практическое руководство. Добавление в WPF-приложение экрана-заставки"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WPF [WPF], splash screen
- startup window [WPF]
- SplashScreen class [WPF]
- splash screen [WPF]
ms.assetid: d70a25c4-5fb9-4c27-b01d-b1b8ef39b3fd
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 973f35f6bfa259490a9423bf0b69d676ad968372
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-a-splash-screen-to-a-wpf-application"></a><span data-ttu-id="f720d-102">Практическое руководство. Добавление в WPF-приложение экрана-заставки</span><span class="sxs-lookup"><span data-stu-id="f720d-102">How to: Add a Splash Screen to a WPF Application</span></span>
<span data-ttu-id="f720d-103">В этом разделе показано, как добавить окно запуска, или *экран-заставка*, приложение Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="f720d-103">This topic shows how to add a startup window, or *splash screen*, to a Windows Presentation Foundation (WPF) application.</span></span>  
  
### <a name="to-add-an-existing-image-as-a-splash-screen"></a><span data-ttu-id="f720d-104">Чтобы добавить существующее изображение в качестве экрана-заставки</span><span class="sxs-lookup"><span data-stu-id="f720d-104">To add an existing image as a splash screen</span></span>  
  
1.  <span data-ttu-id="f720d-105">Создать или найти изображение, которое будет использоваться для экрана-заставки.</span><span class="sxs-lookup"><span data-stu-id="f720d-105">Create or find an image that you want to use for the splash screen.</span></span> <span data-ttu-id="f720d-106">Можно использовать любой формат образа, который поддерживается в Windows компонент обработки Изображений.</span><span class="sxs-lookup"><span data-stu-id="f720d-106">You can use any image format that is supported by the Windows Imaging Component (WIC).</span></span> <span data-ttu-id="f720d-107">Например можно использовать формат BMP, GIF, JPEG, PNG и TIFF.</span><span class="sxs-lookup"><span data-stu-id="f720d-107">For example, you can use the BMP, GIF, JPEG, PNG, or TIFF format.</span></span>  
  
2.  <span data-ttu-id="f720d-108">Добавьте файл изображения в проект приложения WPF.</span><span class="sxs-lookup"><span data-stu-id="f720d-108">Add the image file to the WPF Application project.</span></span> <span data-ttu-id="f720d-109">Дополнительные сведения см. в разделе [NIB: Практическое: Добавление существующих элементов в проект](http://msdn.microsoft.com/en-us/15f4cfb7-78ab-457f-9f14-099a25a6a2d3).</span><span class="sxs-lookup"><span data-stu-id="f720d-109">For more information, see [NIB:How to: Add Existing Items to a Project](http://msdn.microsoft.com/en-us/15f4cfb7-78ab-457f-9f14-099a25a6a2d3).</span></span>  
  
3.  <span data-ttu-id="f720d-110">В обозревателе решений выберите изображение.</span><span class="sxs-lookup"><span data-stu-id="f720d-110">In Solution Explorer, select the image.</span></span>  
  
4.  <span data-ttu-id="f720d-111">В окне «Свойства» щелкните стрелку раскрывающегося списка для **действие при построении** свойство.</span><span class="sxs-lookup"><span data-stu-id="f720d-111">In the Properties window, click the drop-down arrow for the **Build Action** property.</span></span>  
  
5.  <span data-ttu-id="f720d-112">Выберите **экран-заставка** из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="f720d-112">Select **SplashScreen** from the drop-down list.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f720d-113">Если вы не видите **экран-заставка** , то проверьте, что вы используете [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)] с пакетом обновления 1 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="f720d-113">If you do not see the **SplashScreen** option, be sure to check that you are using [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)] SP1 or later.</span></span>  
  
6.  <span data-ttu-id="f720d-114">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="f720d-114">Press F5 to build and run the application.</span></span>  
  
     <span data-ttu-id="f720d-115">Изображение экрана-заставки отображается в центре экрана и исчезнет при появлении главного окна приложения.</span><span class="sxs-lookup"><span data-stu-id="f720d-115">The splash screen image appears in the center of the screen, and then fades when the main application window appears.</span></span>  
  
### <a name="to-remove-the-splash-screen-from-an-application"></a><span data-ttu-id="f720d-116">Для удаления экрана-заставки из приложения</span><span class="sxs-lookup"><span data-stu-id="f720d-116">To remove the splash screen from an application</span></span>  
  
1.  <span data-ttu-id="f720d-117">В обозревателе решений выберите изображение экрана-заставки.</span><span class="sxs-lookup"><span data-stu-id="f720d-117">In Solution Explorer, select the splash screen image.</span></span>  
  
2.  <span data-ttu-id="f720d-118">В окне свойств задайте **действие при построении** для **нет**.</span><span class="sxs-lookup"><span data-stu-id="f720d-118">In the Properties window, set the **Build Action** to **None**.</span></span>  
  
### <a name="to-remove-the-splash-screen-from-an-application"></a><span data-ttu-id="f720d-119">Для удаления экрана-заставки из приложения</span><span class="sxs-lookup"><span data-stu-id="f720d-119">To remove the splash screen from an application</span></span>  
  
-   <span data-ttu-id="f720d-120">В обозревателе решений удалите изображение экрана-заставки.</span><span class="sxs-lookup"><span data-stu-id="f720d-120">In Solution Explorer, delete the splash screen image.</span></span>  
  
-   <span data-ttu-id="f720d-121">Изображение экрана-заставки исключите из проекта.</span><span class="sxs-lookup"><span data-stu-id="f720d-121">Exclude the splash screen image from the project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f720d-122">См. также</span><span class="sxs-lookup"><span data-stu-id="f720d-122">See Also</span></span>  
 <xref:System.Windows.SplashScreen>  
 [<span data-ttu-id="f720d-123">NIB: Практическое: Добавление существующих элементов в проект</span><span class="sxs-lookup"><span data-stu-id="f720d-123">NIB:How to: Add Existing Items to a Project</span></span>](http://msdn.microsoft.com/en-us/15f4cfb7-78ab-457f-9f14-099a25a6a2d3)
