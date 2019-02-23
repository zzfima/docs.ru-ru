---
title: Практическое руководство. Использование объекта ThicknessConverter
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- border thickness [WPF]
- ThicknessConverter objects [WPF]
ms.assetid: 52682194-d7fd-499c-8005-73fcc84e7b2c
ms.openlocfilehash: 653137c0707c2b7ee51f6bdac6bb2501f1845e1a
ms.sourcegitcommit: 8f95d3a37e591963ebbb9af6e90686fd5f3b8707
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2019
ms.locfileid: "56747347"
---
# <a name="how-to-use-a-thicknessconverter-object"></a><span data-ttu-id="036b7-102">Практическое руководство. Использование объекта ThicknessConverter</span><span class="sxs-lookup"><span data-stu-id="036b7-102">How to: Use a ThicknessConverter Object</span></span>
## <a name="example"></a><span data-ttu-id="036b7-103">Пример</span><span class="sxs-lookup"><span data-stu-id="036b7-103">Example</span></span>  
 <span data-ttu-id="036b7-104">В этом примере показано, как создать экземпляр <xref:System.Windows.ThicknessConverter> и использовать его для изменения толщины границы.</span><span class="sxs-lookup"><span data-stu-id="036b7-104">This example shows how to create an instance of <xref:System.Windows.ThicknessConverter> and use it to change the thickness of a border.</span></span>  
  
 <span data-ttu-id="036b7-105">В примере определяется пользовательский метод с именем `changeThickness`; этот метод сначала преобразует содержимое <xref:System.Windows.Controls.ListBoxItem>, как определено в отдельном [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] файл, чтобы экземпляр <xref:System.Windows.Thickness>, а затем преобразует содержимое в <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="036b7-105">The example defines a custom method called `changeThickness`; this method first converts the contents of a <xref:System.Windows.Controls.ListBoxItem>, as defined in a separate [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file, to an instance of <xref:System.Windows.Thickness>, and later converts the content into a <xref:System.String>.</span></span> <span data-ttu-id="036b7-106">Этот метод передает <xref:System.Windows.Controls.ListBoxItem> для <xref:System.Windows.ThicknessConverter> объект, который преобразует <xref:System.Windows.Controls.ContentControl.Content%2A> из <xref:System.Windows.Controls.ListBoxItem> к экземпляру <xref:System.Windows.Thickness>.</span><span class="sxs-lookup"><span data-stu-id="036b7-106">This method passes the <xref:System.Windows.Controls.ListBoxItem> to a <xref:System.Windows.ThicknessConverter> object, which converts the <xref:System.Windows.Controls.ContentControl.Content%2A> of a <xref:System.Windows.Controls.ListBoxItem> to an instance of <xref:System.Windows.Thickness>.</span></span> <span data-ttu-id="036b7-107">Это значение затем передается обратно в качестве значения <xref:System.Windows.Controls.Border.BorderThickness%2A> свойство <xref:System.Windows.Controls.Border>.</span><span class="sxs-lookup"><span data-stu-id="036b7-107">This value is then passed back as the value of the <xref:System.Windows.Controls.Border.BorderThickness%2A> property of the <xref:System.Windows.Controls.Border>.</span></span>  
  
 <span data-ttu-id="036b7-108">Этот пример не запускается.</span><span class="sxs-lookup"><span data-stu-id="036b7-108">This example does not run.</span></span>  
  
 [!code-csharp[ThicknessConverter#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThicknessConverter/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ThicknessConverter#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ThicknessConverter/VisualBasic/Window1.xaml.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="036b7-109">См. также</span><span class="sxs-lookup"><span data-stu-id="036b7-109">See also</span></span>
- <xref:System.Windows.Thickness>
- <xref:System.Windows.ThicknessConverter>
- <xref:System.Windows.Controls.Border>
- <span data-ttu-id="036b7-110">[Практическое руководство. Изменить свойства полей](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms750561(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="036b7-110">[How to: Change the Margin Property](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms750561(v=vs.90))</span></span>
- <span data-ttu-id="036b7-111">[Практическое руководство. Преобразовать в новый тип данных элемента ListBoxItem](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms749147(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="036b7-111">[How to: Convert a ListBoxItem to a new Data Type](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms749147(v=vs.90))</span></span>
- [<span data-ttu-id="036b7-112">Общие сведения о панелях</span><span class="sxs-lookup"><span data-stu-id="036b7-112">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)
