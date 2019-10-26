---
title: Практическое руководство. Реализация проверки привязки
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- validation of binding [WPF]
- data binding [WPF], validation of binding
- binding [WPF], validation of
ms.assetid: eb98b33d-9866-49ae-b981-bc5ff20d607a
ms.openlocfilehash: 7a1a8df78a785066992472c7de37f958ae3467f1
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2019
ms.locfileid: "72920154"
---
# <a name="how-to-implement-binding-validation"></a><span data-ttu-id="ad37a-102">Практическое руководство. Реализация проверки привязки</span><span class="sxs-lookup"><span data-stu-id="ad37a-102">How to: Implement Binding Validation</span></span>

<span data-ttu-id="ad37a-103">В этом примере показано, как использовать <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> и триггер стиля, чтобы предоставить визуальную обратную связь для информирования пользователя о том, что при вводе недопустимого значения на основе настраиваемого правила проверки.</span><span class="sxs-lookup"><span data-stu-id="ad37a-103">This example shows how to use an <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> and a style trigger to provide visual feedback to inform the user when an invalid value is entered, based on a custom validation rule.</span></span>

## <a name="example"></a><span data-ttu-id="ad37a-104">Пример</span><span class="sxs-lookup"><span data-stu-id="ad37a-104">Example</span></span>

<span data-ttu-id="ad37a-105">Текстовое содержимое <xref:System.Windows.Controls.TextBox> в следующем примере привязано к свойству `Age` (типа int) объекта источника привязки с именем `ods`.</span><span class="sxs-lookup"><span data-stu-id="ad37a-105">The text content of the <xref:System.Windows.Controls.TextBox> in the following example is bound to the `Age` property (of type int) of a binding source object named `ods`.</span></span> <span data-ttu-id="ad37a-106">Привязка настроена на использование правила проверки с именем `AgeRangeRule` так, чтобы при вводе нечисловых символов или значения меньше 21 или больше 130 рядом с текстовым полем появился красный восклицательный знак и подсказка с сообщением об ошибке, когда пользователь наводит указатель мыши на текстовое поле.</span><span class="sxs-lookup"><span data-stu-id="ad37a-106">The binding is set up to use a validation rule named `AgeRangeRule` so that if the user enters non-numeric characters or a value that is smaller than 21 or greater than 130, a red exclamation mark appears next to the text box and a tool tip with the error message appears when the user moves the mouse over the text box.</span></span>

