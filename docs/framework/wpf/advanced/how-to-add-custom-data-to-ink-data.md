---
title: "Практическое руководство. Добавление данных пользователя в данные рукописного ввода | Microsoft Docs"
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
  - "данные рукописного ввода, добавление пользовательских данных"
  - "InkCanvas, отображение"
ms.assetid: f02aac6f-3436-4f7c-b6ea-0452cba5332c
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Практическое руководство. Добавление данных пользователя в данные рукописного ввода
Можно добавить пользовательские рукописные данные, которые будут сохранены при сохранении рукописных данных как рукописный ввод сериализованного формата \(ISF\).  Можно сохранить пользовательские данные для <xref:System.Windows.Ink.DrawingAttributes>, <xref:System.Windows.Ink.StrokeCollection> или <xref:System.Windows.Ink.Stroke>.  Возможность сохранить пользовательские данные в трех объектах дает возможность выбрать лучшее место для сохранения данных.  Все три класса используют аналогичные методы для хранения и доступа к пользовательским данным.  
  
 Только следующие типы могут сохраняться как пользовательские данные:  
  
-   <xref:System.Boolean>  
  
-   <xref:System.Boolean>\[\]  
  
-   <xref:System.Byte>  
  
-   <xref:System.Byte>\[\]  
  
-   <xref:System.Char>  
  
-   <xref:System.Char>\[\]  
  
-   <xref:System.DateTime>  
  
-   <xref:System.DateTime>\[\]  
  
-   <xref:System.Decimal>  
  
-   <xref:System.Decimal>\[\]  
  
-   <xref:System.Double>  
  
-   <xref:System.Double>\[\]  
  
-   <xref:System.Int16>  
  
-   <xref:System.Int16>\[\]  
  
-   <xref:System.Int32>  
  
-   <xref:System.Int32>\[\]  
  
-   <xref:System.Int64>  
  
-   <xref:System.Int64>\[\]  
  
-   <xref:System.Single>  
  
-   <xref:System.Single>\[\]  
  
-   <xref:System.String>  
  
-   <xref:System.UInt16>  
  
-   <xref:System.UInt16>\[\]  
  
-   <xref:System.UInt32>  
  
-   <xref:System.UInt32>\[\]  
  
-   <xref:System.UInt64>  
  
-   <xref:System.UInt64>\[\]  
  
## Пример  
 В следующем примере показано, как добавить и получить пользовательские данные из <xref:System.Windows.Ink.StrokeCollection>.  
  
 [!code-csharp[HowToAddCustomDataToInk#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToAddCustomDataToInk/CSharp/Window1.xaml.cs#1)]  
  
 В следующем примере создается приложение, отображающее <xref:System.Windows.Controls.InkCanvas> и две кнопки.  Кнопка `switchAuthor` позволяет использовать два пера двум различным авторам.  Кнопка `changePenColors` изменяет цвет каждого штриха в <xref:System.Windows.Controls.InkCanvas> согласно автору.  Приложение определяет два объекта <xref:System.Windows.Ink.DrawingAttributes> и добавляет каждому пользовательское свойство, указывающее, какой автор рисовал <xref:System.Windows.Ink.Stroke>.  При щелчке пользователя на `changePenColors`, приложение изменяет внешний вид штриха согласно значению пользовательского свойства.  
  
 [!code-xml[HowToAddCustomDataToInk#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToAddCustomDataToInk/CSharp/Window1.xaml#2)]  
  
 [!code-csharp[HowToAddCustomDataToInk#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToAddCustomDataToInk/CSharp/Window1.xaml.cs#3)]