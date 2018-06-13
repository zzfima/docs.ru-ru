---
title: Использование переносимой библиотеки классов с шаблоном "модель-представление-модель представления"
ms.date: 03/30/2017
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
ms.openlocfilehash: aa8423c5c9453a9edb1058f0d5bdf4c494ece088
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33574112"
---
# <a name="using-portable-class-library-with-model-view-view-model"></a><span data-ttu-id="cb949-102">Использование переносимой библиотеки классов с шаблоном "модель-представление-модель представления"</span><span class="sxs-lookup"><span data-stu-id="cb949-102">Using Portable Class Library with Model-View-View Model</span></span>
<span data-ttu-id="cb949-103">Можно использовать .NET Framework [переносимой библиотеки классов](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md) для реализации шаблона Model-View-View Model (MVVM) и совместного использования сборок на нескольких платформах.</span><span class="sxs-lookup"><span data-stu-id="cb949-103">You can use the .NET Framework [Portable Class Library](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md) to implement the Model-View-View Model (MVVM) pattern and share assemblies across multiple platforms.</span></span>  
  
 <span data-ttu-id="cb949-104">MVVM — это шаблон приложения, который изолирует интерфейс пользователя от основной бизнес-логики.</span><span class="sxs-lookup"><span data-stu-id="cb949-104">MVVM is an application pattern that isolates the user interface from the underlying business logic.</span></span> <span data-ttu-id="cb949-105">Можно реализовать классы модели и модели представления в проекте [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] в [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], а затем создать представления, которые учитывают особенности разных платформ.</span><span class="sxs-lookup"><span data-stu-id="cb949-105">You can implement the model and view model classes in a [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] project in [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], and then create views that are customized for different platforms.</span></span> <span data-ttu-id="cb949-106">Такой подход позволяет создавать модель и бизнес-логику данных только один раз и использовать этот код в платформе .NET Framework, приложениях Silverlight, Windows Phone и [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)], как показано на следующей иллюстрации.</span><span class="sxs-lookup"><span data-stu-id="cb949-106">This approach enables you to write the data model and business logic only once, and use that code from .NET Framework, Silverlight, Windows Phone, and [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps, as shown in the following illustration.</span></span>  
  
 <span data-ttu-id="cb949-107">![Переносимый со схемой MVVM](../../../docs/standard/cross-platform/media/portablemvvmdiagram.png "PortableMVVMdiagram")</span><span class="sxs-lookup"><span data-stu-id="cb949-107">![Portable with MVVM diagram](../../../docs/standard/cross-platform/media/portablemvvmdiagram.png "PortableMVVMdiagram")</span></span>  
  
 <span data-ttu-id="cb949-108">В этом разделе не предоставляет общие сведения о шаблоне MVVM.</span><span class="sxs-lookup"><span data-stu-id="cb949-108">This topic does not provide general information about the MVVM pattern.</span></span> <span data-ttu-id="cb949-109">Он только предоставляет сведения об использовании [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] для реализации MVVM.</span><span class="sxs-lookup"><span data-stu-id="cb949-109">It only provides information about how to use [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] to implement MVVM.</span></span> <span data-ttu-id="cb949-110">Дополнительные сведения о MVVM см. в разделе [краткое руководство MVVM](https://msdn.microsoft.com/library/gg430869(v=PandP.40).aspx).</span><span class="sxs-lookup"><span data-stu-id="cb949-110">For more information about MVVM, see the [MVVM Quickstart](https://msdn.microsoft.com/library/gg430869(v=PandP.40).aspx).</span></span>  
  
## <a name="classes-that-support-mvvm"></a><span data-ttu-id="cb949-111">Классы, поддерживающие MVVM</span><span class="sxs-lookup"><span data-stu-id="cb949-111">Classes That Support MVVM</span></span>  
 <span data-ttu-id="cb949-112">При разработке [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)], Silverlight или Windows Phone 7.5 для вашего [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] проекта, следующие классы доступны для реализации шаблона MVVM:</span><span class="sxs-lookup"><span data-stu-id="cb949-112">When you target the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)], Silverlight, or Windows Phone 7.5 for your [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] project, the following classes are available for implementing the MVVM pattern:</span></span>  
  
-   <span data-ttu-id="cb949-113">Класс <xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="cb949-113"><xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=nameWithType> class</span></span>  
  
-   <span data-ttu-id="cb949-114">Класс <xref:System.Collections.ObjectModel.ReadOnlyObservableCollection%601?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="cb949-114"><xref:System.Collections.ObjectModel.ReadOnlyObservableCollection%601?displayProperty=nameWithType> class</span></span>  
  
