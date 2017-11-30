---
title: "Практическое руководство. Использование SystemFonts"
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
- system fonts [WPF]
- fonts [WPF], system fonts
- classes [WPF], SystemFonts
ms.assetid: 3f46a4ec-2225-408a-8123-8838a8f7057a
caps.latest.revision: "27"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8ce82724a4e9a547b8441628f43621f29eab6307
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-systemfonts"></a>Практическое руководство. Использование SystemFonts
В этом примере показано, как использовать статические ресурсы <xref:System.Windows.SystemFonts> класс для изменения стиля или настроек кнопки.  
  
## <a name="example"></a>Пример  
 Системные ресурсы предоставляют несколько значений, определяемых системой, в качестве ресурсов и свойств, помогающих создавать визуальные элементы, согласованные с параметрами системы. <xref:System.Windows.SystemFonts>— Это класс, содержащий значения системного шрифта в виде статических свойств и свойств, которые ссылаются на ключи ресурсов, которые могут использоваться для доступа к этим значениями динамически во время выполнения. Например <xref:System.Windows.SystemFonts.CaptionFontFamily%2A> — <xref:System.Windows.SystemFonts> значение, и <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A> является ключом соответствующего ресурса.  
  
 В [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], можно использовать члены <xref:System.Windows.SystemFonts> как статические свойства или ссылки динамического ресурса (со статическим значением свойства в качестве ключа). Используйте ссылку на динамический ресурс, если метрика шрифта должна автоматически обновляться во время выполнения приложения. В противном случае используйте ссылку на статическое значение.  
  
> [!NOTE]
>  К именам свойств, используемых в качестве ключей ресурсов, добавляется суффикс Key.  
  
 Приведенный ниже показано, как получить доступ и использование свойств объекта <xref:System.Windows.SystemFonts> как статических значений для изменения стиля или настроек кнопки. Этот пример разметки присваивает <xref:System.Windows.SystemFonts> кнопке значения.  
  
 [!code-xaml[SystemRes_snip#FontStaticResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml#fontstaticresources)]  
  
 Чтобы использовать значения из <xref:System.Windows.SystemFonts> в коде, не нужно использовать статическое значение или ссылку на динамический ресурс. Вместо этого используйте неключевые свойства <xref:System.Windows.SystemFonts> класса. Хотя неключевые свойства очевидно определены как статические, поведение во время выполнения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] , размещенного система будет пересчитывать свойства в режиме реального времени и правильно учитывать управляемые пользователем изменения значений системы. В приведенном ниже примере показано, как задать параметры шрифта кнопки.  
  
 [!code-csharp[SystemRes_snip#FontResourcesCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml.cs#fontresourcescode)]
 [!code-vb[SystemRes_snip#FontResourcesCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SystemRes_snip/VisualBasic/Pane1.xaml.vb#fontresourcescode)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.SystemFonts>  
 [Заливка области с помощью системной кисти](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)  
 [Использование SystemParameters](../../../../docs/framework/wpf/advanced/how-to-use-systemparameters.md)  
 [Использование разделов системных шрифтов](../../../../docs/framework/wpf/advanced/how-to-use-system-fonts-keys.md)  
 [Разделы практического руководства](../../../../docs/framework/wpf/advanced/resources-how-to-topics.md)  
 [Расширение разметки x:Static](../../../../docs/framework/xaml-services/x-static-markup-extension.md)  
 [Ресурсы XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [Расширение разметки DynamicResource](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md)
