---
title: "Как использовать SystemParameters"
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
helpviewer_keywords: classes [WPF], SystemParameters
ms.assetid: 02e7a5de-94eb-4953-b91c-52e6c872ad5b
caps.latest.revision: "24"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ec333fbc30374ff6f8e2e7674ab332644ff7aad0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-systemparameters"></a>Как использовать SystemParameters
В этом примере показано, как получить доступ и использование свойств объекта <xref:System.Windows.SystemParameters> для изменения стиля или настроек кнопки.  
  
## <a name="example"></a>Пример  
 Системные ресурсы предоставляют несколько параметров системы в виде ресурсов, помогающих создавать визуальные элементы с учетом параметров системы. <xref:System.Windows.SystemParameters>— Это класс, содержащий свойства значений параметров системы и ключи ресурсов, которые привязаны к значениям. Например <xref:System.Windows.SystemParameters.FullPrimaryScreenHeight%2A> — <xref:System.Windows.SystemParameters> значение свойства и <xref:System.Windows.SystemParameters.FullPrimaryScreenHeightKey%2A> является соответствующим ключом ресурса.  
  
 В [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], можно использовать члены <xref:System.Windows.SystemParameters> как статическое свойство или динамические ссылки на ресурс (со статическим значением свойства в качестве ключа). Используйте ссылку на динамический ресурс, если требуется системное значение для автоматического обновления во время выполнения приложения. В противном случае используйте статическую ссылку. Ключи ресурсов имеют суффикс `Key` добавляется к имени свойства.  
  
 Приведенный ниже показано, как получить доступ и использовать статические значения <xref:System.Windows.SystemParameters> для стиля или настройки кнопки. Этот пример разметки изменяет размер кнопки, применяя <xref:System.Windows.SystemParameters> кнопке значения.  
  
 [!code-xaml[SystemRes_snip#ParameterStaticResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml#parameterstaticresources)]  
  
 Чтобы использовать значения из <xref:System.Windows.SystemParameters> в коде, не нужно использовать статические или динамические ссылки на ресурс. Вместо этого используйте значения <xref:System.Windows.SystemParameters> класса. Хотя неключевые свойства очевидно определены как статические, поведение среды выполнения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] , размещенного в системе будет пересчитывать свойства в режиме реального времени и правильно учитывать управляемые пользователем изменения значений системы. В следующем примере показано, как задать ширину и высоту кнопки с помощью <xref:System.Windows.SystemParameters> значения.  
  
 [!code-csharp[SystemRes_snip#ParameterResourcesCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml.cs#parameterresourcescode)]
 [!code-vb[SystemRes_snip#ParameterResourcesCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SystemRes_snip/VisualBasic/Pane1.xaml.vb#parameterresourcescode)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.SystemParameters>  
 [Заливка области с помощью системной кисти](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)  
 [Использование SystemFonts](../../../../docs/framework/wpf/advanced/how-to-use-systemfonts.md)  
 [Использование разделов системных параметров](../../../../docs/framework/wpf/advanced/how-to-use-system-parameters-keys.md)  
 [Разделы практического руководства](../../../../docs/framework/wpf/advanced/resources-how-to-topics.md)
