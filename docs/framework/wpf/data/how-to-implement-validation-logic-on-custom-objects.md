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
ms.openlocfilehash: e183d286e4b9cd037c352126203b1ecdcca89ebb
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57365364"
---
# <a name="how-to-implement-validation-logic-on-custom-objects"></a><span data-ttu-id="a56d9-102">Практическое руководство. Реализация логики проверки для пользовательских объектов</span><span class="sxs-lookup"><span data-stu-id="a56d9-102">How to: Implement Validation Logic on Custom Objects</span></span>
<span data-ttu-id="a56d9-103">В этом примере показано, как реализация логики проверки для пользовательского объекта, а затем привязать к нему.</span><span class="sxs-lookup"><span data-stu-id="a56d9-103">This example shows how to implement validation logic on a custom object and then bind to it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a56d9-104">Пример</span><span class="sxs-lookup"><span data-stu-id="a56d9-104">Example</span></span>  
 <span data-ttu-id="a56d9-105">Вы можете предоставить логику проверки в бизнес-слоя, если источник объекта реализует <xref:System.ComponentModel.IDataErrorInfo>, как показано в следующем примере, который определяет `Person` объект, реализующий <xref:System.ComponentModel.IDataErrorInfo>:</span><span class="sxs-lookup"><span data-stu-id="a56d9-105">You can provide validation logic on the business layer if your source object implements <xref:System.ComponentModel.IDataErrorInfo>, as in the following example, which defines a `Person` object that implements <xref:System.ComponentModel.IDataErrorInfo>:</span></span>  
  
 [!code-csharp[BusinessLayerValidation#IDataErrorInfo](~/samples/snippets/csharp/VS_Snippets_Wpf/BusinessLayerValidation/CSharp/Data.cs#idataerrorinfo)]
 [!code-vb[BusinessLayerValidation#IDataErrorInfo](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BusinessLayerValidation/VisualBasic/Data.vb#idataerrorinfo)]  
  
 <span data-ttu-id="a56d9-106">В следующем примере свойство text текстового поля привязывается к `Person.Age` свойство, которое станет доступным для привязки через объявление ресурса, которому предоставлен `x:Key` `data`.</span><span class="sxs-lookup"><span data-stu-id="a56d9-106">In the following example, the text property of the text box binds to the `Person.Age` property, which has been made available for binding through a resource declaration that is given the `x:Key` `data`.</span></span> <span data-ttu-id="a56d9-107"><xref:System.Windows.Controls.DataErrorValidationRule> Проверяет наличие ошибок проверки, вызванных <xref:System.ComponentModel.IDataErrorInfo> реализации.</span><span class="sxs-lookup"><span data-stu-id="a56d9-107">The <xref:System.Windows.Controls.DataErrorValidationRule> checks for the validation errors raised by the <xref:System.ComponentModel.IDataErrorInfo> implementation.</span></span>  
  
 [!code-xaml[BusinessLayerValidation#BoundTextBox](~/samples/snippets/csharp/VS_Snippets_Wpf/BusinessLayerValidation/CSharp/Window1.xaml?highlight=8,11-19,25-42)]  
  
 <span data-ttu-id="a56d9-108">Кроме того, вместо использования <xref:System.Windows.Controls.DataErrorValidationRule>, можно задать <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> свойства `true`.</span><span class="sxs-lookup"><span data-stu-id="a56d9-108">Alternatively, instead of using the <xref:System.Windows.Controls.DataErrorValidationRule>, you can set the <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> property to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a56d9-109">См. также</span><span class="sxs-lookup"><span data-stu-id="a56d9-109">See also</span></span>
- <xref:System.Windows.Controls.ExceptionValidationRule>
- [<span data-ttu-id="a56d9-110">Реализация проверки привязки</span><span class="sxs-lookup"><span data-stu-id="a56d9-110">Implement Binding Validation</span></span>](how-to-implement-binding-validation.md)
- [<span data-ttu-id="a56d9-111">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="a56d9-111">How-to Topics</span></span>](data-binding-how-to-topics.md)
