---
title: Практическое руководство. Получение уведомления об изменении данных с использованием компонента BindingSource и интерфейса INotifyPropertyChanged
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- change notifications [Windows Forms], raising
- BindingSource component [Windows Forms], and IPropertyChange
- data sources [Windows Forms], detecting changes
- examples [Windows Forms], BindingSource component
- change notifications
- INotifyPropertyChanged interface [Windows Forms], using with BindingSource
- BindingSource component [Windows Forms], examples
ms.assetid: 7fa2cf51-c09f-4375-adf0-e36c5617f099
ms.openlocfilehash: 6a622e64076d2ed2a073dc0f0e55204d1767cfd7
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2019
ms.locfileid: "65591832"
---
# <a name="how-to-raise-change-notifications-using-a-bindingsource-and-the-inotifypropertychanged-interface"></a><span data-ttu-id="82fb4-102">Практическое руководство. Получение уведомления об изменении данных с использованием компонента BindingSource и интерфейса INotifyPropertyChanged</span><span class="sxs-lookup"><span data-stu-id="82fb4-102">How to: Raise Change Notifications Using a BindingSource and the INotifyPropertyChanged Interface</span></span>
<span data-ttu-id="82fb4-103">Компонент <xref:System.Windows.Forms.BindingSource> автоматически обнаруживает изменения в источнике данных, когда тип, содержащийся в этом источнике, реализует интерфейс <xref:System.ComponentModel.INotifyPropertyChanged> и вызывает события <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> при изменении значения свойства.</span><span class="sxs-lookup"><span data-stu-id="82fb4-103">The <xref:System.Windows.Forms.BindingSource> component will automatically detect changes in a data source when the type contained in the data source implements the <xref:System.ComponentModel.INotifyPropertyChanged> interface and raises <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> events when a property value is changed.</span></span> <span data-ttu-id="82fb4-104">Это очень удобно, так как элементы управления, привязанные к <xref:System.Windows.Forms.BindingSource>, будут автоматически обновляться при изменении значений источника данных.</span><span class="sxs-lookup"><span data-stu-id="82fb4-104">This is useful because controls bound to the <xref:System.Windows.Forms.BindingSource> will then automatically update as the data source values change.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="82fb4-105">Если источник данных реализует <xref:System.ComponentModel.INotifyPropertyChanged> и выполняются асинхронные операции, не следует вносить изменения в источник данных в фоновом потоке.</span><span class="sxs-lookup"><span data-stu-id="82fb4-105">If your data source implements <xref:System.ComponentModel.INotifyPropertyChanged> and you are performing asynchronous operations, you should not make changes to the data source on a background thread.</span></span> <span data-ttu-id="82fb4-106">Вместо этого рекомендуется считывать данные в фоновом потоке и объединять их в список в потоке пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="82fb4-106">Instead, you should read the data on a background thread and merge the data into a list on the UI thread.</span></span>  
  
## <a name="example"></a><span data-ttu-id="82fb4-107">Пример</span><span class="sxs-lookup"><span data-stu-id="82fb4-107">Example</span></span>  
 <span data-ttu-id="82fb4-108">В следующем примере кода показан пример простой реализации интерфейса <xref:System.ComponentModel.INotifyPropertyChanged>.</span><span class="sxs-lookup"><span data-stu-id="82fb4-108">The following code example demonstrates a simple implementation of the <xref:System.ComponentModel.INotifyPropertyChanged> interface.</span></span> <span data-ttu-id="82fb4-109">Также показано, как компонент <xref:System.Windows.Forms.BindingSource> автоматически передает изменения источника данных в связанный элемент управления, когда <xref:System.Windows.Forms.BindingSource> привязан к списку типа <xref:System.ComponentModel.INotifyPropertyChanged>.</span><span class="sxs-lookup"><span data-stu-id="82fb4-109">It also shows how the <xref:System.Windows.Forms.BindingSource> automatically passes a data source change to a bound control when the <xref:System.Windows.Forms.BindingSource> is bound to a list of the <xref:System.ComponentModel.INotifyPropertyChanged> type.</span></span>  
  
 <span data-ttu-id="82fb4-110">При использовании атрибута `CallerMemberName` в вызовах метода `NotifyPropertyChanged` нет необходимости указывать имя свойства в качестве строкового аргумента.</span><span class="sxs-lookup"><span data-stu-id="82fb4-110">If you use the `CallerMemberName` attribute, calls to the `NotifyPropertyChanged` method don't have to specify the property name as a string argument.</span></span> <span data-ttu-id="82fb4-111">Дополнительные сведения см. в разделе [сведения о вызывающем объекте (C#)](../../../csharp/programming-guide/concepts/caller-information.md) или [сведения о вызывающем объекте (Visual Basic)](../../../visual-basic/programming-guide/concepts/caller-information.md).</span><span class="sxs-lookup"><span data-stu-id="82fb4-111">For more information, see [Caller Information (C#)](../../../csharp/programming-guide/concepts/caller-information.md) or [Caller Information (Visual Basic)](../../../visual-basic/programming-guide/concepts/caller-information.md).</span></span>  
  
 [!code-csharp[System.ComponentModel.IPropertyChangeExample#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.IPropertyChangeExample#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="82fb4-112">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="82fb4-112">Compiling the Code</span></span>  
 <span data-ttu-id="82fb4-113">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="82fb4-113">This example requires:</span></span>  
  
- <span data-ttu-id="82fb4-114">ссылки на сборки System, System.Data, System.Drawing и System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="82fb4-114">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82fb4-115">См. также</span><span class="sxs-lookup"><span data-stu-id="82fb4-115">See also</span></span>

- <xref:System.ComponentModel.INotifyPropertyChanged>
- [<span data-ttu-id="82fb4-116">Компонент BindingSource</span><span class="sxs-lookup"><span data-stu-id="82fb4-116">BindingSource Component</span></span>](bindingsource-component.md)
- [<span data-ttu-id="82fb4-117">Практическое руководство. Получение уведомления об изменении, с использованием метода ResetItem компонента BindingSource</span><span class="sxs-lookup"><span data-stu-id="82fb4-117">How to: Raise Change Notifications Using the BindingSource ResetItem Method</span></span>](how-to-raise-change-notifications-using-the-bindingsource-resetitem-method.md)
