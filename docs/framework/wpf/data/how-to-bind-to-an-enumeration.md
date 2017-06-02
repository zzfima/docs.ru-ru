---
title: "Практическое руководство. Привязка к перечислению | Microsoft Docs"
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
  - "привязка данных, перечисление"
  - "привязка данных, перечисление"
  - "перечисление"
ms.assetid: b9091eba-1119-424e-868b-d1a4168b3732
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Практическое руководство. Привязка к перечислению
В этом примере описывается порядок привязки к перечислению посредством привязки к методу GetValues перечисления.  
  
## Пример  
 В следующем примере привязка данных используется для отображения в объекте <xref:System.Windows.Controls.ListBox> списка значений перечисления <xref:System.Windows.HorizontalAlignment>.  Объекты <xref:System.Windows.Controls.ListBox> и <xref:System.Windows.Controls.Button> связываются таким образом, чтобы обеспечить возможность изменения значения свойства <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> объекта <xref:System.Windows.Controls.Button> при выборе значения в объекте <xref:System.Windows.Controls.ListBox>.  
  
 [!code-xml[BindToEnum#BindToEnum](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToEnum/CS/Window1.xaml#bindtoenum)]  
  
## См. также  
 [Создание привязки к методу](../../../../docs/framework/wpf/data/how-to-bind-to-a-method.md)   
 [Общие сведения о связывании данных](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Практические руководства](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)