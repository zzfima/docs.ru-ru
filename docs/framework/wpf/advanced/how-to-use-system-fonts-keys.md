---
title: Практическое руководство. Использование разделов системных шрифтов
ms.date: 03/30/2017
helpviewer_keywords:
- resource keys [WPF], SystemFonts class
ms.assetid: 036ebea7-5677-4f60-8ba4-56c9f9d9b8bd
ms.openlocfilehash: 7283e4225b75909322fa312583e9f1a0679762e2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918384"
---
# <a name="how-to-use-system-fonts-keys"></a>Практическое руководство. Использование разделов системных шрифтов
Системные ресурсы предоставляют ряд метрик системы в качестве ресурсов, что помогает разработчикам создавать визуальные элементы, совместимые с параметрами системы. <xref:System.Windows.SystemFonts>— Это класс, который содержит значения системного шрифта и ресурсы системного шрифта, привязанные к значениям, например <xref:System.Windows.SystemFonts.CaptionFontFamily%2A> и. <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A>  
  
 Метрики системных шрифтов могут использоваться в качестве статического или динамического ресурса. Используйте динамический ресурс, если требуется метрика шрифта для автоматического обновления во время выполнения приложения. В противном случае используйте статический ресурс.  
  
> [!NOTE]
> К динамическим ресурсам добавляется *ключ* ключевого слова к имени свойства.  
  
 В приведенном ниже примере показано, как получить доступ к ресурсам динамических системных шрифтов и использовать их для создания стиля или настройки кнопки. В [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] этом примере создается стиль кнопки, который <xref:System.Windows.SystemFonts> присваивает значения кнопке.  
  
## <a name="example"></a>Пример  
 [!code-xaml[SystemRes_snip#FontDynamicResources](~/samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/MyApp.xaml#fontdynamicresources)]  
  
## <a name="see-also"></a>См. также

- [Заливка области с помощью системной кисти](../graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)
- [Использование SystemParameters](how-to-use-systemparameters.md)
- [Использование SystemFonts](how-to-use-systemfonts.md)
