---
title: Кроссплатформенная разработка с переносной библиотекой классов
ms.date: 09/17/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- Portable Class Library [.NET Framework]
- targeting multiple platforms
- multiple platforms, targeting
ms.assetid: c31e1663-c164-4e65-b66d-d3aa8750a154
author: mairaw
ms.author: mairaw
ms.openlocfilehash: afaa8e118bb21e5c1e4f1c53b1d0d29ca6bb3bf5
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47172710"
---
# <a name="cross-platform-development-with-the-portable-class-library"></a><span data-ttu-id="c93c0-102">Кроссплатформенная разработка с переносимой библиотекой классов</span><span class="sxs-lookup"><span data-stu-id="c93c0-102">Cross-platform development with the Portable Class Library</span></span>

<span data-ttu-id="c93c0-103">Тип проекта переносимой библиотеки классов в Visual Studio поможет вам быстро и легко создавать кросс платформенные приложения и библиотеки для платформ Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="c93c0-103">The Portable Class Library project type in Visual Studio helps you build cross-platform apps and libraries for Microsoft platforms quickly and easily.</span></span>

[!INCLUDE[standard](../../../includes/pcl-to-standard.md)]

<span data-ttu-id="c93c0-104">Переносимые библиотеки классов уменьшают временные и трудовые затраты на разработку и тестирования кода.</span><span class="sxs-lookup"><span data-stu-id="c93c0-104">Portable class libraries can help you reduce the time and costs of developing and testing code.</span></span> <span data-ttu-id="c93c0-105">Используйте этот тип проекта для написания кода и сборки переносимых сборок .NET Framework, а затем ссылайтесь на них из приложений, предназначенных для нескольких платформ, таких как .NET Framework, iOS или Mac.</span><span class="sxs-lookup"><span data-stu-id="c93c0-105">Use this project type to write and build portable .NET Framework assemblies, and then reference those assemblies from apps that target multiple platforms such as the .NET Framework, iOS, or Mac.</span></span>

<span data-ttu-id="c93c0-106">Даже после создания проекта переносимой библиотеки классов в Visual Studio и начала работы над проектом вы сможете изменить целевые платформы.</span><span class="sxs-lookup"><span data-stu-id="c93c0-106">Even after you create a Portable Class Library project in Visual Studio and start developing it, you can change the target platforms.</span></span> <span data-ttu-id="c93c0-107">Visual Studio компилирует библиотеку с новыми сборками, позволяющий определить изменения, которые необходимо внести в код.</span><span class="sxs-lookup"><span data-stu-id="c93c0-107">Visual Studio compiles your library with the new assemblies, which helps you identify the changes you need to make in your code.</span></span>

## <a name="create-a-portable-class-library-project"></a><span data-ttu-id="c93c0-108">Создание проекта переносимой библиотеки классов</span><span class="sxs-lookup"><span data-stu-id="c93c0-108">Create a Portable Class Library project</span></span>

<span data-ttu-id="c93c0-109">Чтобы создать переносимую библиотеку классов, используйте шаблоном в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c93c0-109">To create a Portable Class Library, use the template provided in Visual Studio.</span></span> <span data-ttu-id="c93c0-110">Создайте новый проект (**файл** > **новый проект**) и в **новый проект** диалоговом окне выберите язык программирования (Visual C# или Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="c93c0-110">Create a new project (**File** > **New Project**), and in the **New Project** dialog box, select your programming language (Visual C# or Visual Basic).</span></span> <span data-ttu-id="c93c0-111">Выберите **библиотека классов (для прежних версий Portable)** шаблона.</span><span class="sxs-lookup"><span data-stu-id="c93c0-111">Then, select the **Class Library (Legacy Portable)** template.</span></span> <span data-ttu-id="c93c0-112">Введите имя проекта и выберите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c93c0-112">Enter a name for your project and choose **OK**.</span></span>

<span data-ttu-id="c93c0-113">**Добавление переносимой библиотеки классов** откроется диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="c93c0-113">The **Add Portable Class Library** dialog box appears.</span></span> <span data-ttu-id="c93c0-114">Выберите два или несколько целевых объектов, а затем нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c93c0-114">Choose two or more targets, and then choose **OK**.</span></span>

![Добавить целевые объекты библиотеке переносных классов в Visual Studio](media/add-portable-class-library.png)

