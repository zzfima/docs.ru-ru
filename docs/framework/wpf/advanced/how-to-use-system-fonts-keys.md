---
title: Как использовать разделы системных шрифтов
ms.date: 03/30/2017
helpviewer_keywords:
- resource keys [WPF], SystemFonts class
ms.assetid: 036ebea7-5677-4f60-8ba4-56c9f9d9b8bd
ms.openlocfilehash: c68f197daebd7423aa4ad2e7fdfb6e7f89c74ed0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33544431"
---
# <a name="how-to-use-system-fonts-keys"></a>Как использовать разделы системных шрифтов
Системные ресурсы предоставляют ряд метрик системы в качестве ресурсов, что помогает разработчикам создавать визуальные элементы, совместимые с параметрами системы. <xref:System.Windows.SystemFonts> — Это класс, содержащий значения системных шрифтов и системных ресурсов шрифтов, которые привязаны к значениям — например, <xref:System.Windows.SystemFonts.CaptionFontFamily%2A> и <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A>.  
  
 Метрики системных шрифтов могут использоваться в качестве статического или динамического ресурса. Используйте динамический ресурс, если требуется метрика шрифта для автоматического обновления во время выполнения приложения. В противном случае используйте статический ресурс.  
  
> [!NOTE]
>  Динамические ресурсы имеют ключевое слово *ключ* добавляется к имени свойства.  
  
 В приведенном ниже примере показано, как получить доступ к ресурсам динамических системных шрифтов и использовать их для создания стиля или настройки кнопки. Это [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] примере создается стиль кнопки, которая присваивает <xref:System.Windows.SystemFonts> кнопке значения.  
  
## <a name="example"></a>Пример  
 [!code-xaml[SystemRes_snip#FontDynamicResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/MyApp.xaml#fontdynamicresources)]  
  
## <a name="see-also"></a>См. также  
 [Заливка области с помощью системной кисти](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)  
 [Использование SystemParameters](../../../../docs/framework/wpf/advanced/how-to-use-systemparameters.md)  
 [Использование SystemFonts](../../../../docs/framework/wpf/advanced/how-to-use-systemfonts.md)
