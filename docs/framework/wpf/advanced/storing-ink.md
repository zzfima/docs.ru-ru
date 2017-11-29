---
title: "Хранение рукописных данных"
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
- ISF (Ink Serialized Format)
- storing ink [WPF]
- ink [WPF], storing
- retrieving ink [WPF]
- Ink Serialized Format (ISF)
ms.assetid: a3f6d16b-d682-4680-9965-907332b4d2b8
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 244a4bfa5def1319438d66a52120e36aab0e753b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="storing-ink"></a>Хранение рукописных данных
<xref:System.Windows.Ink.StrokeCollection.Save%2A> Методы предоставляют поддержку хранения рукописного ввода как формат сериализации рукописного ввода (ISF). Конструкторы для <xref:System.Windows.Ink.StrokeCollection> класса обеспечивают поддержку чтения рукописного ввода данных.  
  
## <a name="ink-storage-and-retrieval"></a>Рукописный ввод хранения и извлечения  
 В этом разделе описывается, как сохранять и извлекать рукописного ввода в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] платформы.  
  
 Следующий пример реализует обработчик событий нажатия кнопки, который отображает диалоговое окно сохранения файла и сохраняет рукописные данные из <xref:System.Windows.Controls.InkCanvas> в файл.  
  
 [!code-csharp[DigitalInkTopics#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#12)]
 [!code-vb[DigitalInkTopics#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#12)]  
  
 Следующий пример реализует обработчик событий нажатия кнопки, который отображает диалоговое окно открытия файла и считывает рукописные данные из файла в <xref:System.Windows.Controls.InkCanvas> элемент.  
  
 [!code-csharp[DigitalInkTopics#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#13)]
 [!code-vb[DigitalInkTopics#13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#13)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Controls.InkCanvas>  
 [Windows Presentation Foundation](../../../../docs/framework/wpf/index.md)
