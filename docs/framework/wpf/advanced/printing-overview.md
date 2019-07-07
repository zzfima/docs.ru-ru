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
ms.openlocfilehash: 2090c58369ed3c7bda5df1342291001d9550d48d
ms.sourcegitcommit: eaa6d5cd0f4e7189dbe0bd756e9f53508b01989e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2019
ms.locfileid: "67610459"
---
# <a name="printing-overview"></a>Общие сведения о печати
С помощью Microsoft .NET Framework разработчики приложений с помощью Windows Presentation Foundation (WPF) имеют новый богатый набор печати и API-интерфейсы Управление печатью. В [!INCLUDE[TLA#tla_winvista](../../../../includes/tlasharptla-winvista-md.md)] некоторые из усовершенствований управления печатью также доступны для разработчиков, создающих приложения [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)], и разработчиков, использующих неуправляемый код. В основе этой новой функциональности лежит новый формат файла [!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)] и способ печати [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)].  
  
 В этом разделе содержатся следующие подразделы.  
  
<a name="introduction_to_XPS"></a>   
## <a name="about-xps"></a>О формате XPS  
 XPS представляет это формат электронного документа, формат файла очереди и язык описания страницы. Это формат открытого документа, который использует [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)], [!INCLUDE[TLA#tla_opc](../../../../includes/tlasharptla-opc-md.md)] и другие отраслевые стандарты для создания кроссплатформенных документов. XPS упрощает процесс создания, общие, печати, просматривать и архивирования цифровых документов. Дополнительные сведения о XPS см. в разделе [документы XPS](/windows/desktop/printdocs/documents).  
  
 Несколько методов для печати на основе XPS содержимого с помощью [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] демонстрируются в [печатать файлы XPS программным способом](how-to-programmatically-print-xps-files.md). Ссылки на эти примеры могут оказаться полезными при просмотре содержимого этого раздела. (Разработчикам неуправляемого кода следует изучить документацию по [MXDC_ESCAPE функция](/windows/desktop/printdocs/mxdc-escape). Используйте API в Windows Forms разработчики <xref:System.Drawing.Printing> пространства имен, который не поддерживает полный [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] способ печати, но также поддерживает гибридные GDI в XPS путь печати. См. раздел **Архитектура способа печати** ниже.)  
  
<a name="XPS_print_path_intro"></a>   
## <a name="xps-print-path"></a>Способ печати XPS  
 Способ печати XML Paper Specification (XPS) — это новая [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] компонент, который переопределяет способ обработки печати в приложениях Windows. Так как [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] может заменить язык представления документов (например, RTF), формат очереди печати (например WMF) и язык описания страницы (например PCL или Postscript); новый способ печати поддерживает формат XPS от публикации приложения для последней обработки в драйвере печати или устройстве.  
  
 Путь печати XPS построена на основе модели драйвера принтера XPS (XPSDrv), который предоставляет несколько преимуществ для разработчиков, такие как [!INCLUDE[TLA#tla_wys](../../../../includes/tlasharptla-wys-md.md)] печать, улучшенная поддержка цвета и значительно Повышенная производительность печати. (Сведения о XPSDrv см. в разделе [документации Windows Driver Kit](/windows-hardware/drivers/).)  
  
 Операция диспетчера очереди печати XPS-документов, по сути остается таким же, как в предыдущих версиях Windows. Тем не менее, она была усовершенствована для поддержки способа печати XPS дополнение к существующему [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] способ печати. Новый способ печати использует файл очереди печати XPS. Хотя драйверы принтеров пользовательского режима, написанные для предыдущих версий [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] будут продолжать работать, XPS-драйвер принтера (XPSDrv) необходим, чтобы использовать путь печати XPS.  
  
 Преимущества путь печати XPS являются существенными и включают:  
  
- Поддержка печати [!INCLUDE[TLA2#tla_wys](../../../../includes/tla2sharptla-wys-md.md)]  
  
- Встроенная поддержка дополнительных цветовых профилей, включая 32 бита на канал (bpc), CMYK, именованные цвета, n-краски и встроенную поддержку прозрачности и градиентов.  
  
- Повышенная производительность печати для .NET Framework, так и [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] приложений на основе.  
  
- Отраслевой стандартный формат XPS.  
  
 Для базовых сценариев печати доступен простой и интуитивно понятный API с одной точкой входа для пользовательского интерфейса, конфигурации и отправкой задания. Для расширенных сценариев добавлена дополнительная поддержка настройки [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] (или не [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] вообще), синхронной или асинхронной печати и возможностей пакетной печати. Оба параметра обеспечивают поддержку печати в режиме полного или частичного доверия.  
  
 XPS была разработана с учетом возможности расширения. С помощью инфраструктуры расширяемости, функции и возможности могут добавляться в XPS модульным способом. Функции расширяемости включают следующее.  
  
- Схема печати. Общая схема обновляется регулярно и позволяет быстро расширять возможности устройства. (См. **PrintTicket и PrintCapabilities** ниже.)  
  
- Расширяемый конвейер фильтра. Конвейер фильтров XPS принтера драйвер (XPSDrv) был разработан для включения как прямой, так и масштабируемой печати документов XPS. Дополнительные сведения см. в разделе [драйверы принтера XPSDrv](/windows-hardware/drivers/print/xpsdrv-printer-drivers). 
  
### <a name="print-path-architecture"></a>Архитектура способа печати  
 Хотя оба [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] и приложений .NET Framework поддерживают XPS, [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] и приложения Windows Forms используют [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] в XPS преобразования для создания XPS форматированное содержимое для XPS-драйвер принтера (XPSDrv). Эти приложения не требуется для использования путь печати XPS и можно продолжать использовать [!INCLUDE[TLA#tla_emf](../../../../includes/tlasharptla-emf-md.md)] печать на основе. Однако большинство функций XPS и усовершенствования доступны только приложениям, предназначенным путь печати XPS.  
  
 Чтобы включить использование принтеров на основе XPSDrv [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] и приложениях Windows Forms, в XPS-драйвер принтера (XPSDrv) поддерживает преобразование [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] для XPS формат. Модель XPSDrv также предоставляет преобразователь для XPS для [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] формат, чтобы [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] приложений можно напечатать [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] документов. Для [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] приложения, преобразование XPS для [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] формат выполняется автоматически <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> и <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> методы <xref:System.Windows.Xps.XpsDocumentWriter> каждый раз, когда целевой очереди печати операции записи не поддерживает драйвер XPSDrv. (Приложения Windows Forms не удается выполнить печать [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] документов.)  
  
 На следующем рисунке изображена подсистема печати и определяет части, предоставляемые [!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)]и части, определенные поставщиками программного обеспечения и оборудования:  
  
 ![Снимок экрана показывает, что система печати XPS.](./media/printing-overview/xml-paper-specification-print-system.png)  
  
### <a name="basic-xps-printing"></a>Базовая печать XPS  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] определяет как базовый, так и расширенный [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)]. Для приложений, которые не требуют расширенной настройки печати или доступ к компоненту полный XPS задано "и" базовый поддержка печати доступна. Базовая поддержка печати предоставляется с помощью элемента управления диалогового окна печати, который требует минимальной конфигурации и представляет знакомый [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. Многие компоненты XPS входят, доступных с помощью этой упрощенной модели печати.  
  
#### <a name="printdialog"></a>PrintDialog  
 <xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType> Элемент управления предоставляет единую точку входа для [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], конфигурации и отправки заданий XPS. Сведения о том, как создать и использовать элемент управления, см. в разделе [Вызов диалогового окна печати](how-to-invoke-a-print-dialog.md).  
  
### <a name="advanced-xps-printing"></a>Расширенная печать XPS  
 Чтобы получить доступ к полному набору возможностей XPS, необходимо использовать расширенные API печати. Ниже более подробно описаны несколько соответствующего интерфейса API. Полный список XPS способ печати [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)], см. в разделе <xref:System.Windows.Xps> и <xref:System.Printing> ссылки на пространства имен.  
  
#### <a name="printticket-and-printcapabilities"></a>PrintTicket и PrintCapabilities  
 <xref:System.Printing.PrintTicket> И <xref:System.Printing.PrintCapabilities> классы являются основой расширенных функций XPS. Оба типа объектов представляют собой форматированные структуры [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] возможностей печати, таких как сортировка, двусторонняя печать, сшивание и т. д. Эти структуры определяются схемой печати. Объект <xref:System.Printing.PrintTicket> указывает принтеру, как обрабатывать задание печати. Класс <xref:System.Printing.PrintCapabilities> определяет возможности принтера. Запрашивая возможности принтера, можно создать <xref:System.Printing.PrintTicket>, который использует все преимущества поддерживаемых возможностей принтера. Аналогичным образом можно избежать неподдерживаемых функций.  
  
 В следующем примере демонстрируется, как запрашивать <xref:System.Printing.PrintCapabilities> принтера и создавать <xref:System.Printing.PrintTicket> с помощью кода.  
  
 [!code-cpp[xpscreate#PrinterCapabilities](~/samples/snippets/cpp/VS_Snippets_Wpf/XpsCreate/CPP/XpsCreate.cpp#printercapabilities)]
 [!code-csharp[xpscreate#PrinterCapabilities](~/samples/snippets/csharp/VS_Snippets_Wpf/XpsCreate/CSharp/XpsCreate.cs#printercapabilities)]
 [!code-vb[xpscreate#PrinterCapabilities](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XpsCreate/visualbasic/xpscreate.vb#printercapabilities)]  
  
#### <a name="printserver-and-printqueue"></a>PrintServer и PrintQueue  
 Класс <xref:System.Printing.PrintServer> представляет сетевой сервер печати, а класс <xref:System.Printing.PrintQueue> представляет принтер и связанную с ним очередь выходных заданий. Вместе эти [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] обеспечивают возможность расширенного управления заданиями печати сервера. Объект <xref:System.Printing.PrintServer> или один из его производных классов используется для управления <xref:System.Printing.PrintQueue>. Метод <xref:System.Printing.PrintQueue.AddJob%2A> используется для вставки нового задания печати в очередь.  
  
 В следующем примере демонстрируется создание <xref:System.Printing.LocalPrintServer> и доступ к его <xref:System.Printing.PrintQueue> по умолчанию с помощью кода.  
  
 [!code-csharp[xpsprint#PrintQueueSnip](~/samples/snippets/csharp/VS_Snippets_Wpf/XpsPrint/CSharp/XpsPrintHelper.cs#printqueuesnip)]
 [!code-vb[xpsprint#PrintQueueSnip](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XpsPrint/visualbasic/xpsprinthelper.vb#printqueuesnip)]  
  
#### <a name="xpsdocumentwriter"></a>XpsDocumentWriter  
 <xref:System.Windows.Xps.XpsDocumentWriter>, И множество <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> и <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> методы, используемый для записи документов XPS <xref:System.Printing.PrintQueue>. Например <xref:System.Windows.Xps.XpsDocumentWriter.Write%28System.Windows.Documents.FixedPage%2CSystem.Printing.PrintTicket%29> метод используется для вывода документа XPS и <xref:System.Printing.PrintTicket> синхронно. <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%28System.Windows.Documents.FixedDocument%2CSystem.Printing.PrintTicket%29> Метод используется для вывода документа XPS и <xref:System.Printing.PrintTicket> асинхронно.  
  
 В следующем примере показывается, как создать <xref:System.Windows.Xps.XpsDocumentWriter> с помощью кода.  
  
 [!code-csharp[XpsPrint#PrintQueueSnip](~/samples/snippets/csharp/VS_Snippets_Wpf/XpsPrint/CSharp/XpsPrintHelper.cs#printqueuesnip)]
 [!code-vb[XpsPrint#PrintQueueSnip](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XpsPrint/visualbasic/xpsprinthelper.vb#printqueuesnip)]  
  
 Методы <xref:System.Printing.PrintQueue.AddJob%2A> также предоставляют способы печати. Дополнительные сведения см. в разделе [Печать XPS-файлов программным способом](how-to-programmatically-print-xps-files.md). .  
  
<a name="GDI_Print_Path_intro"></a>   
## <a name="gdi-print-path"></a>Способ печати GDI  
 Хотя [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] приложения поддерживают путь печати XPS, [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] и приложений Windows Forms можно также использовать преимущества некоторых функций XPS. XPS-драйвер принтера (XPSDrv) может преобразовать [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] на основе выходных данных в формате XPS. Для более сложных сценариев поддерживается настраиваемое преобразование содержимого с помощью [конвертера документов XPS Microsoft (MXDC)](/windows/desktop/printdocs/microsoft-xps-document-converter--mxdc-). Аналогичным образом [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] приложения могут выполнять вывод [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] способ печати путем вызова одного из <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> или <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> методы <xref:System.Windows.Xps.XpsDocumentWriter> и назначения принтер XpsDrv в качестве целевого объекта очереди печати.  

Для приложений, которые не требуют XPS функциональность или поддержка, текущий [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] способ печати остается неизменным.  
  
- Дополнительные справочные материалы по [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] печать пути и различных параметров преобразования XPS, см. в разделе [конвертера документов XPS Microsoft (MXDC)](/windows/desktop/printdocs/microsoft-xps-document-converter--mxdc-) и [драйверы принтера XPSDrv](/windows-hardware/drivers/print/xpsdrv-printer-drivers).  
  
<a name="XPS_Driver_Model_intro"></a>   
## <a name="xpsdrv-driver-model"></a>Модель драйвера XPSDrv  
 Путь печати XPS повышает эффективность очереди печати с помощью XPS как собственный формат очереди печати при печати в XPS-включить принтер или драйвер. Упрощенный процесс постановки в очередь избавляет от необходимости создания промежуточных файлов очередей, таких как файл данных [!INCLUDE[TLA2#tla_emf](../../../../includes/tla2sharptla-emf-md.md)], до помещения документа в очередь. Благодаря меньшему размеру файла очереди путь печати XPS можно сократить сетевой трафик и повысить производительность печати.  
  
 [!INCLUDE[TLA2#tla_emf](../../../../includes/tla2sharptla-emf-md.md)] является закрытым форматом, представляющим вывод приложения как последовательность вызовов [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] для служб обработки. В отличие от [!INCLUDE[TLA2#tla_emf](../../../../includes/tla2sharptla-emf-md.md)], формат очереди печати XPS представляет фактический документ без необходимости дальнейшей интерпретации при выводе драйверу принтера на основе XPS (XPSDrv). Драйверы могут работать непосредственно с данными в этом формате. Эта возможность позволяет избежать преобразования данных и цветового пространства, необходимого при использовании файлов [!INCLUDE[TLA2#tla_emf](../../../../includes/tla2sharptla-emf-md.md)] и драйверов печати на основе [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)].  
  
 Размеры файлов очереди обычно уменьшаются при использовании XPS-документы, предназначенных для XPS драйвер принтера (XPSDrv) по сравнению с их [!INCLUDE[TLA2#tla_emf](../../../../includes/tla2sharptla-emf-md.md)] эквиваленты; тем не менее, существуют исключения:  
  
- Очень сложная, многоуровневая или неэффективно созданная векторная графика может быть больше, чем растровая версия того же графического объекта.  
  
- Для отображения экрана XPS-файлы внедряют шрифты устройства, а также шрифты на компьютере; тогда как файлы очереди GDI не внедряют шрифты устройства. Но оба типа шрифтов имеют поднаборы (см. ниже), и драйверы принтера могут удалить шрифты устройства до передачи файла на принтер.  
  
 Уменьшение размера очереди выполняется посредством нескольких механизмов.  
  
- **Поднабор шрифта**. В XPS-файле хранятся только символы, используемые в документе.  
  
- **Поддержка расширенной графики**. Встроенная поддержка прозрачности и примитивов градиента позволяет избежать растризации содержимого в документе [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)].  
  
- **Идентификация общих ресурсов**. Ресурсы, которые используются несколько раз (например, изображение, представляющее эмблему организации), рассматриваются как общие ресурсы и загружаются только один раз.  
  
- **Сжатие ZIP**. Все документы XPS используют сжатие ZIP.  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Controls.PrintDialog>
- <xref:System.Windows.Xps.XpsDocumentWriter>
- <xref:System.Windows.Xps.Packaging.XpsDocument>
- <xref:System.Printing.PrintTicket>
- <xref:System.Printing.PrintCapabilities>
- <xref:System.Printing.PrintServer>
- <xref:System.Printing.PrintQueue>
- [Разделы практического руководства](printing-how-to-topics.md)
- [Документы в WPF](documents-in-wpf.md)
- [XPS-документы](/windows/desktop/printdocs/documents)
- [Сериализация и хранение документов](document-serialization-and-storage.md)
- [Microsoft XPS-документов преобразователя (MXDC)](/windows/desktop/printdocs/microsoft-xps-document-converter--mxdc-)
