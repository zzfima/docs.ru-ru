---
title: "Практическое руководство. Преобразование привязанных данных"
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
- converting [WPF], bound data
- data binding [WPF], converting bound data
- binding data [WPF], converting bound data
ms.assetid: b00aaa19-c6df-4c3b-a9fd-88a0b488df2b
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 88e248c7c8e60fbe8e55567cb642200820b25214
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-convert-bound-data"></a>Практическое руководство. Преобразование привязанных данных
В этом примере показано, как применить преобразования к данным, используемым в привязках.  
  
 Чтобы преобразовать данные во время привязки, необходимо создать класс, реализующий <xref:System.Windows.Data.IValueConverter> интерфейс, который включает в себя <xref:System.Windows.Data.IValueConverter.Convert%2A> и <xref:System.Windows.Data.IValueConverter.ConvertBack%2A> методы.  
  
## <a name="example"></a>Пример  
 Пример реализации преобразователя преобразует значение даты, переданный, чтобы отобразить только года, месяца и дня. При реализации <xref:System.Windows.Data.IValueConverter> интерфейс, рекомендуется для отмечания реализацию с <xref:System.Windows.Data.ValueConversionAttribute> атрибут, чтобы указать для разработки средств типы данных, участвующие в преобразовании, как показано в следующем примере:  
  
 [!code-csharp[DataBindingLab#18](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DateConverter.cs#18)]
 [!code-vb[DataBindingLab#18](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/DateConverter.vb#18)]  
  
 После создания преобразователь, его можно добавить в качестве ресурса в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] файла. В следующем примере *src* соответствует пространству имен, в котором *DateConverter* определен.  
  
 [!code-xaml[DataBindingLab#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#15)]  
  
 Наконец можно использовать преобразователь в привязке, используя следующий синтаксис. В следующем примере текстовое содержимое <xref:System.Windows.Controls.TextBlock> привязан к *StartDate*, который является свойством внешнего источника данных.  
  
 [!code-xaml[DataBindingLab#17](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#17)]  
  
 Ресурсы стиля, указанные в приведенном выше примере определяются в разделе ресурсов, не приведенные в этом разделе.  
  
## <a name="see-also"></a>См. также  
 [Реализация проверки привязки](../../../../docs/framework/wpf/data/how-to-implement-binding-validation.md)  
 [Общие сведения о привязке данных](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Разделы практического руководства](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
