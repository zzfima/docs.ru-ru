---
title: "Практическое руководство. Навигация по набору данных, отображаемых в форме Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cursors [Windows Forms], data sources
- data sources [Windows Forms], Windows Forms
- Windows Forms, navigating
- CurrencyManager class [Windows Forms], navigating Windows Forms data
- data [Windows Forms], navigating
ms.assetid: 97360f7b-b181-4084-966a-4c62518f735b
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7c754bba18e93f63306701381f66af04b593c473
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-navigate-data-in-windows-forms"></a><span data-ttu-id="5cb3d-102">Практическое руководство. Навигация по набору данных, отображаемых в форме Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5cb3d-102">How to: Navigate Data in Windows Forms</span></span>
<span data-ttu-id="5cb3d-103">Самым простым способом перемещения по записям в источнике данных в приложении Windows является привязка <xref:System.Windows.Forms.BindingSource> компонент источника данных, а затем привязать элементы управления к <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="5cb3d-103">In a Windows application, the easiest way to navigate through records in a data source is to bind a <xref:System.Windows.Forms.BindingSource> component to the data source and then bind controls to the <xref:System.Windows.Forms.BindingSource>.</span></span> <span data-ttu-id="5cb3d-104">Затем можно использовать встроенные методы навигации на <xref:System.Windows.Forms.BindingSource> такие <xref:System.Windows.Forms.BindingSource.MoveNext%2A>, <xref:System.Windows.Forms.BindingSource.MoveLast%2A>, <xref:System.Windows.Forms.BindingSource.MovePrevious%2A> и <xref:System.Windows.Forms.BindingSource.MoveFirst%2A>.</span><span class="sxs-lookup"><span data-stu-id="5cb3d-104">You can then use the built-in navigation method on the <xref:System.Windows.Forms.BindingSource> such a <xref:System.Windows.Forms.BindingSource.MoveNext%2A>, <xref:System.Windows.Forms.BindingSource.MoveLast%2A>, <xref:System.Windows.Forms.BindingSource.MovePrevious%2A> and <xref:System.Windows.Forms.BindingSource.MoveFirst%2A>.</span></span> <span data-ttu-id="5cb3d-105">С помощью этих методов настроит <xref:System.Windows.Forms.BindingSource.Position%2A> и <xref:System.Windows.Forms.BindingSource.Current%2A> свойства <xref:System.Windows.Forms.BindingSource> соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="5cb3d-105">Using these methods will adjust the <xref:System.Windows.Forms.BindingSource.Position%2A> and <xref:System.Windows.Forms.BindingSource.Current%2A> properties of the <xref:System.Windows.Forms.BindingSource> appropriately.</span></span> <span data-ttu-id="5cb3d-106">Можно также найти элемент и задать его в качестве текущего элемента, задав <xref:System.Windows.Forms.BindingSource.Position%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="5cb3d-106">You can also find an item and set it as the current item by setting the <xref:System.Windows.Forms.BindingSource.Position%2A> property.</span></span>  
  
### <a name="to-increment-the-position-in-a-data-source"></a><span data-ttu-id="5cb3d-107">Увеличение позиции в источнике данных</span><span class="sxs-lookup"><span data-stu-id="5cb3d-107">To increment the position in a data source</span></span>  
  
1.  <span data-ttu-id="5cb3d-108">Задать <xref:System.Windows.Forms.BindingSource.Position%2A> свойство <xref:System.Windows.Forms.BindingSource> для позиции записи, чтобы перейти на связанных данных.</span><span class="sxs-lookup"><span data-stu-id="5cb3d-108">Set the <xref:System.Windows.Forms.BindingSource.Position%2A> property of the <xref:System.Windows.Forms.BindingSource> for your bound data to the record position to go to.</span></span> <span data-ttu-id="5cb3d-109">В следующем примере демонстрируется использование <xref:System.Windows.Forms.BindingSource.MoveNext%2A> метод <xref:System.Windows.Forms.BindingSource> увеличиваемого <xref:System.Windows.Forms.BindingSource.Position%2A> свойство при `nextButton` нажатии.</span><span class="sxs-lookup"><span data-stu-id="5cb3d-109">The following example illustrates using the <xref:System.Windows.Forms.BindingSource.MoveNext%2A> method of the <xref:System.Windows.Forms.BindingSource> to increment the <xref:System.Windows.Forms.BindingSource.Position%2A> property when the `nextButton` is clicked.</span></span> <span data-ttu-id="5cb3d-110"><xref:System.Windows.Forms.BindingSource> Связан с `Customers` набора данных `Northwind`.</span><span class="sxs-lookup"><span data-stu-id="5cb3d-110">The <xref:System.Windows.Forms.BindingSource> is associated with the `Customers` table of a dataset `Northwind`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5cb3d-111">Установка <xref:System.Windows.Forms.BindingSource.Position%2A> значение за пределами первой или последней записи не приводит к ошибке как [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] не позволяют задать положение значение, выходящее за пределы списка.</span><span class="sxs-lookup"><span data-stu-id="5cb3d-111">Setting the <xref:System.Windows.Forms.BindingSource.Position%2A> property to a value beyond the first or last record does not result in an error, as the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] will not allow you to set the position to a value outside the bounds of the list.</span></span> <span data-ttu-id="5cb3d-112">Если важно знать, достигнута ли первой или последней записи приложения, добавьте логику для проверки превышения количества элементов данных.</span><span class="sxs-lookup"><span data-stu-id="5cb3d-112">If it is important in your application to know whether you have gone past the first or last record, include logic to test whether you will exceed the data element count.</span></span>  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#4](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.NavigatingData#4](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#4)]  
  
