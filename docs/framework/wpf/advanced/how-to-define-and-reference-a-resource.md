---
title: Практическое руководство. Определение и создание ссылки на ресурс
ms.date: 03/30/2017
helpviewer_keywords:
- resources [WPF], defining
- defining resources [WPF]
- resources [WPF], referencing
- referencing resources [WPF]
ms.assetid: b86b876b-0a10-489b-9a5d-581ea9b32406
ms.openlocfilehash: c429e3373ef1b78fba12dd5125af653f66cf5d74
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57371584"
---
# <a name="how-to-define-and-reference-a-resource"></a>Практическое руководство. Определение и создание ссылки на ресурс
В этом примере показано, как определить ресурс и сослаться на него с помощью атрибута в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  
  
## <a name="example"></a>Пример  
 В следующем примере определяется два типа ресурсов: <xref:System.Windows.Media.SolidColorBrush> ресурсов, а также несколько <xref:System.Windows.Style> ресурсы. <xref:System.Windows.Media.SolidColorBrush> Ресурсов `MyBrush` используется для предоставления значений нескольких свойств каждого занять <xref:System.Windows.Media.Brush> введите значение. <xref:System.Windows.Style> Ресурсы `PageBackground`, `TitleText` и `Label` каждого предназначенных для определенного типа элемента управления. Стили устанавливается ряд различных свойств для целевых элементов, если ресурс стиля ссылается ключ ресурса и используется для задания <xref:System.Windows.FrameworkElement.Style%2A> свойства нескольких элементов конкретного элемента управления, определенных в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 Примечание, что одно из свойств метода установки `Label` также ссылается на стиль `MyBrush` ресурс, определенный ранее. Это распространенный способ, но это важно помнить, что ресурсы анализируются и введенные в словарь ресурсов, в том порядке, приведенном. Запрос ресурсов также осуществляется в порядке, найти в словаре, если вы используете [расширение разметки StaticResource](staticresource-markup-extension.md) ссылки на эти из другого ресурса. Убедитесь, что определены любой ресурс, на которую есть ссылки в коллекции ресурсов, чем которой затем запрошена этого ресурса. При необходимости можно обойти строгий порядок создания ресурсов с помощью [расширение разметки DynamicResource](dynamicresource-markup-extension.md) для ссылки на ресурс во время выполнения, вместо этого, но следует иметь в виду, этот DynamicResource метод имеет влияние на производительность. Дополнительные сведения см. в разделе [ресурсы XAML](xaml-resources.md).  
  
 [!code-xaml[FEResource#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResource/CS/default.xaml#xaml)]  
  
## <a name="see-also"></a>См. также
- [Ресурсы XAML](xaml-resources.md)
- [Стилизация и использование шаблонов](../controls/styling-and-templating.md)
