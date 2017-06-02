---
title: "Практическое руководство. Создание привязки к методу | Microsoft Docs"
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
  - "привязка, к методам"
  - "классы, ObjectDataProvider"
  - "привязка данных, привязка к методам с помощью ObjectDataProvider"
  - "методы, привязка к"
  - "ObjectDataProvider - класс"
ms.assetid: 5f55e71e-2182-42a0-88d1-700cc1427a7a
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Практическое руководство. Создание привязки к методу
В следующем примере показывается способ создания привязки к методу с помощью <xref:System.Windows.Data.ObjectDataProvider>.  
  
## Пример  
 В этом примере `TemperatureScale` является классом, имеющим метод `ConvertTemp`, который принимает два параметра \(один `double`, а другой `enum` типа `TempType)` и преобразует данное значение из одной шкалы температуры в другую.  В следующем примере <xref:System.Windows.Data.ObjectDataProvider> используется для создания экземпляра объекта `TemperatureScale`.  Метод `ConvertTemp` вызывается с двумя заданными параметрами.  
  
 [!code-xml[BindToMethod#WindowResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToMethod/CS/Window1.xaml#windowresources)]  
  
 Теперь метод доступен в качестве ресурса и можно привязаться к его результатам.  В следующем примере свойства <xref:System.Windows.Controls.TextBox.Text%2A> <xref:System.Windows.Controls.TextBox> и <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> <xref:System.Windows.Controls.ComboBox> связаны с двумя параметрами метода.  Это дает пользователям возможность указывать температуру для преобразования и шкалу температуры для преобразования.  Обратите внимание, что <xref:System.Windows.Data.Binding.BindsDirectlyToSource%2A> присвоено значение `true`, так как выполняется привязка свойства <xref:System.Windows.Data.ObjectDataProvider.MethodParameters%2A> экземпляра <xref:System.Windows.Data.ObjectDataProvider>, а не свойства в объекта, перезаписанного <xref:System.Windows.Data.ObjectDataProvider> \(объект `TemperatureScale`\).  
  
 <xref:System.Windows.Controls.ContentControl.Content%2A> из последнего <xref:System.Windows.Controls.Label> обновляется, когда пользователь изменяет содержимое <xref:System.Windows.Controls.TextBox> или осуществляет выбор из <xref:System.Windows.Controls.ComboBox>.  
  
 [!code-xml[BindToMethod#UI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToMethod/CS/Window1.xaml#ui)]  
  
 Преобразователь `DoubleToString` принимает значение типа Double и преобразует его в строку в соответствие с <xref:System.Windows.Data.IValueConverter.Convert%2A> \(от [источника привязки](GTMT) к [цели привязки](GTMT), которая является свойством <xref:System.Windows.Controls.TextBox.Text%2A>\) и преобразует `string` в `double` в соответствии с <xref:System.Windows.Data.IValueConverter.ConvertBack%2A>.  
  
 `InvalidationCharacterRule` является <xref:System.Windows.Controls.ValidationRule>, которое проверяет наличие недопустимых знаков.  Шаблон ошибки по умолчанию в виде красной границы вокруг <xref:System.Windows.Controls.TextBox> появляется для уведомления пользователей, если вводимое значение не является значением типа Double.  
  
## См. также  
 [Практические руководства](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)   
 [Привязка к перечислению](../../../../docs/framework/wpf/data/how-to-bind-to-an-enumeration.md)