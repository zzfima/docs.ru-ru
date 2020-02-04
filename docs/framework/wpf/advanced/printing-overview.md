---
title: Общие сведения о печати
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- print path [WPF], XPS
- printers [WPF], XPSDrv-based
- printing [WPF]
- PrintQueue class PrintServer class [WPF]
- XML Paper Specification (XPS) file format
- XPS (XML Paper Specification) file format
- XPSDrv-based printers
- GDI print path [WPF]
ms.assetid: 0de8ac41-9aa6-413d-a121-7aa6f41539b1
ms.openlocfilehash: de9f4b5c0a817d010c7510395b4e5c09ed0a9865
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794281"
---
# <a name="printing-overview"></a>Общие сведения о печати
С Microsoft .NET Framework разработчики приложений, использующие Windows Presentation Foundation (WPF), имеют богатый новый набор API-интерфейсов для управления печатью и системой печати. В Windows Vista некоторые из этих усовершенствований системы печати также доступны разработчикам, создающим Windows Forms приложений и разработчиков, использующих неуправляемый код. Основой этой новой функциональности является новый формат XPS-файла и путь печати XPS.  
  
 В этом разделе содержатся следующие подразделы:  
  
<a name="introduction_to_XPS"></a>   
## <a name="about-xps"></a>О формате XPS  
 XPS — это формат электронного документа, формат файла очереди и язык описания страницы. Это формат открытого документа, который использует XML, соглашения об упаковке и другие отраслевые стандарты для создания кросс-платформенных документов. XPS упрощает процесс создания, совместного использования, печати, просмотра и архивации цифровых документов. Дополнительные сведения о XPS см. в статье [XPS-документы](/windows/desktop/printdocs/documents).  
  
 Некоторые методы печати содержимого на основе XPS с помощью WPF демонстрируются при [программной печати XPS-файлов](how-to-programmatically-print-xps-files.md). Ссылки на эти примеры могут оказаться полезными при просмотре содержимого этого раздела. (Разработчикам неуправляемого кода следует ознакомиться с документацией по [функции MXDC_ESCAPE](/windows/desktop/printdocs/mxdc-escape). Windows Forms разработчики должны использовать API в пространстве имен <xref:System.Drawing.Printing>, который не поддерживает полный путь печати XPS, но поддерживает гибридный путь печати с помощью GDI в XPS. См. раздел **Архитектура способа печати** ниже.)  
  
<a name="XPS_print_path_intro"></a>   
## <a name="xps-print-path"></a>Способ печати XPS  
 Путь печати в формате XPS — это новая функция Windows, которая переопределяет способ обработки печати в приложениях Windows. Так как XPS может заменить язык представления документов (например, RTF), формат диспетчера очереди печати (например, WMF) и язык описания страницы (например, PCL или PostScript); новый способ печати сохраняет формат XPS от публикации приложения до финальной обработки в драйвере или устройстве печати.  
  
 Путь печати XPS основан на модели драйвера принтера XPS (XPSDrv), предоставляющей несколько преимуществ для разработчиков, таких как «то, что вы видите, это то, что вы получаете: «(WYSIWYG), улучшенная поддержка цвета и значительно улучшена производительность печати». (Дополнительные сведения о XPSDrv см. в [документации к пакету драйверов Windows](/windows-hardware/drivers/).)  
  
 Работа диспетчера очереди печати для документов XPS в основном такая же, как и в предыдущих версиях Windows. Однако он был усовершенствован для поддержки пути печати XPS в дополнение к существующему пути печати GDI. Новый способ печати изначально использует файл очереди XPS. Хотя драйверы принтера пользовательского режима, написанные для предыдущих версий Windows, продолжат работать, для использования пути печати XPS требуется драйвер принтера XPS (XPSDrv).  
  
 Преимущества пути печати XPS существенны и включают:  
  
- Поддержка печати в режиме WYSIWYG  
  
- Встроенная поддержка дополнительных цветовых профилей, включая 32 бита на канал (bpc), CMYK, именованные цвета, n-краски и встроенную поддержку прозрачности и градиентов.  
  
- Улучшенная производительность печати как для .NET Framework, так и для приложений на основе Win32.  
  
