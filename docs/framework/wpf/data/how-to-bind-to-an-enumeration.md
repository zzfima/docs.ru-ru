---
title: Практическое руководство. Привязка к перечислению
ms.date: 03/30/2017
helpviewer_keywords:
- binding data [WPF], enumeration
- data binding [WPF], enumeration
- enumeration [WPF]
ms.assetid: b9091eba-1119-424e-868b-d1a4168b3732
ms.openlocfilehash: 93f33e497fd7acb81c55f86bf38737d4e7d79bf2
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73454436"
---
# <a name="how-to-bind-to-an-enumeration"></a><span data-ttu-id="d2b8b-102">Практическое руководство. Привязка к перечислению</span><span class="sxs-lookup"><span data-stu-id="d2b8b-102">How to: Bind to an Enumeration</span></span>
<span data-ttu-id="d2b8b-103">В этом примере показано, как выполнить привязку к перечислению путем привязки к методу методов перечисления.</span><span class="sxs-lookup"><span data-stu-id="d2b8b-103">This example shows how to bind to an enumeration by binding to the enumeration's GetValues method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d2b8b-104">Пример</span><span class="sxs-lookup"><span data-stu-id="d2b8b-104">Example</span></span>  
 <span data-ttu-id="d2b8b-105">В следующем примере <xref:System.Windows.Controls.ListBox> отображает список значений перечисления <xref:System.Windows.HorizontalAlignment> с помощью привязки данных.</span><span class="sxs-lookup"><span data-stu-id="d2b8b-105">In the following example, the <xref:System.Windows.Controls.ListBox> displays the list of <xref:System.Windows.HorizontalAlignment> enumeration values through data binding.</span></span> <span data-ttu-id="d2b8b-106"><xref:System.Windows.Controls.ListBox> и <xref:System.Windows.Controls.Button> связаны так, что можно изменить значение свойства <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> <xref:System.Windows.Controls.Button>, выбрав значение в <xref:System.Windows.Controls.ListBox>.</span><span class="sxs-lookup"><span data-stu-id="d2b8b-106">The <xref:System.Windows.Controls.ListBox> and the <xref:System.Windows.Controls.Button> are bound such that you can change the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property value of the <xref:System.Windows.Controls.Button> by selecting a value in the <xref:System.Windows.Controls.ListBox>.</span></span>  
  
 [!code-xaml[BindToEnum#BindToEnum](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToEnum/CS/Window1.xaml#bindtoenum)]  
  
## <a name="see-also"></a><span data-ttu-id="d2b8b-107">См. также</span><span class="sxs-lookup"><span data-stu-id="d2b8b-107">See also</span></span>

- [<span data-ttu-id="d2b8b-108">Создание привязки к методу</span><span class="sxs-lookup"><span data-stu-id="d2b8b-108">Bind to a Method</span></span>](how-to-bind-to-a-method.md)
- [<span data-ttu-id="d2b8b-109">Общие сведения о привязке данных</span><span class="sxs-lookup"><span data-stu-id="d2b8b-109">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="d2b8b-110">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="d2b8b-110">How-to Topics</span></span>](data-binding-how-to-topics.md)