## <a name="change-targets"></a><span data-ttu-id="c93c0-116">Изменить цели</span><span class="sxs-lookup"><span data-stu-id="c93c0-116">Change targets</span></span>

<span data-ttu-id="c93c0-117">Можно изменить целевые платформы из проекта переносимой библиотеки классов, при ее создании или после начала разработки.</span><span class="sxs-lookup"><span data-stu-id="c93c0-117">You can change the target platforms of a portable class library project when you create it or after you’ve started development.</span></span> <span data-ttu-id="c93c0-118">Если вы хотите изменить целевые платформы после создания проекта, в **обозревателе решений**, откройте контекстное меню для проекта переносимой библиотеки классов (не решение) и затем выберите **свойства** .</span><span class="sxs-lookup"><span data-stu-id="c93c0-118">If you want to change the targets after you’ve created your project, in **Solution Explorer**, open the shortcut menu for your Portable Class Library project (not the solution), and then choose **Properties**.</span></span> <span data-ttu-id="c93c0-119">На странице свойств проекта **библиотеки** вкладке отображается платформ, в данный момент нацелен проект.</span><span class="sxs-lookup"><span data-stu-id="c93c0-119">On the project properties page, the **Library** tab shows the platforms that your project currently targets.</span></span>

![Свойства проекта для переносимой библиотеки классов в Visual Studio](media/pcl-project-properties.png)

<span data-ttu-id="c93c0-121">Чтобы добавить или удалить целевые объекты, выберите **изменение** кнопку и затем установите или снимите соответствующие флажки.</span><span class="sxs-lookup"><span data-stu-id="c93c0-121">To add or remove targets, choose the **Change** button, and then select and clear the appropriate check boxes.</span></span>

<span data-ttu-id="c93c0-122">При изменении целевых платформ API-интерфейсы, доступные для разработки проекта, изменятся в соответствии с выбранными платформами.</span><span class="sxs-lookup"><span data-stu-id="c93c0-122">When you change the targets, the APIs that are available to you for developing your project will change to match your selection.</span></span> <span data-ttu-id="c93c0-123">Visual Studio отображает ошибки и предупреждения после изменения целевых платформ.</span><span class="sxs-lookup"><span data-stu-id="c93c0-123">Visual Studio reports the errors and warnings that may occur as a result of the targets changing.</span></span>

