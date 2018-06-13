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
# <a name="how-to-implement-validation-logic-on-custom-objects"></a>Практическое руководство. Реализация проверки для пользовательских объектов
В этом примере показано, как реализовать логику проверки для пользовательского объекта, а затем привязать к нему.  
  
## <a name="example"></a>Пример  
 Можно обеспечить проверку на бизнес-уровне, если источник объекта реализует <xref:System.ComponentModel.IDataErrorInfo>, как показано в следующем примере:  
  
 [!code-csharp[BusinessLayerValidation#IDataErrorInfo](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BusinessLayerValidation/CSharp/Data.cs#idataerrorinfo)]
 [!code-vb[BusinessLayerValidation#IDataErrorInfo](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BusinessLayerValidation/VisualBasic/Data.vb#idataerrorinfo)]  
  
 В следующем примере свойство text текстового поля привязывается к `Age` свойство `Person` объекта, который был сделан доступным для привязки через объявление ресурса, которому дано `x:Key``data`. <xref:System.Windows.Controls.DataErrorValidationRule> Проверяет наличие ошибок проверки, вызванные <xref:System.ComponentModel.IDataErrorInfo> реализации.  
  
 [!code-xaml[BusinessLayerValidation#BoundTextBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BusinessLayerValidation/CSharp/Window1.xaml#boundtextbox)]  
  
 Кроме того, вместо использования <xref:System.Windows.Controls.DataErrorValidationRule>, можно задать <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> свойства `true`.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Controls.ExceptionValidationRule>  
 [Реализация проверки привязки](../../../../docs/framework/wpf/data/how-to-implement-binding-validation.md)  
 [Разделы практического руководства](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
