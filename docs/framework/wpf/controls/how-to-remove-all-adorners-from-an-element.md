---
title: Практическое руководство. Удаление всех декоративных элементов из элемента
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], removing
ms.assetid: fe5303a3-b76e-4643-aafb-51419032b47b
ms.openlocfilehash: 5b7e2038c8a314a180ba097a30c124f874c25893
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-remove-all-adorners-from-an-element"></a><span data-ttu-id="13504-102">Практическое руководство. Удаление всех декоративных элементов из элемента</span><span class="sxs-lookup"><span data-stu-id="13504-102">How to: Remove all Adorners from an Element</span></span>
<span data-ttu-id="13504-103">В этом примере показано, как программно удалить все графические элементы из указанного <xref:System.Windows.UIElement>.</span><span class="sxs-lookup"><span data-stu-id="13504-103">This example shows how to programmatically remove all adorners from a specified <xref:System.Windows.UIElement>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="13504-104">Пример</span><span class="sxs-lookup"><span data-stu-id="13504-104">Example</span></span>  
 <span data-ttu-id="13504-105">Этот подробный пример кода удаляет все графические элементы в массив декоративных элементов, возвращенных <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A>.</span><span class="sxs-lookup"><span data-stu-id="13504-105">This verbose code example removes all of the adorners in the array of adorners returned by <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A>.</span></span>  <span data-ttu-id="13504-106">В этом примере происходит с графические <xref:System.Windows.UIElement> с именем *myTextBox*.</span><span class="sxs-lookup"><span data-stu-id="13504-106">This example happens to retrieve the adorners on a <xref:System.Windows.UIElement> named *myTextBox*.</span></span>  <span data-ttu-id="13504-107">Если у элемента, указанного в вызове <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A> нет графических объектов, `null` возвращается.</span><span class="sxs-lookup"><span data-stu-id="13504-107">If the element specified in the call to <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A> has no adorners, `null` is returned.</span></span>  <span data-ttu-id="13504-108">Этот код явно проверяет пустой массив и наилучшим образом подходит для приложений, где пустой массив должен быть относительно часто.</span><span class="sxs-lookup"><span data-stu-id="13504-108">This code explicitly checks for a null array, and is best suited for applications where a null array is expected to be relatively common.</span></span>  
  
 [!code-csharp[AdornersMiscCode#_RemoveAllAdornersLong](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removealladornerslong)]
 [!code-vb[AdornersMiscCode#_RemoveAllAdornersLong](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removealladornerslong)]  
  
## <a name="example"></a><span data-ttu-id="13504-109">Пример</span><span class="sxs-lookup"><span data-stu-id="13504-109">Example</span></span>  
 <span data-ttu-id="13504-110">Данный сжатый пример кода функционально эквивалентен подробному примеру, приведенному выше.</span><span class="sxs-lookup"><span data-stu-id="13504-110">This condensed code example is functionally equivalent to the verbose example shown above.</span></span> <span data-ttu-id="13504-111">Этот код не проверяет явно пустой массив, поэтому возможно, <xref:System.NullReferenceException> может быть вызвано исключение.</span><span class="sxs-lookup"><span data-stu-id="13504-111">This code does not explicitly check for a null array, so it is possible that a <xref:System.NullReferenceException> exception may be raised.</span></span>  <span data-ttu-id="13504-112">Этот код является наилучшим образом подходит для приложений, где пустой массив, ожидается редко.</span><span class="sxs-lookup"><span data-stu-id="13504-112">This code is best suited for applications where a null array is expected to be rare.</span></span>  
  
 [!code-csharp[AdornersMiscCode#_RemoveAllAdornersShort](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removealladornersshort)]
 [!code-vb[AdornersMiscCode#_RemoveAllAdornersShort](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removealladornersshort)]  
  
## <a name="see-also"></a><span data-ttu-id="13504-113">См. также</span><span class="sxs-lookup"><span data-stu-id="13504-113">See Also</span></span>  
 [<span data-ttu-id="13504-114">Общие сведения о декоративных элементах</span><span class="sxs-lookup"><span data-stu-id="13504-114">Adorners Overview</span></span>](../../../../docs/framework/wpf/controls/adorners-overview.md)
