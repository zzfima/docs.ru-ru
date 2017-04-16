---
title: "Практическое руководство. Вызов диалогового окна печати | Microsoft Docs"
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
  - "вызов диалоговых окон печати"
  - "диалоговые окна печати, вызов"
ms.assetid: e3a2c84c-74fe-45a4-8501-5813f9dbfed2
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Практическое руководство. Вызов диалогового окна печати
Чтобы обеспечить возможность печати из приложения, необходимо создать и открыть объект <xref:System.Windows.Controls.PrintDialog>.  
  
## Пример  
 Элемент управления <xref:System.Windows.Controls.PrintDialog> обеспечивает одну точку входа для [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], конфигурацию и отправку задания [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)].  Элемент управления прост в использовании и может быть создан с помощью разметки [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] или кода.  В следующем примере показано создание экземпляра, открытие элемента управления в коде и печать из него.  Также показано, как убедиться в том, что окно предоставит пользователям возможность установки конкретного диапазона страниц.  В примере кода предполагается, что в корневой папке диска C: имеется файл FixedDocumentSequence.xps.  
  
 [!code-csharp[printdialog#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrintDialog/CSharp/Window1.xaml.cs#1)]
 [!code-vb[printdialog#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrintDialog/visualbasic/window1.xaml.vb#1)]  
  
 После открытия диалогового окна пользователи смогут выбрать один из принтеров, установленных на компьютере.  Также они будут иметь возможность выбрать [Средство записи XPS\-документов \(Microsoft\)](http://go.microsoft.com/fwlink/?LinkId=147319) для создания файла [!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)] вместо печати.  
  
> [!NOTE]
>  Элемент управления <xref:System.Windows.Controls.PrintDialog?displayProperty=fullName> [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], рассматриваемый в этом разделе, не следует путать с компонентом <xref:System.Windows.Forms.PrintDialog?displayProperty=fullName> [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)].  
  
 Строго говоря, метод <xref:System.Windows.Controls.PrintDialog.PrintDocument%2A> можно использовать даже без открытия диалогового окна.  Из этого следует, что элемент управления может использоваться в качестве невидимого компонента печати.  Однако, из соображений производительности лучше использовать метод <xref:System.Printing.PrintQueue.AddJob%2A> или один из многих методов <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> и <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> <xref:System.Windows.Xps.XpsDocumentWriter>.  Дополнительные сведения см. в разделе [Печать XPS\-файлов программным способом](../../../../docs/framework/wpf/advanced/how-to-programmatically-print-xps-files.md).  
  
## См. также  
 <xref:System.Windows.Controls.PrintDialog>   
 [Документы в WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)   
 [Общие сведения о печати](../../../../docs/framework/wpf/advanced/printing-overview.md)   
 [Microsoft XPS Document Writer](http://go.microsoft.com/fwlink/?LinkId=147319)