---
title: Практическое руководство. Создание значений на основе списка связанных элементов
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], MultiBinding
- Multibinding [WPF]
ms.assetid: b3d06378-b511-4181-95aa-316d60c9229b
ms.openlocfilehash: 77c832c1460749ced58e7a20af333c5ed9dd1555
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57368129"
---
# <a name="how-to-produce-a-value-based-on-a-list-of-bound-items"></a><span data-ttu-id="730c9-102">Практическое руководство. Создание значений на основе списка связанных элементов</span><span class="sxs-lookup"><span data-stu-id="730c9-102">How to: Produce a Value Based on a List of Bound Items</span></span>
<span data-ttu-id="730c9-103"><xref:System.Windows.Data.MultiBinding> позволяет привязать целевое свойство привязки к списку свойств источника и затем применить логику для получения значения с заданными входными данными.</span><span class="sxs-lookup"><span data-stu-id="730c9-103"><xref:System.Windows.Data.MultiBinding> allows you to bind a binding target property to a list of source properties and then apply logic to produce a value with the given inputs.</span></span> <span data-ttu-id="730c9-104">В этом примере демонстрируется использование <xref:System.Windows.Data.MultiBinding>.</span><span class="sxs-lookup"><span data-stu-id="730c9-104">This example demonstrates how to use <xref:System.Windows.Data.MultiBinding>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="730c9-105">Пример</span><span class="sxs-lookup"><span data-stu-id="730c9-105">Example</span></span>  
 <span data-ttu-id="730c9-106">В следующем примере `NameListData` ссылается на коллекцию объектов `PersonName`, которые являются объектами, содержащими два свойства, `firstName` и `lastName`.</span><span class="sxs-lookup"><span data-stu-id="730c9-106">In the following example, `NameListData` refers to a collection of `PersonName` objects, which are objects that contain two properties, `firstName` and `lastName`.</span></span> <span data-ttu-id="730c9-107">В следующем примере создается <xref:System.Windows.Controls.TextBlock> , показаны имена и фамилии человека с фамилией первого.</span><span class="sxs-lookup"><span data-stu-id="730c9-107">The following example produces a <xref:System.Windows.Controls.TextBlock> that shows the first and last names of a person with the last name first.</span></span>  
  
 [!code-xaml[MultiBinding#Resources1](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#resources1)]  
[!code-xaml[MultiBinding#Resources2](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#resources2)]  
[!code-xaml[MultiBinding#MultiBindingTextBox2](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#multibindingtextbox2)]  
[!code-xaml[MultiBinding#Window](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#window)]  
  
 <span data-ttu-id="730c9-108">Чтобы понять, как получается формат фамилии-имени, рассмотрим реализацию `NameConverter`:</span><span class="sxs-lookup"><span data-stu-id="730c9-108">To understand how the last-name-first format is produced, let's take a look at the implementation of the `NameConverter`:</span></span>  
  
 [!code-csharp[MultiBinding#3](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/NameConverter.cs#3)]
 [!code-vb[MultiBinding#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MultiBinding/VisualBasic/NameConverter.vb#3)]  
  
 <span data-ttu-id="730c9-109">Класс `NameConverter` реализует интерфейс списка <xref:System.Windows.Data.IMultiValueConverter>.</span><span class="sxs-lookup"><span data-stu-id="730c9-109">`NameConverter` implements the <xref:System.Windows.Data.IMultiValueConverter> interface.</span></span> <span data-ttu-id="730c9-110">`NameConverter` принимает значения от отдельных привязок и сохраняет их в массиве объектов значений.</span><span class="sxs-lookup"><span data-stu-id="730c9-110">`NameConverter` takes the values from the individual bindings and stores them in the values object array.</span></span> <span data-ttu-id="730c9-111">Порядок, в котором <xref:System.Windows.Data.Binding> элементы отображаются в разделе <xref:System.Windows.Data.MultiBinding> соответствует порядку, в которой хранятся эти значения в массиве.</span><span class="sxs-lookup"><span data-stu-id="730c9-111">The order in which the <xref:System.Windows.Data.Binding> elements appear under the <xref:System.Windows.Data.MultiBinding> element is the order in which those values are stored in the array.</span></span> <span data-ttu-id="730c9-112">Значение <xref:System.Windows.Data.MultiBinding.ConverterParameter%2A> атрибут ссылается аргумент параметра <xref:System.Windows.Data.MultiBinding.Converter%2A> метод, который переключается на параметр для определения формата имени.</span><span class="sxs-lookup"><span data-stu-id="730c9-112">The value of the <xref:System.Windows.Data.MultiBinding.ConverterParameter%2A> attribute is referenced by the parameter argument of the <xref:System.Windows.Data.MultiBinding.Converter%2A> method, which performs a switch on the parameter to determine how to format the name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="730c9-113">См. также</span><span class="sxs-lookup"><span data-stu-id="730c9-113">See also</span></span>
- [<span data-ttu-id="730c9-114">Преобразование привязанных данных</span><span class="sxs-lookup"><span data-stu-id="730c9-114">Convert Bound Data</span></span>](how-to-convert-bound-data.md)
- [<span data-ttu-id="730c9-115">Общие сведения о привязке данных</span><span class="sxs-lookup"><span data-stu-id="730c9-115">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="730c9-116">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="730c9-116">How-to Topics</span></span>](data-binding-how-to-topics.md)
