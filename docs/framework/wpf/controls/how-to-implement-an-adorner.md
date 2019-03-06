---
title: Практическое руководство. Реализация декоративного элемента
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], implementing
ms.assetid: 56ae32b6-0599-455c-b52f-2ff97e6f1ec2
ms.openlocfilehash: 53a25396ba5d8a5c78e850e636b7c882c03d5152
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57362647"
---
# <a name="how-to-implement-an-adorner"></a><span data-ttu-id="01b42-102">Практическое руководство. Реализация декоративного элемента</span><span class="sxs-lookup"><span data-stu-id="01b42-102">How to: Implement an Adorner</span></span>
<span data-ttu-id="01b42-103">В этом примере показана реализация минимальной декоративного элемента.</span><span class="sxs-lookup"><span data-stu-id="01b42-103">This example shows a minimal adorner implementation.</span></span>  
  
## <a name="notes-for-implementers"></a><span data-ttu-id="01b42-104">Примечания для разработчиков</span><span class="sxs-lookup"><span data-stu-id="01b42-104">Notes for Implementers</span></span>  
 <span data-ttu-id="01b42-105">Важно отметить, что декоративные элементы не включают какое-либо обязательное поведение отрисовки. За результат применения декоративного элемента отвечает его автор.</span><span class="sxs-lookup"><span data-stu-id="01b42-105">It is important to note that adorners do not include any inherent rendering behavior; ensuring that an adorner renders is the responsibility of the adorner implementer.</span></span>   <span data-ttu-id="01b42-106">Распространенным способом реализации поведения отрисовки является переопределение <xref:System.Windows.UIElement.OnRender%2A> метод и использование одного или нескольких <xref:System.Windows.Media.DrawingContext> объекты для отрисовки декоративных элементов по мере необходимости (как показано в следующем примере).</span><span class="sxs-lookup"><span data-stu-id="01b42-106">A common way of implementing rendering behavior is to override the <xref:System.Windows.UIElement.OnRender%2A> method and use one or more <xref:System.Windows.Media.DrawingContext> objects to render the adorner's visuals as needed (as shown in this example).</span></span>  
  
## <a name="example"></a><span data-ttu-id="01b42-107">Пример</span><span class="sxs-lookup"><span data-stu-id="01b42-107">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="01b42-108">Описание:</span><span class="sxs-lookup"><span data-stu-id="01b42-108">Description</span></span>  
 <span data-ttu-id="01b42-109">Пользовательский декоративный элемент создается путем реализации класс, наследующий от абстрактного <xref:System.Windows.Documents.Adorner> класса.</span><span class="sxs-lookup"><span data-stu-id="01b42-109">A custom adorner is created by implementing a class that inherits from the abstract <xref:System.Windows.Documents.Adorner> class.</span></span>  <span data-ttu-id="01b42-110">В примере декоративный элемент просто украшает углы <xref:System.Windows.UIElement> кругами путем переопределения <xref:System.Windows.UIElement.OnRender%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="01b42-110">The example adorner simply adorns the corners of a <xref:System.Windows.UIElement> with circles by overriding the <xref:System.Windows.UIElement.OnRender%2A> method.</span></span>  
  
### <a name="code"></a><span data-ttu-id="01b42-111">Код</span><span class="sxs-lookup"><span data-stu-id="01b42-111">Code</span></span>  
 [!code-csharp[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_simplecircleadornerbody)]
 [!code-vb[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_simplecircleadornerbody)]  
  
## <a name="see-also"></a><span data-ttu-id="01b42-112">См. также</span><span class="sxs-lookup"><span data-stu-id="01b42-112">See also</span></span>
- [<span data-ttu-id="01b42-113">Общие сведения о декоративных элементах</span><span class="sxs-lookup"><span data-stu-id="01b42-113">Adorners Overview</span></span>](adorners-overview.md)
