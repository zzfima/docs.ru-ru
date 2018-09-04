---
title: Практическое руководство. Добавление в WPF-приложение экрана-заставки
ms.date: 08/18/2018
helpviewer_keywords:
- WPF [WPF], splash screen
- startup window [WPF]
- SplashScreen class [WPF]
- splash screen [WPF]
ms.assetid: d70a25c4-5fb9-4c27-b01d-b1b8ef39b3fd
ms.openlocfilehash: 46efa041736870c5c0f08baa321ef0dc53cacc0d
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43502758"
---
# <a name="how-to-add-a-splash-screen-to-a-wpf-application"></a><span data-ttu-id="01f32-102">Практическое руководство. Добавление в WPF-приложение экрана-заставки</span><span class="sxs-lookup"><span data-stu-id="01f32-102">How to: Add a Splash Screen to a WPF Application</span></span>

<span data-ttu-id="01f32-103">В этом разделе показано, как добавить окно запуска, или *экран-заставка*, приложение Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="01f32-103">This topic shows how to add a startup window, or *splash screen*, to a Windows Presentation Foundation (WPF) application.</span></span>

## <a name="to-add-an-existing-image-as-a-splash-screen"></a><span data-ttu-id="01f32-104">Чтобы добавить существующий образ в качестве экрана-заставки</span><span class="sxs-lookup"><span data-stu-id="01f32-104">To add an existing image as a splash screen</span></span>

1.  <span data-ttu-id="01f32-105">Создайте или найдите изображение, которое будет использоваться для экрана-заставки.</span><span class="sxs-lookup"><span data-stu-id="01f32-105">Create or find an image that you want to use for the splash screen.</span></span> <span data-ttu-id="01f32-106">Можно использовать любой формат изображения, который поддерживается в Windows Imaging Component (WIC).</span><span class="sxs-lookup"><span data-stu-id="01f32-106">You can use any image format that is supported by the Windows Imaging Component (WIC).</span></span> <span data-ttu-id="01f32-107">Например можно использовать формат BMP, GIF, JPEG, PNG и TIFF.</span><span class="sxs-lookup"><span data-stu-id="01f32-107">For example, you can use the BMP, GIF, JPEG, PNG, or TIFF format.</span></span>

2.  <span data-ttu-id="01f32-108">Добавьте файл изображения в проект приложения WPF.</span><span class="sxs-lookup"><span data-stu-id="01f32-108">Add the image file to the WPF Application project.</span></span>

3.  <span data-ttu-id="01f32-109">В **обозревателе решений**, выберите изображение.</span><span class="sxs-lookup"><span data-stu-id="01f32-109">In **Solution Explorer**, select the image.</span></span>

4.  <span data-ttu-id="01f32-110">В окне «Свойства» щелкните стрелку раскрывающегося списка для **действие при построении** свойство.</span><span class="sxs-lookup"><span data-stu-id="01f32-110">In the Properties window, click the drop-down arrow for the **Build Action** property.</span></span>

5.  <span data-ttu-id="01f32-111">Выберите **экран-заставка** из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="01f32-111">Select **SplashScreen** from the drop-down list.</span></span>

6.  <span data-ttu-id="01f32-112">Нажмите клавишу **F5**, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="01f32-112">Press **F5** to build and run the application.</span></span>

     <span data-ttu-id="01f32-113">Изображение экрана-заставки отображается в центре экрана, исчезнет, когда появится окно основного приложения.</span><span class="sxs-lookup"><span data-stu-id="01f32-113">The splash screen image appears in the center of the screen, and then fades when the main application window appears.</span></span>

## <a name="to-exclude-the-splash-screen-from-build"></a><span data-ttu-id="01f32-114">Чтобы исключить из сборки на экране-заставке</span><span class="sxs-lookup"><span data-stu-id="01f32-114">To exclude the splash screen from build</span></span>

1.  <span data-ttu-id="01f32-115">В **обозревателе решений**, выберите изображение экрана-заставки.</span><span class="sxs-lookup"><span data-stu-id="01f32-115">In **Solution Explorer**, select the splash screen image.</span></span>

2.  <span data-ttu-id="01f32-116">В **свойства** окне **действие при построении** для **None**.</span><span class="sxs-lookup"><span data-stu-id="01f32-116">In the **Properties** window, set the **Build Action** to **None**.</span></span>

## <a name="to-remove-the-splash-screen-from-an-application"></a><span data-ttu-id="01f32-117">Для удаления заставки из приложения</span><span class="sxs-lookup"><span data-stu-id="01f32-117">To remove the splash screen from an application</span></span>

<span data-ttu-id="01f32-118">В **обозревателе решений**, удалить изображение экрана-заставки.</span><span class="sxs-lookup"><span data-stu-id="01f32-118">In **Solution Explorer**, delete the splash screen image.</span></span>

## <a name="see-also"></a><span data-ttu-id="01f32-119">См. также</span><span class="sxs-lookup"><span data-stu-id="01f32-119">See Also</span></span>

- <xref:System.Windows.SplashScreen>
- <span data-ttu-id="01f32-120">[Практическое: Добавление существующих элементов в проект](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/9f4t9t92(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="01f32-120">[How to: Add Existing Items to a Project](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/9f4t9t92(v=vs.100))</span></span>
