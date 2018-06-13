---
title: Практическое руководство. Удаление объекта класса Adorner из элемента
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], removing
ms.assetid: 97cf4d9f-0596-429e-8526-32a30aa4ae99
ms.openlocfilehash: a3e1b08a9ec5e2cd60c063ced5e5f0d5874f8184
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33551847"
---
# <a name="how-to-remove-an-adorner-from-an-element"></a><span data-ttu-id="e40a8-102">Практическое руководство. Удаление объекта класса Adorner из элемента</span><span class="sxs-lookup"><span data-stu-id="e40a8-102">How to: Remove an Adorner from an Element</span></span>
<span data-ttu-id="e40a8-103">В этом примере показано, как программно удалить определенный декоративный элемент из указанного <xref:System.Windows.UIElement>.</span><span class="sxs-lookup"><span data-stu-id="e40a8-103">This example shows how to programmatically remove a specific adorner from a specified <xref:System.Windows.UIElement>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e40a8-104">Пример</span><span class="sxs-lookup"><span data-stu-id="e40a8-104">Example</span></span>  
 <span data-ttu-id="e40a8-105">Этот подробный пример кода удаляет первый декоративный элемент в массив декоративных элементов, возвращенных <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A>.</span><span class="sxs-lookup"><span data-stu-id="e40a8-105">This verbose code example removes the first adorner in the array of adorners returned by <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A>.</span></span>  <span data-ttu-id="e40a8-106">В этом примере происходит с графические <xref:System.Windows.UIElement> с именем *myTextBox*.</span><span class="sxs-lookup"><span data-stu-id="e40a8-106">This example happens to retrieve the adorners on a <xref:System.Windows.UIElement> named *myTextBox*.</span></span>  <span data-ttu-id="e40a8-107">Если у элемента, указанного в вызове <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A> нет графических объектов, `null` возвращается.</span><span class="sxs-lookup"><span data-stu-id="e40a8-107">If the element specified in the call to <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A> has no adorners, `null` is returned.</span></span>  <span data-ttu-id="e40a8-108">Этот код явно проверяет пустой массив и наилучшим образом подходит для приложений, где пустой массив должен быть относительно часто.</span><span class="sxs-lookup"><span data-stu-id="e40a8-108">This code explicitly checks for a null array, and is best suited for applications where a null array is expected to be relatively common.</span></span>  
  
 [!code-csharp[AdornersMiscCode#_RemoveSpecificAdornerLong](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removespecificadornerlong)]
 [!code-vb[AdornersMiscCode#_RemoveSpecificAdornerLong](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removespecificadornerlong)]  
  
## <a name="example"></a><span data-ttu-id="e40a8-109">Пример</span><span class="sxs-lookup"><span data-stu-id="e40a8-109">Example</span></span>  
 <span data-ttu-id="e40a8-110">Данный сжатый пример кода функционально эквивалентен подробному примеру, приведенному выше.</span><span class="sxs-lookup"><span data-stu-id="e40a8-110">This condensed code example is functionally equivalent to the verbose example shown above.</span></span> <span data-ttu-id="e40a8-111">Этот код не проверяет явно пустой массив, поэтому возможно, <xref:System.NullReferenceException> может быть вызвано исключение.</span><span class="sxs-lookup"><span data-stu-id="e40a8-111">This code does not explicitly check for a null array, so it is possible that a <xref:System.NullReferenceException> exception may be raised.</span></span>  <span data-ttu-id="e40a8-112">Этот код является наилучшим образом подходит для приложений, где пустой массив, ожидается редко.</span><span class="sxs-lookup"><span data-stu-id="e40a8-112">This code is best suited for applications where a null array is expected to be rare.</span></span>  
  
 [!code-csharp[AdornersMiscCode#_RemoveSpecificAdornerShort](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removespecificadornershort)]
 [!code-vb[AdornersMiscCode#_RemoveSpecificAdornerShort](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removespecificadornershort)]  
  
## <a name="see-also"></a><span data-ttu-id="e40a8-113">См. также</span><span class="sxs-lookup"><span data-stu-id="e40a8-113">See Also</span></span>  
 [<span data-ttu-id="e40a8-114">Общие сведения о декоративных элементах</span><span class="sxs-lookup"><span data-stu-id="e40a8-114">Adorners Overview</span></span>](../../../../docs/framework/wpf/controls/adorners-overview.md)
