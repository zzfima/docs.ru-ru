---
title: "Практическое руководство. Реализация декоративного элемента"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: adorners [WPF], implementing
ms.assetid: 56ae32b6-0599-455c-b52f-2ff97e6f1ec2
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a3f69fee64ea65e8d49cce523c85669993cc6bce
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-implement-an-adorner"></a><span data-ttu-id="ceae9-102">Практическое руководство. Реализация декоративного элемента</span><span class="sxs-lookup"><span data-stu-id="ceae9-102">How to: Implement an Adorner</span></span>
<span data-ttu-id="ceae9-103">В этом примере показана реализация минимальной графических элементов.</span><span class="sxs-lookup"><span data-stu-id="ceae9-103">This example shows a minimal adorner implementation.</span></span>  
  
## <a name="notes-for-implementers"></a><span data-ttu-id="ceae9-104">Примечания для разработчиков</span><span class="sxs-lookup"><span data-stu-id="ceae9-104">Notes for Implementers</span></span>  
 <span data-ttu-id="ceae9-105">Важно отметить, что декоративные элементы не включают какое-либо обязательное поведение отрисовки. За результат применения декоративного элемента отвечает его автор.</span><span class="sxs-lookup"><span data-stu-id="ceae9-105">It is important to note that adorners do not include any inherent rendering behavior; ensuring that an adorner renders is the responsibility of the adorner implementer.</span></span>   <span data-ttu-id="ceae9-106">Распространенным способом реализации поведения визуализации является переопределение <xref:System.Windows.UIElement.OnRender%2A> метод и использование одного или нескольких <xref:System.Windows.Media.DrawingContext> объектов для подготовки к просмотру декоратора по мере необходимости (как показано в следующем примере).</span><span class="sxs-lookup"><span data-stu-id="ceae9-106">A common way of implementing rendering behavior is to override the <xref:System.Windows.UIElement.OnRender%2A> method and use one or more <xref:System.Windows.Media.DrawingContext> objects to render the adorner's visuals as needed (as shown in this example).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ceae9-107">Пример</span><span class="sxs-lookup"><span data-stu-id="ceae9-107">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="ceae9-108">Описание</span><span class="sxs-lookup"><span data-stu-id="ceae9-108">Description</span></span>  
 <span data-ttu-id="ceae9-109">Пользовательский графический элемент создается путем реализации класса, который наследует от абстрактного <xref:System.Windows.Documents.Adorner> класса.</span><span class="sxs-lookup"><span data-stu-id="ceae9-109">A custom adorner is created by implementing a class that inherits from the abstract <xref:System.Windows.Documents.Adorner> class.</span></span>  <span data-ttu-id="ceae9-110">В примере декоративный элемент просто украшает углы <xref:System.Windows.UIElement> кругами путем переопределения <xref:System.Windows.UIElement.OnRender%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="ceae9-110">The example adorner simply adorns the corners of a <xref:System.Windows.UIElement> with circles by overriding the <xref:System.Windows.UIElement.OnRender%2A> method.</span></span>  
  
### <a name="code"></a><span data-ttu-id="ceae9-111">Код</span><span class="sxs-lookup"><span data-stu-id="ceae9-111">Code</span></span>  
 [!code-csharp[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_simplecircleadornerbody)]
 [!code-vb[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_simplecircleadornerbody)]  
  
## <a name="see-also"></a><span data-ttu-id="ceae9-112">См. также</span><span class="sxs-lookup"><span data-stu-id="ceae9-112">See Also</span></span>  
 [<span data-ttu-id="ceae9-113">Общие сведения о декоративных элементах</span><span class="sxs-lookup"><span data-stu-id="ceae9-113">Adorners Overview</span></span>](../../../../docs/framework/wpf/controls/adorners-overview.md)
