---
title: Как печатать файлы XPS программным способом
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- printing XPS files programmatically [WPF]
- XPS files [WPF], printing programmatically
ms.assetid: 0b1c0a3f-b19e-43d6-bcc9-eb3ec4e555ad
ms.openlocfilehash: cc86a7e7c6a816af37c3d063825ed62583afa78a
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73966990"
---
# <a name="how-to-programmatically-print-xps-files"></a>Как печатать файлы XPS программным способом

Можно использовать одну перегрузку метода <xref:System.Printing.PrintQueue.AddJob%2A> для печати XPS-файлов, не открывая <xref:System.Windows.Controls.PrintDialog> или, в принципе, любого [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].

Вы также можете печатать XPS-файлы с помощью многих методов <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A?displayProperty=nameWithType> и <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A?displayProperty=nameWithType>. Дополнительные сведения см. в разделе [Печать XPS-документа](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771525(v=vs.90)).

Другой способ печати XPS — использование методов <xref:System.Windows.Controls.PrintDialog.PrintDocument%2A?displayProperty=nameWithType> или <xref:System.Windows.Controls.PrintDialog.PrintVisual%2A?displayProperty=nameWithType>. См. раздел [Вызов диалогового окна печати](how-to-invoke-a-print-dialog.md).

## <a name="example"></a>Пример

Ниже приведены основные этапы использования метода <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29> с тремя параметрами. Подробные сведения см. в примере.

1. Определите, является ли принтер принтером XPSDrv. Дополнительные сведения о XPSDrv см. в разделе [Общие сведения о печати](printing-overview.md) .

2. Если принтер не является принтером XPSDrv, задайте однопотоковое подразделение потока.

3. Создайте экземпляр сервера печати и объект очереди печати.

4. Вызовите метод, указав имя задания, файл для печати и флаг <xref:System.Boolean>, указывающий, является ли принтер принтером XPSDrv.

В приведенном ниже примере показано, как выполнить пакетную печать всех XPS-файлов в каталоге. Хотя приложение предлагает пользователю указать каталог, метод <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29> с тремя параметрами не требует [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. Его можно использовать в любом пути кода, где есть имя файла XPS и путь, который можно передать в него.

<xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29>ая перегрузка с тремя параметрами <xref:System.Printing.PrintQueue.AddJob%2A> должна выполняться в одном потоке, когда параметр <xref:System.Boolean> `false`, что необходимо, если используется принтер, отличный от XPSDrv. Однако состояние подразделения по умолчанию для .NET — это несколько потоков. Данное значение по умолчанию должно быть обращено, поскольку в этом примере предполагается, что принтер не является принтером XPSDrv.

Изменить значение по умолчанию можно одним из двух способов. Один из способов — просто добавить <xref:System.STAThreadAttribute> (то есть «`[System.STAThreadAttribute()]`») непосредственно над первой строкой метода `Main` приложения (обычно «`static void Main(string[] args)`»). Однако во многих приложениях требуется, чтобы метод `Main` имел многопотоковое состояние апартамента, поэтому существует второй метод: Установите вызов <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29> в отдельном потоке, состояние апартамента которого установлено в <xref:System.Threading.ApartmentState.STA> с <xref:System.Threading.Thread.SetApartmentState%2A>. В следующем примере используется второй метод.

Соответственно, пример начинается с создания экземпляра объекта <xref:System.Threading.Thread> и передачи ему метода **PrintXPS** в качестве параметра <xref:System.Threading.ThreadStart>. (Метод **PrintXPS** определяется далее в примере.) Далее для потока задается один контейнер потоков. Остальной код метода `Main` начинается с нового потока.

Основу этого примера составляет метод `static` **BatchXPSPrinter.PrintXPS**. После создания сервера печати и очереди метод запрашивает у пользователя каталог, содержащий XPS-файлы. После проверки существования каталога и наличия в нем файлов \*. XPS метод добавляет каждый такой файл в очередь печати. В примере предполагается, что принтер не является XPSDrv, поэтому мы передаем `false` последнему параметру метода <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29>. По этой причине метод проверит разметку XPS в файле перед попыткой преобразовать его в язык описания страницы принтера. Если проверка завершается ошибкой, выдается исключение. В примере кода будет перехвачено исключение, уведомлять пользователя о нем, а затем переходить к обработке следующего XPS-файла.

[!code-csharp[BatchPrintXPSFiles#BatchPrintXPSFiles](~/samples/snippets/csharp/VS_Snippets_Wpf/BatchPrintXPSFiles/CSharp/Program.cs#batchprintxpsfiles)]
[!code-vb[BatchPrintXPSFiles#BatchPrintXPSFiles](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BatchPrintXPSFiles/visualbasic/program.vb#batchprintxpsfiles)]

Если вы используете принтер XPSDrv, последнему параметру можно присвоить значение `true`. В этом случае, поскольку XPS — это язык описания страницы принтера, метод отправит файл на принтер, не проверяя его или не преобразуя в другой язык описания страницы. Если во время разработки вы не уверены, будет ли приложение использовать принтер XPSDrv, можно изменить приложение так, чтобы оно читало <xref:System.Printing.PrintQueue.IsXpsDevice%2A> свойство и ветвь в зависимости от того, что он находит.

Так как в начале выпуска Windows Vista и Microsoft .NET Framework будут доступны неограниченные принтеры XPSDrv, может потребоваться маскировка принтера, отличного от XPSDrv, в качестве принтера XPSDrv. Для этого добавьте файл Pipelineconfig.xml в список файлов в следующем разделе реестра компьютера, на котором выполняется ваше приложение:

HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Print\Environments\Windows NT x86\Drivers\Version-3\\ *\<PseudoXPSPrinter>* \DependentFiles

где  *\<PseudoXPSPrinter>*  — это любая очередь печати. После этого компьютер необходимо перезагрузить.

Эта Маскировка позволяет передавать `true` в качестве последнего параметра <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29> без возникновения исключения, но так как *\<PseudoXPSPrinter >* не является принтером XPSDrv, выводится только мусор.

> [!NOTE]
> Для простоты в примере выше используется присутствие расширения \*. XPS в качестве проверки того, что файл является XPS. Однако файлы XPS не обязательно должны иметь это расширение. [IsXPS. exe (средство соответствия isXPS)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/aa348104(v=vs.100)) — это один из способов тестирования файла на предмет допустимости XPS.

## <a name="see-also"></a>См. также

- <xref:System.Printing.PrintQueue>
- <xref:System.Printing.PrintQueue.AddJob%2A>
- <xref:System.Threading.ApartmentState>
- <xref:System.STAThreadAttribute>
- [Документы XPS](/windows/desktop/printdocs/documents)
- [Печать документа XPS](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771525(v=vs.90))
- [Управляемая и неуправляемая работа с потоками](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/5s8ee185(v=vs.100))
- [isXPS.exe (средство проверки соответствия isXPS)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/aa348104(v=vs.100))
- [Документы в WPF](documents-in-wpf.md)
- [Общие сведения о печати](printing-overview.md)
