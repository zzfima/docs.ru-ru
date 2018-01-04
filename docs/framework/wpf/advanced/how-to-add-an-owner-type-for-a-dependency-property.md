---
title: "Практическое руководство. Добавление типа владельца для свойства зависимости"
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
- classes [WPF], adding as owners of dependency properties
- dependency properties [WPF], adding classes as owners of
ms.assetid: edcce050-0576-4edb-a31a-3f909637b452
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b93934c8f84a7257445b530e27896342bdd73aea
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-an-owner-type-for-a-dependency-property"></a>Практическое руководство. Добавление типа владельца для свойства зависимости
В этом примере показано, как добавить класс в качестве владельца свойства зависимостей, зарегистрированного для другого типа. Таким образом, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] чтения и система свойств способны распознать класс в качестве дополнительного владельца свойства. Добавление в качестве владельца при необходимости позволяет добавлять класс для предоставления метаданных определенного типа.  
  
 В следующем примере `StateProperty` является свойством, зарегистрированным `MyStateControl` класса. Класс `UnrelatedStateControl` добавляет себя в качестве владельца `StateProperty` с помощью <xref:System.Windows.DependencyProperty.AddOwner%2A> метода, в частности, используя подпись, которая обеспечивает новые метаданные для свойства зависимостей, которое существует в добавленном типе. Обратите внимание, что необходимо предоставить [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] методы доступа для свойства, как показано в примере [реализации свойства зависимостей,](../../../../docs/framework/wpf/advanced/how-to-implement-a-dependency-property.md) пример, а также повторно предоставить идентификатор свойства зависимостей для класса, добавляемого в как владелец.  
  
 Без оболочки свойство зависимости по-прежнему будет работать с точки зрения программного доступа с помощью <xref:System.Windows.DependencyObject.GetValue%2A> или <xref:System.Windows.DependencyObject.SetValue%2A>. Однако чаще всего требуется параллельное поведение системы свойств [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] оболочек свойств. Оболочки облегчают программным способом установите для свойства зависимостей и делают возможным установку свойств в качестве [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] атрибуты.  
  
 Чтобы узнать, как переопределить метаданные по умолчанию, в разделе [переопределения метаданных для свойства зависимостей](../../../../docs/framework/wpf/advanced/how-to-override-metadata-for-a-dependency-property.md).  
  
## <a name="example"></a>Пример  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
[!code-csharp[PropertySystemEsoterics#UnrelatedStateControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#unrelatedstatecontrol)]
[!code-vb[PropertySystemEsoterics#UnrelatedStateControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#unrelatedstatecontrol)]  
  
## <a name="see-also"></a>См. также  
 [Пользовательские свойства зависимостей](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)  
 [Общие сведения о свойствах зависимости](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)
