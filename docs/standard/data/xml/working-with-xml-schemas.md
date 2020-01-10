---
title: Работа с XML-схемами
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: bbbcc70c-bf9a-4f6a-af72-1bab5384a187
ms.openlocfilehash: 0fd7313e800024ebb7e3563cb4323c5780cbf1c3
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710015"
---
# <a name="working-with-xml-schemas"></a>Работа с XML-схемами
Чтобы определить структуру XML-документа, связи его элементов, типы данных, ограничения на содержимое, используется определение типа документа (DTD) или схема XSD. XML-документ имеет правильный формат, если он соответствует всем синтаксическим требованиям Рекомендации консорциума W3C по языку XML 1.0. Однако документ считается допустимым только в том случае, если он одновременно имеет правильный формат и соответствует ограничениям, заданным определением DTD или схемой. Следовательно, хотя все допустимые XML-документы имеют правильный формат, не все XML-документы правильного формата, являются допустимыми.  
  
 Дополнительные сведения о XML см. в [документации консорциума W3C по XML 1.0](https://www.w3.org/TR/REC-xml/). Дополнительные сведения о схемах XML см. в документации консорциума W3C по схемам XML по использованию [структур](https://www.w3.org/TR/xmlschema-1/) и [типов данных](https://www.w3.org/TR/xmlschema-2/).  
  
## <a name="in-this-section"></a>В этом разделе  
 [Модель объектов схемы XML (SOM)](../../../../docs/standard/data/xml/xml-schema-object-model-som.md)  
 Обсуждается модель SOM в пространстве имен <xref:System.Xml.Schema?displayProperty=nameWithType>, предоставляющем набор классов, который позволяет считывать схему XSD из файла или создавать ее в памяти программным образом.  
  
 [XmlSchemaSet для компиляции схемы](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md)  
 Обсуждается класс <xref:System.Xml.Schema.XmlSchemaSet>, представляющий собой кэш, где могут храниться и проверяться схемы XSD.  
  
 [Принудительная проверка с помощью XmlSchemaValidator](../../../../docs/standard/data/xml/xmlschemavalidator-push-based-validation.md)  
 Обсуждается класс <xref:System.Xml.Schema.XmlSchemaValidator>, предоставляющий эффективный, высокопроизводительный механизм проверки XML-данных по схемам XSD в принудительном порядке.  
  
 [Выведение XML-схемы](../../../../docs/standard/data/xml/inferring-an-xml-schema.md)  
 Обсуждается применение класса <xref:System.Xml.Schema.XmlSchemaInference> для выведения схемы XSD из структуры XML-документа.  
  
## <a name="reference"></a>Справочные сведения  
 <xref:System.Xml.Schema.XmlSchemaSet> &#124; <xref:System.Xml.Schema.XmlSchemaInference> &#124; <xref:System.Xml.XmlReader>  
  
## <a name="related-sections"></a>Связанные разделы  
 [Проверка XML-документа в модели DOM](../../../../docs/standard/data/xml/validating-an-xml-document-in-the-dom.md)  
 Обсуждается проверка XML в модели DOM. XML можно проверять по мере загрузки в DOM, или проверять ранее не проверенный XML-документ в модели DOM.  
  
 [Проверка по схеме с помощью XPathNavigator](../../../../docs/standard/data/xml/schema-validation-using-xpathnavigator.md)  
 Обсуждается проверка XML-документа, по которому производится перемещение и изменение с помощью класса <xref:System.Xml.XPath.XPathNavigator>.
