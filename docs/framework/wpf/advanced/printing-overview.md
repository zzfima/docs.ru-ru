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
ms.openlocfilehash: 902d51341850b5245b9fa6410b1954b2ab373bbc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187202"
---
# <a name="printing-overview"></a>Общие сведения о печати
С помощью Microsoft .NET Framework разработчики приложений, использующие Windows Presentation Foundation (WPF), имеют новый богатый набор ABI управления системами печати и печати. С Windows Vista некоторые из этих усовершенствований системы печати также доступны разработчикам, создающих приложения Windows Forms, и разработчикам, использующим неуправляемый код. В основе этой новой функциональности лежит новый формат файлов XML Paper Specification (XPS) и путь печати XPS.  
  
 Эта тема описана в следующих разделах.  
  
<a name="introduction_to_XPS"></a>
## <a name="about-xps"></a>О формате XPS  
 XPS — это электронный формат документа, формат файла катушки и язык описания страницы. Это открытый формат документов, который использует XML, Открытые конвенции упаковки (OPC) и другие отраслевые стандарты для создания кросс-платформенных документов. XPS упрощает процесс создания, совместного использования, печати, просмотра и архивирования цифровых документов. Для получения дополнительной информации о XPS, [см.](/windows/desktop/printdocs/documents)  
  
 Несколько методов печати контента на основе XPS с использованием WPF демонстрируются в [программно-печатных xPS Files.](how-to-programmatically-print-xps-files.md) Ссылки на эти примеры могут оказаться полезными при просмотре содержимого этого раздела. (Неуправляемые разработчики кода должны видеть документацию для [функции MXDC_ESCAPE.](/windows/desktop/printdocs/mxdc-escape) Разработчики Windows Forms должны использовать <xref:System.Drawing.Printing> API в пространстве имен, который не поддерживает полный путь печати XPS, но поддерживает гибридный путь печати GDI-to-XPS. См. раздел **Архитектура способа печати** ниже.)  
  
