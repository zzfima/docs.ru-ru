---
title: "Практическое руководство. Перечисление подмножества очередей печати | Microsoft Docs"
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
  - "перечисление, подмножество очередей печати"
  - "очереди печати, перечисление подмножества"
ms.assetid: cc4a1b5b-d46f-4c5e-bc26-22c226e4bee0
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Практическое руководство. Перечисление подмножества очередей печати
Обычной ситуацией, возникающей у специалистов по информационным технологиям, управляющих множеством принтеров компании, является получение списка принтеров, имеющих определенные характеристики.  Эта функциональная возможность обеспечивается методом <xref:System.Printing.PrintServer.GetPrintQueues%2A> объекта <xref:System.Printing.PrintServer> и перечислением <xref:System.Printing.EnumeratedPrintQueueTypes>.  
  
## Пример  
 В примере ниже код начинается с создания массива флагов, определяющих характеристики очередей печати, которые требуется внести в список.  В этом примере выполняется поиск очередей печати, которые установлены локально на сервере печати и являются общими.  Перечисление <xref:System.Printing.EnumeratedPrintQueueTypes> предоставляет множество других возможностей.  
  
 Затем в коде создается объект класса <xref:System.Printing.LocalPrintServer>, производного от <xref:System.Printing.PrintServer>.  Локальный сервер печати является компьютером, на котором запущено приложение.  
  
 Последний значительный этап заключается в передаче массива методу <xref:System.Printing.PrintServer.GetPrintQueues%2A>.  
  
 Наконец, результаты предоставляются пользователю.  
  
 [!code-cpp[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](../../../../samples/snippets/cpp/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/CPP/Program.cpp#listsubsetofprintqueues)]
 [!code-csharp[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/CSharp/Program.cs#listsubsetofprintqueues)]
 [!code-vb[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/visualbasic/program.vb#listsubsetofprintqueues)]  
  
 Этот пример кода может быть расширен с помощью цикла `foreach`, который проходит по каждой очереди печати для дальнейшей блокировки.  Например, можно блокировать принтеры, которые не поддерживают двустороннюю печать, вызвав в цикле метод <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> каждой очереди печати и проверив возвращаемое значение на наличие блока двусторонней печати.  
  
## См. также  
 <xref:System.Printing.PrintServer.GetPrintQueues%2A>   
 <xref:System.Printing.PrintServer>   
 <xref:System.Printing.LocalPrintServer>   
 <xref:System.Printing.EnumeratedPrintQueueTypes>   
 <xref:System.Printing.PrintQueue>   
 <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>   
 [Документы в WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)   
 [Общие сведения о печати](../../../../docs/framework/wpf/advanced/printing-overview.md)   
 [Microsoft XPS Document Writer](http://go.microsoft.com/fwlink/?LinkId=147319)