[!code-xaml[BindValidation#2](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#2)]

<span data-ttu-id="ad37a-107">В следующем примере показана реализация `AgeRangeRule`, которая наследуется от <xref:System.Windows.Controls.ValidationRule> и переопределяет метод <xref:System.Windows.Controls.ValidationRule.Validate%2A>.</span><span class="sxs-lookup"><span data-stu-id="ad37a-107">The following example shows the implementation of `AgeRangeRule`, which inherits from <xref:System.Windows.Controls.ValidationRule> and overrides the <xref:System.Windows.Controls.ValidationRule.Validate%2A> method.</span></span> <span data-ttu-id="ad37a-108">Метод `Int32.Parse` вызывается для значения, чтобы убедиться, что он не содержит недопустимых символов.</span><span class="sxs-lookup"><span data-stu-id="ad37a-108">The `Int32.Parse` method is called on the value to make sure that it does not contain any invalid characters.</span></span> <span data-ttu-id="ad37a-109">Метод <xref:System.Windows.Controls.ValidationRule.Validate%2A> возвращает <xref:System.Windows.Controls.ValidationResult>, который указывает, является ли значение допустимым в зависимости от того, перехвачено исключение во время синтаксического анализа и является ли значение возраста за пределами нижней и верхней границ.</span><span class="sxs-lookup"><span data-stu-id="ad37a-109">The <xref:System.Windows.Controls.ValidationRule.Validate%2A> method returns a <xref:System.Windows.Controls.ValidationResult> that indicates if the value is valid based on whether an exception is caught during the parsing and whether the age value is outside of the lower and upper bounds.</span></span>

[!code-csharp[BindValidation#3](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/AgeRangeRule.cs#3)]
[!code-vb[BindValidation#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BindValidation/VisualBasic/AgeRangeRule.vb#3)]

<span data-ttu-id="ad37a-110">В следующем примере показан пользовательский <xref:System.Windows.Controls.ControlTemplate> `validationTemplate`, который создает красный восклицательный знак, чтобы уведомить пользователя об ошибке проверки.</span><span class="sxs-lookup"><span data-stu-id="ad37a-110">The following example shows the custom <xref:System.Windows.Controls.ControlTemplate> `validationTemplate` that creates a red exclamation mark to notify the user of a validation error.</span></span> <span data-ttu-id="ad37a-111">Шаблоны элементов управления используются для переопределения внешнего вида элемента управления.</span><span class="sxs-lookup"><span data-stu-id="ad37a-111">Control templates are used to redefine the appearance of a control.</span></span>

[!code-xaml[BindValidation#4](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#4)]

<span data-ttu-id="ad37a-112">Как показано в следующем примере, <xref:System.Windows.Controls.ToolTip>, показывающий сообщение об ошибке, создается с использованием стиля с именем `textBoxInError`.</span><span class="sxs-lookup"><span data-stu-id="ad37a-112">As shown in the following example, the <xref:System.Windows.Controls.ToolTip> that shows the error message is created using the style named `textBoxInError`.</span></span> <span data-ttu-id="ad37a-113">Если значение <xref:System.Windows.Controls.Validation.HasError%2A> равно `true`, триггер устанавливает подсказку текущего <xref:System.Windows.Controls.TextBox> в первую ошибку проверки.</span><span class="sxs-lookup"><span data-stu-id="ad37a-113">If the value of <xref:System.Windows.Controls.Validation.HasError%2A> is `true`, the trigger sets the tool tip of the current <xref:System.Windows.Controls.TextBox> to its first validation error.</span></span> <span data-ttu-id="ad37a-114">Для <xref:System.Windows.Data.Binding.RelativeSource%2A> задано значение <xref:System.Windows.Data.RelativeSourceMode.Self>, ссылающееся на текущий элемент.</span><span class="sxs-lookup"><span data-stu-id="ad37a-114">The <xref:System.Windows.Data.Binding.RelativeSource%2A> is set to <xref:System.Windows.Data.RelativeSourceMode.Self>, referring to the current element.</span></span>

[!code-xaml[BindValidation#5](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#5)]

<span data-ttu-id="ad37a-115">Полный пример см. в разделе [образец проверки привязки](https://github.com/Microsoft/WPF-Samples/tree/master/Data%20Binding/BindValidation).</span><span class="sxs-lookup"><span data-stu-id="ad37a-115">For the complete example, see [Bind Validation sample](https://github.com/Microsoft/WPF-Samples/tree/master/Data%20Binding/BindValidation).</span></span>
  
<span data-ttu-id="ad37a-116">Обратите внимание, что если не указать настраиваемый <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> шаблон ошибок по умолчанию будет предоставлять пользователю визуальный отзыв при возникновении ошибки проверки.</span><span class="sxs-lookup"><span data-stu-id="ad37a-116">Note that if you do not provide a custom <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> the default error template appears to provide visual feedback to the user when there is a validation error.</span></span> <span data-ttu-id="ad37a-117">См. "Проверка данных" в разделе [Общие сведения о привязке данных](data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ad37a-117">See "Data Validation" in [Data Binding Overview](data-binding-overview.md) for more information.</span></span> <span data-ttu-id="ad37a-118">Кроме того, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет встроенное правило проверки, которое отслеживает исключения, получаемые во время обновления свойства источника привязки.</span><span class="sxs-lookup"><span data-stu-id="ad37a-118">Also, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] provides a built-in validation rule that catches exceptions that are thrown during the update of the binding source property.</span></span> <span data-ttu-id="ad37a-119">Для получения дополнительной информации см. <xref:System.Windows.Controls.ExceptionValidationRule>.</span><span class="sxs-lookup"><span data-stu-id="ad37a-119">For more information, see <xref:System.Windows.Controls.ExceptionValidationRule>.</span></span>

## <a name="see-also"></a><span data-ttu-id="ad37a-120">См. также</span><span class="sxs-lookup"><span data-stu-id="ad37a-120">See also</span></span>

- [<span data-ttu-id="ad37a-121">Общие сведения о привязке данных</span><span class="sxs-lookup"><span data-stu-id="ad37a-121">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="ad37a-122">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="ad37a-122">How-to Topics</span></span>](data-binding-how-to-topics.md)
