---
title: "Компонент BindingSource"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data binding [Windows Forms], Windows Forms
- Windows Forms, data binding control
- BindingSource component [Windows Forms]
ms.assetid: 3e2faf4c-f5b8-4fa6-9fbc-f59c37ec2fb9
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 006cafafdf8e3c3f4da77394d6155fa52e113b58
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
---
# <a name="bindingsource-component"></a><span data-ttu-id="149ee-102">Компонент BindingSource</span><span class="sxs-lookup"><span data-stu-id="149ee-102">BindingSource Component</span></span>
<span data-ttu-id="149ee-103">Инкапсулирует источник данных для привязки к элементам управления.</span><span class="sxs-lookup"><span data-stu-id="149ee-103">Encapsulates a data source for binding to controls.</span></span>  
  
 <span data-ttu-id="149ee-104">Компонент <xref:System.Windows.Forms.BindingSource> служит двум целям.</span><span class="sxs-lookup"><span data-stu-id="149ee-104">The <xref:System.Windows.Forms.BindingSource> component serves two purposes.</span></span> <span data-ttu-id="149ee-105">Во-первых, он обеспечивает уровень косвенного обращения при выполнении привязки элементов управления в форме к данным.</span><span class="sxs-lookup"><span data-stu-id="149ee-105">First, it provides a layer of indirection when binding the controls on a form to data.</span></span> <span data-ttu-id="149ee-106">Это достигается путем привязки компонента <xref:System.Windows.Forms.BindingSource> к источнику данных и последующей привязки элементов управления в форме к компоненту <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="149ee-106">This is accomplished by binding the <xref:System.Windows.Forms.BindingSource> component to your data source, and then binding the controls on your form to the <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="149ee-107">Все последующие взаимодействия с данными, включая перемещение, сортировку, фильтрацию и обновление, осуществляются с помощью вызовов компонента <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="149ee-107">All further interaction with the data, including navigating, sorting, filtering, and updating, is accomplished with calls to the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
 <span data-ttu-id="149ee-108">Во-вторых, компонент <xref:System.Windows.Forms.BindingSource> может действовать как строго типизированный источник данных.</span><span class="sxs-lookup"><span data-stu-id="149ee-108">Second, the <xref:System.Windows.Forms.BindingSource> component can act as a strongly typed data source.</span></span> <span data-ttu-id="149ee-109">Добавление типа в компонент <xref:System.Windows.Forms.BindingSource> с методом <xref:System.Windows.Forms.BindingSource.Add%2A> создает список этого типа.</span><span class="sxs-lookup"><span data-stu-id="149ee-109">Adding a type to the <xref:System.Windows.Forms.BindingSource> component with the <xref:System.Windows.Forms.BindingSource.Add%2A> method creates a list of that type.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="149ee-110">Содержание</span><span class="sxs-lookup"><span data-stu-id="149ee-110">In This Section</span></span>  
 [<span data-ttu-id="149ee-111">Общие сведения о компоненте BindingSource</span><span class="sxs-lookup"><span data-stu-id="149ee-111">BindingSource Component Overview</span></span>](../../../../docs/framework/winforms/controls/bindingsource-component-overview.md)  
 <span data-ttu-id="149ee-112">Основные понятия, связанные с компонентом <xref:System.Windows.Forms.BindingSource>, позволяющим привязывать источник данных к элементу управления.</span><span class="sxs-lookup"><span data-stu-id="149ee-112">Introduces the general concepts of the <xref:System.Windows.Forms.BindingSource> component, which allows you to bind a data source to a control.</span></span>  
  
 [<span data-ttu-id="149ee-113">Практическое руководство. Привязка элементов управления Windows Forms к значениям DBNull</span><span class="sxs-lookup"><span data-stu-id="149ee-113">How to: Bind Windows Forms Controls to DBNull Database Values</span></span>](../../../../docs/framework/winforms/controls/how-to-bind-windows-forms-controls-to-dbnull-database-values.md)  
 <span data-ttu-id="149ee-114">Показан процесс обработки значения <xref:System.DBNull> из источника данных с помощью компонента <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="149ee-114">Shows how to handle a <xref:System.DBNull> value from the data source using the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
 [<span data-ttu-id="149ee-115">Практическое руководство. Сортировка и фильтрация данных ADO.NET с помощью компонента BindingSource в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="149ee-115">How to: Sort and Filter ADO.NET Data with the Windows Forms BindingSource Component</span></span>](../../../../docs/framework/winforms/controls/sort-and-filter-ado-net-data-with-wf-bindingsource-component.md)  
 <span data-ttu-id="149ee-116">Демонстрируется использование компонента <xref:System.Windows.Forms.BindingSource> для сортировки и фильтрации отображаемых данных.</span><span class="sxs-lookup"><span data-stu-id="149ee-116">Demonstrates using the <xref:System.Windows.Forms.BindingSource> component to apply sorts and filters to displayed data.</span></span>  
  
 [<span data-ttu-id="149ee-117">Практическое руководство. Связывание с веб-службой с помощью компонента BindingSource в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="149ee-117">How to: Bind to a Web Service Using the Windows Forms BindingSource</span></span>](../../../../docs/framework/winforms/controls/how-to-bind-to-a-web-service-using-the-windows-forms-bindingsource.md)  
 <span data-ttu-id="149ee-118">Демонстрируется использование компонента <xref:System.Windows.Forms.BindingSource> для привязки к веб-службе.</span><span class="sxs-lookup"><span data-stu-id="149ee-118">Shows how to use the <xref:System.Windows.Forms.BindingSource> component to bind to a Web service.</span></span>  
  
 [<span data-ttu-id="149ee-119">Практическое руководство. Обработка ошибок и исключений, происходящих при связывании элементов управления с данными</span><span class="sxs-lookup"><span data-stu-id="149ee-119">How to: Handle Errors and Exceptions that Occur with Databinding</span></span>](../../../../docs/framework/winforms/controls/how-to-handle-errors-and-exceptions-that-occur-with-databinding.md)  
 <span data-ttu-id="149ee-120">Демонстрируется использование компонента <xref:System.Windows.Forms.BindingSource> для правильной обработки ошибок, возникающих при операциях привязки к данным.</span><span class="sxs-lookup"><span data-stu-id="149ee-120">Demonstrates using the <xref:System.Windows.Forms.BindingSource> component to gracefully handle errors that occur in a data binding operation.</span></span>  
  
 [<span data-ttu-id="149ee-121">Практическое руководство. Связывание элемента управления с типом в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="149ee-121">How to: Bind a Windows Forms Control to a Type</span></span>](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md)  
 <span data-ttu-id="149ee-122">Демонстрируется использование компонента <xref:System.Windows.Forms.BindingSource> для привязки к типу.</span><span class="sxs-lookup"><span data-stu-id="149ee-122">Demonstrates using a <xref:System.Windows.Forms.BindingSource> component to bind to a type.</span></span>  
  
 [<span data-ttu-id="149ee-123">Практическое руководство. Связывание элемента управления с объектом-фабрикой в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="149ee-123">How to: Bind a Windows Forms Control to a Factory Object</span></span>](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-factory-object.md)  
 <span data-ttu-id="149ee-124">Демонстрируется использование компонента <xref:System.Windows.Forms.BindingSource> для привязки к объекту-фабрике или методу.</span><span class="sxs-lookup"><span data-stu-id="149ee-124">Demonstrates using a <xref:System.Windows.Forms.BindingSource> component to bind to a factory object or method.</span></span>  
  
 [<span data-ttu-id="149ee-125">Практическое руководство. Настройка дополнений к элементам с помощью элемента управления BindingSource в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="149ee-125">How to: Customize Item Addition with the Windows Forms BindingSource</span></span>](../../../../docs/framework/winforms/controls/how-to-customize-item-addition-with-the-windows-forms-bindingsource.md)  
 <span data-ttu-id="149ee-126">Демонстрируется использование компонента <xref:System.Windows.Forms.BindingSource> для создания элементов и добавления их в источник данных. </span><span class="sxs-lookup"><span data-stu-id="149ee-126">Demonstrates using a <xref:System.Windows.Forms.BindingSource> component to create new items and add them to a data source.</span></span>  
  
 [<span data-ttu-id="149ee-127">Практическое руководство. Уведомление об изменении данных с использованием метода ResetItem компонента BindingSource</span><span class="sxs-lookup"><span data-stu-id="149ee-127">How to: Raise Change Notifications Using the BindingSource ResetItem Method</span></span>](../../../../docs/framework/winforms/controls/how-to-raise-change-notifications-using-the-bindingsource-resetitem-method.md)  
 <span data-ttu-id="149ee-128">Демонстрируется использование компонента <xref:System.Windows.Forms.BindingSource> для инициирования событий уведомления об изменениях для источников данных, не поддерживающих уведомление об изменениях.</span><span class="sxs-lookup"><span data-stu-id="149ee-128">Demonstrates using a <xref:System.Windows.Forms.BindingSource> component to raise change-notification events for data sources that do not support change notification.</span></span>  
  
 [<span data-ttu-id="149ee-129">Практическое руководство. Получение уведомления об изменении данных с использованием компонента BindingSource и интерфейса INotifyPropertyChanged</span><span class="sxs-lookup"><span data-stu-id="149ee-129">How to: Raise Change Notifications Using a BindingSource and the INotifyPropertyChanged Interface</span></span>](../../../../docs/framework/winforms/controls/raise-change-notifications--bindingsource.md)  
 <span data-ttu-id="149ee-130">Демонстрируется использование типа, наследуемого от <xref:System.ComponentModel.INotifyPropertyChanged>, с элементом управления <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="149ee-130">Demonstrates how to use a type that inherits from the <xref:System.ComponentModel.INotifyPropertyChanged> with a <xref:System.Windows.Forms.BindingSource> control.</span></span>  
  
 [<span data-ttu-id="149ee-131">Практическое руководство. Отражение в элементе управления данных, которые обновились в источнике, с использованием компонента BindingSource в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="149ee-131">How to: Reflect Data Source Updates in a Windows Forms Control with the BindingSource</span></span>](../../../../docs/framework/winforms/controls/reflect-data-source-updates-in-a-wf-control-with-the-bindingsource.md)  
 <span data-ttu-id="149ee-132">Показано, как обеспечить реакцию на изменения в источнике данных с помощью компонента <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="149ee-132">Demonstrates how to respond to changes in the data source using the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
 [<span data-ttu-id="149ee-133">Практическое руководство. Совместное использование одних и тех же данных в нескольких формах посредством компонента BindingSource</span><span class="sxs-lookup"><span data-stu-id="149ee-133">How to: Share Bound Data Across Forms Using the BindingSource Component</span></span>](../../../../docs/framework/winforms/controls/how-to-share-bound-data-across-forms-using-the-bindingsource-component.md)  
 <span data-ttu-id="149ee-134">Демонстрируется использование компонента <xref:System.Windows.Forms.BindingSource> для привязки нескольких форм к одному и тому же источнику данных.</span><span class="sxs-lookup"><span data-stu-id="149ee-134">Shows how to use the <xref:System.Windows.Forms.BindingSource> to bind multiple forms to the same data source.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="149ee-135">Ссылка</span><span class="sxs-lookup"><span data-stu-id="149ee-135">Reference</span></span>  
 <xref:System.Windows.Forms.BindingSource>  
 <span data-ttu-id="149ee-136">Содержит справочную документацию по компоненту <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="149ee-136">Provides reference documentation for the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
 <xref:System.Windows.Forms.BindingNavigator>  
 <span data-ttu-id="149ee-137">Содержит справочную документацию по элементу управления <xref:System.Windows.Forms.BindingNavigator>.</span><span class="sxs-lookup"><span data-stu-id="149ee-137">Provides reference documentation for the <xref:System.Windows.Forms.BindingNavigator> control.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="149ee-138">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="149ee-138">Related Sections</span></span>  
 [<span data-ttu-id="149ee-139">Привязка данных Windows Forms</span><span class="sxs-lookup"><span data-stu-id="149ee-139">Windows Forms Data Binding</span></span>](../../../../docs/framework/winforms/windows-forms-data-binding.md)  
 <span data-ttu-id="149ee-140">Содержит ссылки на разделы, в которых описывается архитектура привязки к данным в Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="149ee-140">Contains links to topics describing the Windows Forms data binding architecture.</span></span>  
  
 <span data-ttu-id="149ee-141">См. также [Привязка элементов управления к данным в Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="149ee-141">Also see [Bind controls to data in Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio).</span></span>