- Стандартный промышленный формат XPS.  
  
 Для основных сценариев печати доступен простой и интуитивно понятный API с одной точкой входа для пользовательского интерфейса, конфигурации и отправки задания. Для расширенных сценариев добавлена дополнительная поддержка настройки [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] (или не [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] вообще), синхронной или асинхронной печати и возможностей пакетной печати. Оба параметра обеспечивают поддержку печати в режиме полного или частичного доверия.  
  
 Система XPS была разработана с учетом возможностей расширения. С помощью платформы расширяемости функции и возможности можно добавлять в XPS модульным способом. Функции расширяемости включают следующее.  
  
- Схема печати. Общая схема обновляется регулярно и позволяет быстро расширять возможности устройства. (См. **PrintTicket и PrintCapabilities** ниже.)  
  
- Расширяемый конвейер фильтра. Конвейер фильтра драйвера принтера XPS (XPSDrv) был разработан так, чтобы обеспечить как прямую, так и масштабируемую печать документов XPS. Дополнительные сведения см. в разделе [драйверы принтера XPSDrv](/windows-hardware/drivers/print/xpsdrv-printer-drivers). 
  
### <a name="print-path-architecture"></a>Архитектура способа печати  
 Хотя приложения Win32 и .NET Framework поддерживают XPS, приложения Win32 и Windows Forms используют преобразование GDI в XPS для создания содержимого в формате XPS для драйвера принтера XPS (XPSDrv). Эти приложения не обязаны использовать путь печати XPS и могут продолжать использовать распечатку на основе расширенного метафайла (EMF). Однако большинство функций и улучшений XPS доступны только для приложений, предназначенных для печати XPS.  
  
 Чтобы включить использование принтеров на основе XPSDrv в приложениях Win32 и Windows Forms, драйвер принтера XPS (XPSDrv) поддерживает преобразование из GDI в формат XPS. Модель XPSDrv также предоставляет конвертер для формата XPS в GDI, чтобы приложения Win32 могли печатать документы XPS. Для приложений WPF преобразование XPS в формат GDI выполняется автоматически с помощью <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> и <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> методов класса <xref:System.Windows.Xps.XpsDocumentWriter> каждый раз, когда в целевой очереди печати операции записи нет драйвера XPSDrv. (Windows Forms приложения не могут печатать документы XPS.)  
  
 На следующем рисунке показана подсистема печати и определены части, предоставляемые корпорацией Майкрософт, а также части, определяемые поставщиками программного обеспечения и оборудования.  
  
 ![На снимке экрана показана система печати XPS.](./media/printing-overview/xml-paper-specification-print-system.png)  
  
