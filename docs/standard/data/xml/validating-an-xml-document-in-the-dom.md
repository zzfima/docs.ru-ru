---
title: Проверка XML-документа в DOM
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
ms.assetid: 2c61c920-d0f8-4c72-bfcc-6524570f3060
ms.openlocfilehash: 93686ddf1afff76926e77acdbf5aa58e93d6cb77
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710041"
---
# <a name="validating-an-xml-document-in-the-dom"></a>Проверка XML-документа в DOM

По умолчанию класс <xref:System.Xml.XmlDocument> не сверяет код XML в модели DOM ни с данными схемы XSD, ни c определением типа документа (DTD). Код XML проверяется только на правильность формата.

С целью проверки XML в модели DOM можно проверить код XML в процессе его загрузки; для этого нужно передать проверяющий схему <xref:System.Xml.XmlReader> методу <xref:System.Xml.XmlDocument.Load%2A> класса <xref:System.Xml.XmlDocument> или проверить ранее не проверенный XML-документ в модели DOM с помощью метода <xref:System.Xml.XmlDocument.Validate%2A> класса <xref:System.Xml.XmlDocument>.

## <a name="validating-an-xml-document-as-it-is-loaded-into-the-dom"></a>Проверка XML-документа в процессе его загрузки в DOM

Класс <xref:System.Xml.XmlDocument> проверяет XML-данные в процессе их загрузки в модель DOM, когда проверяющий <xref:System.Xml.XmlReader> передается методу <xref:System.Xml.XmlDocument.Load%2A> класса <xref:System.Xml.XmlDocument>.

После успешной проверки применяются настройки схемы по умолчанию, текстовые значения по необходимости преобразуются в атомарные, а сведения о типах ассоциируются с проверенными информационными элементами. В результате типизированные XML-данные заменяют ранее не типизированные XML-данные.

### <a name="creating-an-xml-schema-validating-xmlreader"></a>Создание объекта XmlReader с проверкой по схеме

Для создания объекта <xref:System.Xml.XmlReader> с проверкой по схеме выполните следующие действия.

1. Сформируйте новый экземпляр класса <xref:System.Xml.XmlReaderSettings>.

2. Добавьте схему XML к свойству <xref:System.Xml.XmlReaderSettings.Schemas%2A> экземпляра <xref:System.Xml.XmlReaderSettings>.

3. Укажите `Schema` в качестве <xref:System.Xml.XmlReaderSettings.ValidationType%2A>.

4. Дополнительно можно указать <xref:System.Xml.XmlReaderSettings.ValidationFlags%2A> и <xref:System.Xml.XmlReaderSettings.ValidationEventHandler> для обработки ошибок проверки по схеме, а также предупреждений, выданных в процессе проверки.

5. Наконец, передайте объект <xref:System.Xml.XmlReaderSettings> методу <xref:System.Xml.XmlReader.Create%2A> класса <xref:System.Xml.XmlReader> вместе с XML-документом; в результате будет создан объект <xref:System.Xml.XmlReader> с проверкой по схеме.

### <a name="example"></a>Пример

В следующем примере кода объект <xref:System.Xml.XmlReader> с проверкой по схеме проверяет XML-данные, загружаемые в модель DOM. В XML-документ вносятся недействительные изменения; документ вновь подвергается проверке, что приводит к появлению ошибок проверки схемы. Наконец, одна из ошибок исправляется, после чего часть XML-документа подвергается частичной проверке.

