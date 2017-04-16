---
title: "Практическое руководство. Клонирование принтера | Microsoft Docs"
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
  - "клонирование очередей печати"
  - "клонирование принтеров"
  - "очереди печати"
  - "очереди печати, клонирование"
  - "принтеры, клонирование"
ms.assetid: dd6997c9-fe04-40f8-88a6-92e3ac0889eb
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Практическое руководство. Клонирование принтера
Большинство организаций в некоторых случаях покупают несколько принтеров одинаковой модели.  Как правило, они все вместе устанавливаются с практически одинаковыми параметрами.  Установка каждого принтера по отдельности занимает много времени, кроме того, увеличивается вероятность ошибок.  Пространство имен <xref:System.Printing.IndexedProperties?displayProperty=fullName> и класс <xref:System.Printing.PrintServer.InstallPrintQueue%2A>, которые предоставляются с [!INCLUDE[TLA#tla_avalonwinfx](../../../../includes/tlasharptla-avalonwinfx-md.md)], дают возможность мгновенно установить любое число дополнительных очередей печати клонированием существующей очереди печати.  
  
## Пример  
 В приведенном ниже примере вторая очередь печати клонируется из существующей очереди печати.  Вторая очередь отличается от первой только именем, расположением, портом и статусом общего доступа.  Ниже приведены основные действия по созданию копии очереди печати.  
  
1.  Создайте объект <xref:System.Printing.PrintQueue> для существующего принтера, который подлежит клонированию.  
  
2.  Создайте словарь <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> из коллекции <xref:System.Printing.PrintSystemObject.PropertiesCollection%2A> класса <xref:System.Printing.PrintQueue>.  Свойство <xref:System.Collections.DictionaryEntry.Value%2A> каждой записи в этом словаре является объектом одного из типов, производных от <xref:System.Printing.IndexedProperties.PrintProperty>.  Существует два способа задать значение записи в этом словаре:  
  
    -   использование методов словаря **Remove** и <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.Add%2A> для удаления записи и повторного добавления ее с измененным значением,  
  
    -   использование метода словаря <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.SetProperty%2A>.  
  
     В примере ниже показаны оба способа.  
  
3.  Создайте объект <xref:System.Printing.IndexedProperties.PrintBooleanProperty> и задайте для его свойства <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> значение IsShared, а для свойства <xref:System.Printing.IndexedProperties.PrintBooleanProperty.Value%2A> — значение `true`.  
  
4.  Используйте объект <xref:System.Printing.IndexedProperties.PrintBooleanProperty> в качестве значения записи IsShared элемента <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>.  
  
5.  Создайте объект <xref:System.Printing.IndexedProperties.PrintStringProperty> и задайте для его свойства <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> значение ShareName, а для свойства <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> — соответствующую строку <xref:System.String>.  
  
6.  Используйте объект <xref:System.Printing.IndexedProperties.PrintStringProperty> в качестве значения записи ShareName элемента <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>.  
  
7.  Создайте другой объект <xref:System.Printing.IndexedProperties.PrintStringProperty> и задайте для его свойства <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> значение Location, а для свойства <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> — соответствующую строку <xref:System.String>.  
  
8.  Используйте второй объект <xref:System.Printing.IndexedProperties.PrintStringProperty> в качестве значения записи Location элемента <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>.  
  
9. Создайте массив объектов <xref:System.String>.  Каждый элемент является именем порта на сервере.  
  
10. Используйте <xref:System.Printing.PrintServer.InstallPrintQueue%2A> для установки нового принтера с новыми значениями.  
  
 Пример приведен ниже.  
  
 [!code-csharp[ClonePrinter#ClonePrinter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ClonePrinter/CSharp/Program.cs#cloneprinter)]
 [!code-vb[ClonePrinter#ClonePrinter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ClonePrinter/visualbasic/program.vb#cloneprinter)]  
  
## См. также  
 <xref:System.Printing.IndexedProperties>   
 <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>   
 <xref:System.Printing.LocalPrintServer>   
 <xref:System.Printing.PrintQueue>   
 <xref:System.Collections.DictionaryEntry>   
 [Документы в WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)   
 [Общие сведения о печати](../../../../docs/framework/wpf/advanced/printing-overview.md)