<span data-ttu-id="c93c0-124">Если вы хотите оценить переносимость сборки до можно внести изменения в Visual Studio, можно использовать [анализатор переносимости .NET](https://visualstudiogallery.msdn.microsoft.com/1177943e-cfb7-4822-a8a6-e56c7905292b).</span><span class="sxs-lookup"><span data-stu-id="c93c0-124">If you want to evaluate the portability of your assemblies before you make changes in Visual Studio, you can use the [.NET Portability Analyzer](https://visualstudiogallery.msdn.microsoft.com/1177943e-cfb7-4822-a8a6-e56c7905292b).</span></span>

## <a name="supported-types-and-members"></a><span data-ttu-id="c93c0-125">Поддерживаемые типы и члены</span><span class="sxs-lookup"><span data-stu-id="c93c0-125">Supported types and members</span></span>

<span data-ttu-id="c93c0-126">Типы и члены, доступные в проектах переносимой библиотеки классов, ограничены несколькими факторами совместимости:</span><span class="sxs-lookup"><span data-stu-id="c93c0-126">The types and members that are available in Portable Class Library projects are constrained by several compatibility factors:</span></span>

-   <span data-ttu-id="c93c0-127">они должны быть общими для выбранных целевых платформ;</span><span class="sxs-lookup"><span data-stu-id="c93c0-127">They must be shared across the targets you selected.</span></span>

-   <span data-ttu-id="c93c0-128">они должны вести себя аналогичным образом на всех этих платформах;</span><span class="sxs-lookup"><span data-stu-id="c93c0-128">The must behave similarly across those targets.</span></span>

-   <span data-ttu-id="c93c0-129">они не должны быть кандидатами на вывод из употребления;</span><span class="sxs-lookup"><span data-stu-id="c93c0-129">They must not be candidates for deprecation.</span></span>

-   <span data-ttu-id="c93c0-130">они должны иметь смысл в переносимой среде, особенно если вспомогательные члены не являются переносимыми.</span><span class="sxs-lookup"><span data-stu-id="c93c0-130">They must make sense in a portable environment, especially when supporting members are not portable.</span></span>

<span data-ttu-id="c93c0-131">Если член поддерживается в переносимой библиотеке классов и для выбранных целевых платформ, он будет показан в IntelliSense в вашем проекте.</span><span class="sxs-lookup"><span data-stu-id="c93c0-131">If a member is supported in the Portable Class Library and for your selected targets, it will appear in your project in IntelliSense.</span></span> <span data-ttu-id="c93c0-132">Однако помните, что интерфейс API может поддерживаться в переносимой библиотеки классов, но возможность его использования зависит от выбранных целевых платформ.</span><span class="sxs-lookup"><span data-stu-id="c93c0-132">However, remember that an API may be supported in the Portable Class Library, but whether you can use the API depends on the targets you select.</span></span>

## <a name="api-differences-in-the-portable-class-library"></a><span data-ttu-id="c93c0-133">Отличия API в переносимой библиотеке классов</span><span class="sxs-lookup"><span data-stu-id="c93c0-133">API differences in the Portable Class Library</span></span>

<span data-ttu-id="c93c0-134">Для обеспечения совместимости сборок переносимой библиотеки классов на всех поддерживаемых платформах некоторые члены в переносимой библиотеке классов были немного изменены.</span><span class="sxs-lookup"><span data-stu-id="c93c0-134">To make Portable Class Library assemblies compatible across all supported platforms, some members have been slightly changed in the Portable Class Library.</span></span>

## <a name="use-the-portable-class-library"></a><span data-ttu-id="c93c0-135">Использование переносимой библиотеки классов</span><span class="sxs-lookup"><span data-stu-id="c93c0-135">Use the Portable Class Library</span></span>

<span data-ttu-id="c93c0-136">После построения проекта переносимой библиотеки классов просто добавьте ссылку на нее в других проектах.</span><span class="sxs-lookup"><span data-stu-id="c93c0-136">After you build your Portable Class Library project, you just reference it from other projects.</span></span> <span data-ttu-id="c93c0-137">Можно сделать ссылку на проект или на конкретные сборки, содержащие классы, к которым требуется доступ.</span><span class="sxs-lookup"><span data-stu-id="c93c0-137">You can reference either the project or specific assemblies that contain the classes you want to access.</span></span>

<span data-ttu-id="c93c0-138">Для запуска приложения, ссылающегося на сборку переносимой библиотеки классов, на компьютере должны быть установлены требуемые (или более поздние) версии целевых платформ.</span><span class="sxs-lookup"><span data-stu-id="c93c0-138">To run an app that references a Portable Class Library assembly, the required version (or later) of the targeted platforms must be installed on your computer.</span></span> <span data-ttu-id="c93c0-139">Visual Studio содержит все необходимые платформы, поэтому приложение можно запустить без дальнейших изменений на компьютере, который использовался для его разработки.</span><span class="sxs-lookup"><span data-stu-id="c93c0-139">Visual Studio contains all the required frameworks, so you can run the app without further modification on the computer that you used to develop the app.</span></span>

### <a name="deploy-a-universal-windows-app"></a><span data-ttu-id="c93c0-140">Развернуть приложение универсальной Windows</span><span class="sxs-lookup"><span data-stu-id="c93c0-140">Deploy a Universal Windows app</span></span>

<span data-ttu-id="c93c0-141">При создании приложения универсальной Windows, ссылающийся на сборку переносимой библиотеки классов, все необходимые для развертывания приложения уже включено в пакет приложения и никаких дальнейших действий не требуется.</span><span class="sxs-lookup"><span data-stu-id="c93c0-141">When you create a Universal Windows app that references a Portable Class Library assembly, everything you need to deploy the app is included in the app package, and no further steps are required.</span></span>

### <a name="deploy-a-net-framework-app"></a><span data-ttu-id="c93c0-142">Развертывание .NET Framework приложения</span><span class="sxs-lookup"><span data-stu-id="c93c0-142">Deploy a .NET Framework app</span></span>

<span data-ttu-id="c93c0-143">При развертывании приложения .NET Framework, в котором имеется ссылка на сборку переносимой библиотеки классов, необходимо задать зависимость от нужной версии платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c93c0-143">When you deploy a .NET Framework app that references a Portable Class Library assembly, you must specify a dependency on the correct version of the .NET Framework.</span></span> <span data-ttu-id="c93c0-144">Задание этой зависимости обеспечивает установку нужной версии вместе с приложением.</span><span class="sxs-lookup"><span data-stu-id="c93c0-144">By specifying this dependency, you ensure that the required version is installed with your app.</span></span>

-   <span data-ttu-id="c93c0-145">Чтобы создать зависимость с развертыванием ClickOnce: В **обозревателе решений**, выберите узел проекта для проекта, необходимо опубликовать.</span><span class="sxs-lookup"><span data-stu-id="c93c0-145">To create a dependency with ClickOnce deployment: In **Solution Explorer**, choose the project node for the project you want to publish.</span></span> <span data-ttu-id="c93c0-146">(Это проект, в котором имеется ссылка на проект переносимой библиотеки классов.) В строке меню выберите **проекта** > **свойства**и нажмите кнопку **публикации** вкладки. На **публикации** выберите **предварительные требования**.</span><span class="sxs-lookup"><span data-stu-id="c93c0-146">(This is the project that references the Portable Class Library project.) On the menu bar, choose **Project** > **Properties**, and then choose the **Publish** tab. On the **Publish** page, choose **Prerequisites**.</span></span> <span data-ttu-id="c93c0-147">Отметьте требуемую версию платформы .NET Framework как необходимый компонент.</span><span class="sxs-lookup"><span data-stu-id="c93c0-147">Select the required .NET Framework version as a prerequisite.</span></span>

-   <span data-ttu-id="c93c0-148">Чтобы создать зависимость с проектом установки: В **обозревателе решений**, выберите проект установки.</span><span class="sxs-lookup"><span data-stu-id="c93c0-148">To create a dependency with a setup project: In **Solution Explorer**, choose the setup project.</span></span> <span data-ttu-id="c93c0-149">В строке меню выберите **проекта** > **свойства** > **предварительные требования**.</span><span class="sxs-lookup"><span data-stu-id="c93c0-149">On the menu bar, choose **Project** > **Properties** > **Prerequisites**.</span></span> <span data-ttu-id="c93c0-150">Отметьте требуемую версию платформы .NET Framework как необходимый компонент.</span><span class="sxs-lookup"><span data-stu-id="c93c0-150">Select the required .NET Framework version as a prerequisite.</span></span>

<span data-ttu-id="c93c0-151">Дополнительные сведения о развертывании приложений .NET Framework, см. в разделе [руководство по развертыванию для разработчиков](../../../docs/framework/deployment/deployment-guide-for-developers.md).</span><span class="sxs-lookup"><span data-stu-id="c93c0-151">For more information about deploying .NET Framework apps, see [Deployment Guide for Developers](../../../docs/framework/deployment/deployment-guide-for-developers.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c93c0-152">См. также</span><span class="sxs-lookup"><span data-stu-id="c93c0-152">See also</span></span>

- [<span data-ttu-id="c93c0-153">Использование переносимой библиотеки классов с MVVM</span><span class="sxs-lookup"><span data-stu-id="c93c0-153">Using Portable Class Library with MVVM</span></span>](../../../docs/standard/cross-platform/using-portable-class-library-with-model-view-view-model.md)
- [<span data-ttu-id="c93c0-154">Ресурсы приложений для библиотек, предназначенных для нескольких платформ</span><span class="sxs-lookup"><span data-stu-id="c93c0-154">App Resources for Libraries That Target Multiple Platforms</span></span>](../../../docs/standard/cross-platform/app-resources-for-libraries-that-target-multiple-platforms.md)
- [<span data-ttu-id="c93c0-155">Анализатор переносимости .NET</span><span class="sxs-lookup"><span data-stu-id="c93c0-155">.NET Portability Analyzer</span></span>](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer)
- [<span data-ttu-id="c93c0-156">Поддержка платформы .NET Framework для приложений магазина Windows и среды выполнения Windows</span><span class="sxs-lookup"><span data-stu-id="c93c0-156">.NET Framework Support for Windows Store Apps and Windows Runtime</span></span>](../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md)
- [<span data-ttu-id="c93c0-157">Развертывание</span><span class="sxs-lookup"><span data-stu-id="c93c0-157">Deployment</span></span>](../../../docs/framework/deployment/net-framework-applications.md)
