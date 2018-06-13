---
title: Документы в WPF
ms.date: 03/30/2017
helpviewer_keywords:
- documents [WPF], packaging
- documents [WPF], text layout
- documents [WPF], XPS
- 'XPS documents [WPF], , '
- documents [WPF], controls
- documents [WPF], types of
- documents [WPF], browser-viewable
ms.assetid: 6e8db7bc-050a-4070-aa72-bb8c46e87ff8
ms.openlocfilehash: ced65795c66ab7c3b7eb6c25b225ec551c3969ed
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33548440"
---
# <a name="documents-in-wpf"></a>Документы в WPF
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] предлагает широкий ассортимент функций для работы с документами, позволяющих создавать содержимое высокого качества. Работать с ним удобнее, чем в предыдущих поколениях [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)]. В дополнение к расширенным возможностям и повышенному качеству [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет интегрированные службы для отображения, упаковки и обеспечения безопасности документов. В этом разделе содержатся вводные сведения о типах и упаковке документов [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
  
<a name="types_of_documents"></a>   
## <a name="types-of-documents"></a>Типы документов  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] разделяет документы на две основные категории на основе их предполагаемого использования; эти категории документов называются "документы фиксированного формата" и "документы нефиксированного формата".  
  
 Документы фиксированного формата предназначены для сфер применения, требующих точного представления [!INCLUDE[TLA#tla_wys](../../../../includes/tlasharptla-wys-md.md)] независимо от используемого дисплея или принтера. Документы фиксированного формата используются в компьютерной верстке, текстовой обработке и макетах форм, где строгое соответствие дизайну исходной страницы имеет критическое значение. При использовании такого макета документ фиксированного формата сохраняет точное расположение элементов содержимого независимо от используемого устройства изображения или печати. Так, страница документа фиксированного формата, отображаемая на дисплее 96 точек на дюйм, будет совершенно одинаково отображаться на лазерном принтере 600 точек на дюйм и фотонаборной машине 4800 точек на дюйм. Макет страницы остается неизменным во всех случаях, хотя качество документа повышается с учетом возможностей устройства.  
  
 Для сравнения: документы нефиксированного формата предназначены для повышения удобства просмотра и чтения; их лучше всего использовать, когда в работе с документом важнее всего удобство чтения. Вместо того чтобы использовать какой-либо определенный макет, документы нефиксированного формата динамически корректируют и перемещают содержимое с учетом переменных времени выполнения, таких как размер окна, разрешение устройства и дополнительные пользовательские настройки. Веб-страница — это простой пример документа нефиксированного формата, содержимое на которой динамически форматируется, чтобы уместиться в окне. Документы нефиксированного формата оптимизируют просмотр и чтение для пользователя в зависимости от среды выполнения. Например, один и тот же документ нефиксированного формата будет динамически переформатирован, чтобы обеспечить оптимальную читаемость на дисплее высокого разрешения 19 дюймов или небольшом экране PDA размером 2 x 3 дюйма. Кроме того, документы нефиксированного формата имеют несколько встроенных возможностей, включая поиск, режимы просмотра, оптимизирующие читаемость, и возможность менять размер и внешний вид шрифта.  См. иллюстрации, примеры и подробное описание документов нефиксированного формата в разделе [Общие сведения о документах нефиксированного формата](../../../../docs/framework/wpf/advanced/flow-document-overview.md).  
  
<a name="document_viewer"></a>   
## <a name="document-controls-and-text-layout"></a>Элементы управления документами и макеты текста  
 .NET Framework предоставляет набор встроенных элементов управления, которые упрощают использование документов фиксированного формата, документов нефиксированного формата и основного текста в приложении.  Отображение содержимого фиксированного документа поддерживается с помощью <xref:System.Windows.Controls.DocumentViewer> элемента управления.  Отображение содержимого документа нефиксированного формата поддерживается тремя элементами: <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, и <xref:System.Windows.Controls.FlowDocumentScrollViewer> которой сопоставляются различные сценарии пользователя (см. в следующих разделах).  Другие элементы управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляют упрощенную разметку для стандартных способов использования текста (см. раздел [Текст в пользовательском интерфейсе](#text_in_the_user_interface) ниже).  
  
### <a name="fixed-document-control---documentviewer"></a>Элемент управления документом фиксированного формата DocumentViewer  
 <xref:System.Windows.Controls.DocumentViewer> Управления предназначен для отображения <xref:System.Windows.Documents.FixedDocument> содержимого. <xref:System.Windows.Controls.DocumentViewer> Элемент управления предоставляет интуитивно понятный пользовательский интерфейс, который предоставляет встроенную поддержку для общих операций, включая вывод на печать, скопировать в буфер обмена, масштабирование и возможности поиска текста. Элемент управления предоставляет доступ к страницам содержимого через знакомый механизм прокрутки. Как и все [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] элементов управления, <xref:System.Windows.Controls.DocumentViewer> поддерживает полное или частичное изменение стиля, который включает элемент управления визуально интегрированы в практически для любых приложений или среды.  
  
 <xref:System.Windows.Controls.DocumentViewer> предназначен для отображения содержимого в режиме только для чтения; Редактирование или изменение содержимого недоступен и не поддерживается.  
  
<a name="flow_document"></a>   
### <a name="flow-document-controls"></a>Элементы управления документа нефиксированного формата  
 **Примечание**. Дополнительные сведения о функциях документов нефиксированного формата и создании таких документов см. в разделе [Общие сведения о документах нефиксированного формата](../../../../docs/framework/wpf/advanced/flow-document-overview.md).  
  
 Отображение содержимого документа нефиксированного формата поддерживается три элемента управления: <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, и <xref:System.Windows.Controls.FlowDocumentScrollViewer>.  
  
#### <a name="flowdocumentreader"></a>FlowDocumentReader  
 <xref:System.Windows.Controls.FlowDocumentReader> включает в себя функции, которые позволяют пользователю динамически выбирать различные режимы просмотра, включая одностраничный (страницы в раз), две страницы в раз (книжный формат) режиме постоянной прокрутки (без дна) и режим просмотра.  Дополнительные сведения об этих режимах просмотра см. в разделе <xref:System.Windows.Controls.FlowDocumentReaderViewingMode>.  Если не требуется возможность динамически переключаться между режимами просмотра <xref:System.Windows.Controls.FlowDocumentPageViewer> и <xref:System.Windows.Controls.FlowDocumentScrollViewer> предоставляют облегченные средства просмотра содержимого, которые исправлены в режиме просмотра.  
  
#### <a name="flowdocumentpageviewer-and-flowdocumentscrollviewer"></a>FlowDocumentPageViewer и FlowDocumentScrollViewer  
 <xref:System.Windows.Controls.FlowDocumentPageViewer> Отображает содержимое в страницы во время режима просмотра, а <xref:System.Windows.Controls.FlowDocumentScrollViewer> отображает содержимое в режиме постоянной прокрутки.  Оба <xref:System.Windows.Controls.FlowDocumentPageViewer> и <xref:System.Windows.Controls.FlowDocumentScrollViewer> фиксированной для определенного режима просмотра. Сравнить с <xref:System.Windows.Controls.FlowDocumentReader>, которая содержит функции, которые позволяют пользователю динамически выбирать различные режимы просмотра (в соответствии со <xref:System.Windows.Controls.FlowDocumentReaderViewingMode> перечисления), за счет его более ресурсоемким, чем <xref:System.Windows.Controls.FlowDocumentPageViewer> или <xref:System.Windows.Controls.FlowDocumentScrollViewer>.  
  
 По умолчанию вертикальная полоса прокрутки отображается всегда, а горизонтальная полоса прокрутки становится видимой при необходимости. Значение по умолчанию [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] для <xref:System.Windows.Controls.FlowDocumentScrollViewer> не включает панель инструментов, однако <xref:System.Windows.Controls.FlowDocumentScrollViewer.IsToolBarVisible%2A> свойство может использоваться для включения встроенной панели инструментов.  
  
<a name="text_in_the_user_interface"></a>   
### <a name="text-in-the-user-interface"></a>Текст в пользовательском интерфейсе  
 Текст можно добавлять не только в документы, но и использовать в интерфейсе приложений, например в формах. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет множество элементов управления для отображения текста на экране. Каждый элемент управления предназначен для своего сценария и имеет собственный список функций и ограничений. Как правило <xref:System.Windows.Controls.TextBlock> элемент должен использоваться, если требуется ограниченная поддержка текста, например краткие предложения в [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. <xref:System.Windows.Controls.Label> можно использовать, когда требуется Минимальная поддержка текста. Дополнительные сведения см. в разделе [Общие сведения о классе TextBlock](../../../../docs/framework/wpf/controls/textblock-overview.md).  
  
<a name="packaging"></a>   
## <a name="document-packaging"></a>Упаковка документов  
 <xref:System.IO.Packaging> [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] Предоставляют эффективные средства для организации данных приложения, содержимого документа и связанных ресурсов в одном контейнере, который обеспечивает простой доступ, портативность и легко распространять. ZIP-файл является примером <xref:System.IO.Packaging.Package> может хранить несколько объектов как единое целое. Упаковка [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] предоставления по умолчанию <xref:System.IO.Packaging.ZipPackage> реализацию, созданных с использованием стандарта Open Packaging Conventions с XML и ZIP-файл архитектурой. [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] упаковки [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] упрощает создание пакетов, хранение в них объектов и осуществление доступа к таким объектам. Объект, сохраненный в <xref:System.IO.Packaging.Package> называется <xref:System.IO.Packaging.PackagePart> («часть»). Пакеты также могут включать подписанные цифровые сертификаты, с помощью которых можно идентифицировать создателя части и убедиться, что содержимое пакета не было изменено.  Пакеты также включают <xref:System.IO.Packaging.PackageRelationship> компонент, позволяющий Дополнительные сведения, чтобы добавить в пакет или связывать с определенными частями без фактического изменения содержимого существующих частей.  Службы пакета также поддерживают [!INCLUDE[TLA#tla_rm](../../../../includes/tlasharptla-rm-md.md)].  
  
 Архитектура пакета [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] лежит в основе ряда ключевых технологий:  
  
-   Документы [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)], соответствующие стандарту [!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)].  
  
-   Документы открытого XML-формата Microsoft Office "12" (.docx).  
  
-   Пользовательские форматы хранения для собственного приложения.  
  
 В зависимости от API упаковки, <xref:System.Windows.Xps.Packaging.XpsDocument> специально разработаны для хранения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимого документов фиксированного формата. <xref:System.Windows.Xps.Packaging.XpsDocument> Является самодостаточным документ, который может быть открыт в средстве просмотра отображаются в <xref:System.Windows.Controls.DocumentViewer> управления перенаправления в очереди печати, или непосредственно на вывод [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)]-совместимого принтера.  
  
 В следующих разделах дополнительную информацию о <xref:System.IO.Packaging.Package> и <xref:System.Windows.Xps.Packaging.XpsDocument> [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] в состав [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
<a name="packages"></a>   
### <a name="package-components"></a>Компоненты пакета  
 Интерфейсы API упаковки [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] позволяют упорядочить данные и документы приложения в единый портативный блок. ZIP-файл является одним из наиболее распространенных типов пакетов и типом пакета по умолчанию, предоставляемым [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  <xref:System.IO.Packaging.Package> сам является абстрактным классом, от которого <xref:System.IO.Packaging.ZipPackage> реализуется с помощью открытые стандартные XML и ZIP-файл архитектуры.  <xref:System.IO.Packaging.Package.Open%2A> Использует метод <xref:System.IO.Packaging.ZipPackage> для создания и использования ZIP-файлов по умолчанию. Пакет может содержать три основных типа элементов:  
  
|||  
|-|-|  
|<xref:System.IO.Packaging.PackagePart>|Содержимое приложения, данные, документы и файлы ресурсов.|  
|<xref:System.IO.Packaging.PackageDigitalSignature>|[Сертификат X.509] для идентификации, аутентификации и проверки.|  
|<xref:System.IO.Packaging.PackageRelationship>|Добавленные сведения о пакете или определенной части.|  
  
<a name="PackageParts"></a>   
#### <a name="packageparts"></a>PackageParts  
 Объект <xref:System.IO.Packaging.PackagePart> («часть») является абстрактным классом, который ссылается на объект, сохраненный в <xref:System.IO.Packaging.Package>. В ZIP-файле части пакета соответствуют отдельным файлам, хранящимся в ZIP-файле.  <xref:System.IO.Packaging.ZipPackagePart> предоставляет реализацию по умолчанию для сериализуемых объектов, хранящихся в <xref:System.IO.Packaging.ZipPackage>.  Как и в файловой системе, части, которые содержатся в пакете, хранятся в иерархическом каталоге или организованы по папкам.  С помощью [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] API упаковки, приложения можно записывать, хранить и считывать нескольких <xref:System.IO.Packaging.PackagePart> объекты, используя один контейнер ZIP-файла.  
  
<a name="PackageDigitalSignatures"></a>   
#### <a name="packagedigitalsignatures"></a>PackageDigitalSignatures  
 В целях безопасности <xref:System.IO.Packaging.PackageDigitalSignature> («цифровая подпись») может быть связан с частями внутри пакета. Объект <xref:System.IO.Packaging.PackageDigitalSignature> включает в себя [509], предоставляет две функции:  
  
1.  Идентификация и проверка подлинности создателя части.  
  
2.  Проверка, не была ли часть изменена.  
  
 Цифровая подпись не защищает часть от изменения, но проверка цифровой подписи завершится ошибкой, если часть изменяется каким-либо образом. В таком случае приложение может предпринять соответствующие действия, например не допустить открытия части или уведомить пользователя об изменении (и, следовательно, ненадежности) части.  
  
<a name="PackageRelationships"></a>   
#### <a name="packagerelationships"></a>PackageRelationships  
 Объект <xref:System.IO.Packaging.PackageRelationship> («связи») предоставляет механизм для связывания дополнительных сведений с пакет или часть в пакете. Отношение — это возможность на уровне пакета, позволяющая связывать дополнительную информацию с частью, не меняя фактического содержимого части. Вставлять новые данные непосредственно в содержимое части, как правило, нецелесообразно:  
  
-   Фактический тип части и схема содержимого неизвестны.  
  
-   Даже если эти параметры известны, схема содержимого может не обеспечивать средства для добавления новых данных.  
  
-   Часть может быть защищена от изменений цифровой подписью или шифрованием.  
  
 Отношения пакета предоставляют видимые средства добавления дополнительной информации в отдельные части или весь пакет и создания соответствующих связей между этой информацией и объектами. Отношения пакетов используются для решения двух основных задач:  
  
1.  Определение отношений зависимости между частями.  
  
2.  Определение информационных отношений, добавляющих примечания или другие данные, связанные с частью.  
  
 Объект <xref:System.IO.Packaging.PackageRelationship> предоставляет быстрые, видимые средства для определения зависимостей и добавления дополнительных сведений, связанных с частью пакета или пакета в целом.  
  
<a name="Dependency_Relationships"></a>   
##### <a name="dependency-relationships"></a>Отношения зависимости  
 Отношения зависимости используются для описания зависимостей между частями. Например, пакет может содержать HTML-часть, которая включает один или несколько тегов изображений \<img>. Теги изображений относятся к изображениям, которые хранятся как части внутри пакета или вне его (например, части, доступные через Интернет). Создание <xref:System.IO.Packaging.PackageRelationship> связанный с файлом HTML, делает обнаружение и зависимых ресурсов быстрый и простой доступ к. Браузер или приложение средства просмотра может осуществлять прямой доступ к отношениям частей и сразу приступать к сборке зависимых ресурсов, даже не зная схемы и не выполняя синтаксического анализа документа.  
  
<a name="Information_Relationships"></a>   
##### <a name="information-relationships"></a>Информационные отношения  
 Аналогично примечания или комментария, <xref:System.IO.Packaging.PackageRelationship> может также использоваться для хранения других типов данных, которые будут связаны с частью без необходимости фактического изменения содержимого части.  
  
<a name="XPS_Documents"></a>   
## <a name="xps-documents"></a>XPS-документы  
 Документ [!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)] — это пакет, который содержит один или несколько фиксированных документов и все ресурсы и сведения, необходимые для отображения.  [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] также является собственным форматом файлов в очереди на печать [!INCLUDE[TLA#tla_winvista](../../../../includes/tlasharptla-winvista-md.md)].  <xref:System.Windows.Xps.Packaging.XpsDocument> Хранится в стандартном наборе данных ZIP и могут включать комбинацию XML и двоичных компонентов, таких как файлы изображений и шрифта. [PackageRelationships](#PackageRelationships) используются для определения зависимостей между содержимым и ресурсами, необходимыми для полного отображения документа.  <xref:System.Windows.Xps.Packaging.XpsDocument> Разработки предоставляет решение одного документа с высокой точности, которое поддерживает повторное использование:  
  
-   Чтение, запись и хранение содержимого и ресурсов документов фиксированного формата в одном портативном документе с возможностью удобного распространения.  
  
-   Отображение документов в приложении средства просмотра [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)].  
  
-   Вывод документов в собственном формате вывода в очередь на печать [!INCLUDE[TLA#tla_winvista](../../../../includes/tlasharptla-winvista-md.md)].  
  
-   Перенаправление документов непосредственно на совместимый с [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] принтер.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Documents.FixedDocument>  
 <xref:System.Windows.Documents.FlowDocument>  
 <xref:System.Windows.Xps.Packaging.XpsDocument>  
 <xref:System.IO.Packaging.ZipPackage>  
 <xref:System.IO.Packaging.ZipPackagePart>  
 <xref:System.IO.Packaging.PackageRelationship>  
 <xref:System.Windows.Controls.DocumentViewer>  
 [Text](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)  
 [Общие сведения о документе нефиксированного формата](../../../../docs/framework/wpf/advanced/flow-document-overview.md)  
 [Общие сведения о печати](../../../../docs/framework/wpf/advanced/printing-overview.md)  
 [Сериализация и хранение документов](../../../../docs/framework/wpf/advanced/document-serialization-and-storage.md)
