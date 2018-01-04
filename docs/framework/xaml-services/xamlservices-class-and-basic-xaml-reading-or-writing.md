---
title: "Класс XAMLServices и чтение или запись базового кода XAML"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XAML [XAML Services], XamlServices class
- XamlServices class [XAML Services], how to use
ms.assetid: 6ac27fad-3687-4d7a-add1-3e90675fdfde
caps.latest.revision: "11"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 30d94534f0da0e3946d036fd8e0db59971615c0f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="xamlservices-class-and-basic-xaml-reading-or-writing"></a>Класс XAMLServices и чтение или запись базового кода XAML
<xref:System.Xaml.XamlServices> — это класс, предоставляемый службами XAML .NET Framework XAML, который может использоваться для сценариев  XAML, в которых не требуется отдельный доступ к потоку узлов XAML, или для информации о системе типов XAML, полученной из этих узлов. <xref:System.Xaml.XamlServices> API можно описать следующим образом: `Load` или `Parse` для поддержки пути загрузки XAML, `Save` для поддержки пути сохранения XAML, `Transform` — для предоставления метода объединения пути загрузки и пути сохранения. Можно использовать`Transform` для изменения одной схемы XAML на другую. В этом разделе собраны все классификации этих API и приведены различия между определенными перегрузками методов.  
  
<a name="load"></a>   
## <a name="load"></a>Загрузка  
 Различные перегрузки метода <xref:System.Xaml.XamlServices.Load%2A> полностью реализуют логику пути загрузки. Путь загрузки использует XAML в определенной форме и выводит поток узлов XAML. Большинство этих путей загрузки используют XAML в виде кодированного текстового файла XML. Однако также можно загрузить обычный поток или предварительно загруженный источник XAML, который уже содержится в другой реализации <xref:System.Xaml.XamlReader> .  
  
 Простейшая перегрузка для большинства сценариев — <xref:System.Xaml.XamlServices.Load%28System.String%29>. Эта перегрузка имеет `fileName` параметр: просто имя текстового файла, содержащего XAML для загрузки. Это подходит для таких сценариев применения как приложения с полным доверием, которые ранее выполнили сериализацию состояния или данных на локальном компьютере. Это также полезно для платформ, где вы определяете модель приложений и хотите загрузить один из стандартных файлов, определяющих поведение приложений, начальный пользовательский интерфейс или прочие определяемые платформой возможности, использующие XAML.  
  
 <xref:System.Xaml.XamlServices.Load%28System.IO.Stream%29> используется в аналогичных сценариях. Эта перегрузка может быть полезна, если пользователю предоставляется возможность выбора файлов для загрузки, так как <xref:System.IO.Stream> часто представляет собой выходные данные других API <xref:System.IO> , которые могут получить доступ к файловой системе. Также можно получать доступ к источникам XAML посредством асинхронных загрузок или другими сетевыми способами, также предоставляющими потоки. (Загрузка из потока или выбранного пользователем источника может повлиять на безопасность. Дополнительные сведения см. в разделе [XAML Security Considerations](../../../docs/framework/xaml-services/xaml-security-considerations.md).)  
  
 Перегрузки<xref:System.Xaml.XamlServices.Load%28System.IO.TextReader%29> и <xref:System.Xaml.XamlServices.Load%28System.Xml.XmlReader%29> опираются на средства чтения форматов из предыдущих версий .NET Framework. Для использования этих перегрузок нужно создать экземпляр средства чтения и использовать его API `Create` для загрузки XAML в соответствующей форме (текст или XML). Это не имеет значения, если вы уже переместили указатели записей в других средствах чтения или выполняли другие операции с ними. Логика пути загрузки из <xref:System.Xaml.XamlServices.Load%2A> всегда обрабатывает все входные данные XAML, начиная с корневого элемента. Возможны следующие сценарии использования этих перегрузок:  
  
-   Рабочие области, где реализуются простые возможности редактирования XAML с помощью существующего текстового редактора, поддерживающего XML.  
  
-   Варианты основных сценариев <xref:System.IO> , где для открытия файлов или потоков используются выделенные средства чтения. Логика выполняет простую проверку или обработку содержимого перед повторной попыткой загрузки в формате XAML.  
  
 Можно загрузить файл или поток, либо загрузить <xref:System.Xml.XmlReader>, <xref:System.IO.TextReader>или <xref:System.Xaml.XamlReader> для заключения входных данных XAML в оболочку путем загрузки с интерфейсами API средства чтения.  
  
 Каждая из указанных выше перегрузок представляет собой <xref:System.Xaml.XamlServices.Load%28System.Xml.XmlReader%29>, и переданный <xref:System.Xml.XmlReader> используется для создания нового <xref:System.Xaml.XamlXmlReader>.  
  
 Подпись `Load` для более сложных сценариев — <xref:System.Xaml.XamlServices.Load%28System.Xaml.XamlReader%29>. Эту подпись можно использовать в одном из следующих случаев:  
  
-   Вы определили собственную реализацию <xref:System.Xaml.XamlReader>.  
  
