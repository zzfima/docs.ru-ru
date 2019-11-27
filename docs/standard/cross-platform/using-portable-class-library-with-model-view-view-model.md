---
title: Использование переносимой библиотеки классов с шаблоном "модель-представление-модель представления"
ms.date: 07/18/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Portable Class Library [.NET Framework], and MVVM
- MVVM, and Portable Class Library
ms.assetid: 41a0b9f8-15a2-431a-bc35-e310b2953b03
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 445cf4178b90719f923b66a7778f60c1bc846766
ms.sourcegitcommit: 81ad1f09b93f3b3e6706a7f2e4ddf50ef229ea3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/20/2019
ms.locfileid: "74204971"
---
# <a name="using-portable-class-library-with-model-view-view-model"></a><span data-ttu-id="ed8d7-102">Использование переносимой библиотеки классов с шаблоном "модель-представление-модель представления"</span><span class="sxs-lookup"><span data-stu-id="ed8d7-102">Using Portable Class Library with Model-View-View Model</span></span>
<span data-ttu-id="ed8d7-103">Вы можете использовать .NET Framework [переносимую библиотеку классов](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md) для реализации шаблона модели представления "модель-представление-представление" (MVVM) и совместного использования сборок на нескольких платформах.</span><span class="sxs-lookup"><span data-stu-id="ed8d7-103">You can use the .NET Framework [Portable Class Library](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md) to implement the Model-View-View Model (MVVM) pattern and share assemblies across multiple platforms.</span></span>

[!INCLUDE[standard](../../../includes/pcl-to-standard.md)]

 <span data-ttu-id="ed8d7-104">MVVM — это шаблон приложения, который изолирует интерфейс пользователя от основной бизнес-логики.</span><span class="sxs-lookup"><span data-stu-id="ed8d7-104">MVVM is an application pattern that isolates the user interface from the underlying business logic.</span></span> <span data-ttu-id="ed8d7-105">Классы модели и модели представления можно реализовать в проекте переносимой библиотеки классов в Visual Studio 2012, а затем создавать представления, настроенные для разных платформ.</span><span class="sxs-lookup"><span data-stu-id="ed8d7-105">You can implement the model and view model classes in a Portable Class Library project in Visual Studio 2012, and then create views that are customized for different platforms.</span></span> <span data-ttu-id="ed8d7-106">Такой подход позволяет писать модель данных и бизнес-логику только один раз и использовать этот код из приложений Магазина .NET Framework, Silverlight, Windows Phone и Windows 8. x, как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="ed8d7-106">This approach enables you to write the data model and business logic only once, and use that code from .NET Framework, Silverlight, Windows Phone, and Windows 8.x Store apps, as shown in the following illustration.</span></span>

 ![Показывает переносимую библиотеку классов с MVVM совместной работой сборок на разных платформах.](./media/using-portable-class-library-with-model-view-view-model/mvvm-share-assemblies-across-platforms.png)

 <span data-ttu-id="ed8d7-108">В этом разделе не приведены общие сведения о шаблоне MVVM.</span><span class="sxs-lookup"><span data-stu-id="ed8d7-108">This topic does not provide general information about the MVVM pattern.</span></span> <span data-ttu-id="ed8d7-109">Он содержит только сведения об использовании переносимой библиотеки классов для реализации MVVM.</span><span class="sxs-lookup"><span data-stu-id="ed8d7-109">It only provides information about how to use Portable Class Library to implement MVVM.</span></span> <span data-ttu-id="ed8d7-110">Дополнительные сведения о MVVM см. в [кратком руководстве по MVVM с использованием библиотеки Prism 5,0 для WPF](https://docs.microsoft.com/previous-versions/msp-n-p/gg430857(v=pandp.40)).</span><span class="sxs-lookup"><span data-stu-id="ed8d7-110">For more information about MVVM, see the [MVVM Quickstart Using the Prism Library 5.0 for WPF](https://docs.microsoft.com/previous-versions/msp-n-p/gg430857(v=pandp.40)).</span></span>

## <a name="classes-that-support-mvvm"></a><span data-ttu-id="ed8d7-111">Классы, поддерживающие MVVM</span><span class="sxs-lookup"><span data-stu-id="ed8d7-111">Classes That Support MVVM</span></span>
 <span data-ttu-id="ed8d7-112">При использовании .NET Framework 4,5, [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)], Silverlight или Windows Phone 7,5 для проекта переносимой библиотеки классов доступны следующие классы для реализации шаблона MVVM:</span><span class="sxs-lookup"><span data-stu-id="ed8d7-112">When you target the .NET Framework 4.5, [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)], Silverlight, or Windows Phone 7.5 for your Portable Class Library project, the following classes are available for implementing the MVVM pattern:</span></span>

