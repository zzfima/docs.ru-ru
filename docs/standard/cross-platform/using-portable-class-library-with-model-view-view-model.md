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
ms.openlocfilehash: b53be90764c6537fb27cb1b5ed781a68e69effa0
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2019
ms.locfileid: "67504674"
---
# <a name="using-portable-class-library-with-model-view-view-model"></a><span data-ttu-id="60c8d-102">Использование переносимой библиотеки классов с шаблоном "модель-представление-модель представления"</span><span class="sxs-lookup"><span data-stu-id="60c8d-102">Using Portable Class Library with Model-View-View Model</span></span>
<span data-ttu-id="60c8d-103">Можно использовать .NET Framework [переносимой библиотеки классов](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md) реализовать шаблон модель-представление-View Model (MVVM) и совместного использования сборок на нескольких платформах.</span><span class="sxs-lookup"><span data-stu-id="60c8d-103">You can use the .NET Framework [Portable Class Library](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md) to implement the Model-View-View Model (MVVM) pattern and share assemblies across multiple platforms.</span></span>

[!INCLUDE[standard](../../../includes/pcl-to-standard.md)]

 <span data-ttu-id="60c8d-104">MVVM — это шаблон приложения, который изолирует интерфейс пользователя от основной бизнес-логики.</span><span class="sxs-lookup"><span data-stu-id="60c8d-104">MVVM is an application pattern that isolates the user interface from the underlying business logic.</span></span> <span data-ttu-id="60c8d-105">Можно реализовать классы модели, модели и представления в проекте переносимой библиотеки классов в Visual Studio 2012 и затем создать представления, которые настраиваются для различных платформ.</span><span class="sxs-lookup"><span data-stu-id="60c8d-105">You can implement the model and view model classes in a Portable Class Library project in Visual Studio 2012, and then create views that are customized for different platforms.</span></span> <span data-ttu-id="60c8d-106">Такой подход позволяет создавать модель и бизнес-логику данных только один раз и использовать этот код в платформе .NET Framework, приложениях Silverlight, Windows Phone и [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)], как показано на следующей иллюстрации.</span><span class="sxs-lookup"><span data-stu-id="60c8d-106">This approach enables you to write the data model and business logic only once, and use that code from .NET Framework, Silverlight, Windows Phone, and [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps, as shown in the following illustration.</span></span>

 ![Показывает переносимой библиотеки классов с MVVM совместного использования сборок на платформах.](./media/using-portable-class-library-with-model-view-view-model/mvvm-share-assemblies-across-platforms.png)

 <span data-ttu-id="60c8d-108">В этом разделе не предоставляет общие сведения о шаблоне MVVM.</span><span class="sxs-lookup"><span data-stu-id="60c8d-108">This topic does not provide general information about the MVVM pattern.</span></span> <span data-ttu-id="60c8d-109">Он только сведения о том, как использовать переносимой библиотеки классов для реализации MVVM.</span><span class="sxs-lookup"><span data-stu-id="60c8d-109">It only provides information about how to use Portable Class Library to implement MVVM.</span></span> <span data-ttu-id="60c8d-110">Дополнительные сведения о шаблоне MVVM см. в разделе [MVVM быстрого запуска с помощью 5.0 библиотеку Prism для WPF](https://docs.microsoft.com/previous-versions/msp-n-p/gg430857(v=pandp.40)).</span><span class="sxs-lookup"><span data-stu-id="60c8d-110">For more information about MVVM, see the [MVVM Quickstart Using the Prism Library 5.0 for WPF](https://docs.microsoft.com/previous-versions/msp-n-p/gg430857(v=pandp.40)).</span></span>

## <a name="classes-that-support-mvvm"></a><span data-ttu-id="60c8d-111">Классы, поддерживающие MVVM</span><span class="sxs-lookup"><span data-stu-id="60c8d-111">Classes That Support MVVM</span></span>
 <span data-ttu-id="60c8d-112">При выборе платформы .NET Framework 4.5, [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)], Silverlight или Windows Phone 7.5 для проекта переносимой библиотеки классов для реализации шаблона MVVM доступны следующие классы:</span><span class="sxs-lookup"><span data-stu-id="60c8d-112">When you target the .NET Framework 4.5, [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)], Silverlight, or Windows Phone 7.5 for your Portable Class Library project, the following classes are available for implementing the MVVM pattern:</span></span>

