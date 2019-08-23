---
title: Практическое руководство. Использование SystemFonts
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- system fonts [WPF]
- fonts [WPF], system fonts
- classes [WPF], SystemFonts
ms.assetid: 3f46a4ec-2225-408a-8123-8838a8f7057a
ms.openlocfilehash: 7438705a82faee464649b5f6f577627a379e9a8c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918359"
---
# <a name="how-to-use-systemfonts"></a>Практическое руководство. Использование SystemFonts
В этом примере показано, как использовать статические ресурсы <xref:System.Windows.SystemFonts> класса, чтобы изменить стиль или настроить кнопку.  
  
## <a name="example"></a>Пример  
 Системные ресурсы предоставляют несколько значений, определяемых системой, в качестве ресурсов и свойств, помогающих создавать визуальные элементы, согласованные с параметрами системы. <xref:System.Windows.SystemFonts>— Это класс, который содержит значения системного шрифта как статические свойства и свойства, которые ссылаются на ключи ресурсов, которые могут использоваться для динамического доступа к этим значениям во время выполнения. Например, <xref:System.Windows.SystemFonts.CaptionFontFamily%2A> <xref:System.Windows.SystemFonts> является значением и <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A> является соответствующим ключом ресурса.  
  
 В [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]можно использовать <xref:System.Windows.SystemFonts> члены в качестве статических свойств или ссылок на динамические ресурсы (со статическим значением свойства в качестве ключа). Используйте ссылку на динамический ресурс, если метрика шрифта должна автоматически обновляться во время выполнения приложения. В противном случае используйте ссылку на статическое значение.  
  
> [!NOTE]
> К именам свойств, используемых в качестве ключей ресурсов, добавляется суффикс Key.  
  
 В следующем примере показано, как получить доступ к свойствам <xref:System.Windows.SystemFonts> и использовать их в качестве статических значений для стиля или настройки кнопки. Этот пример разметки присваивает <xref:System.Windows.SystemFonts> значения кнопке.  
  
 [!code-xaml[SystemRes_snip#FontStaticResources](~/samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml#fontstaticresources)]  
  
 Чтобы использовать значения <xref:System.Windows.SystemFonts> в коде, не нужно использовать статическое значение или ссылку на динамический ресурс. Вместо этого используйте неключевые свойства <xref:System.Windows.SystemFonts> класса. Несмотря на то что неключевые свойства, очевидно, определены как статические, поведение [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] во время выполнения, размещенное системой, будет переоценивать свойства в режиме реального времени и будет правильно учитывать изменения, управляемые пользователем, в значениях системы. В приведенном ниже примере показано, как задать параметры шрифта кнопки.  
  
 [!code-csharp[SystemRes_snip#FontResourcesCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml.cs#fontresourcescode)]
 [!code-vb[SystemRes_snip#FontResourcesCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SystemRes_snip/VisualBasic/Pane1.xaml.vb#fontresourcescode)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.SystemFonts>
- [Заливка области с помощью системной кисти](../graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)
- [Использование SystemParameters](how-to-use-systemparameters.md)
- [Использование разделов системных шрифтов](how-to-use-system-fonts-keys.md)
- [Разделы практического руководства](resources-how-to-topics.md)
- [Расширение разметки x:Static](../../xaml-services/x-static-markup-extension.md)
- [Ресурсы XAML](xaml-resources.md)
- [Расширение разметки DynamicResource](dynamicresource-markup-extension.md)
