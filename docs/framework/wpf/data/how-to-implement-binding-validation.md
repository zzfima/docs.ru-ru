---
title: "Практическое руководство. Реализация проверки привязки | Microsoft Docs"
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
  - "привязка, проверка"
  - "привязка данных, проверка привязки"
  - "проверка привязки"
ms.assetid: eb98b33d-9866-49ae-b981-bc5ff20d607a
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# Практическое руководство. Реализация проверки привязки
В этом примере показано использование <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> и триггера стиля для предоставления визуальной обратной связи на основе настраиваемого правила проверки, предназначенной для уведомления пользователя о том, что введено недопустимое значение.  
  
## Пример  
 Текстовое содержимое <xref:System.Windows.Controls.TextBox> в следующем примере привязано к свойству `Age` \(типа int\) объекта [источника привязки](GTMT) `ods`.  Привязка настроена на использование правила проверки `AgeRangeRule` таким образом, что при вводе нечисловых символов или значения меньше 21 или больше 130 рядом с текстовым полем появится красный восклицательный знак. Кроме того, когда пользователь поместит указатель мыши над текстовым полем, отобразится всплывающая подсказка с сообщением об ошибке.  
  
 [!code-xml[BindValidation#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#2)]  
  
 В следующем примере показана реализация объекта `AgeRangeRule`, который наследуется от <xref:System.Windows.Controls.ValidationRule> и переопределяет метод <xref:System.Windows.Controls.ValidationRule.Validate%2A>.  Метод Int32.Parse\(\) вызывается для значения, чтобы убедиться, что оно не содержит недопустимых символов.  Метод <xref:System.Windows.Controls.ValidationRule.Validate%2A> возвращает <xref:System.Windows.Controls.ValidationResult>, который указывает на допустимость значения на основе того, было ли перехвачено исключение при синтаксическом анализе и не выходит ли оно за пределы нижней и верхней границы.  
  
 [!code-csharp[BindValidation#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/AgeRangeRule.cs#3)]  
  
 В следующем примере показан пользовательский <xref:System.Windows.Controls.ControlTemplate> `validationTemplate`, который создает красный восклицательный знак для уведомления пользователя об ошибке проверки.  Шаблоны элемента управления используются для переопределения внешнего вида элемента управления.  
  
 [!code-xml[BindValidation#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#4)]  
  
 Как показано в следующем примере, <xref:System.Windows.Controls.ToolTip>, отображающий сообщение об ошибке, создается с использованием стиля `textBoxInError`.  Если значение <xref:System.Windows.Controls.Validation.HasError%2A> равно `true`, триггер задает подсказке текущего <xref:System.Windows.Controls.TextBox> значение первой ошибки проверки.  <xref:System.Windows.Data.Binding.RelativeSource%2A> устанавливается в значение <xref:System.Windows.Data.RelativeSourceMode>, указывающее на текущий элемент.  
  
 [!code-xml[BindValidation#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#5)]  
  
 Полный пример см. в разделе [Пример проверки данных с использованием привязки](http://go.microsoft.com/fwlink/?LinkID=159972).  
  
 Обратите внимание, что если не предоставляется пользовательский <xref:System.Windows.Controls.Validation.ErrorTemplate%2A>, то отображается шаблон ошибки по умолчанию для предоставления пользователю отчета о том, что произошла ошибка проверки.  См. подраздел «Проверка данных» в разделе [Общие сведения о связывании данных](../../../../docs/framework/wpf/data/data-binding-overview.md) для получения дополнительных сведений.  Кроме того, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет встроенное правило проверки, которое отслеживает исключения, созданные во время обновления свойства источника привязки.  Дополнительные сведения см. в разделе <xref:System.Windows.Controls.ExceptionValidationRule>.  
  
## См. также  
 [Общие сведения о связывании данных](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Практические руководства](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)