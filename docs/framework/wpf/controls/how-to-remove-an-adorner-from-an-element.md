---
title: Практическое руководство. Удаление декоративного объекта из элемента
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], removing
ms.assetid: 97cf4d9f-0596-429e-8526-32a30aa4ae99
ms.openlocfilehash: 256dd6fa0117f88aec2ef6b60c6dcd4c33b57855
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59212405"
---
# <a name="how-to-remove-an-adorner-from-an-element"></a><span data-ttu-id="ee6eb-102">Практическое руководство. Удаление декоративного объекта из элемента</span><span class="sxs-lookup"><span data-stu-id="ee6eb-102">How to: Remove an Adorner from an Element</span></span>
<span data-ttu-id="ee6eb-103">В этом примере показано, как программными средствами удалить определенный декоративный элемент из указанного <xref:System.Windows.UIElement>.</span><span class="sxs-lookup"><span data-stu-id="ee6eb-103">This example shows how to programmatically remove a specific adorner from a specified <xref:System.Windows.UIElement>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ee6eb-104">Пример</span><span class="sxs-lookup"><span data-stu-id="ee6eb-104">Example</span></span>  
 <span data-ttu-id="ee6eb-105">Этот подробный пример кода удаляет первый декоративный элемент в массиве декоративных элементов, возвращенных <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A>.</span><span class="sxs-lookup"><span data-stu-id="ee6eb-105">This verbose code example removes the first adorner in the array of adorners returned by <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A>.</span></span>  <span data-ttu-id="ee6eb-106">В этом примере происходит с графические <xref:System.Windows.UIElement> с именем *myTextBox*.</span><span class="sxs-lookup"><span data-stu-id="ee6eb-106">This example happens to retrieve the adorners on a <xref:System.Windows.UIElement> named *myTextBox*.</span></span>  <span data-ttu-id="ee6eb-107">Если этот элемент указан в вызове <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A> нет графических объектов, `null` возвращается.</span><span class="sxs-lookup"><span data-stu-id="ee6eb-107">If the element specified in the call to <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A> has no adorners, `null` is returned.</span></span>  <span data-ttu-id="ee6eb-108">Этот код явно проверяет пустой массив и лучше всего подходит для приложений, где должен быть относительно распространенную пустой массив.</span><span class="sxs-lookup"><span data-stu-id="ee6eb-108">This code explicitly checks for a null array, and is best suited for applications where a null array is expected to be relatively common.</span></span>  
  
 [!code-csharp[AdornersMiscCode#_RemoveSpecificAdornerLong](~/samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removespecificadornerlong)]
 [!code-vb[AdornersMiscCode#_RemoveSpecificAdornerLong](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removespecificadornerlong)]  
  
## <a name="example"></a><span data-ttu-id="ee6eb-109">Пример</span><span class="sxs-lookup"><span data-stu-id="ee6eb-109">Example</span></span>  
 <span data-ttu-id="ee6eb-110">Данный сжатый пример кода функционально эквивалентен подробному примеру, приведенному выше.</span><span class="sxs-lookup"><span data-stu-id="ee6eb-110">This condensed code example is functionally equivalent to the verbose example shown above.</span></span> <span data-ttu-id="ee6eb-111">Этот код явно не проверяет пустой массив, так что вполне возможно, <xref:System.NullReferenceException> может быть вызвано исключение.</span><span class="sxs-lookup"><span data-stu-id="ee6eb-111">This code does not explicitly check for a null array, so it is possible that a <xref:System.NullReferenceException> exception may be raised.</span></span>  <span data-ttu-id="ee6eb-112">Этот код лучше всего подходит для приложений, где ожидается пустой массив довольно редки.</span><span class="sxs-lookup"><span data-stu-id="ee6eb-112">This code is best suited for applications where a null array is expected to be rare.</span></span>  
  
 [!code-csharp[AdornersMiscCode#_RemoveSpecificAdornerShort](~/samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removespecificadornershort)]
 [!code-vb[AdornersMiscCode#_RemoveSpecificAdornerShort](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removespecificadornershort)]  
  
## <a name="see-also"></a><span data-ttu-id="ee6eb-113">См. также</span><span class="sxs-lookup"><span data-stu-id="ee6eb-113">See also</span></span>

- [<span data-ttu-id="ee6eb-114">Общие сведения о декоративных элементах</span><span class="sxs-lookup"><span data-stu-id="ee6eb-114">Adorners Overview</span></span>](adorners-overview.md)
