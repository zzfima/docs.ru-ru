---
title: Практическое руководство. Привязка декоративного объекта к элементу
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UIElements [WPF], binding adorners to
- adorners [WPF], binding to specified UIElements
ms.assetid: b2101611-a0ee-4137-bdb8-9b3673d2e6b9
ms.openlocfilehash: 4943121aaf8ee6524be3fc9004eafee4fa92e527
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57353924"
---
# <a name="how-to-bind-an-adorner-to-an-element"></a><span data-ttu-id="d8550-102">Практическое руководство. Привязка декоративного объекта к элементу</span><span class="sxs-lookup"><span data-stu-id="d8550-102">How to: Bind an Adorner to an Element</span></span>
<span data-ttu-id="d8550-103">В этом примере показано, как программно привязать декоративный элемент с заданным <xref:System.Windows.UIElement>.</span><span class="sxs-lookup"><span data-stu-id="d8550-103">This example shows how to programmatically bind an adorner to a specified <xref:System.Windows.UIElement>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d8550-104">Пример</span><span class="sxs-lookup"><span data-stu-id="d8550-104">Example</span></span>  
 <span data-ttu-id="d8550-105">Для привязки декоративного элемента к конкретному <xref:System.Windows.UIElement>, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="d8550-105">To bind an adorner to a particular <xref:System.Windows.UIElement>, follow these steps:</span></span>  
  
1.  <span data-ttu-id="d8550-106">Вызовите `static` метод <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> для получения <xref:System.Windows.Documents.AdornerLayer> для объекта <xref:System.Windows.UIElement> декорируемого.</span><span class="sxs-lookup"><span data-stu-id="d8550-106">Call the `static` method <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> to get an <xref:System.Windows.Documents.AdornerLayer> object for the <xref:System.Windows.UIElement> to be adorned.</span></span> <span data-ttu-id="d8550-107"><xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> Пошаговое описание вверх по визуальному дереву, начиная с указанного **UIElement**и возвращает первый слой графических элементов, которые найдет.</span><span class="sxs-lookup"><span data-stu-id="d8550-107"><xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> walks up the visual tree, starting at the specified **UIElement**, and returns the first adorner layer it finds.</span></span> <span data-ttu-id="d8550-108">(Если слои декоративных элементов не найдены, метод возвращает значение 0.)</span><span class="sxs-lookup"><span data-stu-id="d8550-108">(If no adorner layers are found, the method returns null.)</span></span>  
  
2.  <span data-ttu-id="d8550-109">Вызовите <xref:System.Windows.Documents.AdornerLayer.Add%2A> метод для привязки декоративного элемента к целевому объекту **UIElement**.</span><span class="sxs-lookup"><span data-stu-id="d8550-109">Call the <xref:System.Windows.Documents.AdornerLayer.Add%2A> method to bind the adorner to the target **UIElement**.</span></span>  
  
 <span data-ttu-id="d8550-110">Следующий пример связывает SimpleCircleAdorner (как показано выше) для <xref:System.Windows.Controls.TextBox> с именем *myTextBox*.</span><span class="sxs-lookup"><span data-stu-id="d8550-110">The following example binds a SimpleCircleAdorner (shown above) to a <xref:System.Windows.Controls.TextBox> named *myTextBox*.</span></span>  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornsingleelement)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornsingleelement)]  
  
> [!NOTE]
>  <span data-ttu-id="d8550-111">Использование [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] для привязки декоративного элемента к другому элементу в настоящее время не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="d8550-111">Using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to bind an adorner to another element is currently not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8550-112">См. также</span><span class="sxs-lookup"><span data-stu-id="d8550-112">See also</span></span>
- [<span data-ttu-id="d8550-113">Общие сведения о декоративных элементах</span><span class="sxs-lookup"><span data-stu-id="d8550-113">Adorners Overview</span></span>](adorners-overview.md)
