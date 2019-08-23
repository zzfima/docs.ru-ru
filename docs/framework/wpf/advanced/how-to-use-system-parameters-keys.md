---
title: Практическое руководство. Использование разделов системных параметров
ms.date: 03/30/2017
helpviewer_keywords:
- resource keys [WPF], SystemParameters class
- classes [WPF], SystemParameters
ms.assetid: 77571283-d16c-45bb-9f69-cafbbf72b21e
ms.openlocfilehash: edacb4b98ab01f081f668dc3374f6588492210d9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918373"
---
# <a name="how-to-use-system-parameters-keys"></a>Практическое руководство. Использование разделов системных параметров
Системные ресурсы предоставляют ряд метрик системы в качестве ресурсов, что помогает разработчикам создавать визуальные элементы, совместимые с параметрами системы. <xref:System.Windows.SystemParameters>— Это класс, который содержит значения системных параметров и ключи ресурсов, привязанные к значениям, например <xref:System.Windows.SystemParameters.FullPrimaryScreenHeight%2A> и. <xref:System.Windows.SystemParameters.FullPrimaryScreenHeightKey%2A> Метрики параметров системы могут использоваться в качестве статических или динамических ресурсов. Используйте динамический ресурс, если требуется метрика параметра для автоматического обновления во время выполнения приложения; в других случаях используйте статический ресурс.  
  
> [!NOTE]
> К динамическим ресурсам добавляется *ключ* ключевого слова к имени свойства.  
  
 В приведенном ниже примере показано, как получить доступ к ресурсам динамических параметров системы и использовать их для создания стиля или настройки кнопки. В [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] этом примере размер кнопки определяется путем <xref:System.Windows.SystemParameters> назначения значений ширине и высоте кнопки.  
  
## <a name="example"></a>Пример  
 [!code-xaml[SystemRes_snip#ParameterDynamicResources](~/samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/MyApp.xaml#parameterdynamicresources)]  
  
## <a name="see-also"></a>См. также

- [Заливка области с помощью системной кисти](../graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)
- [Использование SystemFonts](how-to-use-systemfonts.md)
- [Использование SystemParameters](how-to-use-systemparameters.md)
