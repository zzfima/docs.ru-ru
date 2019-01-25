---
title: Как выполнить Создание значений на основе списка связанных элементов
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], MultiBinding
- Multibinding [WPF]
ms.assetid: b3d06378-b511-4181-95aa-316d60c9229b
ms.openlocfilehash: 8f4e5b7767e475128b61080ca87e38ee311f4a3a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54706434"
---
# <a name="how-to-produce-a-value-based-on-a-list-of-bound-items"></a><span data-ttu-id="ef869-102">Как выполнить Создание значений на основе списка связанных элементов</span><span class="sxs-lookup"><span data-stu-id="ef869-102">How to: Produce a Value Based on a List of Bound Items</span></span>
<span data-ttu-id="ef869-103"><xref:System.Windows.Data.MultiBinding> позволяет привязать целевое свойство привязки к списку свойств источника и затем применить логику для получения значения с заданными входными данными.</span><span class="sxs-lookup"><span data-stu-id="ef869-103"><xref:System.Windows.Data.MultiBinding> allows you to bind a binding target property to a list of source properties and then apply logic to produce a value with the given inputs.</span></span> <span data-ttu-id="ef869-104">В этом примере демонстрируется использование <xref:System.Windows.Data.MultiBinding>.</span><span class="sxs-lookup"><span data-stu-id="ef869-104">This example demonstrates how to use <xref:System.Windows.Data.MultiBinding>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ef869-105">Пример</span><span class="sxs-lookup"><span data-stu-id="ef869-105">Example</span></span>  
 <span data-ttu-id="ef869-106">В следующем примере `NameListData` ссылается на коллекцию объектов `PersonName`, которые являются объектами, содержащими два свойства, `firstName` и `lastName`.</span><span class="sxs-lookup"><span data-stu-id="ef869-106">In the following example, `NameListData` refers to a collection of `PersonName` objects, which are objects that contain two properties, `firstName` and `lastName`.</span></span> <span data-ttu-id="ef869-107">В следующем примере создается <xref:System.Windows.Controls.TextBlock> , показаны имена и фамилии человека с фамилией первого.</span><span class="sxs-lookup"><span data-stu-id="ef869-107">The following example produces a <xref:System.Windows.Controls.TextBlock> that shows the first and last names of a person with the last name first.</span></span>  
  
 [!code-xaml[MultiBinding#Resources1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#resources1)]  
[!code-xaml[MultiBinding#Resources2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#resources2)]  
[!code-xaml[MultiBinding#MultiBindingTextBox2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#multibindingtextbox2)]  
[!code-xaml[MultiBinding#Window](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#window)]  
  
 <span data-ttu-id="ef869-108">Чтобы понять, как получается формат фамилии-имени, рассмотрим реализацию `NameConverter`:</span><span class="sxs-lookup"><span data-stu-id="ef869-108">To understand how the last-name-first format is produced, let's take a look at the implementation of the `NameConverter`:</span></span>  
  
 [!code-csharp[MultiBinding#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/NameConverter.cs#3)]
 [!code-vb[MultiBinding#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MultiBinding/VisualBasic/NameConverter.vb#3)]  
  
 <span data-ttu-id="ef869-109">Класс `NameConverter` реализует интерфейс списка <xref:System.Windows.Data.IMultiValueConverter>.</span><span class="sxs-lookup"><span data-stu-id="ef869-109">`NameConverter` implements the <xref:System.Windows.Data.IMultiValueConverter> interface.</span></span> <span data-ttu-id="ef869-110">`NameConverter` принимает значения от отдельных привязок и сохраняет их в массиве объектов значений.</span><span class="sxs-lookup"><span data-stu-id="ef869-110">`NameConverter` takes the values from the individual bindings and stores them in the values object array.</span></span> <span data-ttu-id="ef869-111">Порядок, в котором <xref:System.Windows.Data.Binding> элементы отображаются в разделе <xref:System.Windows.Data.MultiBinding> соответствует порядку, в которой хранятся эти значения в массиве.</span><span class="sxs-lookup"><span data-stu-id="ef869-111">The order in which the <xref:System.Windows.Data.Binding> elements appear under the <xref:System.Windows.Data.MultiBinding> element is the order in which those values are stored in the array.</span></span> <span data-ttu-id="ef869-112">Значение <xref:System.Windows.Data.MultiBinding.ConverterParameter%2A> атрибут ссылается аргумент параметра <xref:System.Windows.Data.MultiBinding.Converter%2A> метод, который переключается на параметр для определения формата имени.</span><span class="sxs-lookup"><span data-stu-id="ef869-112">The value of the <xref:System.Windows.Data.MultiBinding.ConverterParameter%2A> attribute is referenced by the parameter argument of the <xref:System.Windows.Data.MultiBinding.Converter%2A> method, which performs a switch on the parameter to determine how to format the name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef869-113">См. также</span><span class="sxs-lookup"><span data-stu-id="ef869-113">See also</span></span>
- [<span data-ttu-id="ef869-114">Преобразование привязанных данных</span><span class="sxs-lookup"><span data-stu-id="ef869-114">Convert Bound Data</span></span>](../../../../docs/framework/wpf/data/how-to-convert-bound-data.md)
- [<span data-ttu-id="ef869-115">Общие сведения о привязке данных</span><span class="sxs-lookup"><span data-stu-id="ef869-115">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)
- [<span data-ttu-id="ef869-116">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="ef869-116">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
