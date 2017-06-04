---
title: "Практическое руководство. Управление обновлением источника из поля TextBox | Microsoft Docs"
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
  - "привязка данных, учет времени обновлений источника"
  - "обновления источника, учет времени"
  - "учет времени обновлений источника"
ms.assetid: ffb7b96a-351d-4c68-81e7-054033781c64
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Практическое руководство. Управление обновлением источника из поля TextBox
В этом разделе описывает способы использования свойства <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> для контроля времени обновлений [источника привязки](GTMT).  В разделе используется элемент управления <xref:System.Windows.Controls.TextBox> в качестве примера.  
  
## Пример  
 Свойство <xref:System.Windows.Controls.TextBox>. <xref:System.Windows.Controls.TextBox.Text%2A> имеет значение <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> <xref:System.Windows.Data.UpdateSourceTrigger> по умолчанию.  Это означает, что если приложение имеет <xref:System.Windows.Controls.TextBox> с привязки к данным свойствам <xref:System.Windows.Controls.TextBox>. <xref:System.Windows.Controls.TextBox.Text%2A>, текст, вводимый вами в <xref:System.Windows.Controls.TextBox>, не обновляет источник до тех пор, пока <xref:System.Windows.Controls.TextBox> не потеряет фокус \(например, если щелкнуть мышью вне <xref:System.Windows.Controls.TextBox>\).  
  
 Если требуется, чтобы источник обновлялся при вводе, задайте <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> привязки к <xref:System.Windows.Data.UpdateSourceTrigger>.  В следующем примере свойства `Text` и <xref:System.Windows.Controls.TextBox>, и <xref:System.Windows.Controls.TextBlock> связаны с теми же свойствами источника.  Свойство <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> привязки <xref:System.Windows.Controls.TextBox> устанавливается в значение <xref:System.Windows.Data.UpdateSourceTrigger>.  
  
 [!code-xml[SimpleBinding#USTHowTo](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml#usthowto)]  
  
 В результате <xref:System.Windows.Controls.TextBlock> отображает текст \(поскольку источник изменяется\), которой пользователь вводит в <xref:System.Windows.Controls.TextBox>, как показано на следующем снимке экрана:  
  
 ![Снимок экрана простого примера привязки данных](../../../../docs/framework/wpf/data/media/databindingsimplebindingsample2.png "DataBindingSimpleBindingSample2")  
  
 Если имеется диалоговое окно или редактируемая пользователем форма, и требуется отложить обновление источника до тех пор, пока пользователь не завершит редактирование поля и нажмет кнопку «ОК», то можно установить значение <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> привязки в <xref:System.Windows.Data.UpdateSourceTrigger>, как в следующем примере:  
  
 [!code-xml[UpdateSource#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UpdateSource/CSharp/Window1.xaml#2)]  
  
 Если задано значение <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>, равное <xref:System.Windows.Data.UpdateSourceTrigger>, то значение источника изменится только тогда, когда приложение вызовет метод <xref:System.Windows.Data.BindingExpression.UpdateSource%2A>.  В следующем примере показан способ вызова <xref:System.Windows.Data.BindingExpression.UpdateSource%2A> для `itemNameTextBox`:  
  
 [!code-csharp[UpdateSource#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UpdateSource/CSharp/Window1.xaml.cs#1)]
 [!code-vb[UpdateSource#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UpdateSource/VisualBasic/Window1.xaml.vb#1)]  
  
> [!NOTE]
>  Можно использовать одинаковые технологии для свойств других элементов управления, но следует помнить, что большинство других свойств имеют значения <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> для <xref:System.Windows.Data.UpdateSourceTrigger> по умолчанию.  Дополнительные сведения см. в свойстве на странице свойства <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>.  
  
> [!NOTE]
>  Свойство <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> имеет дело с обновлениями источника и, таким образом, относится только к привязкам <xref:System.Windows.Data.BindingMode> или <xref:System.Windows.Data.BindingMode>.  Чтобы привязки <xref:System.Windows.Data.BindingMode> и <xref:System.Windows.Data.BindingMode> работали, исходный объект должен предоставить уведомление об изменениях свойства.  Можно обратиться к примеру в данном разделе для получения дополнительных сведений.  Кроме того, можно посмотреть в [Реализация уведомления об изменении свойства](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md).  
  
## См. также  
 [Практические руководства](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)