- <span data-ttu-id="60c8d-113">Класс <xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="60c8d-113"><xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="60c8d-114">Класс <xref:System.Collections.ObjectModel.ReadOnlyObservableCollection%601?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="60c8d-114"><xref:System.Collections.ObjectModel.ReadOnlyObservableCollection%601?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="60c8d-115">Класс <xref:System.Collections.Specialized.INotifyCollectionChanged?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="60c8d-115"><xref:System.Collections.Specialized.INotifyCollectionChanged?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="60c8d-116">Класс <xref:System.Collections.Specialized.NotifyCollectionChangedAction?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="60c8d-116"><xref:System.Collections.Specialized.NotifyCollectionChangedAction?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="60c8d-117">Класс <xref:System.Collections.Specialized.NotifyCollectionChangedEventArgs?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="60c8d-117"><xref:System.Collections.Specialized.NotifyCollectionChangedEventArgs?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="60c8d-118">Класс <xref:System.Collections.Specialized.NotifyCollectionChangedEventHandler?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="60c8d-118"><xref:System.Collections.Specialized.NotifyCollectionChangedEventHandler?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="60c8d-119">Класс <xref:System.ComponentModel.DataErrorsChangedEventArgs?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="60c8d-119"><xref:System.ComponentModel.DataErrorsChangedEventArgs?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="60c8d-120">Класс <xref:System.ComponentModel.INotifyDataErrorInfo?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="60c8d-120"><xref:System.ComponentModel.INotifyDataErrorInfo?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="60c8d-121">Класс <xref:System.ComponentModel.INotifyPropertyChanged?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="60c8d-121"><xref:System.ComponentModel.INotifyPropertyChanged?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="60c8d-122">Класс <xref:System.Windows.Input.ICommand?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="60c8d-122"><xref:System.Windows.Input.ICommand?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="60c8d-123">Все классы в <xref:System.ComponentModel.DataAnnotations?displayProperty=nameWithType> пространства имен</span><span class="sxs-lookup"><span data-stu-id="60c8d-123">All classes in the <xref:System.ComponentModel.DataAnnotations?displayProperty=nameWithType> namespace</span></span>

## <a name="implementing-mvvm"></a><span data-ttu-id="60c8d-124">Реализации MVVM</span><span class="sxs-lookup"><span data-stu-id="60c8d-124">Implementing MVVM</span></span>
 <span data-ttu-id="60c8d-125">Для реализации MVVM, обычно создают модель и модель представления в проекте переносимой библиотеки классов, так как проект переносимой библиотеки классов не могут ссылаться на Непереносимый проект.</span><span class="sxs-lookup"><span data-stu-id="60c8d-125">To implement MVVM, you typically create both the model and the view model in a Portable Class Library project, because a Portable Class Library project cannot reference a non-portable project.</span></span> <span data-ttu-id="60c8d-126">Модели и модели представления может быть в одном проекте или в виде отдельных проектов.</span><span class="sxs-lookup"><span data-stu-id="60c8d-126">The model and view model can be in the same project or in separate projects.</span></span> <span data-ttu-id="60c8d-127">Если вы используете отдельные проекты, добавьте ссылку из проекта модели представления в проект модели.</span><span class="sxs-lookup"><span data-stu-id="60c8d-127">If you use separate projects, add a reference from the view model project to the model project.</span></span>

 <span data-ttu-id="60c8d-128">После компиляции модели и просматривать проекты модели, можно ссылаться на эти сборки в приложении, которая содержит представление.</span><span class="sxs-lookup"><span data-stu-id="60c8d-128">After you compile the model and view model projects, you reference those assemblies in the app that contains the view.</span></span> <span data-ttu-id="60c8d-129">Если представление взаимодействует только с помощью модели представления, необходимо ссылаться на сборку, содержащую модели представления.</span><span class="sxs-lookup"><span data-stu-id="60c8d-129">If the view interacts only with the view model, you only have to reference the assembly that contains the view model.</span></span>