- <span data-ttu-id="ed8d7-113">Класс <xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="ed8d7-113"><xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="ed8d7-114">Класс <xref:System.Collections.ObjectModel.ReadOnlyObservableCollection%601?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="ed8d7-114"><xref:System.Collections.ObjectModel.ReadOnlyObservableCollection%601?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="ed8d7-115">Класс <xref:System.Collections.Specialized.INotifyCollectionChanged?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="ed8d7-115"><xref:System.Collections.Specialized.INotifyCollectionChanged?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="ed8d7-116">Класс <xref:System.Collections.Specialized.NotifyCollectionChangedAction?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="ed8d7-116"><xref:System.Collections.Specialized.NotifyCollectionChangedAction?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="ed8d7-117">Класс <xref:System.Collections.Specialized.NotifyCollectionChangedEventArgs?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="ed8d7-117"><xref:System.Collections.Specialized.NotifyCollectionChangedEventArgs?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="ed8d7-118">Класс <xref:System.Collections.Specialized.NotifyCollectionChangedEventHandler?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="ed8d7-118"><xref:System.Collections.Specialized.NotifyCollectionChangedEventHandler?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="ed8d7-119">Класс <xref:System.ComponentModel.DataErrorsChangedEventArgs?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="ed8d7-119"><xref:System.ComponentModel.DataErrorsChangedEventArgs?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="ed8d7-120">Класс <xref:System.ComponentModel.INotifyDataErrorInfo?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="ed8d7-120"><xref:System.ComponentModel.INotifyDataErrorInfo?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="ed8d7-121">Класс <xref:System.ComponentModel.INotifyPropertyChanged?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="ed8d7-121"><xref:System.ComponentModel.INotifyPropertyChanged?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="ed8d7-122">Класс <xref:System.Windows.Input.ICommand?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="ed8d7-122"><xref:System.Windows.Input.ICommand?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="ed8d7-123">Все классы в пространстве имен <xref:System.ComponentModel.DataAnnotations?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="ed8d7-123">All classes in the <xref:System.ComponentModel.DataAnnotations?displayProperty=nameWithType> namespace</span></span>

## <a name="implementing-mvvm"></a><span data-ttu-id="ed8d7-124">Реализация MVVM</span><span class="sxs-lookup"><span data-stu-id="ed8d7-124">Implementing MVVM</span></span>
 <span data-ttu-id="ed8d7-125">Для реализации MVVM обычно создается модель и модель представления в проекте переносимой библиотеки классов, поскольку проект переносимой библиотеки классов не может ссылаться на непереносимый проект.</span><span class="sxs-lookup"><span data-stu-id="ed8d7-125">To implement MVVM, you typically create both the model and the view model in a Portable Class Library project, because a Portable Class Library project cannot reference a non-portable project.</span></span> <span data-ttu-id="ed8d7-126">Модель и модель представления могут находиться в одном и том же проекте или в отдельных проектах.</span><span class="sxs-lookup"><span data-stu-id="ed8d7-126">The model and view model can be in the same project or in separate projects.</span></span> <span data-ttu-id="ed8d7-127">Если используются отдельные проекты, добавьте ссылку из проекта модели представления в проект модели.</span><span class="sxs-lookup"><span data-stu-id="ed8d7-127">If you use separate projects, add a reference from the view model project to the model project.</span></span>

 <span data-ttu-id="ed8d7-128">После компиляции модели и проектов модели представления вы ссылаетесь на эти сборки в приложении, которое содержит представление.</span><span class="sxs-lookup"><span data-stu-id="ed8d7-128">After you compile the model and view model projects, you reference those assemblies in the app that contains the view.</span></span> <span data-ttu-id="ed8d7-129">Если представление взаимодействует только с моделью представления, необходимо ссылаться только на сборку, содержащую модель представления.</span><span class="sxs-lookup"><span data-stu-id="ed8d7-129">If the view interacts only with the view model, you only have to reference the assembly that contains the view model.</span></span>

