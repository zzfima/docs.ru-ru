---
title: "Работа с XML-схемами"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bbbcc70c-bf9a-4f6a-af72-1bab5384a187
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e21d402dce02ecb332d041f0cda651df911979ca
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="working-with-xml-schemas"></a>Работа с XML-схемами
Чтобы определить структуру XML-документа, связи его элементов, типы данных, ограничения на содержимое, используется определение типа документа (DTD) или схема XSD. XML-документ имеет правильный формат, если он соответствует всем синтаксическим требованиям Рекомендации консорциума W3C по языку XML 1.0. Однако документ считается допустимым только в том случае, если он одновременно имеет правильный формат и соответствует ограничениям, заданным определением DTD или схемой. Следовательно, хотя все допустимые XML-документы имеют правильный формат, не все XML-документы правильного формата, являются допустимыми.  
  
 Дополнительные сведения о XML см. в разделе [рекомендация W3C XML 1.0](http://go.microsoft.com/fwlink/?linkid=7269). Дополнительные сведения о XML-схеме см. в разделе [W3C XML Schema Part 1: структурные рекомендации](http://go.microsoft.com/fwlink/?linkid=48881) и [W3C XML Schema Part 2: рекомендации по типам данных](http://go.microsoft.com/fwlink/?linkid=17392) рекомендации.  
  
## <a name="in-this-section"></a>Содержание  
 [Модель объектов схемы XML (SOM)](../../../../docs/standard/data/xml/xml-schema-object-model-som.md)  
 Обсуждается модель SOM в пространстве имен <xref:System.Xml.Schema?displayProperty=nameWithType>, предоставляющем набор классов, который позволяет считывать схему XSD из файла или создавать ее в памяти программным образом.  
  
 [XmlSchemaSet для компиляции схемы](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md)  
 Обсуждается класс <xref:System.Xml.Schema.XmlSchemaSet>, представляющий собой кэш, где могут храниться и проверяться схемы XSD.  
  
 [Принудительная проверка с помощью XmlSchemaValidator](../../../../docs/standard/data/xml/xmlschemavalidator-push-based-validation.md)  
 Обсуждается класс <xref:System.Xml.Schema.XmlSchemaValidator>, предоставляющий эффективный, высокопроизводительный механизм проверки XML-данных по схемам XSD в принудительном порядке.  
  
 [Определение схемы XML](../../../../docs/standard/data/xml/inferring-an-xml-schema.md)  
 Обсуждается применение класса <xref:System.Xml.Schema.XmlSchemaInference> для выведения схемы XSD из структуры XML-документа.  
  
## <a name="reference"></a>Ссылка  
 <xref:System.Xml.Schema.XmlSchemaSet> &#124; <xref:System.Xml.Schema.XmlSchemaInference> &#124; <xref:System.Xml.XmlReader>  
  
## <a name="related-sections"></a>Связанные разделы  
 [Проверка XML-документа в DOM](../../../../docs/standard/data/xml/validating-an-xml-document-in-the-dom.md)  
 Обсуждается проверка XML в модели DOM. XML можно проверять по мере загрузки в DOM, или проверять ранее не проверенный XML-документ в модели DOM.  
  
 [Проверка схемы с помощью XPathNavigator](../../../../docs/standard/data/xml/schema-validation-using-xpathnavigator.md)  
 Обсуждается проверка XML-документа, по которому производится перемещение и изменение с помощью класса <xref:System.Xml.XPath.XPathNavigator>.
