---
title: "Практическое руководство. сделать объект Freezable доступным только для чтения | Microsoft Docs"
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
  - "Freezable - объекты, сделать доступными только для чтения"
ms.assetid: 6c544b7d-d3c9-4736-aa90-4b8728234ccb
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Практическое руководство. сделать объект Freezable доступным только для чтения
В этом примере демонстрируется, как сделать объект <xref:System.Windows.Freezable> доступным только для чтения путем вызова его метода <xref:System.Windows.Freezable.Freeze%2A>.  
  
 Если для объекта хотя бы одно из перечисленных ниже условий `true`, то зафиксировать объект <xref:System.Windows.Freezable> нельзя.  
  
-   Объект имеет свойства анимации или привязки данных.  
  
-   Объект имеет свойства, устанавливаемые динамическим ресурсом.  Дополнительные сведения о динамических ресурсах см. в разделе [Ресурсы XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
-   Объект содержит подобъекты <xref:System.Windows.Freezable>, которые нельзя зафиксировать.  
  
 Если эти условия `false` и объект <xref:System.Windows.Freezable> не предполагается изменять, можно зафиксировать этот объект, чтобы повысить производительность.  
  
## Пример  
 В следующем примере фиксируется объект <xref:System.Windows.Media.SolidColorBrush>, который является типом объекта <xref:System.Windows.Freezable>.  
  
 [!code-csharp[freezablesample_procedural#FreezeExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#freezeexample1)]
 [!code-vb[freezablesample_procedural#FreezeExample1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#freezeexample1)]  
  
 Дополнительные сведения об объектах <xref:System.Windows.Freezable> содержатся в разделе [Общие сведения об объектах класса Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
## См. также  
 <xref:System.Windows.Freezable>   
 <xref:System.Windows.Freezable.CanFreeze%2A>   
 <xref:System.Windows.Freezable.Freeze%2A>   
 [Общие сведения об объектах класса Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)   
 [Практические руководства](../../../../docs/framework/wpf/advanced/base-elements-how-to-topics.md)