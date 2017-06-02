---
title: "Практическое руководство. Указание источника привязки | Microsoft Docs"
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
  - "привязка данных, привязка к источникам"
  - "привязка к источникам"
  - "привязка данных, источник привязки"
ms.assetid: 55d47757-2648-4a52-987f-b767953f168c
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Практическое руководство. Указание источника привязки
В привязке данных объект [источник привязки](GTMT) ссылается на объект, из которого получаются данные.  В этом разделе описываются различные способы указания [источника привязки](GTMT).  
  
## Пример  
 При привязке нескольких свойств к общему источнику может понадобиться использовать свойство `DataContext`, которое предоставляет удобный способ для установления области видимости, внутри которой все свойства с привязкой к данным наследуют общий источник.  
  
 В следующем примере контекст данных устанавливается для корневого элемента приложения.  Это позволяет всем дочерним элементам наследовать этот контекст данных.  Данные для привязки поступают из настраиваемого класса данных, `NetIncome`, ссылки на который выполняются непосредственно через сопоставление и через полученный ключ ресурса `incomeDataSource`.  
  
 [!code-xml[DirectionalBinding#DataContext1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#datacontext1)]  
[!code-xml[DirectionalBinding#DataContext2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#datacontext2)]  
  
 В следующем примере показано определение класса `NetIncome`.  
  
 [!code-csharp[DirectionalBinding#DataObject](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/billsdata.cs#dataobject)]
 [!code-vb[DirectionalBinding#DataObject](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DirectionalBinding/VisualBasic/NetIncome.vb#dataobject)]  
  
> [!NOTE]
>  Вышеприведенный пример создает экземпляр объекта в разметке и использует его в качестве ресурса.  Если требуется выполнить привязку к объекту, экземпляр которого был уже создан в коде, необходимо установить свойство `DataContext` программным образом.  Пример см. в разделе [Обеспечение доступности данных для привязки в XAML](../../../../docs/framework/wpf/data/how-to-make-data-available-for-binding-in-xaml.md).  
  
 Кроме того, если требуется явно указать источник в отдельных привязках, возможны следующие параметры.  Они имеют приоритет над наследуемым контекстом данных.  
  
|Свойство.|Описание|  
|---------------|--------------|  
|<xref:System.Windows.Data.Binding.Source%2A>|Это свойство используется для установки источника экземпляра объекта.  Если не нужны функциональные возможности установки области видимости, в которой несколько свойств наследуют один и тот же контекст данных, можно использовать свойство <xref:System.Windows.Data.Binding.Source%2A> вместо свойства `DataContext`.  Дополнительные сведения см. в разделе <xref:System.Windows.Data.Binding.Source%2A>.|  
|<xref:System.Windows.Data.Binding.RelativeSource%2A>|Это полезно, если требуется указать источник относительно того, где расположена [цель привязки](GTMT).  Некоторыми общими скриптами, в которых можно использовать это свойство, являются сценарии, когда требуется выполнить привязку одного свойства элемента к другому свойству этого же элемента, или если привязка задается в стиле или шаблоне.  Дополнительные сведения см. в разделе <xref:System.Windows.Data.Binding.RelativeSource%2A>.|  
|<xref:System.Windows.Data.Binding.ElementName%2A>|Следует указать строку, представляющую элемент, к которому требуется осуществить привязку.  Это полезно, если необходимо выполнить привязку к свойству другого элемента в вашем приложении.  Например, если требуется использовать <xref:System.Windows.Controls.Slider> для управления высотой другого элемента управления в приложении, или если требуется выполнить привязку <xref:System.Windows.Controls.ContentControl.Content%2A> элемента управления к свойству <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> элемента управления <xref:System.Windows.Controls.ListBox>.  Дополнительные сведения см. в разделе <xref:System.Windows.Data.Binding.ElementName%2A>.|  
  
## См. также  
 <xref:System.Windows.FrameworkElement.DataContext%2A?displayProperty=fullName>   
 <xref:System.Windows.FrameworkContentElement.DataContext%2A?displayProperty=fullName>   
 [Наследование значения свойства](../../../../docs/framework/wpf/advanced/property-value-inheritance.md)   
 [Общие сведения о связывании данных](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Общие сведения об объявлении привязок](../../../../docs/framework/wpf/data/binding-declarations-overview.md)   
 [Практические руководства](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)