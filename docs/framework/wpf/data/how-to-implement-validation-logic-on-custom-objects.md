---
title: Практическое руководство. Реализация проверки для пользовательских объектов
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- checking for validation errors [WPF]
- validation errors [WPF], checking for
- implementing validation logic on custom objects [WPF]
- custom objects [WPF], implementing validation logic on
ms.assetid: 751fda9b-44f9-4d63-b4f2-1df07ac41e0f
ms.openlocfilehash: dbeddb5eb6996d5758717ddd2d4d5af0b6f57f3c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33555968"
---
# <a name="how-to-implement-validation-logic-on-custom-objects"></a><span data-ttu-id="f3ec8-102">Практическое руководство. Реализация проверки для пользовательских объектов</span><span class="sxs-lookup"><span data-stu-id="f3ec8-102">How to: Implement Validation Logic on Custom Objects</span></span>
<span data-ttu-id="f3ec8-103">В этом примере показано, как реализовать логику проверки для пользовательского объекта, а затем привязать к нему.</span><span class="sxs-lookup"><span data-stu-id="f3ec8-103">This example shows how to implement validation logic on a custom object and then bind to it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f3ec8-104">Пример</span><span class="sxs-lookup"><span data-stu-id="f3ec8-104">Example</span></span>  
 <span data-ttu-id="f3ec8-105">Можно обеспечить проверку на бизнес-уровне, если источник объекта реализует <xref:System.ComponentModel.IDataErrorInfo>, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="f3ec8-105">You can provide validation logic on the business layer if your source object implements <xref:System.ComponentModel.IDataErrorInfo>, as in the following example:</span></span>  
  
 [!code-csharp[BusinessLayerValidation#IDataErrorInfo](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BusinessLayerValidation/CSharp/Data.cs#idataerrorinfo)]
 [!code-vb[BusinessLayerValidation#IDataErrorInfo](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BusinessLayerValidation/VisualBasic/Data.vb#idataerrorinfo)]  
  
 <span data-ttu-id="f3ec8-106">В следующем примере свойство text текстового поля привязывается к `Age` свойство `Person` объекта, который был сделан доступным для привязки через объявление ресурса, которому дано `x:Key``data`.</span><span class="sxs-lookup"><span data-stu-id="f3ec8-106">In the following example, the text property of the text box binds to the `Age` property of the `Person` object, which has been made available for binding through a resource declaration that is given the `x:Key``data`.</span></span> <span data-ttu-id="f3ec8-107"><xref:System.Windows.Controls.DataErrorValidationRule> Проверяет наличие ошибок проверки, вызванные <xref:System.ComponentModel.IDataErrorInfo> реализации.</span><span class="sxs-lookup"><span data-stu-id="f3ec8-107">The <xref:System.Windows.Controls.DataErrorValidationRule> checks for the validation errors raised by the <xref:System.ComponentModel.IDataErrorInfo> implementation.</span></span>  
  
 [!code-xaml[BusinessLayerValidation#BoundTextBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BusinessLayerValidation/CSharp/Window1.xaml#boundtextbox)]  
  
 <span data-ttu-id="f3ec8-108">Кроме того, вместо использования <xref:System.Windows.Controls.DataErrorValidationRule>, можно задать <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> свойства `true`.</span><span class="sxs-lookup"><span data-stu-id="f3ec8-108">Alternatively, instead of using the <xref:System.Windows.Controls.DataErrorValidationRule>, you can set the <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> property to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3ec8-109">См. также</span><span class="sxs-lookup"><span data-stu-id="f3ec8-109">See Also</span></span>  
 <xref:System.Windows.Controls.ExceptionValidationRule>  
 [<span data-ttu-id="f3ec8-110">Реализация проверки привязки</span><span class="sxs-lookup"><span data-stu-id="f3ec8-110">Implement Binding Validation</span></span>](../../../../docs/framework/wpf/data/how-to-implement-binding-validation.md)  
 [<span data-ttu-id="f3ec8-111">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="f3ec8-111">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
