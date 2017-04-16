---
title: "Практическое руководство. Преобразование привязанных данных | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "привязка данных, преобразование привязанных данных"
  - "преобразование, привязанные данные"
  - "привязка данных, преобразование привязанных данных"
ms.assetid: b00aaa19-c6df-4c3b-a9fd-88a0b488df2b
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Практическое руководство. Преобразование привязанных данных
В этом примере демонстрируется применение преобразования к данным, используемым в привязках.  
  
 Чтобы преобразовать данные во время привязки данных, необходимо создать класс, реализующий интерфейс <xref:System.Windows.Data.IValueConverter>, который включает методы <xref:System.Windows.Data.IValueConverter.Convert%2A> и <xref:System.Windows.Data.IValueConverter.ConvertBack%2A>.  
  
## Пример  
 В следующем примере показана реализация преобразователя входной даты в формат с отображением года, месяца и дня.  В реализации интерфейса <xref:System.Windows.Data.IValueConverter> рекомендуется использовать атрибут <xref:System.Windows.Data.ValueConversionAttribute>, определяющий типы данных средств разработки, используемые в преобразовании, как в следующем примере:  
  
 [!code-csharp[DataBindingLab#18](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DateConverter.cs#18)]
 [!code-vb[DataBindingLab#18](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/DateConverter.vb#18)]  
  
 Созданный преобразователь можно добавить в качестве ресурса в файл [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  В следующем примере *src* сопоставляется пространству имен, в котором определен *DateConverter*.  
  
 [!code-xml[DataBindingLab#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#15)]  
  
 Наконец, можно использовать преобразователь в привязке, используя следующий синтаксис.  В следующем примере текстовое содержимое объекта <xref:System.Windows.Controls.TextBlock> привязано к свойству внешнего источника данных *StartDate*.  
  
 [!code-xml[DataBindingLab#17](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#17)]  
  
 Ресурсы стиля, на которые имеются ссылки в приведенном выше примере, определяются в разделе ресурсов, который не приведен в этом разделе.  
  
## См. также  
 [Реализация проверки привязки](../../../../docs/framework/wpf/data/how-to-implement-binding-validation.md)   
 [Общие сведения о связывании данных](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Практические руководства](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)