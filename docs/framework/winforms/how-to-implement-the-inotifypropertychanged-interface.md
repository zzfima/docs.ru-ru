---
title: Как выполнить Реализация интерфейса INotifyPropertyChanged
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- INotifyPropertyChanged interface [Windows Forms], implementing
ms.assetid: eac428af-b43b-46ac-80d9-1a5f88658725
ms.openlocfilehash: c92406899cffa56a1001f50f89cb53303df5da39
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54560078"
---
# <a name="how-to-implement-the-inotifypropertychanged-interface"></a><span data-ttu-id="b4390-102">Как выполнить Реализация интерфейса INotifyPropertyChanged</span><span class="sxs-lookup"><span data-stu-id="b4390-102">How to: Implement the INotifyPropertyChanged Interface</span></span>
<span data-ttu-id="b4390-103">В следующем примере кода показано, как реализовать <xref:System.ComponentModel.INotifyPropertyChanged> интерфейс.</span><span class="sxs-lookup"><span data-stu-id="b4390-103">The following code example demonstrates how to implement the <xref:System.ComponentModel.INotifyPropertyChanged> interface.</span></span> <span data-ttu-id="b4390-104">Реализуйте этот интерфейс для бизнес-объектов, которые используются в привязке данных Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="b4390-104">Implement this interface on business objects that are used in Windows Forms data binding.</span></span> <span data-ttu-id="b4390-105">При реализации, этот интерфейс сообщает связанному элементу управления об изменениях свойств бизнес-объекта.</span><span class="sxs-lookup"><span data-stu-id="b4390-105">When implemented, the interface  communicates to a bound control the property changes on a business object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b4390-106">Пример</span><span class="sxs-lookup"><span data-stu-id="b4390-106">Example</span></span>  
 [!code-csharp[System.ComponentModel.IPropertyChangeExample#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.IPropertyChangeExample#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/VB/Form1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="b4390-107">См. также</span><span class="sxs-lookup"><span data-stu-id="b4390-107">See also</span></span>
- [<span data-ttu-id="b4390-108">Практическое руководство. Применение шаблона PropertyNameChanged</span><span class="sxs-lookup"><span data-stu-id="b4390-108">How to: Apply the PropertyNameChanged Pattern</span></span>](../../../docs/framework/winforms/how-to-apply-the-propertynamechanged-pattern.md)
- [<span data-ttu-id="b4390-109">Привязка данных Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b4390-109">Windows Forms Data Binding</span></span>](../../../docs/framework/winforms/windows-forms-data-binding.md)
- [<span data-ttu-id="b4390-110">Практическое руководство. Получение уведомления об изменении с помощью компонента BindingSource и интерфейса INotifyPropertyChanged</span><span class="sxs-lookup"><span data-stu-id="b4390-110">How to: Raise Change Notifications Using a BindingSource and the INotifyPropertyChanged Interface</span></span>](../../../docs/framework/winforms/controls/raise-change-notifications--bindingsource.md)
- [<span data-ttu-id="b4390-111">Уведомления об изменениях в привязке данных Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b4390-111">Change Notification in Windows Forms Data Binding</span></span>](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)
