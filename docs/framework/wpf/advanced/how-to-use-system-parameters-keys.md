---
title: Как выполнить Использование разделов системных параметров
ms.date: 03/30/2017
helpviewer_keywords:
- resource keys [WPF], SystemParameters class
- classes [WPF], SystemParameters
ms.assetid: 77571283-d16c-45bb-9f69-cafbbf72b21e
ms.openlocfilehash: 13658b0bb97d842eecc8679ee64db68ae780a917
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54728368"
---
# <a name="how-to-use-system-parameters-keys"></a>Как выполнить Использование разделов системных параметров
Системные ресурсы предоставляют ряд метрик системы в качестве ресурсов, что помогает разработчикам создавать визуальные элементы, совместимые с параметрами системы. <xref:System.Windows.SystemParameters> — Это класс, который содержит значения системных параметров и ключи ресурсов, которые привязаны к значениям — например, <xref:System.Windows.SystemParameters.FullPrimaryScreenHeight%2A> и <xref:System.Windows.SystemParameters.FullPrimaryScreenHeightKey%2A>. Метрики параметров системы могут использоваться в качестве статических или динамических ресурсов. Используйте динамический ресурс, если требуется метрика параметра для автоматического обновления во время выполнения приложения; в других случаях используйте статический ресурс.  
  
> [!NOTE]
>  Динамические ресурсы имеют ключевое слово *ключ* добавляется к имени свойства.  
  
 В приведенном ниже примере показано, как получить доступ к ресурсам динамических параметров системы и использовать их для создания стиля или настройки кнопки. Это [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] примере размеры кнопки путем назначения <xref:System.Windows.SystemParameters> значения ширины и высоты кнопки.  
  
## <a name="example"></a>Пример  
 [!code-xaml[SystemRes_snip#ParameterDynamicResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/MyApp.xaml#parameterdynamicresources)]  
  
## <a name="see-also"></a>См. также
- [Заливка области с помощью системной кисти](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)
- [Использование SystemFonts](../../../../docs/framework/wpf/advanced/how-to-use-systemfonts.md)
- [Использование SystemParameters](../../../../docs/framework/wpf/advanced/how-to-use-systemparameters.md)
