---
title: "Практическое руководство. Настройка уведомлений обновлений привязок"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- notifications [WPF], binding updates
- data binding [WPF], notification of binding updates
- binding [WPF], updates [WPF], notifications of
ms.assetid: 5673073e-dbe1-49da-980a-484a88f9595a
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a07337e99e985bfbc0a5dbc5f2d231ee36cf1422
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-up-notification-of-binding-updates"></a><span data-ttu-id="e5671-102">Практическое руководство. Настройка уведомлений обновлений привязок</span><span class="sxs-lookup"><span data-stu-id="e5671-102">How to: Set Up Notification of Binding Updates</span></span>
<span data-ttu-id="e5671-103">В этом примере показано, как настроить уведомления об обновлении свойства цели привязки (целевой) или источника привязки (источник) для привязки.</span><span class="sxs-lookup"><span data-stu-id="e5671-103">This example shows how to set up to be notified when the binding target (target) or the binding source (source) property of a binding has been updated.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e5671-104">Пример</span><span class="sxs-lookup"><span data-stu-id="e5671-104">Example</span></span>  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]<span data-ttu-id="e5671-105">вызывает событие обновления данных каждый раз при обновлении источника или цели привязки.</span><span class="sxs-lookup"><span data-stu-id="e5671-105"> raises a data update event each time that the binding source or target has been updated.</span></span> <span data-ttu-id="e5671-106">Внутри системы это событие используется для информирования [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)], что он должен быть обновлен, поскольку связанные данные были изменены.</span><span class="sxs-lookup"><span data-stu-id="e5671-106">Internally, this event is used to inform the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] that it should update, because the bound data has changed.</span></span> <span data-ttu-id="e5671-107">Обратите внимание, что для работы этих событий, а также для односторонняя или двусторонняя привязка для правильной работы необходимо реализовать класс данных с помощью <xref:System.ComponentModel.INotifyPropertyChanged> интерфейса.</span><span class="sxs-lookup"><span data-stu-id="e5671-107">Note that for these events to work, and also for one-way or two-way binding to work properly, you need to implement your data class using the <xref:System.ComponentModel.INotifyPropertyChanged> interface.</span></span> <span data-ttu-id="e5671-108">Дополнительные сведения см. в разделе [Реализация уведомления об изменении свойств](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md).</span><span class="sxs-lookup"><span data-stu-id="e5671-108">For more information, see [Implement Property Change Notification](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md).</span></span>  
  
 <span data-ttu-id="e5671-109">Задать <xref:System.Windows.Data.Binding.NotifyOnTargetUpdated%2A> или <xref:System.Windows.Data.Binding.NotifyOnSourceUpdated%2A> (или оба) для `true` в привязке.</span><span class="sxs-lookup"><span data-stu-id="e5671-109">Set the <xref:System.Windows.Data.Binding.NotifyOnTargetUpdated%2A> or <xref:System.Windows.Data.Binding.NotifyOnSourceUpdated%2A> property (or both) to `true` in the binding.</span></span> <span data-ttu-id="e5671-110">Обработчик, который предоставляется для ожидания данного события, должен быть подключен непосредственно к элементу, где вы хотите получать сведения об изменениях, или к контексту общих данных, чтобы получить информацию о любом изменении в контексте.</span><span class="sxs-lookup"><span data-stu-id="e5671-110">The handler you provide to listen for this event must be attached directly to the element where you want to be informed of changes, or to the overall data context if you want to be aware that anything in the context has changed.</span></span>  
  
 <span data-ttu-id="e5671-111">Ниже приведен пример, в котором показано, как настроить уведомления при обновлении свойства цели привязки.</span><span class="sxs-lookup"><span data-stu-id="e5671-111">Here is an example that shows how to set up for notification when a target property has been updated.</span></span>  
  
 [!code-xaml[DirectionalBinding#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#2)]  
  
 <span data-ttu-id="e5671-112">Затем можно назначить обработчик, основанный на делегате EventHandler\<T>, в этом примере *OnTargetUpdated*, для обработки события:</span><span class="sxs-lookup"><span data-stu-id="e5671-112">You can then assign a handler based on the EventHandler\<T> delegate, *OnTargetUpdated* in this example, to handle the event:</span></span>  
  
 [!code-csharp[DirectionalBinding#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml.cs#3)]  
[!code-csharp[DirectionalBinding#EndEvent](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml.cs#endevent)]  
  
 <span data-ttu-id="e5671-113">Параметры события можно использовать для задания сведений об измененном свойстве (например, типа или конкретного элемента, если один обработчик подключен к нескольким элементам), что может оказаться полезным в том случае, если существует несколько связанных свойств для одного элемента.</span><span class="sxs-lookup"><span data-stu-id="e5671-113">Parameters of the event can be used to determine details about the property that changed (such as the type or the specific element if the same handler is attached to more than one element), which can be useful if there are multiple bound properties on a single element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5671-114">См. также</span><span class="sxs-lookup"><span data-stu-id="e5671-114">See Also</span></span>  
 [<span data-ttu-id="e5671-115">Общие сведения о привязке данных</span><span class="sxs-lookup"><span data-stu-id="e5671-115">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="e5671-116">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="e5671-116">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
