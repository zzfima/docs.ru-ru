---
title: Отражение обновлений источника данных в элементе управления с помощью BindingSource
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data binding [Windows Forms], updating
- BindingSource component [Windows Forms], updating data binding
- examples [Windows Forms], BindingSource component
- data sources [Windows Forms], updating
- BindingSource component [Windows Forms], examples
ms.assetid: bd8bd9b2-af8a-4f11-a3d5-54eecbe2400b
ms.openlocfilehash: f98296b477dbb674cdbdbd8d03e291dd6ca0c8a3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742436"
---
# <a name="how-to-reflect-data-source-updates-in-a-windows-forms-control-with-the-bindingsource"></a><span data-ttu-id="91c12-102">Практическое руководство. Отражение в элементе управления данных, которые обновились в источнике, с использованием компонента BindingSource в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="91c12-102">How to: Reflect Data Source Updates in a Windows Forms Control with the BindingSource</span></span>
<span data-ttu-id="91c12-103">При использовании элементов управления с привязкой к данным иногда необходимо реагировать на изменения в источнике данных, если источник данных не вызывает события изменения списка.</span><span class="sxs-lookup"><span data-stu-id="91c12-103">When you use data-bound controls, you sometimes have to respond to changes in the data source when the data source does not raise list-changed events.</span></span> <span data-ttu-id="91c12-104">При использовании компонента <xref:System.Windows.Forms.BindingSource> для привязки источника данных к элементу управления Windows Forms можно уведомить элемент управления об изменении источника данных путем вызова метода <xref:System.Windows.Forms.BindingSource.ResetBindings%2A>.</span><span class="sxs-lookup"><span data-stu-id="91c12-104">When you use the <xref:System.Windows.Forms.BindingSource> component to bind your data source to a Windows Forms control, you can notify the control that your data source has changed by calling the <xref:System.Windows.Forms.BindingSource.ResetBindings%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="91c12-105">Пример</span><span class="sxs-lookup"><span data-stu-id="91c12-105">Example</span></span>  
 <span data-ttu-id="91c12-106">В следующем примере кода показано использование метода <xref:System.Windows.Forms.BindingSource.ResetBindings%2A> для уведомления связанного элемента управления об изменении в источнике данных.</span><span class="sxs-lookup"><span data-stu-id="91c12-106">The following code example demonstrates using the <xref:System.Windows.Forms.BindingSource.ResetBindings%2A> method to notify a bound control about an update in the data source.</span></span>  
  
 [!code-cpp[System.Windows.Forms.DataConnector.ResetBindings#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetBindings/CPP/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.DataConnector.ResetBindings#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetBindings/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnector.ResetBindings#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetBindings/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="91c12-107">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="91c12-107">Compiling the Code</span></span>  
 <span data-ttu-id="91c12-108">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="91c12-108">This example requires:</span></span>  
  
- <span data-ttu-id="91c12-109">ссылки на сборки System, System.Drawing и System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="91c12-109">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91c12-110">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="91c12-110">See also</span></span>

- <xref:System.Windows.Forms.BindingNavigator>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="91c12-111">Компонент BindingSource</span><span class="sxs-lookup"><span data-stu-id="91c12-111">BindingSource Component</span></span>](bindingsource-component.md)
- [<span data-ttu-id="91c12-112">Практическое руководство. Связывание элемента управления с типом в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="91c12-112">How to: Bind a Windows Forms Control to a Type</span></span>](how-to-bind-a-windows-forms-control-to-a-type.md)
