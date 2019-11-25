---
title: Практическое руководство. Получение объекта привязки из свойства целевого объекта привязки
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], getting binding objects from bound target properties
- properties [WPF], getting binding objects from
ms.assetid: 87974c5f-136b-4de7-b07d-9285b62ab123
ms.openlocfilehash: cf2ddc93a7c46ee6956d2731a786289f64086360
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976423"
---
# <a name="how-to-get-the-binding-object-from-a-bound-target-property"></a>Практическое руководство. Получение объекта привязки из свойства целевого объекта привязки
В этом примере показано, как получить объект привязки из свойства целевого связанного объекта.

## <a name="example"></a>Пример
 Чтобы получить объект <xref:System.Windows.Data.Binding>, можно выполнить следующие действия:

 [!code-csharp[BindValidation#GetBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml.cs#getbinding)]

> [!NOTE]
> Необходимо указать свойство зависимости для необходимой привязки, поскольку возможно, что привязка данных используется в нескольких (а не в одном) свойствах целевого объекта.

 Кроме того, можно получить <xref:System.Windows.Data.BindingExpression>, а затем получить значение свойства <xref:System.Windows.Data.BindingExpression.ParentBinding%2A>.

 Полный пример см. в разделе [Пример проверки привязки](https://go.microsoft.com/fwlink/?LinkID=159972).

> [!NOTE]
> Если привязка является <xref:System.Windows.Data.MultiBinding>, используйте <xref:System.Windows.Data.BindingOperations.GetMultiBinding%2A?displayProperty=nameWithType>. Если это <xref:System.Windows.Data.PriorityBinding>, используйте <xref:System.Windows.Data.BindingOperations.GetPriorityBinding%2A?displayProperty=nameWithType>. Если вы не уверены, привязано ли целевое свойство с помощью <xref:System.Windows.Data.Binding>, <xref:System.Windows.Data.MultiBinding>или <xref:System.Windows.Data.PriorityBinding>, можно использовать <xref:System.Windows.Data.BindingOperations.GetBindingBase%2A?displayProperty=nameWithType>.

## <a name="see-also"></a>См. также

- [Создание привязки в коде](how-to-create-a-binding-in-code.md)
- [Разделы практического руководства](data-binding-how-to-topics.md)
