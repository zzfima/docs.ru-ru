---
title: "Практическое руководство. Синхронизация элементов управления, связанных с одним источником данных"
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
- controls [Windows Forms], binding multiple
- controls [Windows Forms], synchronizing with data source
ms.assetid: c2f0ecc6-11e6-4c2c-a1ca-0759630c451e
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2573f342530e59fa05e7f24342f251990b2ce47d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-ensure-multiple-controls-bound-to-the-same-data-source-remain-synchronized"></a><span data-ttu-id="e36e8-102">Практическое руководство. Синхронизация элементов управления, связанных с одним источником данных</span><span class="sxs-lookup"><span data-stu-id="e36e8-102">How to: Ensure Multiple Controls Bound to the Same Data Source Remain Synchronized</span></span>
<span data-ttu-id="e36e8-103">Зачастую при работе с привязкой к данным в формах Windows Forms, несколько элементов управления привязаны к одному источнику данных.</span><span class="sxs-lookup"><span data-stu-id="e36e8-103">Oftentimes when working with data binding in Windows Forms, multiple controls are bound to the same data source.</span></span> <span data-ttu-id="e36e8-104">В некоторых случаях может потребоваться выполнить дополнительные действия для обеспечения синхронизация друг с другом и с источником данных связанных свойств элементов управления.</span><span class="sxs-lookup"><span data-stu-id="e36e8-104">In some cases, it may be necessary to take extra steps to ensure that the bound properties of the controls remain synchronized with each other and the data source.</span></span> <span data-ttu-id="e36e8-105">Эти шаги необходимы в двух случаях:</span><span class="sxs-lookup"><span data-stu-id="e36e8-105">These steps are necessary in two situations:</span></span>  
  
-   <span data-ttu-id="e36e8-106">Если источник данных не реализует <xref:System.ComponentModel.IBindingList>и поэтому вызывает <xref:System.ComponentModel.IBindingList.ListChanged> события типа <xref:System.ComponentModel.ListChangedType.ItemChanged>.</span><span class="sxs-lookup"><span data-stu-id="e36e8-106">If the data source does not implement <xref:System.ComponentModel.IBindingList>, and therefore generate <xref:System.ComponentModel.IBindingList.ListChanged> events of type <xref:System.ComponentModel.ListChangedType.ItemChanged>.</span></span>  
  
