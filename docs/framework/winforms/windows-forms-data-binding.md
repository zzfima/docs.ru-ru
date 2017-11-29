---
title: "Привязка данных Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data [Windows Forms]
- Windows Forms, data binding
- data [Windows Forms], architecture
- Windows Forms controls, data binding
ms.assetid: c3826d8e-ea25-4ad4-a669-45bfb19192aa
caps.latest.revision: "25"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 60a9f66fec64ceda71dd5b70211b897c84113429
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
---
# <a name="windows-forms-data-binding"></a><span data-ttu-id="7efbd-102">Привязка данных Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7efbd-102">Windows Forms Data Binding</span></span>
<span data-ttu-id="7efbd-103">Привязка данных в Windows Forms дает возможность отображать и изменять информацию из источника данных в элементах управления в форме.</span><span class="sxs-lookup"><span data-stu-id="7efbd-103">Data binding in Windows Forms gives you the means to display and make changes to information from a data source in controls on the form.</span></span> <span data-ttu-id="7efbd-104">В Windows Forms можно выполнить привязку не только к традиционным источникам данных, но и к практически к любой структуре, содержащий данные.</span><span class="sxs-lookup"><span data-stu-id="7efbd-104">You can bind to both traditional data sources as well as almost any structure that contains data.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7efbd-105">Содержание</span><span class="sxs-lookup"><span data-stu-id="7efbd-105">In This Section</span></span>  
 [<span data-ttu-id="7efbd-106">Привязка данных и Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7efbd-106">Data Binding and Windows Forms</span></span>](../../../docs/framework/winforms/data-binding-and-windows-forms.md)  
 <span data-ttu-id="7efbd-107">Общие сведения о привязке данных в Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="7efbd-107">Provides an overview of data binding in Windows Forms.</span></span>  
  
 [<span data-ttu-id="7efbd-108">Источники данных, поддерживаемые Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7efbd-108">Data Sources Supported by Windows Forms</span></span>](../../../docs/framework/winforms/data-sources-supported-by-windows-forms.md)  
 <span data-ttu-id="7efbd-109">Описывает источники данных, которые можно использовать с Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="7efbd-109">Describes the data sources that can be used with Windows Forms.</span></span>  
  
 [<span data-ttu-id="7efbd-110">Интерфейсы, относящиеся к привязке данных</span><span class="sxs-lookup"><span data-stu-id="7efbd-110">Interfaces Related to Data Binding</span></span>](../../../docs/framework/winforms/interfaces-related-to-data-binding.md)  
 <span data-ttu-id="7efbd-111">Описывает некоторые интерфейсы, используемые для привязки данных Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="7efbd-111">Describes several of the interfaces used with Windows Forms data binding.</span></span>  
  
 [<span data-ttu-id="7efbd-112">Практическое руководство. Навигация по набору данных, отображаемых в форме Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7efbd-112">How to: Navigate Data in Windows Forms</span></span>](../../../docs/framework/winforms/how-to-navigate-data-in-windows-forms.md)  
 <span data-ttu-id="7efbd-113">Показано, как перемещаться по элементам в источнике данных.</span><span class="sxs-lookup"><span data-stu-id="7efbd-113">Shows how to navigate through items in a data source.</span></span>  
  
 [<span data-ttu-id="7efbd-114">Уведомления об изменениях в привязке данных Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7efbd-114">Change Notification in Windows Forms Data Binding</span></span>](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)  
 <span data-ttu-id="7efbd-115">Описывает различные типы уведомлений об изменении для привязки данных Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="7efbd-115">Describes different types of change notification for Windows Forms data binding.</span></span>  
  
 [<span data-ttu-id="7efbd-116">Практическое руководство. Реализация интерфейса INotifyPropertyChanged</span><span class="sxs-lookup"><span data-stu-id="7efbd-116">How to: Implement the INotifyPropertyChanged Interface</span></span>](../../../docs/framework/winforms/how-to-implement-the-inotifypropertychanged-interface.md)  
 <span data-ttu-id="7efbd-117">Показано, как реализовать интерфейс <xref:System.ComponentModel.INotifyPropertyChanged>.</span><span class="sxs-lookup"><span data-stu-id="7efbd-117">Shows how to implement the <xref:System.ComponentModel.INotifyPropertyChanged> interface.</span></span> <span data-ttu-id="7efbd-118">Этот интерфейс сообщает связанному элементу управления об изменениях свойств бизнес-объекта</span><span class="sxs-lookup"><span data-stu-id="7efbd-118">The interface  communicates to a bound control the property changes on a business object</span></span>  
  
 [<span data-ttu-id="7efbd-119">Практическое руководство. Применение шаблона PropertyNameChanged</span><span class="sxs-lookup"><span data-stu-id="7efbd-119">How to: Apply the PropertyNameChanged Pattern</span></span>](../../../docs/framework/winforms/how-to-apply-the-propertynamechanged-pattern.md)  
 <span data-ttu-id="7efbd-120">Показано, как применить *PropertyName*шаблон Changed к свойствам пользовательского элемента управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="7efbd-120">Shows how to apply the *PropertyName*Changed pattern to properties of a Windows Forms user control.</span></span>  
  
 [<span data-ttu-id="7efbd-121">Практическое руководство. Реализация интерфейса ITypedList</span><span class="sxs-lookup"><span data-stu-id="7efbd-121">How to: Implement the ITypedList Interface</span></span>](../../../docs/framework/winforms/how-to-implement-the-itypedlist-interface.md)  
 <span data-ttu-id="7efbd-122">Показано, как задействовать обнаружение схемы для связываемого списка путем реализации интерфейса <xref:System.ComponentModel.ITypedList>.</span><span class="sxs-lookup"><span data-stu-id="7efbd-122">Shows how to enable discovery of the schema for a bindable list by implementing the <xref:System.ComponentModel.ITypedList> interface.</span></span>  
  
 [<span data-ttu-id="7efbd-123">Практическое руководство. Реализация интерфейса IListSource</span><span class="sxs-lookup"><span data-stu-id="7efbd-123">How to: Implement the IListSource Interface</span></span>](../../../docs/framework/winforms/how-to-implement-the-ilistsource-interface.md)  
 <span data-ttu-id="7efbd-124">Показано, как реализовать интерфейс <xref:System.ComponentModel.IListSource>, чтобы создать связываемый класс, который не реализует <xref:System.Collections.IList>, но предоставляет список из другого расположения.</span><span class="sxs-lookup"><span data-stu-id="7efbd-124">Shows how to implement the <xref:System.ComponentModel.IListSource> interface to create a bindable class does not implement <xref:System.Collections.IList>, but provides a list from another location.</span></span>  
  
 [<span data-ttu-id="7efbd-125">Практическое руководство. Синхронизация элементов управления, связанных с одним источником данных</span><span class="sxs-lookup"><span data-stu-id="7efbd-125">How to: Ensure Multiple Controls Bound to the Same Data Source Remain Synchronized</span></span>](../../../docs/framework/winforms/multiple-controls-bound-to-data-source-synchronized.md)  
 <span data-ttu-id="7efbd-126">Показано, как обрабатывать событие <xref:System.Windows.Forms.BindingSource.BindingComplete> для обеспечения синхронизация всех элементов управления, привязанных к источнику данных.</span><span class="sxs-lookup"><span data-stu-id="7efbd-126">Shows how to handle the <xref:System.Windows.Forms.BindingSource.BindingComplete> event to ensure all controls bound to a data source remain synchronized.</span></span>  
  
 [<span data-ttu-id="7efbd-127">Практическое руководство. Правильное позиционирование выделенной строки в дочерней таблице</span><span class="sxs-lookup"><span data-stu-id="7efbd-127">How to: Ensure the Selected Row in a Child Table Remains at the Correct Position</span></span>](../../../docs/framework/winforms/ensure-the-selected-row-in-a-child-table-correct.md)  
 <span data-ttu-id="7efbd-128">Показано, как обеспечить сохранение позиции выбранной строки дочерней таблицы при изменении поля родительской таблицы.</span><span class="sxs-lookup"><span data-stu-id="7efbd-128">Shows how to ensure the selected row of a child table does not change, when a change is made to a field of the parent table.</span></span>  
  
 <span data-ttu-id="7efbd-129">См. также [интерфейсы, связанные с привязкой данных](http://msdn.microsoft.com/library/41e17s4b\(v=vs.110\)), [как: перемещения данных в Windows Forms](http://msdn.microsoft.com/library/b63ha24w\(v=vs.110\)), [как: Создание элемента управления простой привязкой в форме Windows](http://msdn.microsoft.com/library/sw223a62\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="7efbd-129">Also see [Interfaces Related to Data Binding](http://msdn.microsoft.com/library/41e17s4b\(v=vs.110\)), [How to: Navigate Data in Windows Forms](http://msdn.microsoft.com/library/b63ha24w\(v=vs.110\)), [How to: Create a Simple-Bound Control on a Windows Form](http://msdn.microsoft.com/library/sw223a62\(v=vs.110\)).</span></span>  
  
## <a name="reference"></a><span data-ttu-id="7efbd-130">Ссылка</span><span class="sxs-lookup"><span data-stu-id="7efbd-130">Reference</span></span>  
 <xref:System.Windows.Forms.Binding?displayProperty=nameWithType>  
 <span data-ttu-id="7efbd-131">Описывает класс, представляющий привязку связываемых компонентов к источнику данных.</span><span class="sxs-lookup"><span data-stu-id="7efbd-131">Describes the class that represents the binding between a bindable component and a data source.</span></span>  
  
 <xref:System.Windows.Forms.BindingSource?displayProperty=nameWithType>  
 <span data-ttu-id="7efbd-132">Описывает класс, инкапсулирующий источник данных для привязки к элементам управления.</span><span class="sxs-lookup"><span data-stu-id="7efbd-132">Describes the class that encapsulates a data source for binding to controls.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="7efbd-133">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="7efbd-133">Related Sections</span></span>  
 [<span data-ttu-id="7efbd-134">Компонент BindingSource</span><span class="sxs-lookup"><span data-stu-id="7efbd-134">BindingSource Component</span></span>](../../../docs/framework/winforms/controls/bindingsource-component.md)  
 <span data-ttu-id="7efbd-135">Содержит список разделов, описывающих использование компонента <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="7efbd-135">Contains a list of topics that demonstrate how to use the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
 [<span data-ttu-id="7efbd-136">Элемент управления DataGridView</span><span class="sxs-lookup"><span data-stu-id="7efbd-136">DataGridView Control</span></span>](../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)  
 <span data-ttu-id="7efbd-137">Предоставляет список разделов, в которых демонстрируется использование связываемого элемента управления datagrid.</span><span class="sxs-lookup"><span data-stu-id="7efbd-137">Provides a list of topics that demonstrate how to use a bindable datagrid control.</span></span>  
  
 <span data-ttu-id="7efbd-138">См. также [доступ к данным в Visual Studio](/visualstudio/data-tools/accessing-data-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="7efbd-138">Also see [Accessing Data in Visual Studio](/visualstudio/data-tools/accessing-data-in-visual-studio).</span></span>
