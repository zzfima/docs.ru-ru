---
title: Практическое руководство. Реализация логики проверки для пользовательских объектов
ms.date: 08/02/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- checking for validation errors [WPF]
- validation errors [WPF], checking for
- implementing validation logic on custom objects [WPF]
- custom objects [WPF], implementing validation logic on
ms.assetid: 751fda9b-44f9-4d63-b4f2-1df07ac41e0f
ms.openlocfilehash: 8520504757e9e9ec9557b84ca2608b4cb99daf62
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59085926"
---
# <a name="how-to-implement-validation-logic-on-custom-objects"></a><span data-ttu-id="0aa24-102">Практическое руководство. Реализация логики проверки для пользовательских объектов</span><span class="sxs-lookup"><span data-stu-id="0aa24-102">How to: Implement Validation Logic on Custom Objects</span></span>
<span data-ttu-id="0aa24-103">В этом примере показано, как реализация логики проверки для пользовательского объекта, а затем привязать к нему.</span><span class="sxs-lookup"><span data-stu-id="0aa24-103">This example shows how to implement validation logic on a custom object and then bind to it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0aa24-104">Пример</span><span class="sxs-lookup"><span data-stu-id="0aa24-104">Example</span></span>  
 <span data-ttu-id="0aa24-105">Вы можете предоставить логику проверки в бизнес-слоя, если источник объекта реализует <xref:System.ComponentModel.IDataErrorInfo>, как показано в следующем примере, который определяет `Person` объект, реализующий <xref:System.ComponentModel.IDataErrorInfo>:</span><span class="sxs-lookup"><span data-stu-id="0aa24-105">You can provide validation logic on the business layer if your source object implements <xref:System.ComponentModel.IDataErrorInfo>, as in the following example, which defines a `Person` object that implements <xref:System.ComponentModel.IDataErrorInfo>:</span></span>  
  
 [!code-csharp[BusinessLayerValidation#IDataErrorInfo](~/samples/snippets/csharp/VS_Snippets_Wpf/BusinessLayerValidation/CSharp/Data.cs#idataerrorinfo)]
 [!code-vb[BusinessLayerValidation#IDataErrorInfo](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BusinessLayerValidation/VisualBasic/Data.vb#idataerrorinfo)]  
  
 <span data-ttu-id="0aa24-106">В следующем примере свойство text текстового поля привязывается к `Person.Age` свойство, которое станет доступным для привязки через объявление ресурса, которому предоставлен `x:Key` `data`.</span><span class="sxs-lookup"><span data-stu-id="0aa24-106">In the following example, the text property of the text box binds to the `Person.Age` property, which has been made available for binding through a resource declaration that is given the `x:Key` `data`.</span></span> <span data-ttu-id="0aa24-107"><xref:System.Windows.Controls.DataErrorValidationRule> Проверяет наличие ошибок проверки, вызванных <xref:System.ComponentModel.IDataErrorInfo> реализации.</span><span class="sxs-lookup"><span data-stu-id="0aa24-107">The <xref:System.Windows.Controls.DataErrorValidationRule> checks for the validation errors raised by the <xref:System.ComponentModel.IDataErrorInfo> implementation.</span></span>  
  
 [!code-xaml[BusinessLayerValidation#BoundTextBox](~/samples/snippets/csharp/VS_Snippets_Wpf/BusinessLayerValidation/CSharp/Window1.xaml?highlight=8,11-19,25-42)]  
  
 <span data-ttu-id="0aa24-108">Кроме того, вместо использования <xref:System.Windows.Controls.DataErrorValidationRule>, можно задать <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> свойства `true`.</span><span class="sxs-lookup"><span data-stu-id="0aa24-108">Alternatively, instead of using the <xref:System.Windows.Controls.DataErrorValidationRule>, you can set the <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> property to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0aa24-109">См. также</span><span class="sxs-lookup"><span data-stu-id="0aa24-109">See also</span></span>

- <xref:System.Windows.Controls.ExceptionValidationRule>
- [<span data-ttu-id="0aa24-110">Реализация проверки привязки</span><span class="sxs-lookup"><span data-stu-id="0aa24-110">Implement Binding Validation</span></span>](how-to-implement-binding-validation.md)
- [<span data-ttu-id="0aa24-111">Практические руководства</span><span class="sxs-lookup"><span data-stu-id="0aa24-111">How-to Topics</span></span>](data-binding-how-to-topics.md)