[!code-cpp[XmlDocumentValidation.Load#1](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlDocumentValidation.Load/CPP/XmlDocumentValidationExample.cpp#1)]
[!code-csharp[XmlDocumentValidation.Load#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlDocumentValidation.Load/CS/XmlDocumentValidationExample.cs#1)]
[!code-vb[XmlDocumentValidation.Load#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlDocumentValidation.Load/VB/XmlDocumentValidationExample.vb#1)]

В примере в качестве входных данных используется файл `contosoBooks.xml`.

[!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]

В примере в качестве входных данных также используется файл `contosoBooks.xsd`.

[!code-xml[XPathXMLExamples#3](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xsd#3)]

При проверке XML-данных в процессе их загрузки в модель DOM примите во внимание следующее.

- В приведенном выше примере в случае обнаружения недействительного типа всегда вызывается обработчик событий <xref:System.Xml.XmlReaderSettings.ValidationEventHandler>. Если обработчик события <xref:System.Xml.XmlReaderSettings.ValidationEventHandler> не установлен на проверяющий <xref:System.Xml.XmlReader>, при вызове <xref:System.Xml.Schema.XmlSchemaValidationException> возникает исключение <xref:System.Xml.XmlDocument.Load%2A>, когда какой-либо тип атрибута или элемента не совпадает с соответствующим типом, указанным в проверяющей схеме.

- Когда XML-документ загружается в объект <xref:System.Xml.XmlDocument> с ассоциированной схемой, которая определяет принимаемые по умолчанию значения, объект <xref:System.Xml.XmlDocument> рассматривает эти используемые по умолчанию значения так, как если бы они были указаны в документе XML. Это означает, что свойство <xref:System.Xml.XmlReader.IsEmptyElement%2A> всегда возвращает значение `false` для элемента, который получил значение по умолчанию из схемы. Даже если в XML-документ элемент был записан как пустой.

## <a name="validating-an-xml-document-in-the-dom"></a>Проверка XML-документа в DOM

Метод <xref:System.Xml.XmlDocument.Validate%2A> класса <xref:System.Xml.XmlDocument> сверяет XML-данные, загружаемые в модель DOM, со схемами, содержащимися в свойстве <xref:System.Xml.XmlDocument> объекта <xref:System.Xml.XmlDocument.Schemas%2A>. После успешной проверки применяются настройки схемы по умолчанию, текстовые значения по необходимости преобразуются в атомарные, а сведения о типах ассоциируются с проверенными информационными элементами. В результате типизированные XML-данные заменяют ранее не типизированные XML-данные.

Публикуемый ниже пример аналогичен примеру, приведенному ранее в подразделе «Проверка XML-документа в процессе его загрузки в модель DOM». В этом примере XML-документ проверяется не в процессе загрузки в модель DOM, а по завершении данного процесса. При этом используется метод <xref:System.Xml.XmlDocument.Validate%2A> класса <xref:System.Xml.XmlDocument>. Метод <xref:System.Xml.XmlDocument.Validate%2A> сверяет XML-документ со схемами XML, содержащимися в свойстве <xref:System.Xml.XmlDocument.Schemas%2A> объекта <xref:System.Xml.XmlDocument>. Затем в XML-документ вносятся недействительные изменения; документ вновь подвергается проверке, что приводит к появлению ошибок проверки схемы. Наконец, одна из ошибок исправляется, после чего часть XML-документа подвергается частичной проверке.

[!code-csharp[XmlDocumentValidation.Validate#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlDocumentValidation.Validate/CS/XmlDocumentValidationExample.cs#1)]
[!code-vb[XmlDocumentValidation.Validate#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlDocumentValidation.Validate/VB/XmlDocumentValidationExample.vb#1)]

В этом примере в качестве входных данных используются файлы `contosoBooks.xml` и `contosoBooks.xsd`, упоминавшиеся ранее в подразделе «Проверка XML-документа в процессе его загрузки в модель DOM».

## <a name="handling-validation-errors-and-warnings"></a>Обработка ошибок проверки и предупреждений

Сообщения об ошибках проверки схемы XML выдаются при проверке XML-данных, загружаемых в модель DOM. Пользователь извещается обо всех ошибках проверки схемы, обнаруженных в процессе проверки загружаемых XML-данных, или при проверке ранее не подвергавшегося проверке XML-документа.

Ошибки проверки обрабатываются с помощью обработчика <xref:System.Xml.Schema.ValidationEventHandler>. Если обработчик <xref:System.Xml.Schema.ValidationEventHandler> был назначен экземпляру <xref:System.Xml.XmlReaderSettings> или передан методу <xref:System.Xml.XmlDocument.Validate%2A> класса <xref:System.Xml.XmlDocument>, <xref:System.Xml.Schema.ValidationEventHandler> будет обрабатывать ошибки проверки схемы; иначе возникнет исключение <xref:System.Xml.Schema.XmlSchemaValidationException> при обнаружении ошибки проверки схемы.

> [!NOTE]
> XML-данные загружаются в модель DOM, несмотря на возникновение ошибок проверки схемы, если обработчик ошибок <xref:System.Xml.Schema.ValidationEventHandler> не вызовет исключение для остановки процесса.
>
> Предупреждения проверки схемы не выводятся, если на объекте <xref:System.Xml.Schema.XmlSchemaValidationFlags.ReportValidationWarnings> не установлен флаг <xref:System.Xml.XmlReaderSettings>.

 Примеры, иллюстрирующие работу <xref:System.Xml.Schema.ValidationEventHandler>, см. выше в подразделах «Проверка XML-документа в процессе его загрузки в модель DOM» и «Проверка XML-документа в модели DOM».

## <a name="see-also"></a>См. также:

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XmlReader>
- <xref:System.Xml.Schema.ValidationEventHandler>
- <xref:System.Xml.XmlReaderSettings>
- [Обработка XML-данных с использованием модели DOM](../../../../docs/standard/data/xml/process-xml-data-using-the-dom-model.md)
- [Работа с XML-схемами](../../../../docs/standard/data/xml/working-with-xml-schemas.md)