### <a name="model"></a><span data-ttu-id="ed8d7-130">Модель</span><span class="sxs-lookup"><span data-stu-id="ed8d7-130">Model</span></span>
 <span data-ttu-id="ed8d7-131">В следующем примере показан упрощенный класс модели, который может находиться в проекте переносимой библиотеки классов.</span><span class="sxs-lookup"><span data-stu-id="ed8d7-131">The following example shows a simplified model class that could reside in a Portable Class Library project.</span></span>

 [!code-csharp[PortableClassLibraryMVVM#1](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/customer.cs#1)]
 [!code-vb[PortableClassLibraryMVVM#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customer.vb#1)]

 <span data-ttu-id="ed8d7-132">В следующем примере показан простой способ заполнения, извлечения и обновления данных в проекте переносимой библиотеки классов.</span><span class="sxs-lookup"><span data-stu-id="ed8d7-132">The following example shows a simple way to populate, retrieve, and update the data in a Portable Class Library project.</span></span> <span data-ttu-id="ed8d7-133">В реальных приложениях данные извлекаются из источника, например службы Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="ed8d7-133">In a real app, you would retrieve the data from a source such as a Windows Communication Foundation (WCF) service.</span></span>

 [!code-csharp[PortableClassLibraryMVVM#2](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/customerrepository.cs#2)]
 [!code-vb[PortableClassLibraryMVVM#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customerrepository.vb#2)]

### <a name="view-model"></a><span data-ttu-id="ed8d7-134">Просмотр модели</span><span class="sxs-lookup"><span data-stu-id="ed8d7-134">View Model</span></span>
 <span data-ttu-id="ed8d7-135">Базовый класс для моделей представления часто добавляется при реализации шаблона MVVM.</span><span class="sxs-lookup"><span data-stu-id="ed8d7-135">A base class for view models is frequently added when implementing the MVVM pattern.</span></span> <span data-ttu-id="ed8d7-136">В следующем примере показан базовый класс.</span><span class="sxs-lookup"><span data-stu-id="ed8d7-136">The following example shows a base class.</span></span>

 [!code-csharp[PortableClassLibraryMVVM#3](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/viewmodelbase.cs#3)]
 [!code-vb[PortableClassLibraryMVVM#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/viewmodelbase.vb#3)]

 <span data-ttu-id="ed8d7-137">Реализация интерфейса <xref:System.Windows.Input.ICommand> часто используется с шаблоном MVVM.</span><span class="sxs-lookup"><span data-stu-id="ed8d7-137">An implementation of the <xref:System.Windows.Input.ICommand> interface is frequently used with the MVVM pattern.</span></span> <span data-ttu-id="ed8d7-138">В следующем примере показана реализация интерфейса <xref:System.Windows.Input.ICommand>.</span><span class="sxs-lookup"><span data-stu-id="ed8d7-138">The following example shows an implementation of the <xref:System.Windows.Input.ICommand> interface.</span></span>

 [!code-csharp[PortableClassLibraryMVVM#4](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/relaycommand.cs#4)]
 [!code-vb[PortableClassLibraryMVVM#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/relaycommand.vb#4)]

 <span data-ttu-id="ed8d7-139">В следующем примере показана упрощенная модель представления.</span><span class="sxs-lookup"><span data-stu-id="ed8d7-139">The following example shows a simplified view model.</span></span>

 [!code-csharp[PortableClassLibraryMVVM#5](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/mainpageviewmodel.cs#5)]
 [!code-vb[PortableClassLibraryMVVM#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customerviewmodel.vb#5)]  
  
### <a name="view"></a><span data-ttu-id="ed8d7-140">Вид</span><span class="sxs-lookup"><span data-stu-id="ed8d7-140">View</span></span>  
 <span data-ttu-id="ed8d7-141">Из приложения .NET Framework 4,5, приложения Магазина Windows 8. x, приложения на основе Silverlight или приложения Windows Phone 7,5 можно ссылаться на сборку, содержащую проекты модели и представления модели.</span><span class="sxs-lookup"><span data-stu-id="ed8d7-141">From a .NET Framework 4.5 app, Windows 8.x Store app, Silverlight-based app, or Windows Phone 7.5 app, you can reference the assembly that contains the model and view model projects.</span></span>  <span data-ttu-id="ed8d7-142">Затем создается представление, взаимодействующее с моделью представления.</span><span class="sxs-lookup"><span data-stu-id="ed8d7-142">You then create a view that interacts with the view model.</span></span> <span data-ttu-id="ed8d7-143">В следующем примере показано упрощенное приложение Windows Presentation Foundation (WPF), которое извлекает и обновляет данные из модели представления.</span><span class="sxs-lookup"><span data-stu-id="ed8d7-143">The following example shows a simplified Windows Presentation Foundation (WPF) app that retrieves and updates data from the view model.</span></span> <span data-ttu-id="ed8d7-144">Аналогичные представления можно создавать в приложениях Магазина Silverlight, Windows Phone или Windows 8. x.</span><span class="sxs-lookup"><span data-stu-id="ed8d7-144">You could create similar views in Silverlight, Windows Phone, or Windows 8.x Store apps.</span></span>  
  
 [!code-xaml[PortableClassLibraryMVVM#6](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/mainwindow.xaml#6)]  
  
## <a name="see-also"></a><span data-ttu-id="ed8d7-145">См. также:</span><span class="sxs-lookup"><span data-stu-id="ed8d7-145">See also</span></span>

- [<span data-ttu-id="ed8d7-146">Переносимая библиотека классов</span><span class="sxs-lookup"><span data-stu-id="ed8d7-146">Portable Class Library</span></span>](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md)
