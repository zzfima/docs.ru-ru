---
title: Выведение схем из XML-документов
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
ms.assetid: f3d97d53-614d-4a04-a174-87965b7405f6
ms.openlocfilehash: 5c2d997d9006a3f1eb971eac20982b9dd5677ebf
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710756"
---
# <a name="inferring-schemas-from-xml-documents"></a>Выведение схем из XML-документов
В этом разделе описывается, как использовать класс <xref:System.Xml.Schema.XmlSchemaInference> для выведения схемы XSD из структуры XML-документа.  
  
## <a name="the-schema-inference-process"></a>Процесс выведения схемы  
 Класс <xref:System.Xml.Schema.XmlSchemaInference> из пространства имен <xref:System.Xml.Schema?displayProperty=nameWithType> используется для создания одной или нескольких схем XSD из структуры XML-документа. Полученные схемы можно использовать для проверки исходного XML-документа.  
  
 Во время обработки XML-документа <xref:System.Xml.Schema.XmlSchemaInference> класс <xref:System.Xml.Schema.XmlSchemaInference> строит предположения о компонентах схемы, описывающих элементы и атрибуты в XML-документе. Класс <xref:System.Xml.Schema.XmlSchemaInference> также выводит компоненты схемы по принципу ограничения - выводится самый строгий тип для каждого элемента или атрибута. По мере сбора дополнительных сведений о XML-документе эти ограничения ослабляются и выводятся менее строгие типы. Наименее строгим выводимым типом является `xs:string`.  
  
 Рассмотрим, например, следующий фрагмент XML-документа.  
  
```xml  
<parent attribute1="6">  
    <child>One</child>  
    <child>Two</child>  
</parent>  
<parent attribute1="A">  
```  
  
 В примере выше, когда в процессе `attribute1` обнаруживается атрибут `6` со значением <xref:System.Xml.Schema.XmlSchemaInference>, для него предполагается тип `xs:unsignedByte`. Когда в процессе `parent` обнаруживается второй элемент <xref:System.Xml.Schema.XmlSchemaInference>, ограничение ослабляется путем замены типа на `xs:string`, поскольку теперь атрибут `attribute1` имеет значение `A`. Аналогично, атрибут `minOccurs` для всех элементов `child`, выведенных в схему, ослабляется до значения `minOccurs="0"`, поскольку второй родительский элемент не имеет дочерних.  
  
