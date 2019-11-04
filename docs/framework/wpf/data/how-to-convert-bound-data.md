---
title: Практическое руководство. Преобразование привязанных данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- converting [WPF], bound data
- data binding [WPF], converting bound data
- binding data [WPF], converting bound data
ms.assetid: b00aaa19-c6df-4c3b-a9fd-88a0b488df2b
ms.openlocfilehash: f9ad390626092d481bf47f017f643a29302c1b29
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458866"
---
# <a name="how-to-convert-bound-data"></a><span data-ttu-id="b2055-102">Практическое руководство. Преобразование привязанных данных</span><span class="sxs-lookup"><span data-stu-id="b2055-102">How to: Convert Bound Data</span></span>
<span data-ttu-id="b2055-103">В этом примере показано, как применить преобразование к данным, используемым в привязках.</span><span class="sxs-lookup"><span data-stu-id="b2055-103">This example shows how to apply conversion to data that is used in bindings.</span></span>  
  
 <span data-ttu-id="b2055-104">Для преобразования данных во время привязки необходимо создать класс, реализующий интерфейс <xref:System.Windows.Data.IValueConverter>, который включает в себя методы <xref:System.Windows.Data.IValueConverter.Convert%2A> и <xref:System.Windows.Data.IValueConverter.ConvertBack%2A>.</span><span class="sxs-lookup"><span data-stu-id="b2055-104">To convert data during binding, you must create a class that implements the <xref:System.Windows.Data.IValueConverter> interface, which includes the <xref:System.Windows.Data.IValueConverter.Convert%2A> and <xref:System.Windows.Data.IValueConverter.ConvertBack%2A> methods.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b2055-105">Пример</span><span class="sxs-lookup"><span data-stu-id="b2055-105">Example</span></span>  
 <span data-ttu-id="b2055-106">В следующем примере показана реализация преобразователя дат, который преобразует значение даты, переданное в, чтобы показать только год, месяц и день.</span><span class="sxs-lookup"><span data-stu-id="b2055-106">The following example shows the implementation of a date converter that converts the date value passed in so that it only shows the year, the month, and the day.</span></span> <span data-ttu-id="b2055-107">При реализации интерфейса <xref:System.Windows.Data.IValueConverter> рекомендуется снабдить реализацию атрибутом <xref:System.Windows.Data.ValueConversionAttribute>, чтобы указать средствам разработки типы данных, участвующие в преобразовании, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="b2055-107">When implementing the <xref:System.Windows.Data.IValueConverter> interface, it is a good practice to decorate the implementation with a <xref:System.Windows.Data.ValueConversionAttribute> attribute to indicate to development tools the data types involved in the conversion, as in the following example:</span></span>  
  
 [!code-csharp[DataBindingLab#18](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DateConverter.cs#18)]
 [!code-vb[DataBindingLab#18](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/DateConverter.vb#18)]  
  
 <span data-ttu-id="b2055-108">После создания конвертера его можно добавить в качестве ресурса в файл [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b2055-108">Once you have created a converter, you can add it as a resource in your [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file.</span></span> <span data-ttu-id="b2055-109">В следующем примере *src* сопоставляется с пространством имен, в котором определен *датеконвертер* .</span><span class="sxs-lookup"><span data-stu-id="b2055-109">In the following example, *src* maps to the namespace in which *DateConverter* is defined.</span></span>  
  
 [!code-xaml[DataBindingLab#15](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#15)]  
  
 <span data-ttu-id="b2055-110">Наконец, можно использовать преобразователь в привязке, используя следующий синтаксис.</span><span class="sxs-lookup"><span data-stu-id="b2055-110">Finally, you can use the converter in your binding using the following syntax.</span></span> <span data-ttu-id="b2055-111">В следующем примере текстовое содержимое <xref:System.Windows.Controls.TextBlock> привязано к *StartDate*, которое является свойством внешнего источника данных.</span><span class="sxs-lookup"><span data-stu-id="b2055-111">In the following example, the text content of the <xref:System.Windows.Controls.TextBlock> is bound to *StartDate*, which is a property of an external data source.</span></span>  
  
 [!code-xaml[DataBindingLab#17](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#17)]  
  
 <span data-ttu-id="b2055-112">Ресурсы стилей, упоминаемые в приведенном выше примере, определяются в разделе ресурсов, не показанном в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="b2055-112">The style resources referenced in the above example are defined in a resource section not shown in this topic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2055-113">См. также</span><span class="sxs-lookup"><span data-stu-id="b2055-113">See also</span></span>

- [<span data-ttu-id="b2055-114">Реализация проверки привязки</span><span class="sxs-lookup"><span data-stu-id="b2055-114">Implement Binding Validation</span></span>](how-to-implement-binding-validation.md)
- [<span data-ttu-id="b2055-115">Общие сведения о привязке данных</span><span class="sxs-lookup"><span data-stu-id="b2055-115">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="b2055-116">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="b2055-116">How-to Topics</span></span>](data-binding-how-to-topics.md)
