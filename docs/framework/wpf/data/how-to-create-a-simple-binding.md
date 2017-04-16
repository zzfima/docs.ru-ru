---
title: "Практическое руководство. Создать простой привязки | Microsoft Docs"
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
  - "привязка данных, создание"
  - "привязка данных, создание простых привязок"
  - "простая привязка, создание"
ms.assetid: 69b80f72-6259-44cb-8294-5bdcebca1e08
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Практическое руководство. Создать простой привязки
Этот пример показывает создание простого объекта <xref:System.Windows.Data.Binding>.  
  
## Пример  
 В этом примере имеется объект `Person` со строковым свойством с именем `PersonName`.  Объект `Person` определен в пространстве имен с именем `SDKSample`.  
  
 В следующем примере создается экземпляр объекта `Person` со значением `Joe` для свойства `PersonName`.  Это сделано в разделе `Resources` и назначено `x:Key`.  
  
 [!code-xml[SimpleBinding#Instantiation](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#instantiation)]  
[!code-xml[SimpleBinding#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#2)]  
[!code-xml[SimpleBinding#EndWindow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#endwindow)]  
  
 Для привязки к свойству `PersonName` необходимо выполнить следующие действия:  
  
 [!code-xml[SimpleBinding#BDO1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#bdo1)]  
  
 В результате <xref:System.Windows.Controls.TextBlock> отобразится со значением "Joe".  
  
## См. также  
 [Общие сведения о связывании данных](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Практические руководства](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)