## <a name="inferring-schemas-from-xml-documents"></a>Выведение схем из XML-документов  
 Класс <xref:System.Xml.Schema.XmlSchemaInference> использует два перегруженных метода <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> для вывода схемы из XML-документа.  
  
 Первый метод <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A?displayProperty=nameWithType> используется для создания схемы на основе XML-документа. Второй метод <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A?displayProperty=nameWithType> используется для вывода схемы, описывающей несколько XML-документов. Например, можно по очереди передать методу <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A?displayProperty=nameWithType> несколько XML-документов, чтобы создать схему, описывающую весь набор XML-документов.  
  
 Первый метод <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A?displayProperty=nameWithType> выводит схему из XML-документа, содержащегося в объекте <xref:System.Xml.XmlReader>, и возвращает объект <xref:System.Xml.Schema.XmlSchemaSet>, содержащий выведенную схему. Второй метод <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A?displayProperty=nameWithType> ищет в объекте <xref:System.Xml.Schema.XmlSchemaSet> схему, целевое пространство имен которой совпадает с XML-документом, содержащимся в объекте <xref:System.Xml.XmlReader>, уточняет существующую схему и возвращает объект <xref:System.Xml.Schema.XmlSchemaSet>, содержащий выведенную схему.  
  
 Изменения, вносимые в уточняемую схему, основаны на новой структуре, обнаруженной в XML-документе. Например, в процессе обзора XML-документа строятся предположения об обнаруженных типах данных, и схема создается на основе этих предположений. Однако если во втором проходе выведения обнаруживаются данные, отличающиеся от исходных предположений, схема уточняется. В следующем примере показан процесс уточнения.  
  
 [!code-cpp[XmlSchemaInferenceExamples#4](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaInferenceExamples/CPP/XmlSchemaInferenceExamples.cpp#4)]
 [!code-csharp[XmlSchemaInferenceExamples#4](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaInferenceExamples/CS/XmlSchemaInferenceExamples.cs#4)]
 [!code-vb[XmlSchemaInferenceExamples#4](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaInferenceExamples/VB/XmlSchemaInferenceExamples.vb#4)]  
  
 В примере в качестве первого входного аргумента принимается файл `item1.xml`.  
  
 [!code-xml[XmlSchemaInferenceExamples#13](../../../../samples/snippets/xml/VS_Snippets_Data/XmlSchemaInferenceExamples/XML/item1.xml#13)]  
  
 Затем в качестве второго входного аргумента принимается файл `item2.xml`:  
  
 [!code-xml[XmlSchemaInferenceExamples#14](../../../../samples/snippets/xml/VS_Snippets_Data/XmlSchemaInferenceExamples/XML/item2.xml#14)]  
  
 Когда в первом XML-документе обнаруживается атрибут `productID`, для значения `123456789` предполагается тип `xs:unsignedInt`. Однако, когда при чтении второго XML-документа обнаруживается значение `A53-246`, тип `xs:unsignedInt` больше не может предполагаться. Схема уточняется, и тип `productID` заменяется типом `xs:string`. Кроме того, атрибут `minOccurs` для элемента `supplierID` получает значение `0`, поскольку во втором XML-документе отсутствует элемент `supplierID`.  
  
 Далее представлена схема, выведенная из первого XML-документа.  
  
 [!code-xml[XmlSchemaInferenceExamples#15](../../../../samples/snippets/xml/VS_Snippets_Data/XmlSchemaInferenceExamples/XML/InferSchema1.xml#15)]  
  
 Далее представлена схема, выведенная из первого XML-документа и уточненная с помощью второго XML-документа.  
  
 [!code-xml[XmlSchemaInferenceExamples#16](../../../../samples/snippets/xml/VS_Snippets_Data/XmlSchemaInferenceExamples/XML/InferSchema2.xml#16)]  
  
## <a name="inline-schemas"></a>Встроенные схемы  
 Если в процессе <xref:System.Xml.Schema.XmlSchemaInference> обнаруживается встроенная схема XSD, создается исключение <xref:System.Xml.Schema.XmlSchemaInferenceException>. Например, следующая встроенная схема вызывает исключение <xref:System.Xml.Schema.XmlSchemaInferenceException>.  
  
```xml  
<root xmlns:ex="http://www.contoso.com" xmlns="http://www.tempuri.org">  
    <xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema" targetNamespace="http://www.contoso.com">  
        <xs:element name="Contoso" type="xs:normalizedString" />  
    </xs:schema>  
    <ex:Contoso>Test</ex:Contoso>  
</root>  
```  
  
## <a name="schemas-that-cannot-be-refined"></a>Неуточняемые схемы  
 В схемах W3C XML существуют такие конструкции, которые процесс <xref:System.Xml.Schema.XmlSchemaInference> для схемы XSD не может обработать, если задан тип для уточнения, и которые приводят к созданию исключения. Например, сложный тип, на верхнем уровне которого находится компоновщик, отличный от sequence. В модели SOM это соответствует типу <xref:System.Xml.Schema.XmlSchemaComplexType>, свойством <xref:System.Xml.Schema.XmlSchemaComplexType.Particle%2A> которого не является экземпляр <xref:System.Xml.Schema.XmlSchemaSequence>.  
  
## <a name="see-also"></a>См. также:

- <xref:System.Xml.Schema.XmlSchemaInference>
- [Модель объектов схемы XML (SOM)](../../../../docs/standard/data/xml/xml-schema-object-model-som.md)
- [Выведение XML-схемы](../../../../docs/standard/data/xml/inferring-an-xml-schema.md)
- [Правила выведения структуры и типов узлов схемы](../../../../docs/standard/data/xml/rules-for-inferring-schema-node-types-and-structure.md)
- [Правила выведения простых типов](../../../../docs/standard/data/xml/rules-for-inferring-simple-types.md)
