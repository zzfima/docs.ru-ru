---
title: Добавление экрана-заставки
ms.date: 08/18/2018
helpviewer_keywords:
- WPF [WPF], splash screen
- startup window [WPF]
- SplashScreen class [WPF]
- splash screen [WPF]
ms.assetid: d70a25c4-5fb9-4c27-b01d-b1b8ef39b3fd
ms.openlocfilehash: 39f53e21c40f036c65894b4f275cd5fb414999be
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740447"
---
# <a name="how-to-add-a-splash-screen-to-a-wpf-application"></a><span data-ttu-id="84952-102">Практическое руководство. Добавление в WPF-приложение экрана-заставки</span><span class="sxs-lookup"><span data-stu-id="84952-102">How to: Add a Splash Screen to a WPF Application</span></span>

<span data-ttu-id="84952-103">В этом разделе показано, как добавить окно запуска или *экран-заставку*в приложение Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="84952-103">This topic shows how to add a startup window, or *splash screen*, to a Windows Presentation Foundation (WPF) application.</span></span>

## <a name="to-add-an-existing-image-as-a-splash-screen"></a><span data-ttu-id="84952-104">Добавление существующего изображения в качестве экрана-заставки</span><span class="sxs-lookup"><span data-stu-id="84952-104">To add an existing image as a splash screen</span></span>

1. <span data-ttu-id="84952-105">Создайте или найдите изображение, которое вы хотите использовать для экрана-заставки.</span><span class="sxs-lookup"><span data-stu-id="84952-105">Create or find an image that you want to use for the splash screen.</span></span> <span data-ttu-id="84952-106">Можно использовать любой формат изображения, поддерживаемый компонентом Windows Imaging Component (WIC).</span><span class="sxs-lookup"><span data-stu-id="84952-106">You can use any image format that is supported by the Windows Imaging Component (WIC).</span></span> <span data-ttu-id="84952-107">Например, можно использовать формат BMP, GIF, JPEG, PNG или TIFF.</span><span class="sxs-lookup"><span data-stu-id="84952-107">For example, you can use the BMP, GIF, JPEG, PNG, or TIFF format.</span></span>

2. <span data-ttu-id="84952-108">Добавьте файл изображения в проект приложения WPF.</span><span class="sxs-lookup"><span data-stu-id="84952-108">Add the image file to the WPF Application project.</span></span>

3. <span data-ttu-id="84952-109">В **Обозреватель решений**выберите изображение.</span><span class="sxs-lookup"><span data-stu-id="84952-109">In **Solution Explorer**, select the image.</span></span>

4. <span data-ttu-id="84952-110">В окно свойств щелкните стрелку раскрывающегося списка для свойства **действие сборки** .</span><span class="sxs-lookup"><span data-stu-id="84952-110">In the Properties window, click the drop-down arrow for the **Build Action** property.</span></span>

5. <span data-ttu-id="84952-111">Выберите **SplashScreen** из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="84952-111">Select **SplashScreen** from the drop-down list.</span></span>

6. <span data-ttu-id="84952-112">Нажмите клавишу **F5**, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="84952-112">Press **F5** to build and run the application.</span></span>

     <span data-ttu-id="84952-113">Изображение экрана-заставки отображается в центре экрана, а затем исчезает при появлении главного окна приложения.</span><span class="sxs-lookup"><span data-stu-id="84952-113">The splash screen image appears in the center of the screen, and then fades when the main application window appears.</span></span>

## <a name="to-exclude-the-splash-screen-from-build"></a><span data-ttu-id="84952-114">Исключение экрана-заставки из сборки</span><span class="sxs-lookup"><span data-stu-id="84952-114">To exclude the splash screen from build</span></span>

1. <span data-ttu-id="84952-115">В **Обозреватель решений**выберите изображение экрана-заставки.</span><span class="sxs-lookup"><span data-stu-id="84952-115">In **Solution Explorer**, select the splash screen image.</span></span>

2. <span data-ttu-id="84952-116">В окне **Свойства** задайте для **действия сборки** значение **нет**.</span><span class="sxs-lookup"><span data-stu-id="84952-116">In the **Properties** window, set the **Build Action** to **None**.</span></span>

## <a name="to-remove-the-splash-screen-from-an-application"></a><span data-ttu-id="84952-117">Удаление экрана-заставки из приложения</span><span class="sxs-lookup"><span data-stu-id="84952-117">To remove the splash screen from an application</span></span>

<span data-ttu-id="84952-118">В **Обозреватель решений**удалите изображение экрана-заставки.</span><span class="sxs-lookup"><span data-stu-id="84952-118">In **Solution Explorer**, delete the splash screen image.</span></span>

## <a name="see-also"></a><span data-ttu-id="84952-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="84952-119">See also</span></span>

- <xref:System.Windows.SplashScreen>
- <span data-ttu-id="84952-120">[Как добавить существующие элементы в проект](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/9f4t9t92(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="84952-120">[How to: Add Existing Items to a Project](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/9f4t9t92(v=vs.100))</span></span>
