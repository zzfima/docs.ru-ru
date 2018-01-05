---
title: "Практическое руководство. Преобразование привязанных данных"
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
helpviewer_keywords:
- converting [WPF], bound data
- data binding [WPF], converting bound data
- binding data [WPF], converting bound data
ms.assetid: b00aaa19-c6df-4c3b-a9fd-88a0b488df2b
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3f4bcde15940e76e1d022658e32ff6ef8676e45e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-convert-bound-data"></a><span data-ttu-id="0481f-102">Практическое руководство. Преобразование привязанных данных</span><span class="sxs-lookup"><span data-stu-id="0481f-102">How to: Convert Bound Data</span></span>
<span data-ttu-id="0481f-103">В этом примере показано, как применить преобразования к данным, используемым в привязках.</span><span class="sxs-lookup"><span data-stu-id="0481f-103">This example shows how to apply conversion to data that is used in bindings.</span></span>  
  
 <span data-ttu-id="0481f-104">Чтобы преобразовать данные во время привязки, необходимо создать класс, реализующий <xref:System.Windows.Data.IValueConverter> интерфейс, который включает в себя <xref:System.Windows.Data.IValueConverter.Convert%2A> и <xref:System.Windows.Data.IValueConverter.ConvertBack%2A> методы.</span><span class="sxs-lookup"><span data-stu-id="0481f-104">To convert data during binding, you must create a class that implements the <xref:System.Windows.Data.IValueConverter> interface, which includes the <xref:System.Windows.Data.IValueConverter.Convert%2A> and <xref:System.Windows.Data.IValueConverter.ConvertBack%2A> methods.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0481f-105">Пример</span><span class="sxs-lookup"><span data-stu-id="0481f-105">Example</span></span>  
 <span data-ttu-id="0481f-106">Пример реализации преобразователя преобразует значение даты, переданный, чтобы отобразить только года, месяца и дня.</span><span class="sxs-lookup"><span data-stu-id="0481f-106">The following example shows the implementation of a date converter that converts the date value passed in so that it only shows the year, the month, and the day.</span></span> <span data-ttu-id="0481f-107">При реализации <xref:System.Windows.Data.IValueConverter> интерфейс, рекомендуется для отмечания реализацию с <xref:System.Windows.Data.ValueConversionAttribute> атрибут, чтобы указать для разработки средств типы данных, участвующие в преобразовании, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="0481f-107">When implementing the <xref:System.Windows.Data.IValueConverter> interface, it is a good practice to decorate the implementation with a <xref:System.Windows.Data.ValueConversionAttribute> attribute to indicate to development tools the data types involved in the conversion, as in the following example:</span></span>  
  
 [!code-csharp[DataBindingLab#18](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DateConverter.cs#18)]
 [!code-vb[DataBindingLab#18](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/DateConverter.vb#18)]  
  
 <span data-ttu-id="0481f-108">После создания преобразователь, его можно добавить в качестве ресурса в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] файла.</span><span class="sxs-lookup"><span data-stu-id="0481f-108">Once you have created a converter, you can add it as a resource in your [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file.</span></span> <span data-ttu-id="0481f-109">В следующем примере *src* соответствует пространству имен, в котором *DateConverter* определен.</span><span class="sxs-lookup"><span data-stu-id="0481f-109">In the following example, *src* maps to the namespace in which *DateConverter* is defined.</span></span>  
  
 [!code-xaml[DataBindingLab#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#15)]  
  
 <span data-ttu-id="0481f-110">Наконец можно использовать преобразователь в привязке, используя следующий синтаксис.</span><span class="sxs-lookup"><span data-stu-id="0481f-110">Finally, you can use the converter in your binding using the following syntax.</span></span> <span data-ttu-id="0481f-111">В следующем примере текстовое содержимое <xref:System.Windows.Controls.TextBlock> привязан к *StartDate*, который является свойством внешнего источника данных.</span><span class="sxs-lookup"><span data-stu-id="0481f-111">In the following example, the text content of the <xref:System.Windows.Controls.TextBlock> is bound to *StartDate*, which is a property of an external data source.</span></span>  
  
 [!code-xaml[DataBindingLab#17](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#17)]  
  
 <span data-ttu-id="0481f-112">Ресурсы стиля, указанные в приведенном выше примере определяются в разделе ресурсов, не приведенные в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="0481f-112">The style resources referenced in the above example are defined in a resource section not shown in this topic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0481f-113">См. также</span><span class="sxs-lookup"><span data-stu-id="0481f-113">See Also</span></span>  
 [<span data-ttu-id="0481f-114">Реализация проверки привязки</span><span class="sxs-lookup"><span data-stu-id="0481f-114">Implement Binding Validation</span></span>](../../../../docs/framework/wpf/data/how-to-implement-binding-validation.md)  
 [<span data-ttu-id="0481f-115">Общие сведения о привязке данных</span><span class="sxs-lookup"><span data-stu-id="0481f-115">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="0481f-116">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="0481f-116">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
