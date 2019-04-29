---
title: Компонент BindingSource
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [Windows Forms], Windows Forms
- Windows Forms, data binding control
- BindingSource component [Windows Forms]
ms.assetid: 3e2faf4c-f5b8-4fa6-9fbc-f59c37ec2fb9
ms.openlocfilehash: 54639edb512a8bc6c5909282d5e4c210439e2a6e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61683422"
---
# <a name="bindingsource-component"></a><span data-ttu-id="992e8-102">Компонент BindingSource</span><span class="sxs-lookup"><span data-stu-id="992e8-102">BindingSource Component</span></span>
<span data-ttu-id="992e8-103">Инкапсулирует источник данных для привязки к элементам управления.</span><span class="sxs-lookup"><span data-stu-id="992e8-103">Encapsulates a data source for binding to controls.</span></span>  
  
 <span data-ttu-id="992e8-104">Компонент <xref:System.Windows.Forms.BindingSource> служит двум целям.</span><span class="sxs-lookup"><span data-stu-id="992e8-104">The <xref:System.Windows.Forms.BindingSource> component serves two purposes.</span></span> <span data-ttu-id="992e8-105">Во-первых, он обеспечивает уровень косвенного обращения при выполнении привязки элементов управления в форме к данным.</span><span class="sxs-lookup"><span data-stu-id="992e8-105">First, it provides a layer of indirection when binding the controls on a form to data.</span></span> <span data-ttu-id="992e8-106">Это достигается путем привязки компонента <xref:System.Windows.Forms.BindingSource> к источнику данных и последующей привязки элементов управления в форме к компоненту <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="992e8-106">This is accomplished by binding the <xref:System.Windows.Forms.BindingSource> component to your data source, and then binding the controls on your form to the <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="992e8-107">Все последующие взаимодействия с данными, включая перемещение, сортировку, фильтрацию и обновление, осуществляются с помощью вызовов компонента <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="992e8-107">All further interaction with the data, including navigating, sorting, filtering, and updating, is accomplished with calls to the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
 <span data-ttu-id="992e8-108">Во-вторых, компонент <xref:System.Windows.Forms.BindingSource> может действовать как строго типизированный источник данных.</span><span class="sxs-lookup"><span data-stu-id="992e8-108">Second, the <xref:System.Windows.Forms.BindingSource> component can act as a strongly typed data source.</span></span> <span data-ttu-id="992e8-109">Добавление типа в компонент <xref:System.Windows.Forms.BindingSource> с методом <xref:System.Windows.Forms.BindingSource.Add%2A> создает список этого типа.</span><span class="sxs-lookup"><span data-stu-id="992e8-109">Adding a type to the <xref:System.Windows.Forms.BindingSource> component with the <xref:System.Windows.Forms.BindingSource.Add%2A> method creates a list of that type.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="992e8-110">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="992e8-110">In This Section</span></span>  
 [<span data-ttu-id="992e8-111">Общие сведения о компоненте BindingSource</span><span class="sxs-lookup"><span data-stu-id="992e8-111">BindingSource Component Overview</span></span>](bindingsource-component-overview.md)  
 <span data-ttu-id="992e8-112">Основные понятия, связанные с компонентом <xref:System.Windows.Forms.BindingSource>, позволяющим привязывать источник данных к элементу управления.</span><span class="sxs-lookup"><span data-stu-id="992e8-112">Introduces the general concepts of the <xref:System.Windows.Forms.BindingSource> component, which allows you to bind a data source to a control.</span></span>  
  
 [<span data-ttu-id="992e8-113">Практическое руководство. Привязка элементов управления Windows Forms к значениям DBNull</span><span class="sxs-lookup"><span data-stu-id="992e8-113">How to: Bind Windows Forms Controls to DBNull Database Values</span></span>](how-to-bind-windows-forms-controls-to-dbnull-database-values.md)  
 <span data-ttu-id="992e8-114">Показан процесс обработки значения <xref:System.DBNull> из источника данных с помощью компонента <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="992e8-114">Shows how to handle a <xref:System.DBNull> value from the data source using the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
 [<span data-ttu-id="992e8-115">Практическое руководство. Сортировка и фильтрация данных ADO.NET с помощью Windows Forms посредством компонента BindingSource</span><span class="sxs-lookup"><span data-stu-id="992e8-115">How to: Sort and Filter ADO.NET Data with the Windows Forms BindingSource Component</span></span>](sort-and-filter-ado-net-data-with-wf-bindingsource-component.md)  
 <span data-ttu-id="992e8-116">Демонстрируется использование компонента <xref:System.Windows.Forms.BindingSource> для сортировки и фильтрации отображаемых данных.</span><span class="sxs-lookup"><span data-stu-id="992e8-116">Demonstrates using the <xref:System.Windows.Forms.BindingSource> component to apply sorts and filters to displayed data.</span></span>  
  
 [<span data-ttu-id="992e8-117">Практическое руководство. Связывание веб-службой, с помощью компонента BindingSource в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="992e8-117">How to: Bind to a Web Service Using the Windows Forms BindingSource</span></span>](how-to-bind-to-a-web-service-using-the-windows-forms-bindingsource.md)  
 <span data-ttu-id="992e8-118">Демонстрируется использование компонента <xref:System.Windows.Forms.BindingSource> для привязки к веб-службе.</span><span class="sxs-lookup"><span data-stu-id="992e8-118">Shows how to use the <xref:System.Windows.Forms.BindingSource> component to bind to a Web service.</span></span>  
  
 [<span data-ttu-id="992e8-119">Практическое руководство. Обработка ошибок и исключений, происходящих при выполнении привязки данных</span><span class="sxs-lookup"><span data-stu-id="992e8-119">How to: Handle Errors and Exceptions that Occur with Databinding</span></span>](how-to-handle-errors-and-exceptions-that-occur-with-databinding.md)  
 <span data-ttu-id="992e8-120">Демонстрируется использование компонента <xref:System.Windows.Forms.BindingSource> для правильной обработки ошибок, возникающих при операциях привязки к данным.</span><span class="sxs-lookup"><span data-stu-id="992e8-120">Demonstrates using the <xref:System.Windows.Forms.BindingSource> component to gracefully handle errors that occur in a data binding operation.</span></span>  
  
 [<span data-ttu-id="992e8-121">Практическое руководство. Привязка элемента управления Windows Forms к типу</span><span class="sxs-lookup"><span data-stu-id="992e8-121">How to: Bind a Windows Forms Control to a Type</span></span>](how-to-bind-a-windows-forms-control-to-a-type.md)  
 <span data-ttu-id="992e8-122">Демонстрируется использование компонента <xref:System.Windows.Forms.BindingSource> для привязки к типу.</span><span class="sxs-lookup"><span data-stu-id="992e8-122">Demonstrates using a <xref:System.Windows.Forms.BindingSource> component to bind to a type.</span></span>  
  
 [<span data-ttu-id="992e8-123">Практическое руководство. Связывание элемента управления Windows Forms к объекту фабрики</span><span class="sxs-lookup"><span data-stu-id="992e8-123">How to: Bind a Windows Forms Control to a Factory Object</span></span>](how-to-bind-a-windows-forms-control-to-a-factory-object.md)  
 <span data-ttu-id="992e8-124">Демонстрируется использование компонента <xref:System.Windows.Forms.BindingSource> для привязки к объекту-фабрике или методу.</span><span class="sxs-lookup"><span data-stu-id="992e8-124">Demonstrates using a <xref:System.Windows.Forms.BindingSource> component to bind to a factory object or method.</span></span>  
  
 [<span data-ttu-id="992e8-125">Практическое руководство. Настройка добавления элемента с помощью компонента BindingSource в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="992e8-125">How to: Customize Item Addition with the Windows Forms BindingSource</span></span>](how-to-customize-item-addition-with-the-windows-forms-bindingsource.md)  
 <span data-ttu-id="992e8-126">Демонстрируется использование компонента <xref:System.Windows.Forms.BindingSource> для создания элементов и добавления их в источник данных. </span><span class="sxs-lookup"><span data-stu-id="992e8-126">Demonstrates using a <xref:System.Windows.Forms.BindingSource> component to create new items and add them to a data source.</span></span>  
  
 [<span data-ttu-id="992e8-127">Практическое руководство. Получение уведомления об изменении, с использованием метода ResetItem компонента BindingSource</span><span class="sxs-lookup"><span data-stu-id="992e8-127">How to: Raise Change Notifications Using the BindingSource ResetItem Method</span></span>](how-to-raise-change-notifications-using-the-bindingsource-resetitem-method.md)  
 <span data-ttu-id="992e8-128">Демонстрируется использование компонента <xref:System.Windows.Forms.BindingSource> для инициирования событий уведомления об изменениях для источников данных, не поддерживающих уведомление об изменениях.</span><span class="sxs-lookup"><span data-stu-id="992e8-128">Demonstrates using a <xref:System.Windows.Forms.BindingSource> component to raise change-notification events for data sources that do not support change notification.</span></span>  
  
 [<span data-ttu-id="992e8-129">Практическое руководство. Получение уведомления об изменении с помощью компонента BindingSource и интерфейса INotifyPropertyChanged</span><span class="sxs-lookup"><span data-stu-id="992e8-129">How to: Raise Change Notifications Using a BindingSource and the INotifyPropertyChanged Interface</span></span>](raise-change-notifications--bindingsource.md)  
 <span data-ttu-id="992e8-130">Демонстрируется использование типа, наследуемого от <xref:System.ComponentModel.INotifyPropertyChanged>, с элементом управления <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="992e8-130">Demonstrates how to use a type that inherits from the <xref:System.ComponentModel.INotifyPropertyChanged> with a <xref:System.Windows.Forms.BindingSource> control.</span></span>  
  
 [<span data-ttu-id="992e8-131">Практическое руководство. Отражение обновились в источнике данных в элементе управления Windows Forms с использованием компонента BindingSource</span><span class="sxs-lookup"><span data-stu-id="992e8-131">How to: Reflect Data Source Updates in a Windows Forms Control with the BindingSource</span></span>](reflect-data-source-updates-in-a-wf-control-with-the-bindingsource.md)  
 <span data-ttu-id="992e8-132">Показано, как обеспечить реакцию на изменения в источнике данных с помощью компонента <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="992e8-132">Demonstrates how to respond to changes in the data source using the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
 [<span data-ttu-id="992e8-133">Практическое руководство. Совместное использование связанных данных в нескольких формах с помощью компонента BindingSource</span><span class="sxs-lookup"><span data-stu-id="992e8-133">How to: Share Bound Data Across Forms Using the BindingSource Component</span></span>](how-to-share-bound-data-across-forms-using-the-bindingsource-component.md)  
 <span data-ttu-id="992e8-134">Демонстрируется использование компонента <xref:System.Windows.Forms.BindingSource> для привязки нескольких форм к одному и тому же источнику данных.</span><span class="sxs-lookup"><span data-stu-id="992e8-134">Shows how to use the <xref:System.Windows.Forms.BindingSource> to bind multiple forms to the same data source.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="992e8-135">Ссылка</span><span class="sxs-lookup"><span data-stu-id="992e8-135">Reference</span></span>  
 <xref:System.Windows.Forms.BindingSource>  
 <span data-ttu-id="992e8-136">Содержит справочную документацию по компоненту <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="992e8-136">Provides reference documentation for the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
 <xref:System.Windows.Forms.BindingNavigator>  
 <span data-ttu-id="992e8-137">Справочная документация по элементу управления <xref:System.Windows.Forms.BindingNavigator>.</span><span class="sxs-lookup"><span data-stu-id="992e8-137">Provides reference documentation for the <xref:System.Windows.Forms.BindingNavigator> control.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="992e8-138">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="992e8-138">Related Sections</span></span>  
 [<span data-ttu-id="992e8-139">Привязка данных Windows Forms</span><span class="sxs-lookup"><span data-stu-id="992e8-139">Windows Forms Data Binding</span></span>](../windows-forms-data-binding.md)  
 <span data-ttu-id="992e8-140">Содержит ссылки на разделы, в которых описывается архитектура привязки к данным в Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="992e8-140">Contains links to topics describing the Windows Forms data binding architecture.</span></span>  
  
 <span data-ttu-id="992e8-141">См. также [Привязка элементов управления к данным в Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="992e8-141">Also see [Bind controls to data in Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio).</span></span>
