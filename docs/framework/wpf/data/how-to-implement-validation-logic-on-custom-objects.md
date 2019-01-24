---
title: Как выполнить Реализация логики проверки для пользовательских объектов
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
ms.openlocfilehash: e2b77ef65c92ae596c5620c9122dcf3db0bf9462
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54525993"
---
# <a name="how-to-implement-validation-logic-on-custom-objects"></a><span data-ttu-id="61f3f-102">Как выполнить Реализация логики проверки для пользовательских объектов</span><span class="sxs-lookup"><span data-stu-id="61f3f-102">How to: Implement Validation Logic on Custom Objects</span></span>
<span data-ttu-id="61f3f-103">В этом примере показано, как реализация логики проверки для пользовательского объекта, а затем привязать к нему.</span><span class="sxs-lookup"><span data-stu-id="61f3f-103">This example shows how to implement validation logic on a custom object and then bind to it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="61f3f-104">Пример</span><span class="sxs-lookup"><span data-stu-id="61f3f-104">Example</span></span>  
 <span data-ttu-id="61f3f-105">Вы можете предоставить логику проверки в бизнес-слоя, если источник объекта реализует <xref:System.ComponentModel.IDataErrorInfo>, как показано в следующем примере, который определяет `Person` объект, реализующий <xref:System.ComponentModel.IDataErrorInfo>:</span><span class="sxs-lookup"><span data-stu-id="61f3f-105">You can provide validation logic on the business layer if your source object implements <xref:System.ComponentModel.IDataErrorInfo>, as in the following example, which defines a `Person` object that implements <xref:System.ComponentModel.IDataErrorInfo>:</span></span>  
  
 [!code-csharp[BusinessLayerValidation#IDataErrorInfo](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BusinessLayerValidation/CSharp/Data.cs#idataerrorinfo)]
 [!code-vb[BusinessLayerValidation#IDataErrorInfo](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BusinessLayerValidation/VisualBasic/Data.vb#idataerrorinfo)]  
  
 <span data-ttu-id="61f3f-106">В следующем примере свойство text текстового поля привязывается к `Person.Age` свойство, которое станет доступным для привязки через объявление ресурса, которому предоставлен `x:Key` `data`.</span><span class="sxs-lookup"><span data-stu-id="61f3f-106">In the following example, the text property of the text box binds to the `Person.Age` property, which has been made available for binding through a resource declaration that is given the `x:Key` `data`.</span></span> <span data-ttu-id="61f3f-107"><xref:System.Windows.Controls.DataErrorValidationRule> Проверяет наличие ошибок проверки, вызванных <xref:System.ComponentModel.IDataErrorInfo> реализации.</span><span class="sxs-lookup"><span data-stu-id="61f3f-107">The <xref:System.Windows.Controls.DataErrorValidationRule> checks for the validation errors raised by the <xref:System.ComponentModel.IDataErrorInfo> implementation.</span></span>  
  
 [!code-xaml[BusinessLayerValidation#BoundTextBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BusinessLayerValidation/CSharp/Window1.xaml?highlight=8,11-19,25-42)]  
  
 <span data-ttu-id="61f3f-108">Кроме того, вместо использования <xref:System.Windows.Controls.DataErrorValidationRule>, можно задать <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> свойства `true`.</span><span class="sxs-lookup"><span data-stu-id="61f3f-108">Alternatively, instead of using the <xref:System.Windows.Controls.DataErrorValidationRule>, you can set the <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> property to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61f3f-109">См. также</span><span class="sxs-lookup"><span data-stu-id="61f3f-109">See also</span></span>
- <xref:System.Windows.Controls.ExceptionValidationRule>
- [<span data-ttu-id="61f3f-110">Реализация проверки привязки</span><span class="sxs-lookup"><span data-stu-id="61f3f-110">Implement Binding Validation</span></span>](../../../../docs/framework/wpf/data/how-to-implement-binding-validation.md)
- [<span data-ttu-id="61f3f-111">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="61f3f-111">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