-   <span data-ttu-id="e36e8-107">Если источник данных реализует <xref:System.ComponentModel.IEditableObject>.</span><span class="sxs-lookup"><span data-stu-id="e36e8-107">If the data source implements <xref:System.ComponentModel.IEditableObject>.</span></span>  
  
 <span data-ttu-id="e36e8-108">В первом случае можно использовать <xref:System.Windows.Forms.BindingSource> для привязки источника данных к элементам управления.</span><span class="sxs-lookup"><span data-stu-id="e36e8-108">In the former case, you can use a <xref:System.Windows.Forms.BindingSource> to bind the data source to the controls.</span></span> <span data-ttu-id="e36e8-109">В последнем случае используется <xref:System.Windows.Forms.BindingSource> и обрабатывать <xref:System.Windows.Forms.BindingSource.BindingComplete> событий и вызовов <xref:System.Windows.Forms.BindingManagerBase.EndCurrentEdit%2A> в связанном <xref:System.Windows.Forms.BindingManagerBase>.</span><span class="sxs-lookup"><span data-stu-id="e36e8-109">In the latter case, you use a <xref:System.Windows.Forms.BindingSource> and handle the <xref:System.Windows.Forms.BindingSource.BindingComplete> event and call <xref:System.Windows.Forms.BindingManagerBase.EndCurrentEdit%2A> on the associated <xref:System.Windows.Forms.BindingManagerBase>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e36e8-110">Пример</span><span class="sxs-lookup"><span data-stu-id="e36e8-110">Example</span></span>  
 <span data-ttu-id="e36e8-111">В следующем примере кода показано, как привязать три элемента управления — два элемента управления текстового поля и <xref:System.Windows.Forms.DataGridView> управления — в том же столбце в <xref:System.Data.DataSet> с помощью <xref:System.Windows.Forms.BindingSource> компонента.</span><span class="sxs-lookup"><span data-stu-id="e36e8-111">The following code example demonstrates how to bind three controls—two text-box controls and a <xref:System.Windows.Forms.DataGridView> control—to the same column in a <xref:System.Data.DataSet> using a <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="e36e8-112">В этом примере показан способ обработки <xref:System.Windows.Forms.BindingSource.BindingComplete> событий и убедитесь, что при изменении одного текстового поля текстовое значение текстового поля и <xref:System.Windows.Forms.DataGridView> обновление с правильным значением элемента управления.</span><span class="sxs-lookup"><span data-stu-id="e36e8-112">This example demonstrates how to handle the <xref:System.Windows.Forms.BindingSource.BindingComplete> event and ensure that when the text value of one text box is changed, the additional text box and the <xref:System.Windows.Forms.DataGridView> control are updated with the correct value.</span></span>  
  
 <span data-ttu-id="e36e8-113">В этом примере <xref:System.Windows.Forms.BindingSource> для привязки источника данных и элементов управления.</span><span class="sxs-lookup"><span data-stu-id="e36e8-113">The example uses a <xref:System.Windows.Forms.BindingSource> to bind the data source and the controls.</span></span> <span data-ttu-id="e36e8-114">Кроме того, можно привязать элементы управления напрямую к источнику данных и извлечь <xref:System.Windows.Forms.BindingManagerBase> для привязки из формы <xref:System.Windows.Forms.Control.BindingContext%2A> и затем обрабатывать <xref:System.Windows.Forms.BindingManagerBase.BindingComplete> событий для <xref:System.Windows.Forms.BindingManagerBase>.</span><span class="sxs-lookup"><span data-stu-id="e36e8-114">Alternatively, you can bind the controls directly to the data source and retrieve the <xref:System.Windows.Forms.BindingManagerBase> for the binding from the form's <xref:System.Windows.Forms.Control.BindingContext%2A> and then handle the <xref:System.Windows.Forms.BindingManagerBase.BindingComplete> event for the <xref:System.Windows.Forms.BindingManagerBase>.</span></span> <span data-ttu-id="e36e8-115">Пример того, как это сделать, см. на странице справки <xref:System.Windows.Forms.BindingManagerBase.BindingComplete> событие <xref:System.Windows.Forms.BindingManagerBase>.</span><span class="sxs-lookup"><span data-stu-id="e36e8-115">For an example of how to do this, see the Help page about the <xref:System.Windows.Forms.BindingManagerBase.BindingComplete> event of <xref:System.Windows.Forms.BindingManagerBase>.</span></span>  
  
 [!code-csharp[System.Windows.Forms.BindingSourceMultipleControls#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleControls/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.BindingSourceMultipleControls#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleControls/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e36e8-116">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="e36e8-116">Compiling the Code</span></span>  
  
-   <span data-ttu-id="e36e8-117">Для этого примера кода требуются</span><span class="sxs-lookup"><span data-stu-id="e36e8-117">This code example requires</span></span>  
  
-   <span data-ttu-id="e36e8-118">ссылки на сборки <xref:System>, <xref:System.Windows.Forms> и <xref:System.Drawing>.</span><span class="sxs-lookup"><span data-stu-id="e36e8-118">References to the <xref:System>, <xref:System.Windows.Forms>, and <xref:System.Drawing> assemblies.</span></span>  
  
-   <span data-ttu-id="e36e8-119">Форма с <xref:System.Windows.Forms.Form.Load> событие как обработанное и вызов `InitializeControlsAndDataSource` метод в примере из формы <xref:System.Windows.Forms.Form.Load> обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="e36e8-119">A form with the <xref:System.Windows.Forms.Form.Load> event handled and a call to the `InitializeControlsAndDataSource` method in the example from the form's <xref:System.Windows.Forms.Form.Load> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e36e8-120">См. также</span><span class="sxs-lookup"><span data-stu-id="e36e8-120">See Also</span></span>  
 [<span data-ttu-id="e36e8-121">Практическое руководство. Совместное использование одних и тех же данных в нескольких формах посредством компонента BindingSource</span><span class="sxs-lookup"><span data-stu-id="e36e8-121">How to: Share Bound Data Across Forms Using the BindingSource Component</span></span>](../../../docs/framework/winforms/controls/how-to-share-bound-data-across-forms-using-the-bindingsource-component.md)  
 [<span data-ttu-id="e36e8-122">Уведомления об изменениях в привязке данных Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e36e8-122">Change Notification in Windows Forms Data Binding</span></span>](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)  
 [<span data-ttu-id="e36e8-123">Интерфейсы, относящиеся к привязке данных</span><span class="sxs-lookup"><span data-stu-id="e36e8-123">Interfaces Related to Data Binding</span></span>](../../../docs/framework/winforms/interfaces-related-to-data-binding.md)  
 [<span data-ttu-id="e36e8-124">Привязка данных Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e36e8-124">Windows Forms Data Binding</span></span>](../../../docs/framework/winforms/windows-forms-data-binding.md)