<a name="XPS_print_path_intro"></a>
## <a name="xps-print-path"></a>Способ печати XPS  
 Путь печати Бумаги XML Paper (XPS) — это новая функция Windows, которая переопределяет способы обработки печати в приложениях Windows. Потому что XPS может заменить язык представления документов (например, RTF), формат печатной спулера (например, WMF) и язык описания страницы (например, PCL или Postscript); новый путь печати поддерживает формат XPS от публикации приложений до окончательной обработки в драйвере печати или устройстве.  
  
 Путь печати XPS построен на модели драйвера принтера XPS (XPSDrv), которая предоставляет несколько преимуществ для разработчиков, таких как "то, что вы видите, это то, что вы получаете" (WYSIWYG) печать, улучшенная поддержка цвета, и значительно улучшенная производительность печати. (Для получения дополнительной информации о [Windows Driver Kit documentation](/windows-hardware/drivers/)XPSDrv, см.  
  
 Работа печатного спулера для документов XPS по существу такая же, как и в предыдущих версиях Windows. Тем не менее, он был расширен для поддержки пути печати XPS в дополнение к существующему пути печати GDI. Новый путь печати, по-родному, потребляет файл катушки XPS. В то время как драйверы принтера в пользовательском режиме, написанные для предыдущих версий Windows, будут продолжать работать, для использования пути печати XPS требуется драйвер принтера XPS (XPSDrv).  
  
 Преимущества пути печати XPS значительны и включают в себя:  
  
- Поддержка печати WYSIWYG  
  
- Встроенная поддержка дополнительных цветовых профилей, включая 32 бита на канал (bpc), CMYK, именованные цвета, n-краски и встроенную поддержку прозрачности и градиентов.  
  
- Улучшенная производительность печати как для приложений на основе .NET, так и для приложений, основанных на Win32.  
  
- Отраслевой стандартный формат XPS.  
  
 Для базовых сценариев печати доступен простой и интуитивно понятный API с одной точкой входа для пользовательского интерфейса, конфигурации и представления задания. Для расширенных сценариев добавлена дополнительная поддержка настройки [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] (или не [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] вообще), синхронной или асинхронной печати и возможностей пакетной печати. Оба параметра обеспечивают поддержку печати в режиме полного или частичного доверия.  
  
 XPS был разработан с размножесь в виду. С помощью платформы расширяемости функции и возможности могут быть добавлены в XPS модульным образом. Функции расширяемости включают следующее.  
  
- Схема печати. Общая схема обновляется регулярно и позволяет быстро расширять возможности устройства. (См. **PrintTicket и PrintCapabilities** ниже.)  
  
- Расширяемый конвейер фильтра. Конвейер фильтров XPS printer (XPSDrv) был разработан для обеспечения как прямой, так и масштабируемой печати документов XPS. Для получения дополнительной [XPSDrv Printer Drivers](/windows-hardware/drivers/print/xpsdrv-printer-drivers)информации см.
  
### <a name="print-path-architecture"></a>Архитектура способа печати  
 В то время как приложения Win32 и .NET Framework поддерживают XPS, приложения Win32 и Windows Forms используют преобразование GDI для преобразования XPS для создания отформатированных XPS содержимого для драйвера принтера XPS (XPSDrv). Эти приложения не требуются для использования пути печати XPS и могут продолжать использовать расширенную печать Metafile (EMF). Тем не менее, большинство функций и усовершенствований XPS доступны только для приложений, ориентированных на путь печати XPS.  
  
 Для обеспечения использования принтеров на основе XPSDrv приложениями Win32 и Windows Forms драйвер принтера XPS (XPSDrv) поддерживает преобразование GDI в формат XPS. Модель XPSDrv также предоставляет преобразователь для формата XPS в формат GDI, чтобы приложения Win32 могли печатать документы XPS. Для приложений WPF преобразование XPS в формат <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> GDI осуществляется автоматически методами <xref:System.Windows.Xps.XpsDocumentWriter> и методами класса всякий раз, когда в целевой очереди печати операции записи нет драйвера XPSDrv. (Приложения Windows Forms не могут печатать документы XPS.)  
  
 Следующая иллюстрация изображает подсистему печати и определяет части, предоставляемые корпорацией Майкрософт, а также части, определенные поставщиками программного и аппаратного обеспечения:  
  
 ![На скриншоте показана система печати XPS.](./media/printing-overview/xml-paper-specification-print-system.png)  
  
### <a name="basic-xps-printing"></a>Базовая печать XPS  
 WPF определяет как базовый, так и продвинутый API. Для тех приложений, которые не требуют обширной настройки печати или доступа к полному набору функций XPS, доступна базовая поддержка печати. Базовая поддержка печати предоставляется с помощью элемента управления диалогового окна печати, который требует минимальной конфигурации и представляет знакомый [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. Многие функции XPS доступны с помощью этой упрощенной модели печати.  
  
#### <a name="printdialog"></a>PrintDialog  
 Элемент <xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType> управления обеспечивает единую [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]точку входа для, конфигурации и представления задания XPS. Сведения о том, как создать и использовать элемент управления, см. в разделе [Вызов диалогового окна печати](how-to-invoke-a-print-dialog.md).  
  
### <a name="advanced-xps-printing"></a>Расширенная печать XPS  
 Для доступа к полному набору функций XPS необходимо использовать расширенный API печати. Ниже более подробно описаны некоторые соответствующие API. Для получения полного списка AAP-путей <xref:System.Windows.Xps> печати <xref:System.Printing> XPS см.  
  
#### <a name="printticket-and-printcapabilities"></a>PrintTicket и PrintCapabilities  
 <xref:System.Printing.PrintTicket> Классы <xref:System.Printing.PrintCapabilities> являются основой передовых функций XPS. Оба типа объектов представляют xML отформатированные структуры типоориентированных функций, таких как сопоставление, двусторонняя печать, скрепление и т.д. Эти структуры определяются схемой печати. Объект <xref:System.Printing.PrintTicket> указывает принтеру, как обрабатывать задание печати. Класс <xref:System.Printing.PrintCapabilities> определяет возможности принтера. Запрашивая возможности принтера, можно создать <xref:System.Printing.PrintTicket>, который использует все преимущества поддерживаемых возможностей принтера. Аналогичным образом можно избежать неподдерживаемых функций.  
  
 В следующем примере демонстрируется, как запрашивать <xref:System.Printing.PrintCapabilities> принтера и создавать <xref:System.Printing.PrintTicket> с помощью кода.  
  
 [!code-cpp[xpscreate#PrinterCapabilities](~/samples/snippets/cpp/VS_Snippets_Wpf/XpsCreate/CPP/XpsCreate.cpp#printercapabilities)]
 [!code-csharp[xpscreate#PrinterCapabilities](~/samples/snippets/csharp/VS_Snippets_Wpf/XpsCreate/CSharp/XpsCreate.cs#printercapabilities)]
 [!code-vb[xpscreate#PrinterCapabilities](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XpsCreate/visualbasic/xpscreate.vb#printercapabilities)]  
  
#### <a name="printserver-and-printqueue"></a>PrintServer и PrintQueue  
 Класс <xref:System.Printing.PrintServer> представляет сетевой сервер печати, а класс <xref:System.Printing.PrintQueue> представляет принтер и связанную с ним очередь выходных заданий. Вместе эти AA позволяют эффективно едать работу по печати сервера. Объект <xref:System.Printing.PrintServer> или один из его производных классов используется для управления <xref:System.Printing.PrintQueue>. Метод <xref:System.Printing.PrintQueue.AddJob%2A> используется для вставки нового задания печати в очередь.  
  
 В следующем примере демонстрируется создание <xref:System.Printing.LocalPrintServer> и доступ к его <xref:System.Printing.PrintQueue> по умолчанию с помощью кода.  
  
 [!code-csharp[xpsprint#PrintQueueSnip](~/samples/snippets/csharp/VS_Snippets_Wpf/XpsPrint/CSharp/XpsPrintHelper.cs#printqueuesnip)]
 [!code-vb[xpsprint#PrintQueueSnip](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XpsPrint/visualbasic/xpsprinthelper.vb#printqueuesnip)]  
  
#### <a name="xpsdocumentwriter"></a>XpsDocumentWriter  
 An <xref:System.Windows.Xps.XpsDocumentWriter>, с <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> его <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> много и методы, используется для <xref:System.Printing.PrintQueue>записи документов XPS в . Например, <xref:System.Windows.Xps.XpsDocumentWriter.Write%28System.Windows.Documents.FixedPage%2CSystem.Printing.PrintTicket%29> метод используется для вывода документа <xref:System.Printing.PrintTicket> XPS и синхронно. Метод <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%28System.Windows.Documents.FixedDocument%2CSystem.Printing.PrintTicket%29> используется для вывода документа XPS и <xref:System.Printing.PrintTicket> асинхронно.  
  
 В следующем примере показывается, как создать <xref:System.Windows.Xps.XpsDocumentWriter> с помощью кода.  
  
 [!code-csharp[XpsPrint#PrintQueueSnip](~/samples/snippets/csharp/VS_Snippets_Wpf/XpsPrint/CSharp/XpsPrintHelper.cs#printqueuesnip)]
 [!code-vb[XpsPrint#PrintQueueSnip](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XpsPrint/visualbasic/xpsprinthelper.vb#printqueuesnip)]  
  
 Методы <xref:System.Printing.PrintQueue.AddJob%2A> также предоставляют способы печати. Дополнительные сведения см. в разделе [Печать XPS-файлов программным способом](how-to-programmatically-print-xps-files.md). .  
  
<a name="GDI_Print_Path_intro"></a>
## <a name="gdi-print-path"></a>Способ печати GDI  
 В то время как приложения WPF нативно поддерживают путь печати XPS, приложения Win32 и Windows Forms также могут воспользоваться некоторыми функциями XPS. Драйвер принтера XPS (XPSDrv) может конвертировать выход на основе GDI в формат XPS. Для расширенных сценариев пользовательская конверсия содержимого поддерживается с помощью [преобразователя документов Microsoft XPS (MXDC).](/windows/desktop/printdocs/microsoft-xps-document-converter--mxdc-) Аналогичным образом, приложения WPF могут также выходить на <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> путь <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> печати GDI, вызывая один из методов <xref:System.Windows.Xps.XpsDocumentWriter> класса и обозначая принтер non-XpsDrv в качестве целевой очереди печати.  

Для приложений, не требующих функциональности или поддержки XPS, текущий путь печати GDI остается неизменным.  
  
- Дополнительные справочные материалы о пути печати GDI и различных вариантах преобразования XPS можно получить в [Microsoft XPS Document Converter (MXDC)](/windows/desktop/printdocs/microsoft-xps-document-converter--mxdc-) и [Драйверах принтеров XPSDrv.](/windows-hardware/drivers/print/xpsdrv-printer-drivers)  
  
<a name="XPS_Driver_Model_intro"></a>
## <a name="xpsdrv-driver-model"></a>Модель драйвера XPSDrv  
 Путь печати XPS повышает эффективность spooler, используя XPS в качестве родного формата катушки печати при печати на принтер ес с поддержкой XPS или драйвера. Упрощенный процесс спулинга устраняет необходимость создания промежуточного файла катушки, например файла данных EMF, до того, как документ будет спущен на пул. Благодаря меньшим размерам файла катушки, путь печати XPS может уменьшить сетевой трафик и улучшить производительность печати.  
  
 EMF — это закрытый формат, который представляет выход приложений как серию вызовов в GDI для оказания услуг. В отличие от EMF, формат spool XPS представляет собой фактический документ, не требуя дальнейшей интерпретации при выходе на основе XPS драйвер принтера (XPSDrv). Драйверы могут работать непосредственно с данными в этом формате. Эта возможность исключает преобразования данных и цветового пространства, необходимые при использовании файлов EMF и GDI-драйверов печати.  
  
 Размеры файлов Spool обычно уменьшаются при использовании документов XPS, ориентированных на драйвер принтера XPS (XPSDrv) по сравнению с их эквивалентами EMF; однако есть исключения:  
  
- Очень сложная, многоуровневая или неэффективно созданная векторная графика может быть больше, чем растровая версия того же графического объекта.  
  
- Для отображения экрана XPS-файлы внедряют шрифты устройства, а также шрифты на компьютере; тогда как файлы очереди GDI не внедряют шрифты устройства. Но оба типа шрифтов имеют поднаборы (см. ниже), и драйверы принтера могут удалить шрифты устройства до передачи файла на принтер.  
  
 Уменьшение размера очереди выполняется посредством нескольких механизмов.  
  
- **Поднабор шрифта**. В файле XPS хранятся только символы, используемые в настоящем документе.  
  
- **Поддержка расширенной графики**. Поддержка родной прозрачностью и градиентными примитивами позволяет избежать rasterization содержания в документе XPS.  
  
- **Идентификация общих ресурсов**. Ресурсы, которые используются несколько раз (например, изображение, представляющее эмблему организации), рассматриваются как общие ресурсы и загружаются только один раз.  
  
- **Сжатие ЗИП**. Во всех документах XPS используется сжатие зип.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Controls.PrintDialog>
- <xref:System.Windows.Xps.XpsDocumentWriter>
- <xref:System.Windows.Xps.Packaging.XpsDocument>
- <xref:System.Printing.PrintTicket>
- <xref:System.Printing.PrintCapabilities>
- <xref:System.Printing.PrintServer>
- <xref:System.Printing.PrintQueue>
- [Как-к темам](printing-how-to-topics.md)
- [Документы в WPF](documents-in-wpf.md)
- [XPS-документы](/windows/desktop/printdocs/documents)
- [Сериализация и хранение документов](document-serialization-and-storage.md)
- [Преобразователь документов Microsoft XPS (MXDC)](/windows/desktop/printdocs/microsoft-xps-document-converter--mxdc-)