-   <span data-ttu-id="cb949-115">Класс <xref:System.Collections.Specialized.INotifyCollectionChanged?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="cb949-115"><xref:System.Collections.Specialized.INotifyCollectionChanged?displayProperty=nameWithType> class</span></span>  
  
-   <span data-ttu-id="cb949-116">Класс <xref:System.Collections.Specialized.NotifyCollectionChangedAction?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="cb949-116"><xref:System.Collections.Specialized.NotifyCollectionChangedAction?displayProperty=nameWithType> class</span></span>  
  
-   <span data-ttu-id="cb949-117">Класс <xref:System.Collections.Specialized.NotifyCollectionChangedEventArgs?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="cb949-117"><xref:System.Collections.Specialized.NotifyCollectionChangedEventArgs?displayProperty=nameWithType> class</span></span>  
  
-   <span data-ttu-id="cb949-118">Класс <xref:System.Collections.Specialized.NotifyCollectionChangedEventHandler?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="cb949-118"><xref:System.Collections.Specialized.NotifyCollectionChangedEventHandler?displayProperty=nameWithType> class</span></span>  
  
-   <span data-ttu-id="cb949-119">Класс <xref:System.ComponentModel.DataErrorsChangedEventArgs?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="cb949-119"><xref:System.ComponentModel.DataErrorsChangedEventArgs?displayProperty=nameWithType> class</span></span>  
  
-   <span data-ttu-id="cb949-120">Класс <xref:System.ComponentModel.INotifyDataErrorInfo?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="cb949-120"><xref:System.ComponentModel.INotifyDataErrorInfo?displayProperty=nameWithType> class</span></span>  
  
-   <span data-ttu-id="cb949-121">Класс <xref:System.ComponentModel.INotifyPropertyChanged?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="cb949-121"><xref:System.ComponentModel.INotifyPropertyChanged?displayProperty=nameWithType> class</span></span>  
  
-   <span data-ttu-id="cb949-122">Класс <xref:System.Windows.Input.ICommand?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="cb949-122"><xref:System.Windows.Input.ICommand?displayProperty=nameWithType> class</span></span>  
  
-   <span data-ttu-id="cb949-123">Все классы в <xref:System.ComponentModel.DataAnnotations?displayProperty=nameWithType> пространства имен</span><span class="sxs-lookup"><span data-stu-id="cb949-123">All classes in the <xref:System.ComponentModel.DataAnnotations?displayProperty=nameWithType> namespace</span></span>  
  
## <a name="implementing-mvvm"></a><span data-ttu-id="cb949-124">Реализация MVVM</span><span class="sxs-lookup"><span data-stu-id="cb949-124">Implementing MVVM</span></span>  
 <span data-ttu-id="cb949-125">Чтобы реализовать MVVM, обычно создаются модели и модели представления в [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] проект, поскольку [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] Непереносимый проект не может ссылаться на проект.</span><span class="sxs-lookup"><span data-stu-id="cb949-125">To implement MVVM, you typically create both the model and the view model in a [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] project, because a [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] project cannot reference a non-portable project.</span></span> <span data-ttu-id="cb949-126">Модели и модели представления может быть в том же проекте или в виде отдельных проектов.</span><span class="sxs-lookup"><span data-stu-id="cb949-126">The model and view model can be in the same project or in separate projects.</span></span> <span data-ttu-id="cb949-127">Если вы используете отдельные проекты, добавьте ссылку из проекта модели представления в проект модели.</span><span class="sxs-lookup"><span data-stu-id="cb949-127">If you use separate projects, add a reference from the view model project to the model project.</span></span>  
  
 <span data-ttu-id="cb949-128">После компиляции модели и просматривать проекты модели, можно ссылаться на эти сборки в приложении, которая содержит представление.</span><span class="sxs-lookup"><span data-stu-id="cb949-128">After you compile the model and view model projects, you reference those assemblies in the app that contains the view.</span></span> <span data-ttu-id="cb949-129">Если представление взаимодействует только с помощью модели представления, имеется ссылка на сборку, содержащую модель представления.</span><span class="sxs-lookup"><span data-stu-id="cb949-129">If the view interacts only with the view model, you only have to reference the assembly that contains the view model.</span></span>  
  