### <a name="to-check-whether-you-have-passed-the-end-or-beginning"></a><span data-ttu-id="5cb3d-113">Чтобы проверить, является ли начала или конца</span><span class="sxs-lookup"><span data-stu-id="5cb3d-113">To check whether you have passed the end or beginning</span></span>  
  
1.  <span data-ttu-id="5cb3d-114">Создайте обработчик событий для события <xref:System.Windows.Forms.BindingSource.PositionChanged>.</span><span class="sxs-lookup"><span data-stu-id="5cb3d-114">Create an event handler for the <xref:System.Windows.Forms.BindingSource.PositionChanged> event.</span></span> <span data-ttu-id="5cb3d-115">В обработчике можно проверить ли предлагаемое позиция превысил счетчик элемент фактические данные.</span><span class="sxs-lookup"><span data-stu-id="5cb3d-115">In the handler, you can test whether the proposed position value has exceeded the actual data element count.</span></span>  
  
     <span data-ttu-id="5cb3d-116">В следующем примере показано, как можно проверить ли достижения последнего элемента данных.</span><span class="sxs-lookup"><span data-stu-id="5cb3d-116">The following example illustrates how you can test whether you have reached the last data element.</span></span> <span data-ttu-id="5cb3d-117">В примере, если вы находитесь на последний элемент **Далее** отключить кнопку в форме.</span><span class="sxs-lookup"><span data-stu-id="5cb3d-117">In the example, if you are at the last element, the **Next** button on the form is disabled.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5cb3d-118">Имейте в виду, что следует изменить список Навигация в коде, следует снова включить **Далее** кнопку, чтобы пользователи могли просматривать всю длину нового списка.</span><span class="sxs-lookup"><span data-stu-id="5cb3d-118">Be aware that, should you change the list you are navigating in code, you should re-enable the **Next** button, so that users may browse the entire length of the new list.</span></span> <span data-ttu-id="5cb3d-119">Кроме того, имейте в виду, указанных выше <xref:System.Windows.Forms.BindingSource.PositionChanged> событий для конкретного <xref:System.Windows.Forms.BindingSource> вы работаете с должно быть связано со своим методом обработки событий.</span><span class="sxs-lookup"><span data-stu-id="5cb3d-119">Additionally, be aware that the above <xref:System.Windows.Forms.BindingSource.PositionChanged> event for the specific <xref:System.Windows.Forms.BindingSource> you are working with needs to be associated with its event-handling method.</span></span> <span data-ttu-id="5cb3d-120">Ниже приведен пример метода обработки <xref:System.Windows.Forms.BindingSource.PositionChanged> событий:</span><span class="sxs-lookup"><span data-stu-id="5cb3d-120">The following is an example of a method for handling the <xref:System.Windows.Forms.BindingSource.PositionChanged> event:</span></span>  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.NavigatingData#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#3)]  
  
### <a name="to-find-an-item-and-set-it-as-the-current-item"></a><span data-ttu-id="5cb3d-121">Чтобы найти элемент и задать его в качестве текущего элемента</span><span class="sxs-lookup"><span data-stu-id="5cb3d-121">To find an item and set it as the current item</span></span>  
  
1.  <span data-ttu-id="5cb3d-122">Найдите запись, которую вы хотите установить в качестве текущего элемента.</span><span class="sxs-lookup"><span data-stu-id="5cb3d-122">Find the record you wish to set as the current item.</span></span> <span data-ttu-id="5cb3d-123">Это можно сделать с помощью <xref:System.Windows.Forms.BindingSource.Find%2A> метод <xref:System.Windows.Forms.BindingSource>, если источник данных реализует <xref:System.ComponentModel.IBindingList>.</span><span class="sxs-lookup"><span data-stu-id="5cb3d-123">You can do this using the <xref:System.Windows.Forms.BindingSource.Find%2A> method of the <xref:System.Windows.Forms.BindingSource>, if your data source implements <xref:System.ComponentModel.IBindingList>.</span></span> <span data-ttu-id="5cb3d-124">Некоторые примеры данных источники, реализующие <xref:System.ComponentModel.IBindingList> , <xref:System.ComponentModel.BindingList%601> и <xref:System.Data.DataView>.</span><span class="sxs-lookup"><span data-stu-id="5cb3d-124">Some examples of data sources that implement <xref:System.ComponentModel.IBindingList> are <xref:System.ComponentModel.BindingList%601> and <xref:System.Data.DataView>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#2](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.NavigatingData#2](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="5cb3d-125">См. также</span><span class="sxs-lookup"><span data-stu-id="5cb3d-125">See Also</span></span>  
 [<span data-ttu-id="5cb3d-126">Источники данных, поддерживаемые Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5cb3d-126">Data Sources Supported by Windows Forms</span></span>](../../../docs/framework/winforms/data-sources-supported-by-windows-forms.md)  
 [<span data-ttu-id="5cb3d-127">Уведомления об изменениях в привязке данных Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5cb3d-127">Change Notification in Windows Forms Data Binding</span></span>](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)  
 [<span data-ttu-id="5cb3d-128">Привязка данных и Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5cb3d-128">Data Binding and Windows Forms</span></span>](../../../docs/framework/winforms/data-binding-and-windows-forms.md)  
 [<span data-ttu-id="5cb3d-129">Привязка данных Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5cb3d-129">Windows Forms Data Binding</span></span>](../../../docs/framework/winforms/windows-forms-data-binding.md)
