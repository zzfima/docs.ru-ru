---
title: "Свойства зависимостей типа коллекция | Microsoft Docs"
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
  - "свойства типа-коллекции"
  - "свойства зависимостей"
  - "свойства, тип коллекции"
  - "свойства, dependency"
ms.assetid: 99f96a42-3ab7-4f64-a16b-2e10d654e97c
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Свойства зависимостей типа коллекция
Данный раздел содержит рекомендации и рекомендуемые шаблоны для реализации [свойства зависимостей](GTMT), типом которых является коллекция.  
  
   
  
<a name="implementing"></a>   
## Реализация свойства зависимостей типа коллекция  
 В общем случае для свойства зависимостей шаблоном реализации, которому необходимо следовать, является определение обертки свойства [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)], где это свойство возвращается идентификатором <xref:System.Windows.DependencyProperty>, а не полем или другой конструкцией.  Необходимо следовать этому же шаблону и при реализации свойства типа коллекция.  Однако свойство типа коллекция представляет некоторые сложности в шаблоне, если тип, содержащийся в коллекции, является классом, производным от <xref:System.Windows.DependencyObject> или <xref:System.Windows.Freezable>.  
  
<a name="initializing"></a>   
## Инициализация коллекции со значением не по умолчанию  
 При создании свойства зависимостей значение свойства по умолчанию не задается в качестве начального значения поля.  Вместо этого значение по умолчанию задается с помощью метаданных свойства зависимостей.  Если свойство является ссылочным типом, то значение по умолчанию, заданное в метаданных свойства зависимостей, не является значением по умолчанию для каждого экземпляра. Вместо этого оно является значением по умолчанию, которое применяется ко всем экземплярам типа.  Поэтому необходимо избегать использования единственной статической коллекции, определенную метаданными свойства коллекции, как рабочее значение по умолчанию для только что созданных экземпляров типа.  Вместо этого следует убедиться, что значение коллекции намеренно задается одной \(одним экземпляром\) коллекцией как часть логики конструктора класса.  В противном случае будет создан случайный одноэлементный класс.  
  
 Рассмотрим следующий пример.  В следующем разделе примера показано определение класса `Aquarium`.  Класс определяет свойство зависимостей типа коллекция `AquariumObjects`, которое использует базовый тип <xref:System.Collections.Generic.List%601> с ограничением типа <xref:System.Windows.FrameworkElement>.  В вызове <xref:System.Windows.DependencyProperty.Register%28System.String%2CSystem.Type%2CSystem.Type%2CSystem.Windows.PropertyMetadata%29> для свойства зависимости метаданные устанавливают значение по умолчанию новым базовым <xref:System.Collections.Generic.List%601>.  
  
 <!-- TODO: review snippet reference [!code-csharp[PropertiesOvwSupport#CollectionProblemDefinition](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml.cs#collectionproblemdefinition)]  -->
 [!code-vb[PropertiesOvwSupport#CollectionProblemDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page4.xaml.vb#collectionproblemdefinition)]  
[!code-csharp[PropertiesOvwSupport#CollectionProblemEndB](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml.cs#collectionproblemendb)]
[!code-vb[PropertiesOvwSupport#CollectionProblemEndB](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page4.xaml.vb#collectionproblemendb)]  
  
 Однако, если оставить код как показано, это одно приведенное значение по умолчанию будет совместно используемым значением всеми экземплярами `Aquarium`.  Если выполнить следующий код проверки, предназначенный для того, чтобы показать, как будут созданы два отдельных экземпляра `Aquarium` и как к каждому из них будет добавлен один отличный `Fish`, обнаружится интересный результат:  
  
 [!code-csharp[PropertiesOvwSupport#CollectionProblemTestCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml.cs#collectionproblemtestcode)]
 [!code-vb[PropertiesOvwSupport#CollectionProblemTestCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page4.xaml.vb#collectionproblemtestcode)]  
  
 В каждой коллекции вместо числа 1 будет 2.  Это происходит потому, что каждый `Aquarium` добавляет свой `Fish` в коллекцию значений по умолчанию, созданную в результате единственного вызова конструктора в метаданных и совместно используемую в дальнейшем всеми экземплярами.  Эта ситуация почти никогда не является требуемым результатом.  
  
 Чтобы устранить эту проблему, необходимо задать значение свойства зависимости коллекции уникальным экземпляром в составе вызова конструктора класса.  Так как свойство зависимости доступно только для чтения, для его задания используется метод <xref:System.Windows.DependencyObject.SetValue%28System.Windows.DependencyPropertyKey%2CSystem.Object%29> с использованием <xref:System.Windows.DependencyPropertyKey>, являющегося единственно доступным в классе.  
  
 [!code-csharp[PropertiesOvwSupport#CollectionProblemCtor](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml.cs#collectionproblemctor)]
 [!code-vb[PropertiesOvwSupport#CollectionProblemCtor](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page4.xaml.vb#collectionproblemctor)]  
  
 Теперь, если запустить тот же код проверки еще раз, можно увидеть более ожидаемых результаты: каждый `Aquarium` поддерживает свою собственную уникальную коллекцию.  
  
 Если бы свойство коллекции было доступным и для чтения, и для записи, шаблон слегка отличался бы от этого.  В таком случае можно было бы вызвать открытый доступ из конструктора для выполнения инициализации, он бы так же вызвал не ключевую сигнатуру <xref:System.Windows.DependencyObject.SetValue%28System.Windows.DependencyProperty%2CSystem.Object%29> внутри обертки записи при помощи открытого идентификатора <xref:System.Windows.DependencyProperty>.  
  
## Сообщение об изменениях значений привязки из свойств коллекции  
 Свойство коллекции, которое само является свойством зависимости, автоматически не сообщает об изменениях своим подсвойствам.  При создании привязки в коллекции привязке не будет сообщено об изменениях и следовательно нарушатся некоторые сценарии привязки данных.  Однако, если использовать тип коллекции <xref:System.Windows.FreezableCollection%601> в качестве типа коллекции, то об изменениях субсвойств в содержащихся в коллекции элементах будет сообщено, и привязка будет работать, как ожидалось.  
  
 Чтобы включить привязку подсвойства в объектной коллекции зависимости, создайте свойство коллекции типа <xref:System.Windows.FreezableCollection%601> с ограничением типа для этой коллекции любым классом, производным от <xref:System.Windows.DependencyObject>.  
  
## См. также  
 <xref:System.Windows.FreezableCollection%601>   
 [Код XAML и пользовательские классы для WPF](../../../../docs/framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)   
 [Общие сведения о связывании данных](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Общие сведения о свойствах зависимости](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)   
 [Пользовательские свойства зависимостей](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)   
 [Метаданные свойства зависимости](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md)