-   Для <xref:System.Xaml.XamlReader> необходимо задать параметры, отличающиеся от параметров по умолчанию.  
  
 Примеры параметров, отличных от параметров по умолчанию: <xref:System.Xaml.XamlReaderSettings.AllowProtectedMembersOnRoot%2A>; <xref:System.Xaml.XamlReaderSettings.BaseUri%2A>; <xref:System.Xaml.XamlReaderSettings.IgnoreUidsOnPropertyElements%2A>; <xref:System.Xaml.XamlReaderSettings.LocalAssembly%2A>; <xref:System.Xaml.XamlReaderSettings.ValuesMustBeString%2A>. Средство чтения для <xref:System.Xaml.XamlServices> по умолчанию — <xref:System.Xaml.XamlXmlReader>. Если указать собственный <xref:System.Xaml.XamlXmlReader>с параметрами, то для следующих свойств устанавливаются значения <xref:System.Xaml.XamlXmlReaderSettings>, отличные от значений по умолчанию : <xref:System.Xaml.XamlXmlReaderSettings.CloseInput%2A>; <xref:System.Xaml.XamlXmlReaderSettings.SkipXmlCompatibilityProcessing%2A>; <xref:System.Xaml.XamlXmlReaderSettings.XmlLang%2A>; <xref:System.Xaml.XamlXmlReaderSettings.XmlSpacePreserve%2A>.  
  
<a name="parse"></a>   
## <a name="parse"></a>Parse  
 <xref:System.Xaml.XamlServices.Parse%2A> и `Load` схожи, поскольку это путь загрузки API, который создает поток узлов XAML из входных данных XAML. Однако в этом случае входные данные XAML предоставляются непосредственно в виде строки, содержащей весь код XAML для загрузки. <xref:System.Xaml.XamlServices.Parse%2A> — упрощенный подход, который больше подходит для сценариев приложений, чем для сценариев платформ. Для получения дополнительной информации см. <xref:System.Xaml.XamlServices.Parse%2A>. <xref:System.Xaml.XamlServices.Parse%2A> представляет собой вызов <xref:System.Xaml.XamlServices.Load%28System.Xml.XmlReader%29> в оболочке, содержащий <xref:System.IO.StringReader> внутри.  
  
<a name="save"></a>   
## <a name="save"></a>Save  
 Различные перегрузки <xref:System.Xaml.XamlServices.Save%2A> реализуют путь сохранения. Все методы <xref:System.Xaml.XamlServices.Save%2A> принимают граф объекта на вход, а выходом является поток, файл или экземпляр <xref:System.Xml.XmlWriter>/<xref:System.IO.TextWriter> .  
  
 Входной объект должен быть корневым объектом какого-либо объектного представления. Это может быть единственный корневой элемент бизнес-объекта, корневой объект дерева объектов страницы в сценарии с пользовательским интерфейсом, рабочая область редактирования в средстве разработки или другие подходящие виды корневых объектов.  
  
 Во многих случаях сохраняемое дерево объектов связано с исходной операцией, которая загрузила XAML либо с <xref:System.Xaml.XamlServices.Load%2A>, либо с другим API, реализованным моделью платформы или приложения. В полученном дереве объектов могут быть различия, связанные с изменениями состояния, изменениями при получении от пользователя параметром среды выполнения, измененного XAML в случае, когда приложение является областью редактирования XAML и т. д. Вне зависимости от различий принцип, согласно которому сначала происходит загрузка XAML из разметки, а затем происходит его сохранение и сравнение двух форм разметки XAML, иногда называется представлением приема-передачи XAML.  
  
 Задача при сохранении и сериализации сложного объекта, заданного в форме разметки, состоит в достижении баланса между полным представлением без потери информации и детализацией, в силу которой XAML становится менее удобочитаемым. Кроме того, у разных пользователей XAML могут быть разные определения или ожидания относительно такого баланса. API <xref:System.Xaml.XamlServices.Save%2A> представляют одно определение такого баланса. API <xref:System.Xaml.XamlServices.Save%2A> используют доступный контекст схемы XAML и характеристики <xref:System.Xaml.XamlType>, <xref:System.Xaml.XamlMember>и других встроенных функций XAML и других понятий системных типов XAML по умолчанию на базе CLR, чтобы определить, можно ли оптимизировать определенные конструкции потока узлов XAML при их сохранении в разметку. Например, пути сохранения <xref:System.Xaml.XamlServices> могут использовать контекст схемы XAML по умолчанию на основе CLR для преобразования <xref:System.Xaml.XamlType>  для объектов, могут определять <xref:System.Xaml.XamlType.ContentProperty%2A?displayProperty=nameWithType>, а затем могут опускать теги элементов свойства при записи свойства в содержимое XAML объекта.  
  
<a name="transform"></a>   
## <a name="transform"></a>Преобразование  
 <xref:System.Xaml.XamlServices.Transform%2A> преобразует XAML, связывая путь загрузки и путь сохранения в одну операцию. Для <xref:System.Xaml.XamlReader> и <xref:System.Xaml.XamlWriter>может использоваться другой контекст схемы или другая система резервных типов, что повлияет на преобразование полученного XAML-кода. Это хорошо подходит для операций широкого преобразования.  
  
 <xref:System.Xaml.XamlServices.Transform%2A>обычно не используется для операций, зависящих от проверки каждого узла в потоке узлов XAML, Вместо этого необходимо определить собственную серию операций с путями загрузки и сохранения и использовать собственную логику. В одном из путей используйте пару из средства чтения и средства записи XAML в собственном цикле узлов. Например, можно загрузить исходный XAML с помощью <xref:System.Xaml.XamlXmlReader> , а затем переходить в узлы при помощи последовательных вызовов <xref:System.Xaml.XamlXmlReader.Read%2A> . Работая на уровне потока узлов XAML, можно настраивать отдельные узлы (типы, члены, другие узлы) для применения преобразований или оставить узлы как есть. Затем можно передать узел дальше в соответствующий API `Write` <xref:System.Xaml.XamlObjectWriter> и записать объект. Для получения дополнительной информации см. [Understanding XAML Node Stream Structures and Concepts](../../../docs/framework/xaml-services/understanding-xaml-node-stream-structures-and-concepts.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Xaml.XamlObjectWriter>  
 <xref:System.Xaml.XamlServices>  
 [Службы XAML](../../../docs/framework/xaml-services/index.md)
