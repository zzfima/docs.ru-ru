---
title: "Как печатать файлы XPS программным способом | Microsoft Docs"
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
  - "печать файлов XPS программным способом"
  - "XPS-файлы, печать программным способом"
ms.assetid: 0b1c0a3f-b19e-43d6-bcc9-eb3ec4e555ad
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Как печатать файлы XPS программным способом
Для печати файлов [!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)] можно использовать перегрузку метода <xref:System.Printing.PrintQueue.AddJob%2A> не открывая <xref:System.Windows.Controls.PrintDialog> или, в принципе, вообще [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].  
  
 Кроме того, напечатать файлы [!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)] можно с помощью методов <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> и <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> объекта <xref:System.Windows.Xps.XpsDocumentWriter>.  Для получения дополнительных сведений об этом см. [Printing an XPS Document](http://msdn.microsoft.com/ru-ru/849555c8-0c4e-48c0-86bc-a5494c69b36c).  
  
 Другой способ печати [!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)] заключается в использовании методов <xref:System.Windows.Controls.PrintDialog.PrintDocument%2A> или <xref:System.Windows.Controls.PrintDialog.PrintVisual%2A> элемента управления <xref:System.Windows.Controls.PrintDialog>.  См. раздел [Вызов диалогового окна печати](../../../../docs/framework/wpf/advanced/how-to-invoke-a-print-dialog.md).  
  
## Пример  
 Ниже приведены основные шаги использования метода <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29> с тремя параметрами.  Нижеприведенный пример содержит подробные сведения.  
  
1.  Определите, является ли принтер принтером XPSDrv.  \(Дополнительные сведения о драйвере XPSDrv см. в разделе [Общие сведения о печати](../../../../docs/framework/wpf/advanced/printing-overview.md).\)  
  
2.  Если принтер не является принтером XPSDrv, установите подразделение потока на однопотоковое.  
  
3.  Создайте экземпляр сервера печати и объект очереди печати.  
  
