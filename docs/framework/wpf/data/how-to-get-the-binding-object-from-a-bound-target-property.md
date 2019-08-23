---
title: Практическое руководство. Получение объекта привязки из свойства целевого объекта привязки
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], getting binding objects from bound target properties
- properties [WPF], getting binding objects from
ms.assetid: 87974c5f-136b-4de7-b07d-9285b62ab123
ms.openlocfilehash: c7aacc2145ffe98ec7b58afb3b2e3dca151ef0ad
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965434"
---
# <a name="how-to-get-the-binding-object-from-a-bound-target-property"></a>Практическое руководство. Получение объекта привязки из свойства целевого объекта привязки
В этом примере показано, как получить объект привязки из свойства целевого связанного объекта.  
  
## <a name="example"></a>Пример  
 Чтобы получить объект, <xref:System.Windows.Data.Binding> можно выполнить следующие действия.  
  
 [!code-csharp[BindValidation#GetBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml.cs#getbinding)]  
  
> [!NOTE]
> Необходимо указать свойство зависимости для необходимой привязки, поскольку возможно, что привязка данных используется в нескольких (а не в одном) свойствах целевого объекта.  
  
 Кроме того, можно получить <xref:System.Windows.Data.BindingExpression> и получить значение <xref:System.Windows.Data.BindingExpression.ParentBinding%2A> свойства.  
  
 Полный пример см. в разделе [Пример проверки привязки](https://go.microsoft.com/fwlink/?LinkID=159972).  
  
> [!NOTE]
> Если привязка — <xref:System.Windows.Data.MultiBinding>, используйте <xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetMultiBinding%2A>. Если это <xref:System.Windows.Data.BindingOperations>,используйте.<xref:System.Windows.Data.BindingOperations.GetPriorityBinding%2A>. <xref:System.Windows.Data.PriorityBinding> Если вы не уверены, привязано ли целевое свойство, с <xref:System.Windows.Data.Binding>помощью <xref:System.Windows.Data.MultiBinding>, или <xref:System.Windows.Data.PriorityBinding>, можно использовать.<xref:System.Windows.Data.BindingOperations.GetBindingBase%2A> <xref:System.Windows.Data.BindingOperations>  
  
## <a name="see-also"></a>См. также

- [Создание привязки в коде](how-to-create-a-binding-in-code.md)
- [Разделы практического руководства](data-binding-how-to-topics.md)
