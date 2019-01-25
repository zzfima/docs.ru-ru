---
title: Как выполнить Использование объекта ThicknessConverter
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- border thickness [WPF]
- ThicknessConverter objects [WPF]
ms.assetid: 52682194-d7fd-499c-8005-73fcc84e7b2c
ms.openlocfilehash: 22215a155f4a204e3edeebc464413d5718290bb4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54577075"
---
# <a name="how-to-use-a-thicknessconverter-object"></a><span data-ttu-id="13a4f-102">Как выполнить Использование объекта ThicknessConverter</span><span class="sxs-lookup"><span data-stu-id="13a4f-102">How to: Use a ThicknessConverter Object</span></span>
## <a name="example"></a><span data-ttu-id="13a4f-103">Пример</span><span class="sxs-lookup"><span data-stu-id="13a4f-103">Example</span></span>  
 <span data-ttu-id="13a4f-104">В этом примере показано, как создать экземпляр <xref:System.Windows.ThicknessConverter> и использовать его для изменения толщины границы.</span><span class="sxs-lookup"><span data-stu-id="13a4f-104">This example shows how to create an instance of <xref:System.Windows.ThicknessConverter> and use it to change the thickness of a border.</span></span>  
  
 <span data-ttu-id="13a4f-105">В примере определяется пользовательский метод с именем `changeThickness`; этот метод сначала преобразует содержимое <xref:System.Windows.Controls.ListBoxItem>, как определено в отдельном [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] файл, чтобы экземпляр <xref:System.Windows.Thickness>, а затем преобразует содержимое в <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="13a4f-105">The example defines a custom method called `changeThickness`; this method first converts the contents of a <xref:System.Windows.Controls.ListBoxItem>, as defined in a separate [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file, to an instance of <xref:System.Windows.Thickness>, and later converts the content into a <xref:System.String>.</span></span> <span data-ttu-id="13a4f-106">Этот метод передает <xref:System.Windows.Controls.ListBoxItem> для <xref:System.Windows.ThicknessConverter> объект, который преобразует <xref:System.Windows.Controls.ContentControl.Content%2A> из <xref:System.Windows.Controls.ListBoxItem> к экземпляру <xref:System.Windows.Thickness>.</span><span class="sxs-lookup"><span data-stu-id="13a4f-106">This method passes the <xref:System.Windows.Controls.ListBoxItem> to a <xref:System.Windows.ThicknessConverter> object, which converts the <xref:System.Windows.Controls.ContentControl.Content%2A> of a <xref:System.Windows.Controls.ListBoxItem> to an instance of <xref:System.Windows.Thickness>.</span></span> <span data-ttu-id="13a4f-107">Это значение затем передается обратно в качестве значения <xref:System.Windows.Controls.Border.BorderThickness%2A> свойство <xref:System.Windows.Controls.Border>.</span><span class="sxs-lookup"><span data-stu-id="13a4f-107">This value is then passed back as the value of the <xref:System.Windows.Controls.Border.BorderThickness%2A> property of the <xref:System.Windows.Controls.Border>.</span></span>  
  
 <span data-ttu-id="13a4f-108">Этот пример не запускается.</span><span class="sxs-lookup"><span data-stu-id="13a4f-108">This example does not run.</span></span>  
  
 [!code-csharp[ThicknessConverter#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThicknessConverter/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ThicknessConverter#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ThicknessConverter/VisualBasic/Window1.xaml.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="13a4f-109">См. также</span><span class="sxs-lookup"><span data-stu-id="13a4f-109">See also</span></span>
- <xref:System.Windows.Thickness>
- <xref:System.Windows.ThicknessConverter>
- <xref:System.Windows.Controls.Border>
- [<span data-ttu-id="13a4f-110">Практическое руководство. Изменить свойства полей</span><span class="sxs-lookup"><span data-stu-id="13a4f-110">How to: Change the Margin Property</span></span>](https://msdn.microsoft.com/library/8a313efd-5f99-4097-b4c1-8fa49d8379a2)
- [<span data-ttu-id="13a4f-111">Практическое руководство. Преобразовать в новый тип данных элемента ListBoxItem</span><span class="sxs-lookup"><span data-stu-id="13a4f-111">How to: Convert a ListBoxItem to a new Data Type</span></span>](https://msdn.microsoft.com/library/7a080b88-184e-4b27-bb61-d42bafba9727)
- [<span data-ttu-id="13a4f-112">Общие сведения о панелях</span><span class="sxs-lookup"><span data-stu-id="13a4f-112">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)