4.  Вызовите метод, указав имя задания, файл для печати и флаг <xref:System.Boolean>, указывающий, является ли принтер принтером XPSDrv.  
  
 В примере, который приведен ниже, показано, как выполнить пакетную печать всех файлов [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] каталога.  Хотя приложение предлагает пользователю указать каталог, метод с тремя параметрами <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29> не требует [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].  Метод можно использовать в любом пути кода, где присутствуют имя файла [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] и путь, который можно ему передать.  
  
 Перегрузка метода <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29> с тремя параметрами для <xref:System.Printing.PrintQueue.AddJob%2A> должна выполняться в однопотоковом подразделении, когда параметр <xref:System.Boolean> принимает значение `false`, которое он должен принимать при использовании принтера не XPSDrv.  Однако по умолчанию состояние подразделения [!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)] является многопотоковым.  Это значение по умолчанию должно быть отменено, поскольку в примере предполагается, что используется принтер не XPSDrv.  
  
 Существует два способа, чтобы изменить значение по умолчанию.  Одним из них является простое добавление <xref:System.STAThreadAttribute> \(то есть "`[System.STAThreadAttribute()]`"\) непосредственно над первой строкой метода `Main` приложения \(обычно, "`static void Main(string[] args)`"\).  Однако многие приложения требуют, чтобы метод `Main` имел состояние многопотокового подразделения, поэтому существует второй метод: помещение вызова метода <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29> в отдельный поток, состояние подразделения которого установлено значение <xref:System.Threading.ApartmentState>, с методом <xref:System.Threading.Thread.SetApartmentState%2A>.  В примере, который приведен ниже, используется этот второй метод.  
  
 Соответственно, пример начинается с создания экземпляра объекта <xref:System.Threading.Thread> и передачи его методу **PrintXPS** как параметра <xref:System.Threading.ThreadStart>.  \(Метод **PrintXPS** определяется позже в этом примере\). Далее поток устанавливается в однопотоковое подразделение.  Новый поток запускает только оставшийся код метода `Main`.  
  
 Суть примера содержится в методе `static` **BatchXPSPrinter.PrintXPS**.  После создания сервера печати и очереди метод предлагает пользователю выбрать каталог, содержащий файлы [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)].  После проверки существования каталога и наличия в нем файлов xps метод добавляет каждый такой файл в очередь печати.  Предполагается, что принтер не поддерживает XPSDrv, поэтому мы передаем значение `false` последнему параметру метода <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29>.  По этой причине, метод будет проверять разметку [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] в файле перед попыткой преобразования его в язык описания страниц принтера.  Если проверка завершилась неудачно, вызывается исключение.  Пример кода получит исключение, уведомит о нем пользователя и перейдет к обработке следующего файла [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)].  
  
 [!code-csharp[BatchPrintXPSFiles#BatchPrintXPSFiles](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BatchPrintXPSFiles/CSharp/Program.cs#batchprintxpsfiles)]
 [!code-vb[BatchPrintXPSFiles#BatchPrintXPSFiles](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BatchPrintXPSFiles/visualbasic/program.vb#batchprintxpsfiles)]  
  
 При использовании принтера XPSDrv можно установить для последнего параметра значение `true`.  В этом случае, поскольку [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] является языком описания страницы принтера, метод отправит файл на принтер без проверки его или преобразования в другой язык описания страниц.  Если имеются сомнения во время разработки приложения, что оно будет использовать принтер XPSDrv, можно изменить приложение таким образом, чтобы оно считывало свойство <xref:System.Printing.PrintQueue.IsXpsDevice%2A> и выполняло переход в соответствии с тем, что будет обнаружено.  
  
 Поскольку будет существовать изначально несколько принтеров XPSDrv, доступных сразу после выпуска [!INCLUDE[TLA#tla_winvista](../../../../includes/tlasharptla-winvista-md.md)] и [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)], может потребоваться маскировка принтера не XPSDrv в качестве принтера XPSDrv.  Для этого следует добавить файл Pipelineconfig.xml в список файлов в следующем разделе реестра компьютера, на котором запущено приложение:  
  
 HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\Control\\Print\\Environments\\Windows NT x86\\Drivers\\Version\-3\\*\<PseudoXPSPrinter\>*\\DependentFiles  
  
 где *\<PseudoXPSPrinter\>* — любая очередь печати.  Затем необходимо перезагрузить компьютер.  
  
 Эта маскировка позволит передать значение `true` в качестве последнего параметра метода <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29> без вызова исключения, но поскольку *\<PseudoXPSPrinter\>* является не действительным принтером XPSDrv, будет печататься только мусор.  
  
 **Примечание**. Для упрощения, в примере выше используется наличие расширения xps в качестве проверки того, что файлом является [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)].  Однако файлам [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] нет необходимости иметь это расширение.  [isXPS.exe \(средство проверки соответствия isXPS\)](../Topic/isXPS.exe%20\(isXPS%20Conformance%20Tool\).md) является одним из способов проверки файла на соответствие [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)].  
  
## См. также  
 <xref:System.Printing.PrintQueue>   
 <xref:System.Printing.PrintQueue.AddJob%2A>   
 <xref:System.Threading.ApartmentState>   
 <xref:System.STAThreadAttribute>   
 [XPS](http://www.microsoft.com/xps)   
 [Printing an XPS Document](http://msdn.microsoft.com/ru-ru/849555c8-0c4e-48c0-86bc-a5494c69b36c)   
 [Managed and Unmanaged Threading](http://msdn.microsoft.com/ru-ru/db425c20-4b2f-4433-bf96-76071c7881e5)   
 [isXPS.exe \(средство проверки соответствия isXPS\)](../Topic/isXPS.exe%20\(isXPS%20Conformance%20Tool\).md)   
 [Документы в WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)   
 [Общие сведения о печати](../../../../docs/framework/wpf/advanced/printing-overview.md)