### <a name="basic-xps-printing"></a>Базовая печать XPS  
 WPF определяет как базовый, так и расширенный API. Для приложений, которые не нуждаются в расширенной настройке печати или доступе к полному набору функций XPS, доступна базовая поддержка печати. Базовая поддержка печати предоставляется с помощью элемента управления диалогового окна печати, который требует минимальной конфигурации и представляет знакомый [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. При использовании этой упрощенной модели печати доступны многие функции XPS.  
  
#### <a name="printdialog"></a>PrintDialog  
 Элемент управления <xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType> предоставляет единую точку входа для отправки заданий [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], конфигурации и XPS. Сведения о том, как создать и использовать элемент управления, см. в разделе [Вызов диалогового окна печати](how-to-invoke-a-print-dialog.md).  
  
### <a name="advanced-xps-printing"></a>Расширенная печать XPS  
 Для доступа к полному набору функций XPS необходимо использовать расширенный API печати. Несколько соответствующих API подробно описаны ниже. Полный список API-интерфейсов для печати в формате XPS см. в разделе ссылки на пространства имен <xref:System.Windows.Xps> и <xref:System.Printing>.  
  
#### <a name="printticket-and-printcapabilities"></a>PrintTicket и PrintCapabilities  
 Классы <xref:System.Printing.PrintTicket> и <xref:System.Printing.PrintCapabilities> являются основой расширенных функций XPS. Оба типа объектов являются структурами, ориентированными на печать в формате XML, такими как параметры сортировки, двусторонняя печать, сшивание и т. д. Эти структуры определяются схемой печати. Объект <xref:System.Printing.PrintTicket> указывает принтеру, как обрабатывать задание печати. Класс <xref:System.Printing.PrintCapabilities> определяет возможности принтера. Запрашивая возможности принтера, можно создать <xref:System.Printing.PrintTicket>, который использует все преимущества поддерживаемых возможностей принтера. Аналогичным образом можно избежать неподдерживаемых функций.  
  
 В следующем примере демонстрируется, как запрашивать <xref:System.Printing.PrintCapabilities> принтера и создавать <xref:System.Printing.PrintTicket> с помощью кода.  
  
 [!code-cpp[xpscreate#PrinterCapabilities](~/samples/snippets/cpp/VS_Snippets_Wpf/XpsCreate/CPP/XpsCreate.cpp#printercapabilities)]
 [!code-csharp[xpscreate#PrinterCapabilities](~/samples/snippets/csharp/VS_Snippets_Wpf/XpsCreate/CSharp/XpsCreate.cs#printercapabilities)]
 [!code-vb[xpscreate#PrinterCapabilities](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XpsCreate/visualbasic/xpscreate.vb#printercapabilities)]  
  
#### <a name="printserver-and-printqueue"></a>PrintServer и PrintQueue  
 Класс <xref:System.Printing.PrintServer> представляет сетевой сервер печати, а класс <xref:System.Printing.PrintQueue> представляет принтер и связанную с ним очередь выходных заданий. Вместе эти интерфейсы API позволяют выполнять расширенное управление заданиями печати сервера. Объект <xref:System.Printing.PrintServer> или один из его производных классов используется для управления <xref:System.Printing.PrintQueue>. Метод <xref:System.Printing.PrintQueue.AddJob%2A> используется для вставки нового задания печати в очередь.  
  
 В следующем примере демонстрируется создание <xref:System.Printing.LocalPrintServer> и доступ к его <xref:System.Printing.PrintQueue> по умолчанию с помощью кода.  
  
 [!code-csharp[xpsprint#PrintQueueSnip](~/samples/snippets/csharp/VS_Snippets_Wpf/XpsPrint/CSharp/XpsPrintHelper.cs#printqueuesnip)]
 [!code-vb[xpsprint#PrintQueueSnip](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XpsPrint/visualbasic/xpsprinthelper.vb#printqueuesnip)]  
  
#### <a name="xpsdocumentwriter"></a>XpsDocumentWriter  
 <xref:System.Windows.Xps.XpsDocumentWriter>с множеством методов <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> и <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> используется для записи документов XPS в <xref:System.Printing.PrintQueue>. Например, метод <xref:System.Windows.Xps.XpsDocumentWriter.Write%28System.Windows.Documents.FixedPage%2CSystem.Printing.PrintTicket%29> используется для вывода документа XPS и <xref:System.Printing.PrintTicket> синхронно. Метод <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%28System.Windows.Documents.FixedDocument%2CSystem.Printing.PrintTicket%29> используется для вывода документа XPS и <xref:System.Printing.PrintTicket> асинхронно.  
  
 В следующем примере показывается, как создать <xref:System.Windows.Xps.XpsDocumentWriter> с помощью кода.  
  
 [!code-csharp[XpsPrint#PrintQueueSnip](~/samples/snippets/csharp/VS_Snippets_Wpf/XpsPrint/CSharp/XpsPrintHelper.cs#printqueuesnip)]
 [!code-vb[XpsPrint#PrintQueueSnip](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XpsPrint/visualbasic/xpsprinthelper.vb#printqueuesnip)]  
  
 Методы <xref:System.Printing.PrintQueue.AddJob%2A> также предоставляют способы печати. Дополнительные сведения см. в разделе [Печать XPS-файлов программным способом](how-to-programmatically-print-xps-files.md). .  
  
<a name="GDI_Print_Path_intro"></a>   
## <a name="gdi-print-path"></a>Способ печати GDI  
 Хотя приложения WPF изначально поддерживают путь печати XPS, приложения Win32 и Windows Forms также могут воспользоваться преимуществами некоторых функций XPS. Драйвер принтера XPS (XPSDrv) может преобразовывать выходные данные на основе GDI в формат XPS. Для расширенных сценариев поддерживается настраиваемое преобразование содержимого с помощью [конвертера документов XPS (Майкрософт) (мксдк)](/windows/desktop/printdocs/microsoft-xps-document-converter--mxdc-). Аналогичным образом приложения WPF также могут выводить данные в путь печати GDI, вызывая один из методов <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> или <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> класса <xref:System.Windows.Xps.XpsDocumentWriter> и обозначающий принтер без XpsDrv в качестве целевой очереди печати.  

Для приложений, не требующих функциональности или поддержки XPS, текущий путь печати GDI остается неизменным.  
  
- Дополнительные справочные материалы по способу печати GDI и различным параметрам преобразования XPS см. в [статье конвертеры документов XPS (мксдк)](/windows/desktop/printdocs/microsoft-xps-document-converter--mxdc-) и [драйверы принтера XPSDrv](/windows-hardware/drivers/print/xpsdrv-printer-drivers).  
  
<a name="XPS_Driver_Model_intro"></a>   
## <a name="xpsdrv-driver-model"></a>Модель драйвера XPSDrv  
 Путь печати XPS повышает эффективность очереди печати за счет использования XPS в качестве собственного формата очереди печати при печати на принтере или драйвере, поддерживающем XPS. Упрощенный процесс буферизации устраняет необходимость создания промежуточного файла буферизации, например файла данных EMF, перед помещением в очередь документа. Благодаря уменьшению размеров файлов очереди печать XPS может уменьшить сетевой трафик и повысить производительность печати.  
  
 EMF — это закрытый формат, представляющий выходные данные приложения в виде последовательности вызовов GDI для служб отрисовки. В отличие от EMF, формат буферизации XPS представляет фактический документ без необходимости дальнейшей интерпретации при выходе в драйвер принтера на основе XPS (XPSDrv). Драйверы могут работать непосредственно с данными в этом формате. Эта возможность устраняет необходимость преобразования данных и цветового пространства при использовании файлов EMF и драйверов печати на основе GDI.  
  
 Размеры файлов в очереди обычно уменьшаются при использовании документов XPS, предназначенных для драйвера принтера XPS (XPSDrv), по сравнению с их эквивалентами EMF; Однако существуют исключения.  
  
- Очень сложная, многоуровневая или неэффективно созданная векторная графика может быть больше, чем растровая версия того же графического объекта.  
  
- Для отображения экрана XPS-файлы внедряют шрифты устройства, а также шрифты на компьютере; тогда как файлы очереди GDI не внедряют шрифты устройства. Но оба типа шрифтов имеют поднаборы (см. ниже), и драйверы принтера могут удалить шрифты устройства до передачи файла на принтер.  
  
 Уменьшение размера очереди выполняется посредством нескольких механизмов.  
  
- **Поднабор шрифта**. В XPS-файл будут храниться только символы, используемые в фактическом документе.  
  
- **Поддержка расширенной графики**. Встроенная поддержка прозрачности и примитивов градиента позволяет избежать растрирования содержимого в документе XPS.  
  
- **Идентификация общих ресурсов**. Ресурсы, которые используются несколько раз (например, изображение, представляющее эмблему организации), рассматриваются как общие ресурсы и загружаются только один раз.  
  
- **Сжатие ZIP**. Все документы XPS используют сжатие ZIP.  
  
## <a name="see-also"></a>См. также:

- <xref:System.Windows.Controls.PrintDialog>
- <xref:System.Windows.Xps.XpsDocumentWriter>
- <xref:System.Windows.Xps.Packaging.XpsDocument>
- <xref:System.Printing.PrintTicket>
- <xref:System.Printing.PrintCapabilities>
- <xref:System.Printing.PrintServer>
- <xref:System.Printing.PrintQueue>
- [Практические руководства](printing-how-to-topics.md)
- [Документы в WPF](documents-in-wpf.md)
- [Документы XPS](/windows/desktop/printdocs/documents)
- [Сериализация и хранение документов](document-serialization-and-storage.md)
- [Конвертер документов XPS (Майкрософт) (МКСДК)](/windows/desktop/printdocs/microsoft-xps-document-converter--mxdc-)
