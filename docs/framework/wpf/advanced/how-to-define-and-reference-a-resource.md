---
title: "Практическое руководство. Определение и создание ссылки на ресурс"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- resources [WPF], defining
- defining resources [WPF]
- resources [WPF], referencing
- referencing resources [WPF]
ms.assetid: b86b876b-0a10-489b-9a5d-581ea9b32406
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 173be3048f7bf082db2eef2ea21eb1e0319f9a43
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-define-and-reference-a-resource"></a>Практическое руководство. Определение и создание ссылки на ресурс
В этом примере показано, как определить ресурс и ссылки на него с помощью атрибута в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  
  
## <a name="example"></a>Пример  
 В следующем примере определяются два типа ресурсов: <xref:System.Windows.Media.SolidColorBrush> ресурсов, а также несколько <xref:System.Windows.Style> ресурсов. <xref:System.Windows.Media.SolidColorBrush> Ресурсов `MyBrush` используется для предоставления значений нескольких свойств, каждый из которых принимает <xref:System.Windows.Media.Brush> введите значение. <xref:System.Windows.Style> Ресурсов `PageBackground`, `TitleText` и `Label` каждый целевой определенного типа элемента управления. Стили устанавливается ряд различных свойств для целевых элементов, если ресурс стиля ссылается ключ ресурса и используется для задания <xref:System.Windows.FrameworkElement.Style%2A> свойства нескольких элементов конкретного элемента управления, определенных в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 Примечание, что одно из свойств метода установки `Label` также ссылается на стиль `MyBrush` ресурсов, определенные ранее. Это распространенный способ, но важно запомнить синтаксический анализ и введенные в словаре ресурсов, в том порядке, приведенном ресурсов. Запрос ресурсов также осуществляется в порядке найдены в словаре, если вы используете [StaticResource Markup Extension](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md) чтобы ссылаться на них из другого ресурса. Убедитесь, что любой ресурс, на которую ссылается, определены в коллекции ресурсов, до которой затем запрошена этого ресурса. При необходимости можно обойти строгий порядок создания ресурсов с помощью [DynamicResource Markup Extension](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md) вместо этого ссылок во время выполнения, но следует иметь в виду, это DynamicResource метод окажет влияние на производительность. Дополнительные сведения см. в разделе [ресурсов XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
 [!code-xaml[FEResource#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEResource/CS/default.xaml#xaml)]  
  
## <a name="see-also"></a>См. также  
 [Ресурсы XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [Стилизация и использование шаблонов](../../../../docs/framework/wpf/controls/styling-and-templating.md)
