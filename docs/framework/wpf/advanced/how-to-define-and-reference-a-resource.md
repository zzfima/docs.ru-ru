---
title: Практическое руководство. Определение и создание ссылки на ресурс
ms.date: 03/30/2017
helpviewer_keywords:
- resources [WPF], defining
- defining resources [WPF]
- resources [WPF], referencing
- referencing resources [WPF]
ms.assetid: b86b876b-0a10-489b-9a5d-581ea9b32406
ms.openlocfilehash: 89471c45aabd9f3415c45a2e8af41d1a52900324
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460174"
---
# <a name="how-to-define-and-reference-a-resource"></a>Практическое руководство. Определение и создание ссылки на ресурс

В этом примере показано, как определить ресурс и ссылаться на него с помощью атрибута в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].

## <a name="example"></a>Пример

В следующем примере определяются два типа ресурсов: ресурс <xref:System.Windows.Media.SolidColorBrush> и несколько <xref:System.Windows.Style>ных ресурсов. <xref:System.Windows.Media.SolidColorBrush> `MyBrush` ресурсов используется для предоставления значения нескольких свойств, каждое из которых принимает значение <xref:System.Windows.Media.Brush> типа. Ресурсы <xref:System.Windows.Style> `PageBackground`, `TitleText` и `Label` каждый целевой тип элемента управления. Стили задают различные свойства целевых элементов управления, когда этот ресурс стиля ссылается по ключу ресурса и используется для задания <xref:System.Windows.FrameworkElement.Style%2A> свойства нескольких определенных элементов управления, определенных в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].

Обратите внимание, что одно из свойств в методах задания стиля `Label` также ссылается на `MyBrush` ресурс, определенный ранее. Это распространенный прием, но важно помнить, что ресурсы анализируются и записываются в словарь ресурсов в том порядке, в котором они указаны. Ресурсы также запрашиваются в порядке, найденном в словаре, если для ссылки на них в другом ресурсе используется [расширение разметки StaticResource](staticresource-markup-extension.md) . Убедитесь, что любой ресурс, на который вы ссылаетесь, определен ранее в коллекции ресурсов, чем тот, где этот ресурс будет запрошен. При необходимости можно обойти четкий порядок создания ссылок на ресурсы, используя [расширение разметки DynamicResource](dynamicresource-markup-extension.md) для ссылки на ресурс во время выполнения, но следует иметь в виду, что этот метод DynamicResource имеет производительность. последствия. Дополнительные сведения см. в разделе [ресурсы XAML](xaml-resources.md).

[!code-xaml[FEResource#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResource/CS/default.xaml#xaml)]

## <a name="see-also"></a>См. также

- [Ресурсы XAML](xaml-resources.md)
- [Стилизация и использование шаблонов](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
