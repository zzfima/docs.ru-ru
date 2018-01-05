---
title: "Практическое руководство. Реализация проверки привязки"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- validation of binding [WPF]
- data binding [WPF], validation of binding
- binding [WPF], validation of
ms.assetid: eb98b33d-9866-49ae-b981-bc5ff20d607a
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2d57fb099fa364d34b7df5c5fce792eb42079a31
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-implement-binding-validation"></a><span data-ttu-id="e4fa5-102">Практическое руководство. Реализация проверки привязки</span><span class="sxs-lookup"><span data-stu-id="e4fa5-102">How to: Implement Binding Validation</span></span>
<span data-ttu-id="e4fa5-103">В этом примере показано, как использовать <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> и триггера стиля для предоставления визуальную обратную связь, чтобы информировать пользователей при вводе недопустимого значения на основании пользовательского правила проверки.</span><span class="sxs-lookup"><span data-stu-id="e4fa5-103">This example shows how to use an <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> and a style trigger to provide visual feedback to inform the user when an invalid value is entered, based on a custom validation rule.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e4fa5-104">Пример</span><span class="sxs-lookup"><span data-stu-id="e4fa5-104">Example</span></span>  
 <span data-ttu-id="e4fa5-105">Текстовое содержимое <xref:System.Windows.Controls.TextBox> в следующем примере привязан к `Age` свойство (тип int) объекта источника привязки с именем `ods`.</span><span class="sxs-lookup"><span data-stu-id="e4fa5-105">The text content of the <xref:System.Windows.Controls.TextBox> in the following example is bound to the `Age` property (of type int) of a binding source object named `ods`.</span></span> <span data-ttu-id="e4fa5-106">Привязка настроена на использование правила проверки с именем `AgeRangeRule` так, чтобы при вводе нечисловых символов или значения меньше 21 или больше 130 рядом с текстовым полем появился красный восклицательный знак и подсказка с сообщением об ошибке, когда пользователь наводит указатель мыши на текстовое поле.</span><span class="sxs-lookup"><span data-stu-id="e4fa5-106">The binding is set up to use a validation rule named `AgeRangeRule` so that if the user enters non-numeric characters or a value that is smaller than 21 or greater than 130, a red exclamation mark appears next to the text box and a tool tip with the error message appears when the user moves the mouse over the text box.</span></span>  
  
 [!code-xaml[BindValidation#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="e4fa5-107">В следующем примере показана реализация `AgeRangeRule`, который наследует от <xref:System.Windows.Controls.ValidationRule> и переопределяет <xref:System.Windows.Controls.ValidationRule.Validate%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="e4fa5-107">The following example shows the implementation of `AgeRangeRule`, which inherits from <xref:System.Windows.Controls.ValidationRule> and overrides the <xref:System.Windows.Controls.ValidationRule.Validate%2A> method.</span></span> <span data-ttu-id="e4fa5-108">Метод Int32.Parse() вызывается для значения, чтобы убедиться в том, что он не содержит недопустимых символов.</span><span class="sxs-lookup"><span data-stu-id="e4fa5-108">The Int32.Parse() method is called on the value to make sure that it does not contain any invalid characters.</span></span> <span data-ttu-id="e4fa5-109"><xref:System.Windows.Controls.ValidationRule.Validate%2A> Возвращает <xref:System.Windows.Controls.ValidationResult> , указывающее, если значение допустимо на основе ли исключение перехватывается во время синтаксического анализа и ли оно за пределами нижнюю и верхнюю границу.</span><span class="sxs-lookup"><span data-stu-id="e4fa5-109">The <xref:System.Windows.Controls.ValidationRule.Validate%2A> method returns a <xref:System.Windows.Controls.ValidationResult> that indicates if the value is valid based on whether an exception is caught during the parsing and whether the age value is outside of the lower and upper bounds.</span></span>  
  
 [!code-csharp[BindValidation#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/AgeRangeRule.cs#3)]  
  
 <span data-ttu-id="e4fa5-110">В следующем примере показано пользовательское <xref:System.Windows.Controls.ControlTemplate> `validationTemplate` , создающего красный восклицательный знак для уведомления пользователя об ошибке проверки.</span><span class="sxs-lookup"><span data-stu-id="e4fa5-110">The following example shows the custom <xref:System.Windows.Controls.ControlTemplate> `validationTemplate` that creates a red exclamation mark to notify the user of a validation error.</span></span> <span data-ttu-id="e4fa5-111">Шаблоны элементов управления используются для переопределения внешнего вида элемента управления.</span><span class="sxs-lookup"><span data-stu-id="e4fa5-111">Control templates are used to redefine the appearance of a control.</span></span>  
  
 [!code-xaml[BindValidation#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#4)]  
  
 <span data-ttu-id="e4fa5-112">Как показано в следующем примере <xref:System.Windows.Controls.ToolTip> , показано сообщение об ошибке создается с использованием стиля с именем `textBoxInError`.</span><span class="sxs-lookup"><span data-stu-id="e4fa5-112">As shown in the following example, the <xref:System.Windows.Controls.ToolTip> that shows the error message is created using the style named `textBoxInError`.</span></span> <span data-ttu-id="e4fa5-113">Если значение <xref:System.Windows.Controls.Validation.HasError%2A> — `true`, триггер задает подсказке текущего <xref:System.Windows.Controls.TextBox> для первой ошибки проверки.</span><span class="sxs-lookup"><span data-stu-id="e4fa5-113">If the value of <xref:System.Windows.Controls.Validation.HasError%2A> is `true`, the trigger sets the tool tip of the current <xref:System.Windows.Controls.TextBox> to its first validation error.</span></span> <span data-ttu-id="e4fa5-114"><xref:System.Windows.Data.Binding.RelativeSource%2A> Равно <xref:System.Windows.Data.RelativeSourceMode.Self>, ссылающийся на текущий элемент.</span><span class="sxs-lookup"><span data-stu-id="e4fa5-114">The <xref:System.Windows.Data.Binding.RelativeSource%2A> is set to <xref:System.Windows.Data.RelativeSourceMode.Self>, referring to the current element.</span></span>  
  
 [!code-xaml[BindValidation#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#5)]  
  
 <span data-ttu-id="e4fa5-115">Полный пример см. в [Примере проверки привязки](http://go.microsoft.com/fwlink/?LinkID=159972).</span><span class="sxs-lookup"><span data-stu-id="e4fa5-115">For the complete example, see [Binding Validation Sample](http://go.microsoft.com/fwlink/?LinkID=159972).</span></span>  
  
 <span data-ttu-id="e4fa5-116">Обратите внимание, что если не указать настраиваемый <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> отображается шаблон ошибки по умолчанию для предоставления пользователю визуальную обратную связь при ошибке проверки.</span><span class="sxs-lookup"><span data-stu-id="e4fa5-116">Note that if you do not provide a custom <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> the default error template appears to provide visual feedback to the user when there is a validation error.</span></span> <span data-ttu-id="e4fa5-117">См. "Проверка данных" в разделе [Общие сведения о привязке данных](../../../../docs/framework/wpf/data/data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e4fa5-117">See "Data Validation" in [Data Binding Overview](../../../../docs/framework/wpf/data/data-binding-overview.md) for more information.</span></span> <span data-ttu-id="e4fa5-118">Кроме того, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет встроенное правило проверки, которое отслеживает исключения, получаемые во время обновления свойства источника привязки.</span><span class="sxs-lookup"><span data-stu-id="e4fa5-118">Also, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] provides a built-in validation rule that catches exceptions that are thrown during the update of the binding source property.</span></span> <span data-ttu-id="e4fa5-119">Дополнительные сведения см. в разделе <xref:System.Windows.Controls.ExceptionValidationRule>.</span><span class="sxs-lookup"><span data-stu-id="e4fa5-119">For more information, see <xref:System.Windows.Controls.ExceptionValidationRule>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4fa5-120">См. также</span><span class="sxs-lookup"><span data-stu-id="e4fa5-120">See Also</span></span>  
 [<span data-ttu-id="e4fa5-121">Общие сведения о привязке данных</span><span class="sxs-lookup"><span data-stu-id="e4fa5-121">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="e4fa5-122">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="e4fa5-122">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
