---
title: "Практическое руководство. Получение свойств объекта системы печати без отражения | Microsoft Docs"
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
  - "PrintSystemObject, получение свойств"
ms.assetid: 43560f28-183d-41c1-b9d1-de7c2552273e
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Практическое руководство. Получение свойств объекта системы печати без отражения
Использование отражения для перечисления свойств \(и типов этих свойств\) в объекте может уменьшить скорость работы приложения.  Пространство имен <xref:System.Printing.IndexedProperties> позволяет извлечь эту информации с помощью отражения.  
  
## Пример  
 Ниже приведены шаги, необходимые для выполнения этой операции.  
  
1.  Создайте экземпляр типа.  В примере, приведенном ниже, тип является типом <xref:System.Printing.PrintQueue>, поставляемым вместе с [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)]. Однако почти идентичный этому код должен работать для типов, производных от <xref:System.Printing.PrintSystemObject>.  
  
2.  Создайте <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> из <xref:System.Printing.PrintSystemObject.PropertiesCollection%2A> типа.  Свойство <xref:System.Collections.DictionaryEntry.Value%2A> каждой записи в этом словаре является объектом одного из типов, производных от <xref:System.Printing.IndexedProperties.PrintProperty>.  
  
3.  Перечислите члены словаря.  Для каждого из них выполните следующие действия.  
  
4.  Приведите значение каждого элемента в <xref:System.Printing.IndexedProperties.PrintProperty> и используйте его для создания объекта <xref:System.Printing.IndexedProperties.PrintProperty>.  
  
5.  Получите тип <xref:System.Printing.IndexedProperties.PrintProperty.Value%2A> каждого объекта <xref:System.Printing.IndexedProperties.PrintProperty>.  
  
 [!code-csharp[GetPrintObjectPropertyTypesWithoutReflection#ShowPropertyTypesWithoutReflection](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GetPrintObjectPropertyTypesWithoutReflection/CSharp/Program.cs#showpropertytypeswithoutreflection)]
 [!code-vb[GetPrintObjectPropertyTypesWithoutReflection#ShowPropertyTypesWithoutReflection](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GetPrintObjectPropertyTypesWithoutReflection/visualbasic/program.vb#showpropertytypeswithoutreflection)]  
  
## См. также  
 <xref:System.Printing.IndexedProperties.PrintProperty>   
 <xref:System.Printing.PrintSystemObject>   
 <xref:System.Printing.IndexedProperties>   
 <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>   
 <xref:System.Printing.LocalPrintServer>   
 <xref:System.Printing.PrintQueue>   
 <xref:System.Collections.DictionaryEntry>   
 [Документы в WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)   
 [Общие сведения о печати](../../../../docs/framework/wpf/advanced/printing-overview.md)