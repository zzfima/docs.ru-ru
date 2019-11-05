---
title: Практическое руководство. Преобразование привязанных данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- converting [WPF], bound data
- data binding [WPF], converting bound data
- binding data [WPF], converting bound data
ms.assetid: b00aaa19-c6df-4c3b-a9fd-88a0b488df2b
ms.openlocfilehash: f9ad390626092d481bf47f017f643a29302c1b29
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458866"
---
# <a name="how-to-convert-bound-data"></a>Практическое руководство. Преобразование привязанных данных
В этом примере показано, как применить преобразование к данным, используемым в привязках.  
  
 Для преобразования данных во время привязки необходимо создать класс, реализующий интерфейс <xref:System.Windows.Data.IValueConverter>, который включает в себя методы <xref:System.Windows.Data.IValueConverter.Convert%2A> и <xref:System.Windows.Data.IValueConverter.ConvertBack%2A>.  
  
## <a name="example"></a>Пример  
 В следующем примере показана реализация преобразователя дат, который преобразует значение даты, переданное в, чтобы показать только год, месяц и день. При реализации интерфейса <xref:System.Windows.Data.IValueConverter> рекомендуется снабдить реализацию атрибутом <xref:System.Windows.Data.ValueConversionAttribute>, чтобы указать средствам разработки типы данных, участвующие в преобразовании, как показано в следующем примере:  
  
 [!code-csharp[DataBindingLab#18](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DateConverter.cs#18)]
 [!code-vb[DataBindingLab#18](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/DateConverter.vb#18)]  
  
 После создания конвертера его можно добавить в качестве ресурса в файл [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. В следующем примере *src* сопоставляется с пространством имен, в котором определен *датеконвертер* .  
  
 [!code-xaml[DataBindingLab#15](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#15)]  
  
 Наконец, можно использовать преобразователь в привязке, используя следующий синтаксис. В следующем примере текстовое содержимое <xref:System.Windows.Controls.TextBlock> привязано к *StartDate*, которое является свойством внешнего источника данных.  
  
 [!code-xaml[DataBindingLab#17](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#17)]  
  
 Ресурсы стилей, упоминаемые в приведенном выше примере, определяются в разделе ресурсов, не показанном в этом разделе.  
  
## <a name="see-also"></a>См. также

- [Реализация проверки привязки](how-to-implement-binding-validation.md)
- [Общие сведения о привязке данных](../../../desktop-wpf/data/data-binding-overview.md)
- [Разделы практического руководства](data-binding-how-to-topics.md)
