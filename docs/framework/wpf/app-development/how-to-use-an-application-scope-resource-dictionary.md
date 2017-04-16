---
title: "Практическое руководство. Использование словаря ресурсов области определения приложения | Microsoft Docs"
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
  - "словари ресурсов области видимости приложения"
  - "словари, ресурс"
  - "словари ресурсов, область видимости приложения"
ms.assetid: 53857682-bd2c-4f2c-8f25-1307d0b451a2
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Практическое руководство. Использование словаря ресурсов области определения приложения
В этом примере показана процедура определения и использования словаря пользовательских ресурсов в области приложения.  
  
## Пример  
 <xref:System.Windows.Application> предоставляет хранилище области приложения для разделяемых ресурсов: <xref:System.Windows.Application.Resources%2A>.  По умолчанию свойство <xref:System.Windows.Application.Resources%2A> инициализируется с экземпляром типа <xref:System.Windows.ResourceDictionary>.  Этот экземпляр используется при получении и установке свойств в области приложения с помощью <xref:System.Windows.Application.Resources%2A>.  \(Дополнительные сведения см. в разделе [How to: Get and Set an Application\-Scope Resource](http://msdn.microsoft.com/ru-ru/39e0420c-c9fc-47dc-8956-fdd95b214095).\)  
  
 Если имеется несколько ресурсов, установленных с помощью <xref:System.Windows.Application.Resources%2A>, можно использовать для хранения этих ресурсов словарь пользовательских ресурсов и установить <xref:System.Windows.Application.Resources%2A> с ним.  В следующем примере показано, как объявить настраиваемый словарь ресурсов с помощью XAML.  
  
 [!code-xml[HOWTOResourceDictionaries#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MyResourceDictionary.xaml#1)]  
  
 Замена целых словарей ресурсов с помощью <xref:System.Windows.Application.Resources%2A> позволяет поддерживать темы области приложения, когда каждая тема инкапсулируется одним словарем ресурсов.  В приведенном ниже примере описывается задание <xref:System.Windows.ResourceDictionary>.  
  
 [!code-xml[HOWTOResourceDictionaries#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/App.xaml#2)]  
  
 В следующем примере показывается, как можно получить ресурсы области приложения из словаря ресурсов, предоставляемого <xref:System.Windows.Application.Resources%2A> в XAML.  
  
 [!code-xml[HOWTOResourceDictionaries#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MainWindow.xaml#4)]  
  
 В следующем примере показывается, как можно получить ресурсы в коде.  
  
 [!code-csharp[HOWTOResourceDictionaries#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MainWindow.xaml.cs#3)]
 [!code-vb[HOWTOResourceDictionaries#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToResourceDictionaries/VB/MainWindow.xaml.vb#3)]  
  
 При использовании <xref:System.Windows.Application.Resources%2A> необходимо учесть следующие два момента.  Во\-первых, *ключ* словаря является объектом, поэтому необходимо использовать строго тот же экземпляр объекта при установке и получении значения свойства.  \(Следует отметить, что при использовании строки ключ чувствителен к регистру символов.\) Во\-вторых, *значение* словаря является объектом, поэтому необходимо преобразовать это значение в требуемый тип при получении значения свойства.  
  
## См. также  
 <xref:System.Windows.ResourceDictionary>   
 <xref:System.Windows.Application.Resources%2A>   
 [Ресурсы XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md)   
 [Объединенные словари ресурсов](../../../../docs/framework/wpf/advanced/merged-resource-dictionaries.md)