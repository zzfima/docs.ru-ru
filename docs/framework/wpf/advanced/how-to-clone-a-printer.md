---
title: "Практическое руководство. Клонирование принтера"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- print queues [WPF]
- cloning printers [WPF]
- printers [WPF], cloning
- print queues [WPF], cloning
- cloning print queues [WPF]
ms.assetid: dd6997c9-fe04-40f8-88a6-92e3ac0889eb
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 303cb9c1c5b6521839987a56cdc008eac0559cf1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-clone-a-printer"></a>Практическое руководство. Клонирование принтера
Большинство компаний в определенный момент купит нескольких принтеров той же модели. Как правило они все вместе устанавливаются с практически одинаковыми параметрами. Установка каждого принтера может занять много времени и подвержены ошибкам. <xref:System.Printing.IndexedProperties?displayProperty=nameWithType> Пространства имен и <xref:System.Printing.PrintServer.InstallPrintQueue%2A> класс, который предоставляется через [!INCLUDE[TLA#tla_avalonwinfx](../../../../includes/tlasharptla-avalonwinfx-md.md)] дает возможность мгновенно установить любое число дополнительных очередей печати, которые будут скопированы из существующей очереди печати.  
  
## <a name="example"></a>Пример  
 В приведенном ниже примере вторая очередь печати клонируется из существующей очереди печати. Второй отличающимся от первого только в его имя, расположение, порт и состояние общего доступа. Ниже приведены основные действия по созданию.  
  
1.  Создание <xref:System.Printing.PrintQueue> объекта для существующего принтера, который требуется создать точную копию.  
  
2.  Создание <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> из <xref:System.Printing.PrintSystemObject.PropertiesCollection%2A> из <xref:System.Printing.PrintQueue>. <xref:System.Collections.DictionaryEntry.Value%2A> Каждой записи в этом словаре является объектом одного из типов, производных от <xref:System.Printing.IndexedProperties.PrintProperty>. Существует два способа задать значение записи в этом словаре.  
  
    -   Использование словаря **удалить** и <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.Add%2A> методов, чтобы удалить запись, а затем снова добавьте его с требуемым значением.  
  
    -   Использование словаря <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.SetProperty%2A> метод.  
  
     В приведенном ниже примере показаны оба способа.  
  
3.  Создание <xref:System.Printing.IndexedProperties.PrintBooleanProperty> и задайте его <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> для «IsShared» и его <xref:System.Printing.IndexedProperties.PrintBooleanProperty.Value%2A> для `true`.  
  
4.  Используйте <xref:System.Printing.IndexedProperties.PrintBooleanProperty> объект, который будет значение <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>в записи «IsShared».  
  
5.  Создание <xref:System.Printing.IndexedProperties.PrintStringProperty> и задайте его <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> для «ShareName» и его <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> — соответствующую <xref:System.String>.  
  
6.  Используйте <xref:System.Printing.IndexedProperties.PrintStringProperty> объект, который будет значение <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>в записи «ShareName».  
  
7.  Создайте другой <xref:System.Printing.IndexedProperties.PrintStringProperty> и задайте его <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> для «Местоположение» и его <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> — соответствующую <xref:System.String>.  
  
8.  Используйте второй <xref:System.Printing.IndexedProperties.PrintStringProperty> объект, который будет значение <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>в записи «Местоположение».  
  
9. Создайте массив <xref:System.String>s. Каждый элемент — это имя порта на сервере.  
  
10. Используйте <xref:System.Printing.PrintServer.InstallPrintQueue%2A> для установки нового принтера с новыми значениями.  
  
 Пример приведен ниже.  
  
 [!code-csharp[ClonePrinter#ClonePrinter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ClonePrinter/CSharp/Program.cs#cloneprinter)]
 [!code-vb[ClonePrinter#ClonePrinter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ClonePrinter/visualbasic/program.vb#cloneprinter)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Printing.IndexedProperties>  
 <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>  
 <xref:System.Printing.LocalPrintServer>  
 <xref:System.Printing.PrintQueue>  
 <xref:System.Collections.DictionaryEntry>  
 [Документы в WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [Общие сведения о печати](../../../../docs/framework/wpf/advanced/printing-overview.md)