### <a name="model"></a><span data-ttu-id="60c8d-130">Модель</span><span class="sxs-lookup"><span data-stu-id="60c8d-130">Model</span></span>
 <span data-ttu-id="60c8d-131">В следующем примере показан класс упрощенной модели, могут располагаться в проекте переносимой библиотеки классов.</span><span class="sxs-lookup"><span data-stu-id="60c8d-131">The following example shows a simplified model class that could reside in a Portable Class Library project.</span></span>

 [!code-csharp[PortableClassLibraryMVVM#1](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/customer.cs#1)]
 [!code-vb[PortableClassLibraryMVVM#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customer.vb#1)]

 <span data-ttu-id="60c8d-132">Следующий пример показывает простой способ для заполнения, извлечения и обновления данных в проекте переносимой библиотеки классов.</span><span class="sxs-lookup"><span data-stu-id="60c8d-132">The following example shows a simple way to populate, retrieve, and update the data in a Portable Class Library project.</span></span> <span data-ttu-id="60c8d-133">В реальном приложении можно извлечь данные из источника, например службы Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="60c8d-133">In a real app, you would retrieve the data from a source such as a Windows Communication Foundation (WCF) service.</span></span>

 [!code-csharp[PortableClassLibraryMVVM#2](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/customerrepository.cs#2)]
 [!code-vb[PortableClassLibraryMVVM#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customerrepository.vb#2)]

### <a name="view-model"></a><span data-ttu-id="60c8d-134">Модель представления</span><span class="sxs-lookup"><span data-stu-id="60c8d-134">View Model</span></span>
 <span data-ttu-id="60c8d-135">Базовый класс для представления моделей часто добавляется при реализации шаблона MVVM.</span><span class="sxs-lookup"><span data-stu-id="60c8d-135">A base class for view models is frequently added when implementing the MVVM pattern.</span></span> <span data-ttu-id="60c8d-136">В следующем примере базового класса.</span><span class="sxs-lookup"><span data-stu-id="60c8d-136">The following example shows a base class.</span></span>

 [!code-csharp[PortableClassLibraryMVVM#3](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/viewmodelbase.cs#3)]
 [!code-vb[PortableClassLibraryMVVM#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/viewmodelbase.vb#3)]

 <span data-ttu-id="60c8d-137">Реализация <xref:System.Windows.Input.ICommand> интерфейс часто используется с помощью шаблона MVVM.</span><span class="sxs-lookup"><span data-stu-id="60c8d-137">An implementation of the <xref:System.Windows.Input.ICommand> interface is frequently used with the MVVM pattern.</span></span> <span data-ttu-id="60c8d-138">В следующем примере показана реализация интерфейса <xref:System.Windows.Input.ICommand>.</span><span class="sxs-lookup"><span data-stu-id="60c8d-138">The following example shows an implementation of the <xref:System.Windows.Input.ICommand> interface.</span></span>

 [!code-csharp[PortableClassLibraryMVVM#4](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/relaycommand.cs#4)]
 [!code-vb[PortableClassLibraryMVVM#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/relaycommand.vb#4)]

 <span data-ttu-id="60c8d-139">В примере показан упрощенный вид модели.</span><span class="sxs-lookup"><span data-stu-id="60c8d-139">The following example shows a simplified view model.</span></span>

 [!code-csharp[PortableClassLibraryMVVM#5](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/mainpageviewmodel.cs#5)]
 [!code-vb[PortableClassLibraryMVVM#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customerviewmodel.vb#5)]  
  
### <a name="view"></a><span data-ttu-id="60c8d-140">Просмотр</span><span class="sxs-lookup"><span data-stu-id="60c8d-140">View</span></span>  
 <span data-ttu-id="60c8d-141">Из приложения .NET Framework 4.5 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] приложения, приложения Silverlight или приложения Windows Phone 7.5, могут ссылаться на сборки, содержащей проекты модели модель и представление.</span><span class="sxs-lookup"><span data-stu-id="60c8d-141">From a .NET Framework 4.5 app, [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] app, Silverlight-based app, or Windows Phone 7.5 app, you can reference the assembly that contains the model and view model projects.</span></span>  <span data-ttu-id="60c8d-142">Затем создается представление, которое взаимодействует с моделью представления.</span><span class="sxs-lookup"><span data-stu-id="60c8d-142">You then create a view that interacts with the view model.</span></span> <span data-ttu-id="60c8d-143">В примере показан упрощенный приложение Windows Presentation Foundation (WPF), которое извлекает и обновляет данные из модели представления.</span><span class="sxs-lookup"><span data-stu-id="60c8d-143">The following example shows a simplified Windows Presentation Foundation (WPF) app that retrieves and updates data from the view model.</span></span> <span data-ttu-id="60c8d-144">В Silverlight, Windows Phone, можно создать похожих представлениях или [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] приложений.</span><span class="sxs-lookup"><span data-stu-id="60c8d-144">You could create similar views in Silverlight, Windows Phone, or [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps.</span></span>  
  
 [!code-xaml[PortableClassLibraryMVVM#6](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/mainwindow.xaml#6)]  
  
## <a name="see-also"></a><span data-ttu-id="60c8d-145">См. также</span><span class="sxs-lookup"><span data-stu-id="60c8d-145">See also</span></span>

- [<span data-ttu-id="60c8d-146">Переносимая библиотека классов</span><span class="sxs-lookup"><span data-stu-id="60c8d-146">Portable Class Library</span></span>](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md)