### <a name="model"></a><span data-ttu-id="cb949-130">Модель</span><span class="sxs-lookup"><span data-stu-id="cb949-130">Model</span></span>  
 <span data-ttu-id="cb949-131">В следующем примере показано упрощенная модель класс, который может находиться в [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] проекта.</span><span class="sxs-lookup"><span data-stu-id="cb949-131">The following example shows a simplified model class that could reside in a [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] project.</span></span>  
  
 [!code-csharp[PortableClassLibraryMVVM#1](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/customer.cs#1)]
 [!code-vb[PortableClassLibraryMVVM#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customer.vb#1)]  
  
 <span data-ttu-id="cb949-132">В следующем примере показано простой способ заполнения, получения и обновления данных в [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] проекта.</span><span class="sxs-lookup"><span data-stu-id="cb949-132">The following example shows a simple way to populate, retrieve, and update the data in a [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] project.</span></span> <span data-ttu-id="cb949-133">В реальном приложении будет получать данные из источника, например службы Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="cb949-133">In a real app, you would retrieve the data from a source such as a Windows Communication Foundation (WCF) service.</span></span>  
  
 [!code-csharp[PortableClassLibraryMVVM#2](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/customerrepository.cs#2)]
 [!code-vb[PortableClassLibraryMVVM#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customerrepository.vb#2)]  
  
### <a name="view-model"></a><span data-ttu-id="cb949-134">Модель представления</span><span class="sxs-lookup"><span data-stu-id="cb949-134">View Model</span></span>  
 <span data-ttu-id="cb949-135">Базовый класс для представления моделей часто добавляется при реализации шаблона MVVM.</span><span class="sxs-lookup"><span data-stu-id="cb949-135">A base class for view models is frequently added when implementing the MVVM pattern.</span></span> <span data-ttu-id="cb949-136">В следующем примере базовый класс.</span><span class="sxs-lookup"><span data-stu-id="cb949-136">The following example shows a base class.</span></span>  
  
 [!code-csharp[PortableClassLibraryMVVM#3](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/viewmodelbase.cs#3)]
 [!code-vb[PortableClassLibraryMVVM#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/viewmodelbase.vb#3)]  
  
 <span data-ttu-id="cb949-137">Реализация <xref:System.Windows.Input.ICommand> часто используется интерфейс с шаблоном MVVM.</span><span class="sxs-lookup"><span data-stu-id="cb949-137">An implementation of the <xref:System.Windows.Input.ICommand> interface is frequently used with the MVVM pattern.</span></span> <span data-ttu-id="cb949-138">В следующем примере показана реализация интерфейса <xref:System.Windows.Input.ICommand>.</span><span class="sxs-lookup"><span data-stu-id="cb949-138">The following example shows an implementation of the <xref:System.Windows.Input.ICommand> interface.</span></span>  
  
 [!code-csharp[PortableClassLibraryMVVM#4](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/relaycommand.cs#4)]
 [!code-vb[PortableClassLibraryMVVM#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/relaycommand.vb#4)]  
  
 <span data-ttu-id="cb949-139">В следующем примере показано упрощенное представление модели.</span><span class="sxs-lookup"><span data-stu-id="cb949-139">The following example shows a simplified view model.</span></span>  
  
 [!code-csharp[PortableClassLibraryMVVM#5](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/mainpageviewmodel.cs#5)]
 [!code-vb[PortableClassLibraryMVVM#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customerviewmodel.vb#5)]  
  
### <a name="view"></a><span data-ttu-id="cb949-140">Просмотр</span><span class="sxs-lookup"><span data-stu-id="cb949-140">View</span></span>  
 <span data-ttu-id="cb949-141">Из [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] приложения, [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] приложения, приложения Silverlight или приложения Windows Phone 7.5, могут ссылаться на сборку, содержащую проекты модели и представления модели.</span><span class="sxs-lookup"><span data-stu-id="cb949-141">From a [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] app, [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] app, Silverlight-based app, or Windows Phone 7.5 app, you can reference the assembly that contains the model and view model projects.</span></span>  <span data-ttu-id="cb949-142">Затем создается представление, которое взаимодействует с модели представления.</span><span class="sxs-lookup"><span data-stu-id="cb949-142">You then create a view that interacts with the view model.</span></span> <span data-ttu-id="cb949-143">В следующем примере показано упрощенное приложения Windows Presentation Foundation (WPF), который получает и обновляет данные из модели представления.</span><span class="sxs-lookup"><span data-stu-id="cb949-143">The following example shows a simplified Windows Presentation Foundation (WPF) app that retrieves and updates data from the view model.</span></span> <span data-ttu-id="cb949-144">Вы можете создать сходные представления в Silverlight, Windows Phone или [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] приложений.</span><span class="sxs-lookup"><span data-stu-id="cb949-144">You could create similar views in Silverlight, Windows Phone, or [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps.</span></span>  
  
 [!code-xaml[PortableClassLibraryMVVM#6](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/mainwindow.xaml#6)]  
  
## <a name="see-also"></a><span data-ttu-id="cb949-145">См. также</span><span class="sxs-lookup"><span data-stu-id="cb949-145">See Also</span></span>  
 [<span data-ttu-id="cb949-146">Переносимая библиотека классов</span><span class="sxs-lookup"><span data-stu-id="cb949-146">Portable Class Library</span></span>](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md)
